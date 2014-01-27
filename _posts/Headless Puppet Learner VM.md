
I'm recently following the tutorial on puppet.

I need to remotely start the VM.

1. Download the unzip the VM.
        
       #wget https://downloads.puppetlabs.com/learning/learn_puppet_centos-6.4-pe-3.1.0-ovf-20131031.zip
       #unzip learn_puppet_centos-6.4-pe-3.1.0-ovf-20131031.zip

2. Import ovf VM
        
        #VBoxManage import learn_puppet_centos-6.4-pe-3.1.0.ovf

        #VBoxManage list vms

3. Modify Network Setting
        
        #VBoxManage modifyvm learn_puppet_centos-6.4-pe-3.1.0 --nic2 bridged --bridgeadapter2 enp3s0
        #VBoxManage modifyvm learn_puppet_centos-6.4-pe-3.1.0 --natpf1 "guestssh,tcp,,2222,,22"

4. start headless VM
        
        #VBoxHeadless --startvm learn_puppet_centos-6.4-pe-3.1.0


        VBoxManage unregistervm     <uuid>|<name> [--delete]

