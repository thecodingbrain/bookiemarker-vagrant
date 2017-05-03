Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty32"
  
  config.vm.network :forwarded_port, guest: 7220, host: 7220 # CodingBrain app
  config.vm.network :forwarded_port, guest: 7230, host: 7230 # BookieMarker app
  config.vm.network :forwarded_port, guest: 7232, host: 7232 # Postgres
  config.vm.network :forwarded_port, guest: 7234, host: 7234 # RabbitMQ
  config.vm.network :forwarded_port, guest: 7235, host: 7235 # RabbitMQ management server

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end

  config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
  end
  
  config.vm.post_up_message = "Your machine is ready! Open localhost:7220 in your browser to get started."
end
