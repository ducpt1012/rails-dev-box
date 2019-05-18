# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
   # Download file vagrant box before vagrant up to save time
   # https://cloud-images.ubuntu.com/releases/19.04/release/ubuntu-19.04-server-cloudimg-amd64-vagrant.box
   # Using vagrant box add ubuntu1904 /path_file_box
  config.vm.box      = 'ubuntu1804'
  config.vm.hostname = 'rails-pc'

  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :forwarded_port, guest: 3306, host: 3306
  config.vm.network :forwarded_port, guest: 5432, host: 5432

  config.vm.provision :shell, path: 'bootstrap.sh', keep_color: true

  config.vm.provider 'virtualbox' do |v|
    v.memory = 2048
    v.cpus   = 2
  end
end
