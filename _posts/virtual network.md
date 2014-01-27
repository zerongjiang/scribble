
Adapter/Ping   |Guest->Host  |Host->Guest  |Guest->Guest |Guest->WWW   |WWW->Guest   |
---------------|-------------|-------------|-------------|-------------|-------------|
NAT            |Yes          |No[^1]       |No           |Yes          |No           |
NAT Network[^2]|Yes          |             |             |             |             |
Bridged        |Yes          |Yes          |Yes          |Yes          |Yes          |
Internal       |NO           |NO           |Yes          |NO           |NO           |
Host-only      |Yes          |Yes          |Yes          |NO           |NO           |

[^1]: Yes with port-forward.

[^2]: Introduced in VirtualBox 4.3.

**Reference:**
[Networking in VirtualBox]( https://blogs.oracle.com/fatbloke/entry/networking_in_virtualbox1)