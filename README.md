# Network Design Documentation

## Project Overview
The objective of this project is to design a network infrastructure for a company with two departments, Accounts and Delivery, enabling communication between devices within each department. This documentation outlines the steps taken to configure the network using Cisco Packet Tracer.

## Network Requirements
1. Two departments: Accounts and Delivery.
2. Each department must have at least two PCs.
3. Network address: 192.168.40.0
4. Devices in both departments should be able to communicate.

## Solution

### Subnet Calculation
To accommodate the two departments, we need to determine the subnet mask:
\[2^n = \text{number of networks}\]

Given \(n\) as the number of bits borrowed from the host for subnetting:
\[2^n = 2\]
\[n = 1\]
Hence, the subnet mask is 255.255.255.128.

### IP Range Calculation
1. **For Network 1**
   - Network ID: 192.168.40.0
   - Host IP Range: 192.168.40.1 - 192.168.40.126
   - Broadcast: 192.168.40.127

2. **For Network 2**
   - Network ID: 192.168.40.128
   - Host IP Range: 192.168.40.129 - 192.168.40.254
   - Broadcast: 192.168.40.255

## Configuration Steps

### Router Configuration
1. Access the router's command-line interface (CLI).
2. Enable privileged EXEC mode.
3. Enter global configuration mode.
4. Select the interfaces to be configured (`gig0/0-1`).
5. Ensure interfaces are not shutdown.
6. Save and apply changes.
7. Exit interface configuration.

### Router Interface Configuration
1. Configure the IP address for the first switch (`gig0/0`): `192.168.40.1 255.255.255.128`.
2. Save changes and exit.

### Switch Configuration
1. Configure the IP address for the second switch (`gig0/1`): `192.168.40.129 255.255.255.128`.
2. Save changes and exit.

### Verify Configuration
1. View the router's startup configuration: `show start`.

## Device Configuration
1. Assign static IP addresses to devices.
2. Set the router's IP address (192.168.40.1) as the gateway.
3. Configure subnet masks.

## Conclusion
Upon completion of the above steps, the network infrastructure is established, enabling communication between devices within the Accounts and Delivery departments.

## Additional Notes
- Ensure proper documentation and labeling of devices for future reference.
- Regularly test network connectivity and perform maintenance as needed.

Feel free to modify and adapt this documentation as necessary for your project requirements.
