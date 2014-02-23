$script = <<SCRIPT
sudo su

apt-get -y update
apt-get install -y python-software-properties
apt-get install -y git curl

# Add nodejs repo
add-apt-repository -y ppa:chris-lea/node.js
apt-get -y update

# Install nodejs
apt-get install -y nodejs
SCRIPT


Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu"
  config.vm.network "public_network"
  config.vm.provision :shell, :inline => $script 

  #config.vm.provision "docker", images: ["ubuntu"]
  #config.vm.network "forwarded_port", guest: 8080, host: 8080
end
