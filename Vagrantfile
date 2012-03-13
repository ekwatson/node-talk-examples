Vagrant::Config.run do |config|
  config.vm.box = "base"

  config.vm.forward_port 3000, 3000

  config.vm.share_folder "examples", "/home/vagrant/examples", "examples"

  config.vm.provision :chef_solo do |chef|
    chef.add_recipe "nodejs"
    chef.add_recipe "mongodb-debs"
    chef.add_recipe "redis-server"
    chef.json = {
      "nodejs" => {
        "version" => "0.6.12"
      }    	      
    }
  end
end
