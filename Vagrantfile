# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General Vagrant VM configuration
  config.vm.box = "geerlingguy/ubuntu2004"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |v|
    v.memory = 2048
    v.linked_clone = true
  end

  # Client App server
  config.vm.define "client" do |app|
    app.vm.hostname = "lx-app.client"
    app.vm.network :private_network, ip: "192.168.60.4"
  end

  # Backend App server
  config.vm.define "client" do |app|
    app.vm.hostname = "lx-app.backend"
    app.vm.network :private_network, ip: "192.168.60.5"
  end

  # Mongodb server
  config.vm.define "client" do |app|
    app.vm.hostname = "lx-app.mongodb"
    app.vm.network :private_network, ip: "192.168.60.6"
  end
  
  # Ansible provisioning.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yaml"
  end
end