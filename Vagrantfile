# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
    config.vm.box = "trusty32"
    config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-i386-vagrant-disk1.box"

    #config.vm.network "public_network", :bridge => 'eth0'
    config.vm.network "private_network", ip: "192.168.50.4"
    config.vm.hostname = "jenkins.leftxs.org"

    config.vm.provider "virtualbox" do |vb|
        #vb.customize ["modifyvm", :id, "--memory", "1024"]
        vb.customize ["modifyvm", :id, "--name", "jenkins" ]
    end

    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "provisioning/playbook.yml"
    end
end
