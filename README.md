clonevm

clonevm clones a libvirt virtual machine, and gives the clone a new VM name, MAC address, hostname, and ssh host keys.

Usage:

clonevm [--connect URI] [--subnet subnet] template newvm

clonevm has some assumptions that don't work in a data center, but it makes things simpler if you just have a computer and a few virtual machines.

clonevm requires virsh, virt-clone and fping. fping is used to ping all the adresses in the subnet where the new VM is expected to show up, to then get the IP address from the ARP cache. clonevm can be run from another machine, but must be on the same subnet as the virtual machine.

clonevm works with virtual machines running Linux or BSD, with OpenSSH or Dropbear. root login to the VM must be enabled.

vmip

vmip uses the fping/arp method to get the IP address(es) of a virtual machine, or list the current addesses of all running VMs.

e.g.

vmip | sort -V
