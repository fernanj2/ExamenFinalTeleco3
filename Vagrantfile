# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

	if Vagrant.has_plugin? "vagrant-vbguest"
		config.vbguest.no_install = true
		config.vbguest.auto_update = false
		config.vbguest.no_remote = true
	end

config.vm.define :firewall do |firewall|
	firewall.vm.box = "generic/centos8"
	firewall.vm.network :private_network, ip: "192.168.70.2"
	firewall.vm.network :public_network, ip: "192.168.150.96"
      firewall.vm.provision "shell", path: "script.sh"
      firewall.vm.network :forwarded_port, guest: 80, host:8080
      firewall.vm.hostname = "firewall"
end

config.vm.define :streama do |streama|
	streama.vm.box = "generic/centos8"
	streama.vm.network :private_network, ip: "192.168.70.3"
	streama.vm.network :public_network, ip: "192.168.150.97"
	streama.vm.provision "shell", path: "scriptst.sh"
	streama.vm.hostname = "streama"
end
end
