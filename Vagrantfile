# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.ssh.insert_key = false
    config.vm.define "web01" do |lb|
      lb.vm.box = "centos/7"
      lb.vm.hostname = "%s" % "web01"

    #   lb.vm.provision :ansible do |ansible|
    #     ansible.verbose = "v"
    #     ansible.playbook = "playbook.yml"
    #     ansible.sudo = true
    #     ansible.inventory_path = 'hosts'
    #     ansible.host_key_checking = false
    #     end
    end
end
