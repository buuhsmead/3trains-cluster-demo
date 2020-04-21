# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV["LC_ALL"] = "en_US.UTF-8"

Vagrant.configure("2") do |config|
#  config.vm.box = "generic/rhel7"
#  config.vm.box_version = "2.0.6"
#  config.vm.box = "fedora/31-cloud-base"
#  config.vm.box_version = "31.20191023.0"
  config.vm.box = "centos/7"
  config.vm.hostname = "wildfly"
  config.vm.provider :virtualbox do |vb|
        vb.name = "wildfly"
    end
  config.vm.post_up_message = "The BOX is up"

  config.vm.network "forwarded_port", guest:  8080, host:  8080, protocol: "tcp"
  config.vm.network "forwarded_port", guest:  8180, host:  8180, protocol: "tcp"
  config.vm.network "forwarded_port", guest:  8280, host:  8280, protocol: "tcp"


  config.vm.provider "virtualbox" do |vb|
  # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
    vb.memory = "4096"
    vb.cpus   = 2
  end

  config.vm.provision :ansible do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "playbook.yml"
#    ansible.raw_arguments  = [
#  "-e ansible_python_interpreter=/usr/bin/python",
#]
  end

end

