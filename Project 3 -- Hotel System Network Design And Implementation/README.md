# Project Documentation: Vic Modern Hotel Network Design

## Introduction
This documentation outlines the design and implementation of the network infrastructure for Vic Modern Hotel. The hotel consists of three floors, each housing different departments. The network design aims to provide seamless connectivity and efficient management of resources across all departments.

## Hotel Requiements
The hotel has three floors, each housing different departments. The first floor accommodates Reception, Store, and Logistics; the second floor comprises Finance, HR, and Sales/Marketing; while the third floor hosts IT and Admin departments. Here's a breakdown of the requirements and implementation:

1. **Router Placement**: Three routers are strategically placed in the server room within the IT department, each connecting to a different floor.
   
2. **Interconnection**: All routers are linked to each other using serial DCE cables to facilitate seamless communication.

3. **IP Addressing**: The network between routers is segmented into distinct subnets: 10.10.10.0/30, 10.10.10.4/30, and 10.10.10.8/30, ensuring efficient addressing and routing.

4. **Switch Deployment**: Each floor is equipped with a dedicated switch located within its premises, enabling local network connectivity.

5. **Wireless Networks**: Wi-Fi networks are deployed on each floor to accommodate connectivity for laptops and mobile devices.

6. **Printers**: Every department is provisioned with a printer to facilitate printing needs within the hotel.

7. **VLAN Setup**: Departments are segregated into VLANs, each assigned with specific network details as follows:

   - 1st Floor:
     - Reception: VLAN 80, Network 192.168.8.0/24
     - Store: VLAN 70, Network 192.168.7.0/24
     - Logistics: VLAN 60, Network 192.168.6.0/24
   - 2nd Floor:
     - Finance: VLAN 50, Network 192.168.5.0/24
     - HR: VLAN 40, Network 192.168.4.0/24
     - Sales: VLAN 30, Network 192.168.3.0/24
   - 3rd Floor:
     - Admin: VLAN 20, Network 192.168.2.0/24
     - IT: VLAN 10, Network 192.168.1.0/24

8. **Routing Protocol**: OSPF is employed as the routing protocol for efficient route advertisement and management.

9. **Dynamic IP Assignment**: DHCP servers are configured on respective routers to dynamically assign IP addresses to devices within the network.

10. **Inter-Device Communication**: All devices within the network are configured to communicate seamlessly with each other, fostering collaboration and productivity.

11. **SSH Configuration**: Secure Shell (SSH) is enabled on all routers to facilitate secure remote login and management.

12. **Testing Environment**: A dedicated PC named Test-PC is added to port fa0/1 in the IT department for remote login testing purposes.

13. **Port Security**: Port security measures are implemented on the IT department's switch to restrict access, allowing only Test-PC to connect via port fa0/1, utilizing the sticky method for MAC address acquisition with a violation mode set to shutdown.

## Requirements Summary
The following requirements were considered during the design and implementation process:
1. Three routers connecting each floor, placed in the IT department.
2. Interconnection between routers using serial DCE cables.
3. VLAN segmentation for each department.
4. DHCP configuration for dynamic IP address allocation.
5. Implementation of SSH for secure remote login.
6. Port security configuration to restrict access to specific devices.
7. WLAN setup for wireless connectivity.
8. Implementation of OSPF routing protocol.

## Network Topology
The network topology consists of three floors, each with its own router and switch. The routers are interconnected using serial DCE cables, and VLANs are configured to segregate departments within each floor.

![image](https://github.com/ijlal321/Networking-Projects/assets/103317626/c1af513a-9c5a-448d-8168-74bf2a7f8ae4)


## Hardware Configuration
### Routers
1. Place 3 routers on each floor and enable serial communication.
2. Add HWIC-2T interface card to each router.
3. Connect routers to each other via serial DCE cables.
4. Enable clock rate on router interfaces to establish connectivity.

### Switches
1. Configure VLANs on switches to segregate departments.
2. Assign appropriate ports to each VLAN.
3. Save configurations to ensure persistence.

### DHCP Configuration
1. Configure each router as a DHCP server.
2. Define IP address pools for each VLAN.
3. Ensure that DHCP relay is enabled for inter-VLAN communication.

### SSH Configuration
1. Enable SSH on all routers.
2. Generate RSA keys for secure authentication.
3. Set up user authentication and privilege levels.

### Port Security Configuration
1. Configure port security on the IT department switch.
2. Use the sticky method to obtain MAC addresses.
3. Set violation mode to shutdown to restrict unauthorized access.

### WLAN Setup
1. Install and configure Cisco Access Points on each floor.
2. Define SSIDs and security parameters for wireless networks.
3. Ensure proper coverage and connectivity.

### OSPF Configuration
1. Enable OSPF on all routers.
2. Define router IDs and area configurations.
3. Advertise routes to ensure network reachability.

## Testing and Verification
1. Verify network connectivity between devices.
2. Test DHCP functionality by connecting devices to the network.
3. Ensure SSH login is successful from remote devices.
4. Verify port security by attempting unauthorized access.

## Conclusion
The network infrastructure for Vic Modern Hotel has been successfully designed and implemented to meet the specified requirements. It provides reliable connectivity, security, and scalability to support the hotel's operations effectively. 

For detailed step-by-step instructions on configuring SSH, DHCP, port security, and other aspects of the network, please refer to the following sections.

### Configuration Steps:

#### Configure SSH for Remote Login:
1. Access the router's CLI interface.
2. Enter global configuration mode by typing `configure terminal`.
3. Generate RSA keys using the `crypto key generate rsa` command.
4. Set up user authentication and privilege levels using the `username` and `privilege` commands.
5. Enable SSH version 2 for secure communication.
6. Exit configuration mode and save the configuration.

#### Add Test-PC to IT Department Switch:
1. Access the switch's CLI interface.
2. Navigate to the interface connected to the Test-PC (e.g., `interface fa0/1`).
3. Configure port security using the `switchport port-security` command.
4. Use the sticky method to obtain the MAC address of the Test-PC (`switchport port-security mac-address sticky`).
5. Set violation mode to shutdown to restrict unauthorized access (`switchport port-security violation shutdown`).
6. Exit configuration mode and save the configuration.

These steps provide a comprehensive guide for configuring essential components of the network infrastructure. Adjustments may be necessary based on specific hardware and software configurations.
