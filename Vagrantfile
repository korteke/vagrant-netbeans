# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "ubuntu14_04"

    config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

    config.vm.network "private_network", ip: "192.168.0.130"

    config.vm.provider :virtualbox do |vb|
      vb.gui = true
    end

    config.vm.hostname = "netbeans.local"

    config.vm.provision :ansible do |ansible|
      ansible.playbook = "provisioning/main.yml"
    end

    config.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777", "fmode=666"]

end
