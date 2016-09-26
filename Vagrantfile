# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "trusty64"
  config.vm.provider :libvirt do |domain|
    domain.nested = true
    domain.memory = 8192
  end
  config.vm.define :dashboard do |node|
    node.vm.hostname = 'web01'
    node.vm.network :private_network,
      :ip => '172.10.10.104/24'
  end
  config.vm.define :ctl01 do |node|
    node.vm.hostname = 'ctl01'
    node.vm.network :private_network,
      :ip => '172.10.10.101/24'
  end
  config.vm.define :ctl02 do |node|
    node.vm.hostname = 'ctl02'
    node.vm.network :private_network,
      :ip => '172.10.10.102/24'
  end
  config.vm.define :ctl03 do |node|
    node.vm.hostname = 'ctl02'
    node.vm.network :private_network,
      :ip => '172.10.10.103/24'
  end
  config.vm.define :cpt01 do |node|
    node.vm.hostname = 'cpt01'
    node.vm.network :private_network,
      :ip => '172.10.10.105/24'
  end
  config.vm.define :cpt02 do |node|
    node.vm.hostname = 'cpt02'
    node.vm.network :private_network,
      :ip => '172.10.10.106/24'
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end

  config.vm.define :saltmaster do |node|
    node.vm.hostname = 'cfg01'
    node.vm.network :private_network,
      :ip => '172.10.10.107/24'
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "saltmaster.yml"
    end
  end

end
