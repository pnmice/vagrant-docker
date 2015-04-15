Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end

  config.vm.network :private_network, ip: "192.168.111.222"   
  
  config.vm.provision "shell",
    inline: "apt-get -y update"
#    inline: "apt-get install -y linux-image-extra-`uname -r`"
#    inline: "apt-get -y update"
  config.vm.provision "docker"
end
