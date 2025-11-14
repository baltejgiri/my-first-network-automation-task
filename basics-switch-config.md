## Basic configuration for remote management

I have used Cisco Nexus 9K virtual image on eve-ng and connected it's interface gig1/0/1 to the home network using networks called **Management (Cloud 0)**, which uses the pnet0 on the eve-ng VM.

```cisco
!
configure terminal
!
hostname C9K-SW1
ip domain name ptn.internal
crypto key generate rsa modulus 2048
username admin privilege 15 secret Admin@123
line vty 0 4
 login local
 transport input ssh
 logging synchronous
!
exit
!
service password-encryption
ip ssh version 2
!   
interface GigabitEthernet1/0/1
 description uplink_to_eve_management_pnet0
 no switchport
 ip address 172.16.105.31 255.255.255.0
 no shutdown
!
end
!
!
!verify network connectivity to interface GigabitEthernet1/0/1
ping 172.16.105.31
!verify ssh access
ssh -l admin 172.16.105.31
!
write memory
!
```