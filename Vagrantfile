# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
    
  config.vm.provider "vmware_fusion" do |v, override|
    override.vm.box = "precise64_fusion"
    override.vm.box_url = "http://files.vagrantup.com/precise64_vmware.box"
  end
  
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true
  
  config.vm.define :loadbalancer, primary: true  do |role|
    
    role.vm.provider "vmware_fusion" do |v, override|
      v.vmx["memsize"] = "2048"
      v.vmx["numvcpus"] = "2"
    end
    
    role.vm.hostname = 'loadbalancer.example.com'
    role.hostmanager.aliases = %w(loadbalancer.local loadbalancer)
    #role.vm.network "private_network", ip: "192.168.1.5"
    role.vm.provision :shell, :path => "./scripts/setup_load_balancer.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8080
    role.vm.network :forwarded_port, guest: 9999, host: 9999
  end
  
  config.vm.define :web1 do |role|
    
    role.vm.provider "vmware_fusion" do |v, override|
      v.vmx["memsize"] = "512"
      v.vmx["numvcpus"] = "1"
    end
    
    role.vm.hostname = 'webserver1.example.com'
    role.hostmanager.aliases = %w(webserver1.local webserver1)
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8010
  end
  
  config.vm.define :web2 do |role|
    
    role.vm.provider "vmware_fusion" do |v, override|
      v.vmx["memsize"] = "512"
      v.vmx["numvcpus"] = "1"
    end
    
    role.vm.hostname = 'webserver2.example.com'
    role.hostmanager.aliases = %w(webserver2.local webserver2)
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8020
  end
  
  config.vm.define :web3 do |role|
    
    role.vm.provider "vmware_fusion" do |v, override|
      v.vmx["memsize"] = "512"
      v.vmx["numvcpus"] = "1"
    end
    
    role.vm.hostname = 'webserver3.example.com'
    role.hostmanager.aliases = %w(webserver3.local webserver3)
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8030
  end
  
  config.vm.define :web4 do |role|
    
    role.vm.provider "vmware_fusion" do |v, override|
      v.vmx["memsize"] = "512"
      v.vmx["numvcpus"] = "1"
    end
    
    role.vm.hostname = 'webserver4.example.com'
    role.hostmanager.aliases = %w(webserver4.local webserver4)
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8040
  end
  
  config.vm.define :web5 do |role|
    
    role.vm.provider "vmware_fusion" do |v, override|
      v.vmx["memsize"] = "512"
      v.vmx["numvcpus"] = "1"
    end
    
    role.vm.hostname = 'webserver5.example.com'
    role.hostmanager.aliases = %w(webserver5.local webserver5)
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8050
  end
  
  config.vm.define :web6 do |role|
    
    role.vm.provider "vmware_fusion" do |v, override|
      v.vmx["memsize"] = "512"
      v.vmx["numvcpus"] = "1"
    end
    
    role.vm.hostname = 'webserver6.example.com'
    role.hostmanager.aliases = %w(webserver6.local webserver6)
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8060
  end
  
  config.vm.define :web7 do |role|
    
    role.vm.provider "vmware_fusion" do |v, override|
      v.vmx["memsize"] = "512"
      v.vmx["numvcpus"] = "1"
    end
    
    role.vm.hostname = 'webserver7.example.com'
    role.hostmanager.aliases = %w(webserver7.local webserver7)
    role.vm.provision :shell, :path => "./scripts/setup_web_server.sh"
    role.vm.provision :shell, :path => "./scripts/setup_serf.sh"
    role.vm.network :forwarded_port, guest: 80, host: 8070
  end
  
end
