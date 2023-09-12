
$edit_sshd = <<-SCRIPT
sudo echo "server ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/server
sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config;
sudo systemctl restart sshd;
SCRIPT

Vagrant.configure("2") do |config|
    (1..2).each do |i|
        config.vm.define "postgres#{i}" do |node|
            node.vm.box = "centos/8"
            node.vm.hostname = "postgres#{i}"
            node.vm.network "forwarded_port", guest: 22, host: "222#{i}", id: "ssh"
            node.vm.network "private_network", ip: "192.168.56.10#{i}", :device => "eth2", :adapter => 2, :netmask => "255.255.255.0"
            node.vm.provision "shell", inline: "sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-Linux-*" 
            node.vm.provision "shell", inline: "sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-Linux-*"
            node.vm.provision "shell", inline: "yum install -y python3"
            node.vm.provision "shell", inline: $edit_sshd
            node.vm.provider "virtualbox" do |vb|
                vb.cpus = 1
                vb.memory = "512"
            end
        end
    end
    config.vm.define "etcd" do |node|
        node.vm.box = "centos/8"
        node.vm.hostname = "etcd"
        node.vm.network "forwarded_port", guest: 22, host: "4722", id: "ssh"
        node.vm.network "private_network", ip: "192.168.56.147", :device => "eth2", :adapter => 2, :netmask => "255.255.255.0"
        node.vm.provision "shell", inline: "sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-Linux-*" 
        node.vm.provision "shell", inline: "sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-Linux-*"
        node.vm.provision "shell", inline: "yum install -y python3"
        node.vm.provision "shell", inline: $edit_sshd
        node.vm.provider "virtualbox" do |vb|
            vb.cpus = 1
            vb.memory = "256"
        end
    end
end
