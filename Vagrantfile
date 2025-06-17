Vagrant.configure("2") do |config|
   config.vm.box = "debian/bookworm64"
   config.vm.hostname = "gitlab-ci-server"
   
   config.vm.network "forwarded_port", guest: 80, host: 8080
   config.vm.network "forwarded_port", guest: 443, host: 8443

	config.vm.network "public_network"

	config.vm.provider "virtualbox" do |vb|
	 vb.memory = "6000"
	end

	config.vm.provision "shell", inline: <<-SHELL
	 apt update && apt upgrade -y
	SHELL
end
