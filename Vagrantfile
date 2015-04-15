Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end

  config.vm.network :private_network, ip: "192.168.111.2"   
  

  config.vm.provision "shell",
    inline: "apt-get -y update"
  config.vm.provision "docker" do |d|
	d.pull_images "zaiste/jenkins"
	d.run "docker run -d -p 49001:8080 -v $PWD/jenkins:/var/lib/jenkins -t zaiste/jenkins"
  end	
end
