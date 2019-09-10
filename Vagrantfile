Vagrant.configure("2") do |config|
  
  $ip="192.168.77.21"
  config.vm.box = 'centos/7'
  config.vm.hostname = "origin"
  config.vm.network "private_network", ip: $ip
  config.vm.box_check_update = false
  config.vm.synced_folder ".idea/", disabled: true
  config.vm.provider "virtualbox" do |v|
    # play with these values
    v.memory = 8192
    v.cpus = 2
  end

  config.vm.provision "shell", path: "openshift-bootstrap", env: {"DOMAIN" => $ip, "INTERACTIVE" => "false"}

end