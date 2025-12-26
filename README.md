# Network Design Project: Cairo & Alexandria Branches

**Alexandria University**  
**Faculty of Engineering**  
**Computer and Systems Engineering Department**  

**Course:** Computer Networks  
**Assignment:** Site Design  
**Date:** December 2025  

## Project Overview

This project involves the design, implementation, and simulation of a network connecting multiple branches of Company X, an autonomous system (AS) with locations in Cairo and Alexandria. The network is designed to ensure reliable communication and efficient data transfer between sites using IPv4.

The project is implemented and simulated using **GNS3**.

## Objectives

*   Design and implement a network for small and large scale scenarios.
*   Develop an IP addressing scheme using FLSM.
*   Configure Switching and Routing protocols (EIGRP & BGP).
*   Ensure full network reachability.

## Network Topology & Requirements

### Branch Details

| Branch | Building | Department | Switch | Users | Network |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Cairo** | Building 1 (B1) | Sales | SW1 | 2 PCs | `20.1.1.0/24` |
| | | HR | SW2 | 2 PCs | `30.1.1.0/24` |
| | Building 2 (B2) | IT | SW3 | 2 PCs | `40.1.1.0/24` |
| **Alexandria** | Building 1 (B1) | Operation | SW4 | 2 PCs | `50.1.1.0/24` |

### Configuration Specifications

1.  **IP Assignment:**
    *   Separate Network IP for each department.
    *   **FLSM Strategy:** Fixed Length Subnet Masking using 256 hosts per network (Class C /24 subnets).

2.  **Routing Protocols:**
    *   **EIGRP (Enhanced Interior Gateway Routing Protocol):** Used for internal routing within the Cairo branch.
        *   Between Router **RW1** and Router **RW3**.
        *   Between Router **RW2** and Router **RW3**.
        *   Ensures communication between Building 1 (B1) and Building 2 (B2).
    *   **BGP (Border Gateway Protocol):** Used for external routing between branches.
        *   Between Router **RW3** (Cairo) and Router **RW4** (Alexandria).
        *   Enables communication between Cairo and Alexandria sites.

3.  **Hardware & Simulation:**
    *   **Simulator:** GNS3.
    *   **Devices:** Routers (RW1, RW2, RW3, RW4), Switches (SW1, SW2, SW3, SW4), and PCs.
    *   **Team Size:** Group of up to two members.

## Implementation Details

*   **Subnetting:** Each department is assigned a specific /24 subnet as listed in the topology table.
*   **Connectivity:** All PCs are assigned dynamic or static IPs within their respective subnets and are reachable from any other PC in the network.
*   **Routing Configuration:**
    *   EIGRP AS is configured to route internal Cairo traffic.
    *   BGP AS numbers are assigned to Cairo and Alexandria routers to facilitate inter-branch routing.

## Files

*   `networklab2.gns3`: The main GNS3 project file containing the network topology and configurations.
