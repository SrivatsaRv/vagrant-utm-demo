Vagrant.configure("2") do |config|
  config.vm.box = "utm/debian11"
  # Set VM properties for UTM
  config.vm.provider "utm" do |u|
    u.name = "debian_vm"
    u.memory = "2048"   # 4GB memory
    u.cpus = 4          # 4 CPUs
    u.directory_share_mode = "virtFS"
    #u.directory_share_mode = "webDAV"  # Use webDAV for manual directory sharing
  end

  # Provisioning all requirements using a shell script
  config.vm.provision "shell", path: "provision.sh"

  # Forward port 8080 from the VM to the host for NGINX access
  config.vm.network "forwarded_port", guest: 8080, host: 8080
end

