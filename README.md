# Basic Cisco Switch Configuration & Security Hardening

This laboratory project demonstrates the implementation of fundamental configuration and security practices on a Cisco Catalyst 2960 Switch using Cisco Packet Tracer.

## Core Concepts Covered
* Hostname Assignment: Rebranding the system identity.
* Privileged EXEC Mode Security: Encrypted access protection.
* Physical Management Protection: Securing the Console line.
* Remote Access Security: Securing Virtual Terminal (VTY) lines.
* Data Privacy: Encrypting plain-text credentials globally.
* Legal Notification: Configuring a warning banner (MOTD).
* Management SVI: Assigning a management IP to VLAN 1.

## IOS Commands Implemented
```text
enable
configure terminal
hostname SW-Office

enable secret cisco123

line console 0
password cisco
login
exit

line vty 0 15
password cisco
login
exit

service password-encryption

banner motd "UNAUTHORIZED ACCESS IS PROHIBITED"

interface vlan 1
ip address 192.168.1.50 255.255.255.0
no shutdown
exit

exit
copy running-config startup-config
