---
layout: post
title: Run Puppet-PE virtual machine remotely
date: 2014-01-12 11:08:08
categories:
- Uncategorized
tags: []
---

Virtualbox has a commandline toolbox that can do a lot of things.

Here's the steps to run [Puppet VM](http://docs.puppetlabs.com/learning/) on a remote server without GUI. So you can play with it.

1. Download the unzip the VM.
   
   ```bash  
   wget https://downloads.puppetlabs.com/learning/learn_puppet_centos-6.4-pe-3.1.0-ovf-20131031.zip
   unzip learn_puppet_centos-6.4-pe-3.1.0-ovf-20131031.zip
   ```

2. Import VM from ovf.
   
   ```bash     
   VBoxManage import learn_puppet_centos-6.4-pe-3.1.0.ovf
   VBoxManage list vms
   ```

3. Modify Network Setting
   
   ```bash     
   # enable bridge mode on 2nd adapter
   VBoxManage modifyvm learn_puppet_centos-6.4-pe-3.1.0 --nic2 bridged --bridgeadapter2 enp3s0
   # enable port-forward on 1st adapter
   VBoxManage modifyvm learn_puppet_centos-6.4-pe-3.1.0 --natpf1 "guestssh,tcp,,2222,,22"
   ```

4. start headless VM

   ```bash
   VBoxHeadless --startvm learn_puppet_centos-6.4-pe-3.1.0 --vrde off
   ```

5. rm VM

   ```bash
   VBoxManage unregistervm     <uuid>|<name> [--delete]
   ```

---

Sources:

http://www.virtualbox.org/manual/ch07.html

