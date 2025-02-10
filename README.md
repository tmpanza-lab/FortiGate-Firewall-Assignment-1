# FortiGate FW - Assignment Project 1

## Objective

The objective of this lab assignment is to configure a network topology involving VLAN segmentation, inter-VLAN routing, and internet access through a FortiGate firewall, this setup ensures that different departments (IT, Sales, and Management) are logically separated while still having controlled communication between VLANs and internet access via the FortiGate firewall.

### Skills Learned

- Basic FortiGate Administration Skill
- Network Configuration and Management 
- Security Management Skills
- Advanced Networking Skills (VLAN Configuration, Inter-VLAN Routing, DHCP Configuration, Static and Default Routing, Switch Configuration, Subnetting & IP Addressing)


### Tools Used

- FortiGate VM: A virtual appliance used in virtualized environments, such as VMware
- FortiOS Web Interface (GUI)
- FortiOS Command Line Interface (CLI)
- Cisco iOS Command Line Interface (CLI)
- FortiView Dashboard: Built-in monitoring tool for real-time traffic and event analysis.
- GNS3 for simulated network devices (e.g., routers, PCs, or switches) to test


*Ref 1: Network Diagram*
![image](https://github.com/user-attachments/assets/356ad897-1378-46ca-94ed-b8c53e4b1b38)




## STEPS

#FortiGate Configuration

1)	Set Hostname and idle timeout
![image](https://github.com/user-attachments/assets/e1bef052-d394-4bd2-ba86-743a5ca6ccc3)
 
To set the admin timeout to 30 minutes:
![image](https://github.com/user-attachments/assets/ba620938-a32c-4f92-bf79-c659d38093fa)

2)	Configure the interfaces

Port 2
![image](https://github.com/user-attachments/assets/44f65a86-0ef8-4af4-ae41-3202e0052a79)
 
Port 1
![image](https://github.com/user-attachments/assets/3cec1ea0-67dd-47df-bc66-45f05e393c4a)
 
Port 3
![image](https://github.com/user-attachments/assets/ffe8a934-d124-481c-8cc2-229a3f67fa04)
 
Admin
![image](https://github.com/user-attachments/assets/f71e7d5f-e652-408a-b029-9da11629d175)
 
# Add Static Routes To other VLANs
![image](https://github.com/user-attachments/assets/59925560-e6df-4205-9ad0-72c9dbbf4824)
![image](https://github.com/user-attachments/assets/39e8452c-617f-4df0-b833-c1f0c5aade8f)

 
 

3)	Create the VLANs
![image](https://github.com/user-attachments/assets/68804e46-293f-4c82-8a1f-423e15318fd8)
 
# Switch Configuration to change interface Fe0/0 to trunk link
![image](https://github.com/user-attachments/assets/2d7b1c32-1f81-4f5d-81ac-dee6e0b6d30b)
![image](https://github.com/user-attachments/assets/2a310fd6-e5c4-4140-94d9-454e1622c654)
 
 

4) Configure DHCP for VLANs
![image](https://github.com/user-attachments/assets/53e1c7a5-7b6c-4a14-93df-402867412ea1)
![image](https://github.com/user-attachments/assets/45d07a02-8436-438f-9418-355115605276)
![image](https://github.com/user-attachments/assets/dae98d30-e455-4c90-9e6d-cf90c96fa599)
![image](https://github.com/user-attachments/assets/12af9569-ec5e-49aa-960e-2e42e754c7cc)

 
Verify Configuration
![image](https://github.com/user-attachments/assets/f8aee803-26b2-43b8-8b57-f574a0d85bdc)
![image](https://github.com/user-attachments/assets/600003ec-8999-485d-88f7-d61ea1d92c32)
 
 






Verify clients are receiving IP Address from DHCP Server

IT-PC
![image](https://github.com/user-attachments/assets/31ac1396-7919-4b07-9ad4-d0a46bca694f)
 
SALES-PC
![image](https://github.com/user-attachments/assets/54bfc533-ce90-4449-85d7-f83e6736fbcf)
 
FIREWALL
![image](https://github.com/user-attachments/assets/a1bbd0a8-a2ef-4d36-bfd6-97f60ed9fa67)
 


5) Create inter-VLAN routing

Enable IVR (Inter-VLAN Routing) On FortiGate ###

# We have Two Options to Enable IVR:

1)	Create A firewall Policy That Allow Traffic between VLANs

## Don't Forget To Activate Multiple interfaces Policy From Feature visibility ##

![image](https://github.com/user-attachments/assets/75559591-d40b-495e-a665-df075d53c7ea)


2)	Create VLANs Zone
![image](https://github.com/user-attachments/assets/804ae3ed-1a0f-403a-ba33-33d924605353)
![image](https://github.com/user-attachments/assets/ab93c978-1e16-42aa-afe6-a46187b405fd)
 
 

6) Create a static route toward INTERNET
![image](https://github.com/user-attachments/assets/331e9030-bef0-4051-9a56-e99cd37f3f1f)
 

7) Give internet access to VLANs and ADMIN

# INTERNET POLICY
![image](https://github.com/user-attachments/assets/c4bea189-3eba-4912-90d7-4bd0b719f22d)
 













#Cisco Switch VLAN Configuration

1)	Create the VLANs
![image](https://github.com/user-attachments/assets/97df2cbe-ae60-48a7-a131-79b19f58e4c7)
 

Give the VLANs a name and description in the database on each switch.
![image](https://github.com/user-attachments/assets/7d767baf-13d2-4044-9a0c-43768032df06)
 


Verify the VLANs have been assigned the IP addresses in the database on each switch.
![image](https://github.com/user-attachments/assets/ead8e42d-c013-4e14-b5f0-d5cb551be518)
 


Verify the VLANs are in the database on each switch.
![image](https://github.com/user-attachments/assets/8c1a2e28-7aeb-4f3c-a742-3e0145be2a80)
 


2)	Assign IP@ to VLAN10-MGMT-PC vlan
![image](https://github.com/user-attachments/assets/d9cb21f2-bf21-47dc-9687-80178b424924)
 ![image](https://github.com/user-attachments/assets/aaf276be-eac7-4bb2-8b5e-4e0ba512c5bc)

TEST connectivity Ping the VLAN 10 gateway
![image](https://github.com/user-attachments/assets/ac65da25-e0d3-420c-bfce-0efe293d8e4b)
 

3)	Assign the VLANs to the interfaces
 ![image](https://github.com/user-attachments/assets/88fc0720-11fa-4026-8b81-1f24172cd8ab)


Verify the interfaces are assigned to the correct VLANs in the database on each switch.
![image](https://github.com/user-attachments/assets/2c382c60-d399-41b5-ac7c-2d1dfb72a10b)
 

Enable Layer 3 Switch inter-VLAN routing
 ![image](https://github.com/user-attachments/assets/9e620e96-80f8-4dfe-9895-102d310ae515)

## Questions for this assignment

# What are the commands to change hostname and Idle timeout?
![image](https://github.com/user-attachments/assets/267c452c-bc1f-481d-9f70-e6dfa98d1730)


# What are the commands to configure the port3 WAN interface?

![image](https://github.com/user-attachments/assets/05f570df-abfe-433c-b8d3-21c141c65b30)



# What are the commands to create vlan10 in FortiGate Firewall?

![image](https://github.com/user-attachments/assets/9499a6f9-9500-4770-9bd8-db369ecf472c)



The switch port connected to port2 of firewall should be on which mode (Trunk/Access)?

Trunk mode carries multiple VLANs over a single link, it tags frames with VLAN IDs (802.1Q tagging) so that different VLANs can be identified.

These LAB skills are essential for Network Engineers, Security Engineers, and System Administrators, particularly those working with enterprise networks and cybersecurity infrastructure.




