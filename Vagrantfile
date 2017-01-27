# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.require_version ">= 1.8.1"

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  config.ssh.insert_key = false
  config.ssh.forward_agent = true

  config.vm.define 'vagrant-spark' do |h|
    h.vm.hostname = 'vagrant-spark'
    h.ssh.guest_port = 2200
    h.vm.network :forwarded_port, guest: 22, host: 2200, id: :ssh, auto_correct: false
    h.vm.network "private_network", ip: "192.168.10.10"
  end

  config.vm.provider "virtualbox" do |vb|
    vb.memory = 4096
    vb.cpus = 2
  end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "vagrant-setup.yml"
    ansible.inventory_path = "hosts"
    ansible.skip_tags = nil
    ansible.tags = nil
    ansible.raw_arguments = []
  end

end
