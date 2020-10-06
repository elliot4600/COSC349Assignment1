# -*- mode: ruby -*-
# vi: set ft=ruby :

# A Vagrantfile that sets up 3 VM's - two web servers and a database server.
Vagrant.configure("2") do |config|
  
  # All servers will run Ubuntu
  config.vm.box = "ubuntu/xenial64"
  
  # Automatically checks for Ubuntu updates when "vagrant up" is called from terminal
  config.vm.box_check_update = true



  # Sets up a VM as a database server which will interact with both the public and private web servers.
  config.vm.define "database" do |database|

    # Set server name
    database.vm.hostname = "database"

    # Assign the IP for the VM on the private network
    database.vm.network "private_network", ip: "192.168.2.13"

    # Permissions to ensure this will run properly on lab computers.
    database.vm.synced_folder ".", "/vagrant", owner: "vagrant", group: "vagrant", mount_options: ["dmode=775,fmode=777"]

    database.vm.provision :shell, path: "database.sh"

  end



  # Sets up the webserver for Business' clients to access which interacts with the database.
  config.vm.define "publicserver" do |publicserver|

    # Set server name
    publicserver.vm.hostname = "publicserver"
    
    # Enables port forwarding. 
    # The host computer can connect to IPv4 Address 127.0.0.1 port 8080.
    # Network request will reach our webserver VM's port 80.
    publicserver.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

    # Assign the IP for the VM on the private network
    publicserver.vm.network "private_network", ip: "192.168.2.11"

    # Permissions to ensure this will run properly on lab computers.
    publicserver.vm.synced_folder ".", "/vagrant", owner: "vagrant", group: "vagrant", mount_options: ["dmode=775,fmode=777"]

    publicserver.vm.provision :shell, path: "publicserver.sh"

  end

  # Sets up the webserver for Business to access which interacts with the database.
  config.vm.define "privateserver" do |privateserver|

    # Set server name
    privateserver.vm.hostname = "privateserver"

    # Enables port forwarding. 
    # The host computer can connect to IPv4 Address 127.0.0.1 port 8081.
    # Network request will reach our webserver VM's port 80.
    privateserver.vm.network "forwarded_port", guest: 80, host: 8081, host_ip: "127.0.0.1"

    # Assign the IP for the VM on the private network
    privateserver.vm.network "private_network", ip: "192.168.2.12"

    # Permissions to ensure this will run properly on lab computers.
    privateserver.vm.synced_folder ".", "/vagrant", owner: "vagrant", group: "vagrant", mount_options: ["dmode=775,fmode=777"]

    
    privateserver.vm.provision :shell, path: "privateserver.sh"


  end

 

end

#  LocalWords:  webserver xenial64
