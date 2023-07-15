Vagrant.configure("2") do |config|
      config.vm.box = "bento/ubuntu-18.04"
    
      config.vm.provider "virtualbox" do |vb|
      # Display the VirtualBox GUI when booting the machine
      vb.gui = true
      vb.name = "postgresql"
      vb.cpus = 2
      vb.memory = 1024
      vb.customize ["modifyvm", :id, "--vram", "128"]
      vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]  
      end
    
      config.vm.hostname = "postgresql" 
    
      config.vm.provision "shell", inline: <<-SHELL
         
         sudo vi /etc/apt/sources.list.d/pgdg.list
         deb http://apt.postgresql.org/pub/repos/apt/ trusty-pgdg main
         wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
         sudo apt-get update
         sudo apt-get install postgresql-8.4
      SHELL
    
    end
