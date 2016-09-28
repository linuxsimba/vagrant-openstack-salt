# vagrant-openstack-salt

Installs Openstack Salt onto 3 Controller VMs, a Horizon/Dashboard VM, and 2
Compute VMs.

> Works only for libvirt Systems. No Virtualbox support. But patches are
> welcome!

## Requirements

* vagrant
* libvirt-bin
* vagrant-libvirt

Use a fresh Vagrant Box built using github.com/chef/bento Ubuntu 14.04 Packer
JSON file.

## INSTALL

* Install Vagrant

* Install vagrant-libvirt

* Install Ansible via PPA or PyPi, YUM or APT. Requires **Ansible 2.0+**

### PyPI
```
easy_install pip
pip install ansible
```

### PPA (Ubuntu Only)
```
add-apt-repository ppa:ansible/ansible
apt-get update
apt-get install ansible
```

* [Install Packer](http://www.packer.io/downloads.html)

* Install the [Chef/Bento github repo](https://github.com/chef/bento)

* Build the Ubuntu 14.04 Vagrant Box for QEMU


## SUMMARY OF INSTALL
```
** Install vagrant
** Install vagrant-libvirt
** Install Packer  using instructions at https://www.packer.io/downloads.html
# cd $HOME
# git clone https://github.com/chef/bento
# cd bento
# packer build -only qemu -var "disk_size=102400" ubuntu-14.04-amd64.json
# vagrant box add builds/ubuntu-14.04.libvirt.box --name trusty64-salt
# cd $HOME
# git clone https://github.com/linuxsimba/vagrant-openstack-salt
# cd vagrant-openstack-salt
# vagrant up --no-parallel

```

After the Vagrant Install Log into the Saltmaster and kick off the Install

