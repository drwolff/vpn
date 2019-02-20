# immortal_vpn

1.  setup your VPN (Fedora can't handle file import with inline certs so cut/paste all that into ~/.cert/whatever.crt)
      
      https://www.privateinternetaccess.com/pages/client-support/
2.  find your VPN uuid 
      
      nmcli con | grep -i vpn
3.  edit your /etc/rc.d/rc.local with code from this repo (change *** to your uuid)
      
      https://raw.githubusercontent.com/drwolff/immortal_vpn/master/rc.local
4.  configure VPN kill switch
      
      https://linuxconfig.org/how-to-create-a-vpn-killswitch-using-iptables-on-linux
5.  reboot
