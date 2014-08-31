# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise64"
  
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end

#  config.vm.network "private_network", ip: "192.168.50.4", virtualbox__intnet: true
  config.vm.network :forwarded_port, host: 5678, guest: 80
  config.vm.network :forwarded_port, host: 7474, guest: 7474
  config.vm.network :private_network, ip: "33.33.33.10"  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
