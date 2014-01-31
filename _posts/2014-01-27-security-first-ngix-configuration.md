---
layout: post
title: Security first NGINX configuration
date: 2014-01-27 11:28:28
categories:
- Uncategorized
tags: []
---
Finally my personal site hit **A+** on [SSL Test](https://www.ssllabs.com/ssltest/analyze.html?d=jzr.me).

Preparation:

#### Install lastest version nginx from official repo.

1. Use 2048-bit Private Keys (RSA,ECDSA)

    ```bash
    openssl req -new -newkey rsa:2048 -nodes -keyout domain.com.key -out domain.com.csr
    ```
2. Use 2048bit Diffie-Hellman parameters.

    ```bash
    mkdir -p /etc/nginx/ssl/
    openssl dhparam -out /etc/nginx/ssl/dhparam.pem 2048
    ```

3. Enable session resumption to improve https performance

    ```
    ssl_session_cache shared:SSL:10m; # a 1mb cache can hold about 4000 sessions
    ssl_session_timeout 10m;
    ```

4. Secure Protocols: 
    
    ```
    ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
    ```
    
    I also enabled `SSLv3` to support support `IE6` on `Windows XP`.

4. Server Control Cipher Suite Selection

        
    ```
    ssl_prefer_server_ciphers on;
    ```
        
5. Robust **Cipher Suites** support **Forward Secrecy**
    
    ```
    ssl_ciphers "EECDH+ECDSA+AESGCM EECDH+aRSA+AESGCM EECDH+ECDSA+SHA384 EECDH+ECDSA+SHA256 EECDH+aRSA+SHA384 EECDH+aRSA+SHA256 EECDH+aRSA+RC4 EECDH EDH+aRSA RC4 !aNULL !eNULL !LOW !3DES !MD5 !EXP !PSK !SRP !DSS";
    ```

6. Enable [**HSTS**](http://dev.chromium.org/sts) to avoid ssl stripping
    
    ```
    add_header Strict-Transport-Security "max-age=31536000; includeSubdomains;";
    ```

    This header should be seen in SSL server.
    
7. Enable [**OCSP Stapling**](http://en.wikipedia.org/wiki/OCSP_stapling)
    
    ```
    ssl_stapling on;
    ssl_stapling_verify on;
    ssl_trusted_certificate /etc/nginx/ssl/stapling.trusted.crt;
    resolver 8.8.8.8;
    ```

8. SPDY
    
    Make sure nginx has **`--with-http_spdy_module`**

    ```
    nginx -V
    ```

    Add `spdy` to `listen` directive

    ```
    listen 443 ssl deferred spdy;
    ```

Good Luck!

---

References:
- https://www.imperialviolet.org/2010/06/25/overclocking-ssl.html
- https://www.ssllabs.com/projects/best-practices/index.html
- https://community.qualys.com/blogs/securitylabs/2013/08/05/configuring-apache-nginx-and-openssl-for-forward-secrecy
- http://tautt.com/best-nginx-configuration-for-security/
- https://www.imququ.com/post/web-security-and-response-header.html
- http://en.wikipedia.org/wiki/Transport_Layer_Security#Web_browsers

Test&Debug:

- SSL Server Test: https://www.ssllabs.com/ssltest/index.html
- Chrome SPDY Lookup Tool: [chrome://net-internals/#spdy](chrome://net-internals/#spdy)
- Chrome HSTS query and forget tool: [chrome://net-internals/#hsts](chrome://net-internals/#hsts)
