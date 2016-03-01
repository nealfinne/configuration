# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "debian/jessie64"
  config.vm.hostname = "dev.okgreta.com"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder "./", "/vagrant/", type: "nfs"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  config.vm.provision :ansible do |ansible|
    ansible.limit = "dev.okgreta.com"
    ansible.inventory_path = "ansible/hosts"
    ansible.playbook = "ansible/site.yaml"
  end
end
