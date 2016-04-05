# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.ssh.insert_key = false
    config.vm.define "lb" do |lb|
      lb.vm.box = "centos/7"
      lb.vm.hostname = "%s" % "lb"
      lb.vm.network "forwarded_port", guest: 80, host: 8081, auto_correct: true
    end
    config.vm.define "web01" do |web01|
      web01.vm.box = "centos/7"
      web01.vm.hostname = "%s" % "web01"
      web01.vm.network "forwarded_port", guest: 80, host: 8008, auto_correct: true
    end
end
