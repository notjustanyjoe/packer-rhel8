# -*- mode: ruby -*-
# vi: set ft=ruby :

# This is a very basic vagrant file to bring up the test machine you created with packer. 
Vagrant.configure("2") do |config|
  config.vm.box = "builds/virtualbox-rhel8.box"
  config.ssh.username = "vagrant"
  config.ssh.password = "vagrant"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider "virtualbox" do |vb|
      vb.gui = true
  end
end
