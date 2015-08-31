Vagrant.configure(2)  do |config|
  config.vm.box = "https://f0fff3908f081cb6461b407be80daf97f07ac418.googledrive.com/host/0BwtuV7VyVTSkUG1PM3pCeDJ4dVE/centos7.box"
  config.vm.hostname = "graylog"

  config.vm.network :forwarded_port, guest: 9000, host: 9000
  config.vm.network :forwarded_port, guest: 12900, host: 12900
  config.vm.network :forwarded_port, guest: 12201, host: 12201, protocol: 'udp'
  config.vm.network :forwarded_port, guest: 12201, host: 12201, protocol: 'tcp'

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end

  $script = <<SCRIPT
    yum update
SCRIPT

  config.vm.provision "shell", inline: $script
end
