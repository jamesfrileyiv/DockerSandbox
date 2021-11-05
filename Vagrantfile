# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "docker" do |docker| 
    docker.vm.box = "geerlingguy/ubuntu1804"
    docker.vm.hostname = "docker"
    docker.vm.network "private_network", ip: "10.1.0.2"
    docker.vm.network "forwarded_port", guest: 4440, host: 4440   # rundeck
    docker.vm.network "forwarded_port", guest: 80, host: 8080     # web
    docker.vm.network "forwarded_port", guest: 443, host: 4430    # web
    docker.vm.network "forwarded_port", guest: 9200, host: 9200   # elasticsearch
    docker.vm.network "forwarded_port", guest: 5601, host: 5601   # kibana
    docker.vm.provision "shell", path: "../Scripts/install_docker.sh"
  end 
end
