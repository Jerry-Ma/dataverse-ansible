# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "sjoeboo/centos-7-1-x86-ansible"
  config.vm.box_url = "https://atlas.hashicorp.com/sjoeboo/boxes/centos-7-1-x86-ansible"
  config.vm.hostname = "dataverse"
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end
  config.vm.network "private_network", type: "dhcp"
  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "forwarded_port", guest: 443, host: 443
  #config.vm.network "forwarded_port", guest: 8983, host: 8993
  #config.vm.network "forwarded_port", guest: 8080, host: 8088
  #config.vm.network "forwarded_port", guest: 8181, host: 8188

  config.vm.provision "shell", path: "scripts/vagrant/git-dataverse.sh"

end
