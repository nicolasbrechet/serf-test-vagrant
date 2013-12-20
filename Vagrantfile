# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.box = "precise64_fusion"
  config.vm.box_url = "http://files.vagrantup.com/precise64_vmware.box"
    
  config.vm.define :loadbalancer, primary: true  do |role|
    role.vm.hostname = "loadbalancer.local"
    role.vm.network "private_network", ip: "192.168.1.5"
    role.vm.provision :shell, :path => "./scripts/setup_load_balancer.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8080
    role.vm.network :forwarded_port, guest: 9999, host: 9999
  end
  
  config.vm.define :web1 do |role|
    role.vm.hostname = "webServer1.local"
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8010
  end
  
  config.vm.define :web2 do |role|
    role.vm.hostname = "webServer2.local"
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8020
  end
  
  config.vm.define :web3 do |role|
    role.vm.hostname = "webServer3.local"
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8030
  end
  
  config.vm.define :web4 do |role|
    role.vm.hostname = "webServer4.local"
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8040
  end
  
  config.vm.define :web5 do |role|
    role.vm.hostname = "webServer5.local"
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8050
  end
  
  config.vm.define :web6 do |role|
    role.vm.hostname = "webServer6.local"
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8060
  end
  
  config.vm.define :web7 do |role|
    role.vm.hostname = "webServer7.local"
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8070
  end
  
end
