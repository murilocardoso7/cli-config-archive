# 🔐 Cisco SSH Configuration

```bash
enable
configure terminal
hostname Router
interface gigabitEthernet0/0
ip address 192.168.101.10 255.255.255.0
no shutdown
exit
ip default-gateway 192.168.101.1
ip domain-name teste.com
crypto key generate rsa modulus 1024
username <USER> privilege 15 secret <PASSWORD>
line vty 0 4
login local
transport input ssh
exit
end
copy running-config startup-config
