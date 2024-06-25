# Setup-IIH

- [Setup-IIH](#setup-iih)
  - [Setting up VMs and Installing Apps](#setting-up-vms-and-installing-apps)
    - [Requirements:](#requirements)
    - [Installation Steps:](#installation-steps)
  - [Modifying OPC UA Model and IIH Configuration](#modifying-opc-ua-model-and-iih-configuration)

## Setting up VMs and Installing Apps

### Requirements:
- TIA-Portal
- Industrial Edge Management
- Edge Device

### Installation Steps:
1. **Set up your VMs:**
    - Ensure TIA-Portal and Industrial Edge Management are installed and configured on your system.
    - Install the necessary apps on your Edge Device: Common Configurator, IIH Semantics, IIH Essentials, Registry Service, Databus, Databus Gateway, and SIMATIC S7+ Connector.

2. **Configuring Databus:**
    - Open Industrial Edge Management and navigate to "Data Connections" > Databus.
    - Launch the Industrial Edge Device (IED) with IIH.
    - Add a new user with specified Topic, Username, Password, and Rights.
    - Add desired topics.
    - Deploy the configuration.

3. **Configuring OPC UA Server:**
    - Open Common Configurator on your Edge Device.
    - Navigate to Settings > Databus Credentials.
    - Enter credentials and save.
    - Navigate to Settings > OPC UA Server.
    - Manage users, add a user with username and password.
  
4. **Export Variables from TIA-Portal:**
    - Install the SIMATIC SCADA Export Add-In for TIA-Portal.
    - Ensure variables to be imported have the option "Visible in HMI Engineering" set.
    - Export tags by right-clicking on the PLC and choosing export to SIMATIC SCADA.

5. **Importing S7 Tags in IIH:**
    - Open Common Configurator and navigate to Get Data > Connector Configuration > SIMATIC S7+ Connector > Tags.
    - Import the file from TIA-Portal.
    - Choose an Acquisition Cycle, Access Mode, and publish to Databus.
    - Deploy the configuration.

## Modifying OPC UA Model and IIH Configuration

1. **Optionally Modifying OPC UA Model (only needed for datatype modification):**
    - Open SIOME and modify the [OPC UA Model](cfg-data/MachineConnectModelComplete.xml).
    - Add necessary nodes and attributes.
    - Export the updated model.

2. **Loading OPC UA Model into IIH:**
    - In Common Configurator, navigate to Define Data > OPC UA model.
    - Import the optionally updated [model file](cfg-data/MachineConnectModelComplete.xml). You need to import the model four times and select the namespaces according to the following sequence.
      -  Base Information Model
      -  Information Model Kit
      -  Information Model Discrete
      -  Information Model Discrete Instances.

3. **Connecting S7 Values with OPC UA Model:**
    - In Common Configurator, navigate to Define Data > Organize.
    - Connect S7 tags with OPC UA Model using Drag and Drop.
    - Deploy the configuration.


