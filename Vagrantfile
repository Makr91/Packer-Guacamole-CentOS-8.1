# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.synced_folder '.', '/vagrant', type: 'nfs'
  # VirtualBox.
  config.vm.define "virtualbox" do |virtualbox|
    virtualbox.vm.hostname = "virtualbox-centos8"
    virtualbox.vm.box = "file://builds/virtualbox-centos8.box"
    virtualbox.vm.network :private_network, ip: "172.16.3.3"
    config.vm.provider :virtualbox do |v|
      v.gui = false
      v.memory = 4096
      v.cpus = 2
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--ioapic", "on"]
    end
  end
end
