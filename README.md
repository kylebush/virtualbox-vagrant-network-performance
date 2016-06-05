## Virtual Box / Vagrant Network Performance
Performance testing various network configuration options with Virtual Box and Vagrant on Mac OSX.  Check out my [blog post](http://kylebush.github.io/Improve-VirtualBox-Vagrant-Network-IO-Performance/) for additional information and test results.

## Requirements
- Mac OS X (Test with OS X El Capitan | Version 10.11.5)
- [Homebrew](http://brew.sh)
- [VirtualBox 5.0.10](https://www.virtualbox.org/wiki/Downloads)
- [Vagrant](https://www.vagrantup.com/)

## Install Homebrew
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Install Virtual Box
```
brew cask install virtualbox
```

## Install Vagrant
```
brew cask install vagrant
```

## Install and run
```shell
git clone git@github.com:kylebush/virtualbox-vagrant-network-performance.git
cd virtualbox-vagrant-network-performance
vagrant plugin install vagrant-vbguest
vagrant up
vagrant ssh test-vm
```

You can try different configuration by updating the Vagrantfile and rebuilding the VM: 

```
vagrant destroy test-vm
vagrant up 
vagrant ssh test-vm
```

To run the speed test:
```
speedtest-cli 
```