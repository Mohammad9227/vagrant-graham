Vagrant.configure("2") do |config|
  config.vm.box = "debian/buster64"
  config.vm.define "debian-vm"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "UbuntuVM"
    vb.memory = "1024"
    vb.cpus = 2
  end
  config.vm.network "private_network", type: "dhcp"
  config.vm.network "forwarded_port", guest: 9090, host: 9090
  config.vm.synced_folder ".", "/vagrant"
  config.vm.provision "shell", inline: "echo 'root:admin_pass' | chpasswd"
end
