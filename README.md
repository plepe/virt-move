Move a virtual machine to a different host using lvmsync. The disks of the VMs
have to be logical volumes in the volume group 'lvm' with the same name as the
vm name.

The script will create a snapshot of the current volume, transfer the snapshot to the new host, powerdown the virtual machine, transfer the changes of the snapshot (using lvmsync) and re-start the virtual machine.

INSTALL
=======
```sh
apt-get install ruby pv
gem install lvmsync
```

USAGE
=====
```sh
virt-move [options] <vm> <host>
```

Use `virt-move --help` to see available options.
