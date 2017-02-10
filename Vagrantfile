# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/xenial64"

  config.vm.define "consul1" do |consul1|
    config.vm.provision "shell" do |s|
      s.path = "provision.sh"
      s.args = ["/vagrant/consul1/config.json"]
    end
    consul1.vm.hostname = "consul1"
    consul1.vm.network "private_network", ip: "172.20.20.10"
  end
  # End consul1

  config.vm.define "consul2" do |consul2|
    config.vm.provision "shell" do |s|
      s.path = "provision.sh"
      s.args = ["/vagrant/consul2/config.json"]
    end
    consul2.vm.hostname = "consul2"
    consul2.vm.network "private_network", ip: "172.20.20.20"
  end
  #End consul2

  config.vm.define "consul3" do |consul3|
    config.vm.provision "shell" do |s|
      s.path = "provision.sh"
      s.args = ["/vagrant/consul3/config.json"]
    end
    consul3.vm.hostname = "consul3"
    consul3.vm.network "private_network", ip: "172.20.20.30"
  end
  #End consul3

  config.vm.define "consulclient" do |client|
    config.vm.provision "shell" do |s|
      s.path = "provisionclient.sh"
      s.args = ["/vagrant/consulclient/config.json"]
    end
    client.vm.hostname = "consulclient"
    client.vm.network "private_network", ip: "172.20.20.40"
  end
  #End consulclient
end
