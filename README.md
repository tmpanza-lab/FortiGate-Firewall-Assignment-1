# FortiGate Firewall Assignment 1: Project 1 LAB

## Objective

The objective of this lab assignment is to configure a network topology involving VLAN segmentation, inter-VLAN routing, and internet access through a FortiGate firewall, this setup ensures that different departments (IT, Sales, and Management) are logically separated while still having controlled communication between VLANs and internet access via the FortiGate firewall.

### Skills Learned

- Cybersecurity skills
- Networking Skills (VLAN Configuration, Inter-VLAN Routing, DHCP Configuration, Static and Default Routing, Switch Configuration, Subnetting & IP Addressing)
- Security & Firewall Skills (Firewall Configuration (FortiGate), Access Control & Traffic Filtering, Network Address Translation (NAT)
- System Administration & Troubleshooting (Monitoring & Debugging, User & Device Management)


### Tools Used

- FortiGate VM: A virtual appliance used in virtualized environments, such as VMware or Hyper-V
- FortiOS Web Interface (GUI)
- FortiOS Command Line Interface (CLI)
- FortiView Dashboard: Built-in monitoring tool for real-time traffic and event analysis.
- Backup and Restore Tools
- FTP/HTTP/HTTPS Servers: For uploading firmware or serving configurations during the lab.
- Traffic Generation Tools
- GNS3 for simulated network devices (e.g., routers, PCs, or switches) to test


*Ref 1: Network Diagram*
 ![image](https://github.com/user-attachments/assets/8e32791f-cba3-42af-9816-68bc806362ad)



## Steps

## FORTIGATE FIREWALL CONFIGURATION

## Set Hostname and idle timeout
![image](https://github.com/user-attachments/assets/78e8b4e9-1fb2-4ab9-b9f3-f16ecbb74eff)
![image](https://github.com/user-attachments/assets/786b7fbe-a958-43ac-b96f-66bfd0848608)
 

 

# Configure the interfaces
![image](https://github.com/user-attachments/assets/1f000d7d-0bc2-4541-8bec-d9393ead68c6)
![image](https://github.com/user-attachments/assets/ea935049-5f23-473f-b6f2-62cff44e67af)
![image](https://github.com/user-attachments/assets/7b1f339f-ef2b-4ee4-9e9c-2229762f84a8)
![image](https://github.com/user-attachments/assets/725e6afa-e8ad-422c-aeda-6d40a6de00f0)
 
# Create the VLANs
![image](https://github.com/user-attachments/assets/a274c83d-b5b8-438c-b77f-7f7b845a5c4f)
![image](https://github.com/user-attachments/assets/e42aa54b-37cd-4077-903c-92da2940aada)

# Configure DHCP for VLANs
![image](https://github.com/user-attachments/assets/92e4c22d-1b43-4a58-b088-556702ec196f)
 

# Create inter-VLAN Routing
![image](https://github.com/user-attachments/assets/c1896898-5ca9-4be5-8bd7-096aed730353)
![image](https://github.com/user-attachments/assets/5507513e-31fd-4dc7-b6fa-cc3e9d09d071)

# Create Static route towards the INTERNET
![image](https://github.com/user-attachments/assets/dae79f76-4dca-4984-afe1-1b218caeb311)
![image](https://github.com/user-attachments/assets/f22cae34-ea28-45ca-a5ce-07b1fe4991dd)
 
 
INTERNET POLICY
![image](https://github.com/user-attachments/assets/02170a08-5c7d-4871-a234-63ca8aa5adb2)
![image](https://github.com/user-attachments/assets/15cb310e-80c6-44e9-8a37-1b548fdbcf6a)
 
 

# Give internet access to VLANs and ADMIN
![image](https://github.com/user-attachments/assets/660b5e4b-230c-4bfe-9321-b7ed55755679)
 




## CISCO SWICTH CONFIGURATION

# Create the VLANs
![image](https://github.com/user-attachments/assets/301dadef-c974-4d65-8f7a-714d0bf85cc0)
 

# Assign IP address to MGMT VLAN
![image](https://github.com/user-attachments/assets/239d0a63-6fae-4767-81a1-13a6bcf0eda3)
 

# Assign the VLANs to the interfaces
![image](https://github.com/user-attachments/assets/d948a830-b45b-427e-912f-928113a7e035)
![image](https://github.com/user-attachments/assets/58c6474f-bdb4-4135-a90b-c25dd56e66d1)
![image](https://github.com/user-attachments/assets/e633c7a5-0401-4c8a-bbf7-9051dd31f405)
 
 
 


## Questions for this assignment

# What are the commands to change hostname and Idle timeout?

* Config system global
* Set host name <HOSTNAME>
* Set admin-console-timeout <VALUE>


# What are the commands to configure the port3 WAN interface?

* Config system interface
* Edit “port3”
* Set mode dhcp
* Set allowaccess ping
* Set alias WAN
* Set role wan


# What are the commands to create vlan10 in FortiGate Firewall?

* Config system interface
* Edit “vlan10”
* Set vdom “root”
* Set ip 192.168.10.1 255.255.255.0
* Set allowaccess ping ssh http
* Set alias LAN
* Set role lan
* Set interface “port2”
* Set vlanid 10


# The switch port connected to port2 of firewall should be on which mode (Trunk/Access)?

Trunk mode carries multiple VLANs over a single link, it tags frames with VLAN IDs (802.1Q tagging) so that different VLANs can be identified.



# These LAB skills are essential for Network Engineers, Security Engineers, and System Administrators, particularly those working with enterprise networks and cybersecurity infrastructure.




