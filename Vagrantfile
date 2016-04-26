Vagrant.configure(2) do |config|

        config.vm.hostname = "Zabbix3"
        config.vm.box = "Chef.box"
	config.vm.network :private_network, ip: "192.168.56.103"
        config.vm.provider :virtualbox do |v|
                v.name = "Zabbix3"
                v.customize ["modifyvm", :id, "--memory", 2048]
                v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
                end

  	config.vm.provision "ansible" do |ansible|
    		ansible.playbook = 'provision.yml'
    		ansible.verbose = 'vv'
 		end
end
