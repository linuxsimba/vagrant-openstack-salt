# vagrant-openstack-salt

## Requirements

* vagrant
* libvirt-bin
* vagrant-libvirt

Use a fresh Vagrant Box built using github.com/chef/bento Ubuntu 14.04 Packer
JSON file.

```
** Install Packer  using instructions at https://www.packer.io/downloads.html
# cd $HOME
# git clone https://github.com/chef/bento
# cd bento
# packer build -only qemu -var "disk_size=102400" ubuntu-14.04-amd64.json
# vagrant box add builds/ubuntu-14.04.libvirt.box --name trusty64-salt
# cd $HOME
# git clone https://github.com/linuxsimba/vagrant-openstack-salt
# cd vagrant-openstack-salt
# vagrant up
```
