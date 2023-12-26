Vagrant.configure("2") do |config|
    config.vm.box = "debian/bookworm64"
    config.vm.network "forwarded_port", guest: 3306, host: 3306
  
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
  
    config.vm.provision "shell", inline: <<-SHELL
      # Update and install necessary packages
      sudo apt-get update
      sudo apt-get install -y build-essential curl git
  
      # Additional configurations as needed
  
    SHELL
  end