Fedora VM autostart VPN + pi-hole DNS

1. Install VMware

2. Create a new Fedora VM

3. Log into the Fedora VM as root

4. Change runlevel to CLI 
      systemctl set-default multi-user.target
      reboot

5. Install & configure ProtonVPN
      https://protonvpn.com/support/linux-vpn-tool/
      dnf install -y openvpn dialog python3-pip python3-setuptools
      pip3 install protonvpn-cli
      protonvpn init
      protonvpn configure
            set DNS leak protection & killswitch
      protonvpn c --sc
            connect to the fastest secure core server
      
6. Edit /etc/rc.d/rc.local
      https://raw.githubusercontent.com/drwolff/immortal_vpn/master/protonvpn
      reboot
      
7. install pi-hole
      https://github.com/pi-hole/pi-hole/#one-step-automated-install
      https://docs.pi-hole.net/main/basic-install/
      curl -sSL https://install.pi-hole.net | bash
      
8. Update VMware DNS settings
      Network and Internet settings
      Change adapter options
      Right-click VMware Network Adapter VMnet8
      Click Properties
      Double-click Internet Protocol Version 4 (TCP/IPv4)
      Use the following DNS server addresses:
            Preferred DNS server: your Fedora VM's IP address
      Click OK twice
      
9. Update your host OS DNS settings
      https://www.windowscentral.com/how-change-your-pcs-dns-settings-windows-10
      https://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245

10. Done
