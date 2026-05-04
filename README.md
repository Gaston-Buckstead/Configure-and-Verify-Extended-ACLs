# Configure-and-Verify-Extended-ACLs

## Overview: This project configures and verifies extended IPv4 ACLs on R1 to enforce security policies between VLAN networks.

## Topology
<img width="544" height="269" alt="image" src="https://github.com/user-attachments/assets/eabe899a-bf5d-4716-bbc8-333ee1b3d64c" />

## R1.txt
<img width="405" height="471" alt="image" src="https://github.com/user-attachments/assets/aa84709e-a2f2-43fc-b6ba-9c4744840ab0" />

## Extended ACLs configured
ip access-list extended FILTER_STUDENT_TRAFFIC

 deny tcp 172.18.0.0 0.0.0.255 172.16.0.0 0.0.0.255 eq 22
 
 deny icmp 172.18.0.0 0.0.0.255 172.16.0.0 0.0.0.255 echo
 
 deny tcp 172.18.0.0 0.0.0.255 172.16.0.0 0.0.0.255 eq www
 
 deny tcp 172.18.0.0 0.0.0.255 172.16.0.0 0.0.0.255 eq 443
 
 deny icmp 172.18.0.0 0.0.0.255 172.17.0.0 0.0.0.255 echo
 
 permit ip any any
 
ip access-list extended FILTER_FACULTY_TRAFFIC

 deny tcp 172.17.0.0 0.0.0.255 172.16.0.0 0.0.0.255 eq 22
 
 deny icmp 172.17.0.0 0.0.0.255 172.16.0.0 0.0.0.255 echo
 
 permit ip any any

Download Packet Tracer Here
