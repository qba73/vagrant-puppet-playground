# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "192.168.33.2"

  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "512"
  end

  config.vm.provision "shell", inline: <<-SHELL
    UBUNTU_NAME="trusty"
    wget http://apt.puppetlabs.com/puppetlabs-release-$UBUNTU_NAME.deb
    sudo dpkg -i puppetlabs-release-$UBUNTU_NAME.deb
    sudo apt-get update
    sudo apt-get install -y -q puppet
    echo Puppet version: `puppet --version`
  SHELL
end
