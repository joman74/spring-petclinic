# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

config.vm.box = "centos/7"

config.vm.network "forwarded_port", guest: 8080, host: 8484

config.vm.synced_folder ".", "/vagrant/sync", disabled: true
config.vm.provision :shell, path: "bootstrap.sh"
config.vm.provision :file, source: "target/spring-petclinic-1.4.2.jar",
destination: "/tmp/spring-petclinic-1.4.2.jar", run: "always"
config.vm.provision :shell, inline: "java -jar 
/tmp/spring-petclinic-1.4.2.jar &", run: "always"
end
