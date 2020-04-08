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
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/main.yml"
    ansible.host_vars = {
      "ubuntu" => {"apache_package" => "apache2",
                   "OS_NAME" => "ubuntu"},
      "centos" => {"apache_package" => "httpd",
                   "OS_NAME" => "centos"},
    }
  end
end
