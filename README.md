# Basic_Switch_Config











Task 
1.	Set HostName
2.	Enable Password
3.	Show Enable Password
4.	Setting Ip Address
5.	Setup Default Gateway 
6.	Make Telnet
7.	Create Vlan
Switch1>en
Switch# config t
Switch1(config)# hostname SW1
SW1(config)# enable password Sifat

SW1(config)#end

Show Enable Password

SW1#sh running-config | include enable 

SW1(config)#enable secret Cisco

Setting Ip Address
SW1(config)# int vlan1
SW1(config)#ip address 192.168.1.1 255.255.255.0
SW1(config)#no shut 
Same for other Switch2 192.168.1.2 and Switch3 192.168.1.3

Setup Default Gateway 
SW1(config)#ip default-gateway 192.168.1.100
Same for other switches
Show The Gateway address
SW1#Sh ip route

SW1#config t
SW1(config)# int range fa0/1,fa0/2,fa0/3,fa0/4

Create Virtual Terminal Season There are 16 available 0-15
SW1(config)#line v
SW1(config)#line vty 0 7 
SW1(config-line)#password Sifat
SW1(config-line)#login
SW1(config-line)#end

Delete Logged in information 

Clear line vty
Create VLAN
SW1#config t
Enter configuration commands, one per line. End with CNTL/Z.
SW1(config)#vlan 50
SW1(config-vlan)#name Vlan50

If you want to create vlan for single port need to access 
SW1(config)#int fa0/4
SW1(config-if)#sw
SW1(config-if)#switchport m
SW1(config-if)#switchport mode a
SW1(config-if)#switchport mode access 
SW1(config-if)#sw
SW1(config-if)#switchport ac
SW1(config-if)#switchport access v
SW1(config-if)#switchport access vlan 50
SW1(config-if)#

If you want to show all configuration of one switchport
sh running-config interface FastEthernet 0/4
If you want multiple vlan in one single interface need to be trunk 

