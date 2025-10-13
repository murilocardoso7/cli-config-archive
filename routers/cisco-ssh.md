# 🔐 Cisco SSH Configuration

```bash
enable
configure terminal
hostname R1
interface gigabitEthernet0/0
ip address 192.168.101.10 255.255.255.0
no shutdown
exit
ip default-gateway 192.168.101.1
ip domain-name eve.lab
crypto key generate rsa modulus 1024
ip ssh version 2
ip ssh authentication-retries 3
ip ssh time-out 60
username <USER> privilege 15 secret <PASSWORD> 
line vty 0 4
login local
transport input ssh
end
write memory
