$useraddscript = <<SCRIPT
useradd -m henk
useradd -m joop
useradd -m jan
useradd -m student
useradd -m linda
useradd -m anka
useradd -m richard
useradd -m koos
useradd -m caitlyn
groupadd operators
groupadd administratie
usermod -aG operators henk
usermod -aG operators joop
usermod -aG operators jan
usermod -aG administratie linda
usermod -aG administratie anka 
usermod -aG administratie richard
usermod -aG administratie koos
usermod -aG administratie caitlyn
mkdir /operators
mkdir /administratie 
mkdir /financieel
mkdir /administratie/loon 
mkdir /administratie/klanten
mkdir /administratie/factuur
chown henk /operators
chgrp operators /operators
chown henk:administratie /administratie
chown henk:administratie /administratie/loon
chown henk:administratie /administratie/klanten
chmod 770 /operators
chmod 770 /administratie
chmod 774 /administratie/loon 

SCRIPT


Vagrant.configure('2') do |config|
    config.ssh.insert_key = false

    # set default settings
    config.vm.box = "ubuntu/bionic64"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 1024
        vb.cpus = 1
    end
     
	config.vm.define :web1 do |machine1|
        machine1.vm.host_name = "web1.local"
        machine1.vm.network "private_network", ip: "192.168.10.243"
        machine1.vm.provision "shell", inline: $useraddscript
		machine1.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
		machine1.vm.synced_folder "DevOps4.3/", "/home/vagrant/mission"
	end
	config.vm.define :web2 do |machine2|
        machine2.vm.host_name = "web2.local"
        machine2.vm.network "private_network", ip: "192.168.10.244"
        machine2.vm.provision "shell", inline: $useraddscript
		machine2.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
		machine2.vm.synced_folder "DevOps4.3/", "/home/vagrant/mission"
	end
end

