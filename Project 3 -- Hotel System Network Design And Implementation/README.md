# Project Documentation: Vic Modern Hotel Network Design

## Introduction
This documentation outlines the design and implementation of the network infrastructure for Vic Modern Hotel. The hotel consists of three floors, each housing different departments. The network design aims to provide seamless connectivity and efficient management of resources across all departments.

## Requirements
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

## DHCP Configuration
1. Configure each router as a DHCP server.
2. Define IP address pools for each VLAN.
3. Ensure that DHCP relay is enabled for inter-VLAN communication.

## SSH Configuration
1. Enable SSH on all routers.
2. Generate RSA keys for secure authentication.
3. Set up user authentication and privilege levels.

## Port Security Configuration
1. Configure port security on the IT department switch.
2. Use the sticky method to obtain MAC addresses.
3. Set violation mode to shutdown to restrict unauthorized access.

## WLAN Setup
1. Install and configure Cisco Access Points on each floor.
2. Define SSIDs and security parameters for wireless networks.
3. Ensure proper coverage and connectivity.

## OSPF Configuration
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