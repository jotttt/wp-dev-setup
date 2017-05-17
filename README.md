# Wordpress development setup
Links and preferences for setup of Wordpress development environment

## Heaviliy borrowed from these sites
- [How to use ansible on windows](http://www.tomsitpro.com/articles/how-to-use-ansible-on-windows,1-3479.html)

## Setup Windows
- install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- Install [Vagrant](https://www.vagrantup.com/downloads.html)

## Setup your project folder
  - from console run ```vagrant init``` in your relevant project folder
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
      end
    end
    ```
    (This VagrantFile will download an Ubuntu box on VirtualBox, call it 'ansible,' assign a private IP and give it 2GB of RAM.)
  - next type ```vagrant ssh``` to ssh into the created Linux box
  - ensure all packages are up to date before starting: ```sudo apt-get update```
    
