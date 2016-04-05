# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.provider "virtualbox" do |v|
      v.memory = 256
      v.cpus = 1
    end

    config.ssh.insert_key = false

    config.vm.define "lb" do |lb|
      lb.vm.box = "centos/7"
      lb.vm.hostname = "%s" % "lb"
      lb.vm.network "forwarded_port", guest: 80, host: 8081, auto_correct: true
      lb.vm.network "forwarded_port", guest: 22, host: 2200, auto_correct: true, id: 'ssh'
    end
    config.vm.define "web01" do |web01|
      web01.vm.box = "centos/7"
      web01.vm.hostname = "%s" % "web01"
      web01.vm.network "forwarded_port", guest: 80, host: 8008, auto_correct: true
      web01.vm.network "forwarded_port", guest: 22, host: 2222, auto_correct: true, id: 'ssh'
    end
    config.vm.define "web02" do |web02|
      web02.vm.box = "centos/7"
      web02.vm.hostname = "%s" % "web02"
      web02.vm.network "forwarded_port", guest: 80, host: 8088, auto_correct: true
      web02.vm.network "forwarded_port", guest: 22, host: 2221, auto_correct: true, id: 'ssh'
    end
end
