# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest: 5432, host: 5432
  config.vm.synced_folder "./infodatabase", "/home/infodatabase"
  config.vm.provision  "docker"
  config.vm.provision "shell", path: "script.sh"
  config.vm.provider :virtualbox do |vb|
  vb.customize [ 'modifyvm', :id, '--name', 'basedatos' ]
  vb.memory = 4096
  vb.cpus = 2  
  end
end  