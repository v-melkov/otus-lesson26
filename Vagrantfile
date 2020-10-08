# -*- mode: ruby -*-
# vim: set ft=ruby :
Vagrant.configure('2') do |config|
  config.vm.box = 'centos/7'
  config.vm.synced_folder '.', '/vagrant', disabled: true
  config.vbguest.no_install = true

  config.vm.define "server" do |server|
    server.vm.hostname = "server"
    server.vm.network "private_network", ip: "192.168.11.101"
    server.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", 1024]
      vb.customize ["modifyvm", :id, "--name", "server"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
  end

  config.vm.define "client" do |client|
    client.vm.hostname = "client"
    client.vm.network "private_network", ip: "192.168.11.102"
    client.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", 4096]
      vb.customize ["modifyvm", :id, "--name", "client"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
  end
end
