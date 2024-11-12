 
# Configuración de Vagrantfile para Apache Server
Vagrant.configure("2") do |config|
    # Definir la caja base (Ubuntu en este caso)
    config.vm.box = "ubuntu/bionic64"
    
    # Configurar la máquina virtual con 512 MB de RAM y 1 CPU
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
    
    # Configurar el aprovisionamiento para instalar Apache
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
    SHELL
    
    # Configurar la carpeta compartida
    # La carpeta local "html" se montará en /var/www/html en la VM
    config.vm.synced_folder "./html", "/var/www/html"
    
    # Configurar red privada para acceder al servidor web desde el host
    config.vm.network "private_network", ip: "192.168.33.10"
  end
  