# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = "enzzito/mykubuntu2204-gui"
  config.vm.box_version = "0.0.1"
  config.vm.box_check_update = true
  config.disksize.size = '50GB'
  config.vm.provision "shell", inline: <<-SHELL
    bash /vagrant/scripts/create_new_disk_part.sh
  SHELL
  config.vm.define "kubuntu22" do |kubuntu22|
    kubuntu22.vm.hostname = "kubuntu22"
    kubuntu22.vm.network "private_network", ip: "10.0.0.21"
    kubuntu22.vm.synced_folder ".", "/vagrant", create: true
    kubuntu22.vm.provider "virtualbox" do |vb|
      vb.memory = 10240
      vb.cpus = 4
      vb.gui = true
    end
    kubuntu22.vm.provision "ansible" do |ansible|
        ansible.limit = "all"
        ansible.playbook = "playbooks/plasma-provisioner.yml"
    end
  end
end
