$speedtest_cli = <<SCRIPT
sudo apt-get install -y python-pip
sudo pip install speedtest-cli
SCRIPT

Vagrant.configure(2) do |config|

  config.vm.define "test-vm" do |vagrant_machine|

    vagrant_machine.vm.hostname = "test-vm"
    vagrant_machine.vm.network "private_network", ip: "192.168.5.5"

    vagrant_machine.vm.box = "ubuntu/trusty64"
  
    # Install speedtest-cli 
    vagrant_machine.vm.provision "shell", inline: $speedtest_cli

    config.vm.provider "virtualbox" do |v|
      v.name =  "test-vm"
      v.memory = 4096
      v.cpus = 2

      #v.customize ["modifyvm", :id, "--nictype1", "Am79C973"]  ## PCNet-Fast III adapter
      #v.customize ["modifyvm", :id, "--nictype2", "Am79C973"]  ## PCNet-Fast III adapter
      
      #v.customize ["modifyvm", :id, "--nictype1", "virtio"]    ## Paravirtualized Network adapter
      #v.customize ["modifyvm", :id, "--nictype2", "virtio"]    ## Paravirtualized Network adapter
      
    end
  end
end
