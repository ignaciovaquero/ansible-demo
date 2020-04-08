# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|

  config.vm.define "centos" do |centos|
     centos.vm.box = "centos/7"
     centos.vm.network "private_network", ip: "192.168.33.10"
     centos.vm.provider "virtualbox"
  end
  config.vm.define "ubuntu" do |ubuntu|
     ubuntu.vm.box = "s3than/trusty64"
     ubuntu.vm.network "private_network", ip: "192.168.33.11"
     ubuntu.vm.provider "virtualbox"
  end

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "1024"
  end
  config.vm.provision "shell",
    inline: "echo 'ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAID+0hFkga7ntqA/OZgb402Dun1VKvdvNng1SjAf3jbbd ansible-demo' >> /home/vagrant/.ssh/authorized_keys"
end
