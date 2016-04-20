# -*- mode: ruby -*-
# vi: set ft=ruby :

$init = <<SCRIPT
SCRIPT

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false

  config.ssh.insert_key = false
  config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"

  config.vm.provision :shell, :path => ".provision/base.sh", privileged: false
  config.vm.provision :shell, run: "always", inline: $init

  config.vm.network :private_network, ip: "192.168.3.14"
  config.vm.synced_folder ".", "/vagrant", type: "nfs", create: true

  config.vm.hostname = "Docker-Playground"
  config.vm.provider :virtualbox do |vb|
    vb.name = "Docker Playground"
    vb.customize ['modifyvm', :id, '--memory', '2048']
  end

end
