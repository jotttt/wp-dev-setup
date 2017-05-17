# Wordpress development setup
Links and preferences for setup of Wordpress development environment

## Setup Windows
- install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- Install [Vagrant](https://www.vagrantup.com/downloads.html)
  - run 'vagrant init' in the new project folder
  - replace the generated vagrant file content with this:
    ```
    # -*- mode: ruby -*-
    # vi: set ft=ruby :

    Vagrant.configure(2) do |config|
      config.vm.define "ansible" do |ctl|
          ctl.vm.box = "boxcutter/ubuntu1604"
          ctl.vm.hostname = "ansible"
          ctl.vm.network "private_network",ip: "192.168.2.5"
          ctl.vm.provider "virtualbox" do |vb|
              vb.memory = 2048
          end
      endend
    ```
    
