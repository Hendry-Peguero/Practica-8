# Configuración de Vagrantfile para servidor Apache
Vagrant.configure("2") do |config|
    # Asignar la imagen de base de Ubuntu
    config.vm.box = "ubuntu/bionic64"
  
    # Asignar memoria RAM y CPU
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  
    # Configurar la red para acceder al servidor web
    config.vm.network "private_network", ip: "192.168.56.10"
  
    # Instalar Apache
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
      systemctl enable apache2
    SHELL
  
    # Compartir la carpeta del servidor Apache con el directorio local
    config.vm.synced_folder "./web", "/var/www/html"
  end
  