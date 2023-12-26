Vagrant.configure("2") do |config|
    config.vm.box = "debian/bookworm64"
    config.vm.network "forwarded_port", guest: 3306, host: 3306
  
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
  
    config.vm.provision "shell", inline: <<-SHELL
      # Update and install necessary packages
      sudo su -

      apt-get update
      apt-get install -y build-essential curl wget
      wget https://dev.mysql.com/get/mysql-apt-config_0.8.29-1_all.deb
      export DEBIAN_FRONTEND=noninteractive && dpkg -i ./mysql-apt-config_*_all.deb
      apt update -y
      apt install mysql-server -y
      
    SHELL
  end