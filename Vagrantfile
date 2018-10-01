# -*- mode: ruby -*-
# vi: set ft=ruby :

# TEJOYASH IT SOLUTIONS ( www.tejoyasha.com )

Vagrant.configure("2") do |config|

config.vm.define "lb1" do |lb1| 
  lb1.vm.box = "ubuntu/trusty32" 
  lb1.vm.network "private_network", ip: "10.0.0.10" 
  lb1.vm.provision "shell", path: "provision-lb.sh"
  lb1.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 1
  end
end


config.vm.define "web1" do |web1| 
  web1.vm.box = "ubuntu/trusty32"
  web1.vm.network "private_network", ip: "10.0.0.11" 
  web1.vm.provision "shell", args: 1 ,path: "provision-web1.sh"
 config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 1
  end
end

config.vm.define "web2" do |web2| 
  web2.vm.box = "ubuntu/trusty32" 
  web2.vm.network "private_network", ip: "10.0.0.12" 
  web2.vm.provision "shell", args: 1, path: "provision-web2.sh"
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 1
  end
end

end
