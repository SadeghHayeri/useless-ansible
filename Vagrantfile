# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"

  # config.vm.network "public_network"

  config.vm.define "a" do |a|
  end

  config.vm.define "b" do |b|
  end

  config.vm.provision "shell", inline: <<-SHELL
    echo -e "pass\npass" | passwd root
    echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
    sed -in 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
    service sshd restart
  SHELL
end

