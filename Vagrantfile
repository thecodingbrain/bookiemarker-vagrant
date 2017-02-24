Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty32"
  
  config.vm.network "forwarded_port", guest: 80, host: 5010
  config.vm.network "forwarded_port", guest: 8000, host: 5000
  config.vm.network :forwarded_port, guest: 5432, host: 5432
  config.vm.network :forwarded_port, guest: 5672, host: 5672
  config.vm.network :forwarded_port, guest: 15672, host: 15672

  config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
  end
  
  config.vm.post_up_message = "Your machine is ready! Open localhost:5000 in your browser to get started."
end
