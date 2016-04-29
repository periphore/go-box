# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.ssh.insert_key = false
  config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"

  config.vm.provision :shell, :path => ".provision/dependencies.sh", privileged: false

  config.vm.network :private_network, ip: "192.168.3.14"

  config.vm.synced_folder ".", "/vagrant", type: "nfs", create: true

  config.vm.hostname = "Periphore-Go-Box"
  config.vm.provider :virtualbox do |vb|
    vb.name = "Periphore Go Box"
    vb.customize ['modifyvm', :id, '--memory', '2048']
  end

end
