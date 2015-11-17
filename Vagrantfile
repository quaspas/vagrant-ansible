# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.define :webapp do |web_config|
        web_config.vm.box = "ubuntu/trusty64"
        web_config.vm.network :private_network, ip: "192.168.33.10"
        web_config.vm.network :forwarded_port, guest: 80, host: 4567
    end

    config.vm.provider "virtualbox" do |v|
        v.memory = 1024
    end
end
