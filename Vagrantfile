# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "trusty64-salt"
  config.vm.provider :libvirt do |domain|
    domain.nested = true
    domain.memory = 8192
    domain.cpus = 5
  end
  config.vm.define :ctl01 do |node|
    node.vm.hostname = 'ctl01'
    node.vm.network :private_network,
      :ip => '192.168.200.101/24'
  end
  config.vm.define :ctl02 do |node|
    node.vm.hostname = 'ctl02'
    node.vm.network :private_network,
      :ip => '192.168.200.102/24'
  end
  config.vm.define :ctl03 do |node|
    node.vm.hostname = 'ctl03'
    node.vm.network :private_network,
      :ip => '192.168.200.103/24'
  end
  config.vm.define :cpt01 do |node|
    node.vm.hostname = 'cpt01'
    node.vm.network :private_network,
      :ip => '192.168.200.105/24'
  end
  config.vm.define :cpt02 do |node|
    node.vm.hostname = 'cpt02'
    node.vm.network :private_network,
      :ip => '192.168.200.106/24'
  end

  config.vm.define :saltmaster do |node|
    node.vm.hostname = 'cfg01'
    node.vm.network :private_network,
      :ip => '192.168.200.107/24'
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "saltmaster.yml"
    end
  end

  # Common ansible script ran on all VMs
  # First before any other ansible script
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "minion.yml"
  end

end
