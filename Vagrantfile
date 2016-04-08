#If this box is not on your machine, vagrant up base and make that a base box. Then add that to vagrant
#$box_name = "my_hashicorp_precise32"
$box_name = "geerlingguy/centos7"

def small(config)
    config.vm.provider "virtualbox" do |v|
      v.memory = 512 
      v.cpus = 1
    end
end

def medium(config)
    config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 2
    end
end

def large(config)
    config.vm.provider "virtualbox" do |v|
      v.memory = 4096 
      v.cpus = 4
    end
end


Vagrant.configure(2) do |config|

    config.vm.define "gem_master", autostart: true do |boot|
        small(config)
        boot.vm.box = $box_name
        #boot.vm.hostname = "gemini-master"
        boot.vm.network "private_network", ip: "192.168.2.2", virtualbox__intnet: "gem"
    end

end



