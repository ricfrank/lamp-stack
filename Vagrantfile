# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "test"
  
  # Forward guest port 80 to host port 4567
  config.vm.forward_port 80, 7654
  #config.vm.forward_port 3306, 3306

  # Share folder between guest(vagrant box) and host(my machine) 
  config.vm.share_folder("web", "/var/www/lamp_stack", ".")

  # Enable the Puppet provisioner
  config.vm.provision :puppet do |puppet|
      puppet.manifests_path = "manifests"
      puppet.manifest_file = "base.pp"
      #puppet.module_path = "modules"
      puppet.options = "--verbose"
      puppet.options = "--debug"
  end

end
