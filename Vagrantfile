Vagrant.configure("2") do |config|

    # Every Vagrant development environment requires a box. You can search for
    # boxes at https://vagrantcloud.com/search.
  
  config.vm.define "ubuntu" do |web|
    web.vm.box = "ubuntu/bionic64"
    web.vm.network "private_network", ip: "192.168.56.6", auto_config: "false"
     # web.vm.network "forwarded_port", guest: 80, host: 8080
    web.vm.disk :disk, size: "15GB", primary: true
    web.vm.provider "virtualbox" do |web|
      # Customize the amount of memory on the VM:
      web.cpus = "3"
      web.memory = "3024"
    end
  
    web.vm.provision "shell", inline: <<-SHELL
      export DEBIAN_FRONTEND=noninteractive
      apt-get update
    #  apt-get -y install nginx
    #  service nginx start
      sudo ip route add default via 192.168.56.5 metric 90
    #  sudo tee /var/www/html/index.nginx-debian.html <<EOF
    #  <!DOCTYPE html>
    #  <html>
    #  </head>
    #  <body>
    #   !!!!Welcome to nginx! My name is Dmitriy T.
    #  </body>
    #  </html>
    #  EOF
    SHELL
  end
   
  config.vm.define "mikrot" do |mikrot|
    mikrot.vm.box = "https://storage.yandexcloud.net/dtomin-netology/net_pub_91_vagrant-6_49.box"
    mikrot.vm.network "private_network", ip: "192.168.56.5"
    mikrot.vm.provider "virtualbox" do |mikrot|
    # Customize the amount of memory on the VM:
      mikrot.cpus = "2"
      mikrot.memory = "1024"
    end
   end
  end
