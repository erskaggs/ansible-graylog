VAGRANTFILE_API_VERSION = "2"

service_name = 'graylog'

Vagrant.configure(2)  do |config|
  config.vm.box = "bento/centos-7.1"
  config.vm.hostname = "graylog"

  config.vm.network :forwarded_port, guest: 9000, host: 9000
  config.vm.network :forwarded_port, guest: 12900, host: 12900
  config.vm.network :forwarded_port, guest: 12201, host: 12201, protocol: 'udp'
  config.vm.network :forwarded_port, guest: 12201, host: 12201, protocol: 'tcp'

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end

  $script = <<SCRIPT
    yum -y update
    yum -y install epel-release
    yum -y install ansible
SCRIPT

  config.vm.provision "shell", inline: $script
end
