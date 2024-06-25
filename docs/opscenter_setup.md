# Setup-Opcenter

- [Setup-Opcenter](#setup-opcenter)
  - [Setting up VMs and Installing Apps](#setting-up-vms-and-installing-apps)
    - [Requirements:](#requirements)
  - [Opcenter Execution Foundation Installation](#opcenter-execution-foundation-installation)
  - [Opcenter Configuration Tool Setup](#opcenter-configuration-tool-setup)
  - [OPC Client Configuration](#opc-client-configuration)

## Setting up VMs and Installing Apps

### Requirements:
- Three VMs with fullfilled prerequisites for Opcenter Execution Discrete

## Opcenter Execution Foundation Installation
1. **Server Setup:**
   - Deploy three servers, each with Opcenter Execution Foundation.
   - Customize server names for identification.
     - Name for primary instance
     - Names for replica instances

2. **SQL Server Configuration:**
   - Enable TCP/IP in SQL Server Network Configuration.
   - Confirm correct SQL Server port (e.g., 1434/TCP).

3. **Firewall Configuration:**
   - Refer to Opcenter Execution Foundation Installation Guide for firewall setup.
     - Ensure correct firewall configurations for seamless communication.

## Opcenter Configuration Tool Setup
4. **Engineering VM Setup:**
   - Launch Opcenter Configuration Tool on the Engineering VM (Primary-Installation).
   - Configure environment settings, security, databases, automation gateway, and web endpoints.
   - Enable Automation Gateway Server and hot-standby redundancy, specifying server names accordingly.

5. **Joining Servers:**
   - On other two servers (Replica-Installation), initiate Opcenter Configuration Tool and select the join option.
   - Enter the server name of the Engineering host.
   - Provide appropriate credentials and environment password.

6. **Additional Configurations:**
   - Verify Erlang and RabbitMQ installations if necessary.
   - Set up a load balancer as per Opcenter Execution Installation Manual.


## OPC Client Configuration

7.  **Automation Channel Configuration:**
    - Enable redundancy failover and specify IP addresses of the two edge devices.