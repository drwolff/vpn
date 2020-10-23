# Fedora VM autostart VPN + pi-hole DNS

### 1. Install Fedora

### 2. Log in as root

### 3. Change runlevel to CLI 
      
      systemctl set-default multi-user.target
      
      reboot

### 4. Install & configure ProtonVPN

https://protonvpn.com/support/linux-vpn-tool/

      dnf install -y openvpn dialog python3-pip python3-setuptools
      
      pip3 install protonvpn-cli
      
      protonvpn init

Set DNS leak protection & killswitch

      protonvpn configure
      
Connect to the fastest secure core server
      
      protonvpn c --sc
      
### 5. Edit rc.local

      vi /etc/rc.d/rc.local

https://raw.githubusercontent.com/drwolff/immortal_vpn/master/protonvpn
      
      chmod +x etc/rc.d/rc.local
      
      reboot
      
### 6. install pi-hole

https://github.com/pi-hole/pi-hole/#one-step-automated-install

https://docs.pi-hole.net/main/basic-install/

      curl -sSL https://install.pi-hole.net | bash
      
### 7. Update DNS settings (VMware)

      Network and Internet settings

      Change adapter options

      Right-click VMware Network Adapter VMnet8

      Click Properties

      Double-click Internet Protocol Version 4 (TCP/IPv4)

      Use the following DNS server addresses:
      
            Preferred DNS server: your Fedora VM's IP address

      Click OK twice
      
### 8. Update your host DNS settings

https://www.windowscentral.com/how-change-your-pcs-dns-settings-windows-10

https://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245

### 9. Done
