# Design and Implementation of a Small Office Home Office Network (Project #2)

### Overview
This project entails the design and implementation of a network for XYZ company's branch office located near the village of Bonalbo, Eastern Australia. The company specializes in the buying and selling of food items and is experiencing rapid growth with over 2 million customers globally. The network for the branch office needs to be designed separately from the headquarters and should accommodate the following requirements:

- Utilization of one Cisco router and one Cisco switch.
- Establishment of three departments: Admin/IT, Finance/HR, and Customer service/Reception.
- Each department to be allocated to different VLANs.
- Provision of wireless network access for users in each department.
- Automatic acquisition of IPv4 addresses for host devices.
- Seamless communication between devices in all departments.

## Technologies Implemented
1. **Creating a Simple Network using a Router and Access Layer Switch:** Utilized Cisco router and switch to establish the network infrastructure.
2. **Connecting Networking Devices with Correct Cabling:** Employed appropriate cabling techniques to ensure proper connectivity between devices.
3. **Creating VLANs and Assigning Ports VLAN Numbers:** Configured VLANs to segregate network traffic for different departments and assigned VLAN IDs to switch ports accordingly.

   ```bash
   Open terminal
   Enter en to enable switch
   Enter config t to start changing
   ```
   
   - **For Admin Department:**
     ```bash
     Int range fa0/2-4
     switchport mode access
     switchport access vlan 10
     ```

   - **For Finance Department:**
     ```bash
     Int range fa0/5-7
     switchport mode access
     switchport access vlan 20
     ```

   - **For Customer Department:**
     ```bash
     Int range fa0/8-10
     switchport mode access
     switchport access vlan 30
     ```

   ```bash
   Do wr   # Save changes
   Exit
   Do sh start
   ```

4. **Subnetting and IP Addressing:** Implemented subnetting to divide the network into segments and allocated IP addresses to devices within each subnet.

   - **Creating Subnets:**
     - **1st Network:**
       - Network Id: 192.168.1.0
       - Broadcast ID: 192.168.1.63
       - IP Range: 192.168.1-63
     - **2nd Network:**
       - Network Id: 192.168.1.64
       - Broadcast ID: 192.168.1.127
       - IP Range: 192.168.65-126
     - **3rd Network:**
       - Network Id: 192.168.1.128
       - Broadcast ID: 192.168.1.192
       - IP Range: 192.168.129-190

5. **Configuring Inter-VLAN Routing (Router on a Stick):** Enabled communication between VLANs by configuring the router to route traffic between them.
   
6. **Configuring DHCP Server (Router as the DHCP Server):** Configured the router to act as a DHCP server to automatically assign IP addresses to devices on the network.

   ```bash
   Open CLI
   En
   Config t
   Int gig0/0
   No sh
   Do wr
   ```

   - **Configuring DHCP Pools:**
     ```bash
     Service dhcp
     ```
     - **For Admin Department:**
       ```bash
       Ip dhcp pool admin-pool
       Network 192.168.1.0 255.255.255.192
       Default-router 192.168.1.1
       Dns-Server 192.168.1.1
       Domain-name Admin.com
       ```
     
     - **For Finance Department:**
       ```bash
       Ip dhcp pool finance-pool
       Network 192.168.1.64 255.255.255.192
       Default-router 192.168.1.65
       Dns-Server 192.168.1.65
       Domain-name finance.com
       ```
     
     - **For Customer Department:**
       ```bash
       Ip dhcp pool customer-pool
       Network 192.168.1.128 255.255.255.192
       Default-router 192.168.1.129
       Dns-Server 192.168.1.129
       Domain-name Customer.com
       ```

   ```bash
   Do wr
   ```

7. **Configuring WLAN or Wireless Network (Cisco Access Point):** Set up wireless access points to provide wireless network connectivity for users in each department.

   - **SSID and Password Configuration:** Set SSID and password for each access point.
   
8. **Host Device Configurations:** Configured individual host devices with appropriate network settings.

9. **Testing and Verifying Network Communication:** Conducted testing to ensure seamless communication between devices across departments.

#### Network Topology
The network topology was designed to meet the requirements of XYZ company's branch office. It consists of the following components:
- Router: Cisco router serving as the gateway for inter-VLAN communication.
- Switch: Cisco switch used for connecting devices within each department and facilitating VLANs.
- Access Points: Cisco access points providing wireless network access for users.
- Host Devices: Devices within each department configured to communicate with one another.

The network topology has been thoroughly tested and verified to ensure proper functionality.

#### Conclusion
The implemented network design successfully meets the requirements of XYZ company's branch office, providing efficient connectivity and communication for the Admin/IT, Finance/HR, and Customer service/Reception departments. The network design adheres to industry best practices and ensures scalability for future growth.

#### GitHub Repository
For the Packet Tracer file and further details, please refer to the GitHub repository [[link to be inserted](https://github.com/ijlal321/Networking-Projects/tree/main)https://github.com/ijlal321/Networking-Projects/tree/main].
