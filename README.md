# immortal_vpn

1.  setup your VPN
      
      https://www.privateinternetaccess.com/pages/client-support/
2.  find your VPN uuid 
      
      nmcli con list | grep -i vpn
3.  edit your /etc/rc.d/rc.local with code from this repo
      
      https://raw.githubusercontent.com/drwolff/immortal_vpn/master/rc.local
4.  configure VPN kill switch
      
      https://linuxconfig.org/how-to-create-a-vpn-killswitch-using-iptables-on-linux
5.  reboot
