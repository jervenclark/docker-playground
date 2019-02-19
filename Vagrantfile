# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"
  config.vm.box_check_update = false

  config.vm.provision "docker"

  config.vm.network :private_network, ip: "192.168.3.14"
  config.vm.synced_folder ".", "/vagrant"

  config.vm.hostname = "Docker-Playground"
  config.vm.provider :virtualbox do |vb|
    vb.name = "Docker Playground"
    vb.customize ['modifyvm', :id, '--memory', '2048']
  end
end
