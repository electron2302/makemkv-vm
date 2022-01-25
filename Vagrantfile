Vagrant.configure("2") do |config|
  config.vm.box = "fasmat/ubuntu2004-desktop"
  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  
  config.vm.network "public_network"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "MakeMKV Box"
    vb.gui = true
    vb.memory = "8192"
    vb.cpus = 4
    vb.customize ["modifyvm", :id, "--usbxhci", "on"]
  end
  
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
  end
  
end
