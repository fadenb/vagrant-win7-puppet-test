Vagrant.configure("2") do |config|

  # Max time to wait for the guest to shutdown
  config.windows.halt_timeout = 25

  # Admin user name and password
  config.winrm.username = "vagrant"
  config.winrm.password = "vagrant"

  # Configure base box parameters
  config.vm.box = "tiny7_puppet3.3.1"
  # private basebox due to licensing foo. Modify to your needs accordingly.
  config.vm.box_url = "../boxes/tiny7_puppet3.3.1.box"
  config.vm.guest = :windows

  # Port forward WinRM and RDP
  config.vm.network :forwarded_port, guest: 5985, host: 5985

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file  = "win7.pp"
    puppet.module_path    = "modules"
    puppet.options        = "--verbose --debug"
  end

end
