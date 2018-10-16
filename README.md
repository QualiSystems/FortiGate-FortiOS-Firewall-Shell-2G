![](https://github.com/QualiSystems/cloudshell-shells-documentaion-templates/blob/master/cloudshell_logo.png)

# **FortiGateFortiOSFirewallShell2G**

Release date: October 2018

Shell version: 1.0.0

Document version: 1.0.0

# In This Guide

* [Overview](#overview)
* [Downloading the Shell](#downloading-the-shell)
* [Importing and Configuring the Shell](#importing-and-configuring-the-shell)
* [Updating Python Dependencies for Shells](#updating-python-dependencies-for-shells)
* [Typical Workflows](#typical-workflows)
* [References](#references)
* [Release Notes](#release-notes)


# Overview
A shell integrates a device model, application or other technology with CloudShell. A shell consists of a data model that defines how the device and its properties are modeled in CloudShell, along with automation that enables interaction with the device via CloudShell.

### Firewall Shells
CloudShell's Firewall shells enable you to manage your Firewall device similar to your networking equipment but without connectivity. In CloudShell, a Firewall shell runs commands, such as Autoload, Load, and Save Configuration. 

### **FortiGate FortiOS Firewall Shell 2G**
**FortiGate FortiOS Firewall Shell 2G** provides you with connectivity and management capabilities such as device structure discovery and power management for the **FortiGate**. 

For more information on the **FortiGate**, see the official **FortiNet** product documentation.

### Standard version
**FortiGate FortiOS Firewall Shell 2G 1.0.0** is based on the **Cloudshell Firewall Standard 3.0.1**.

For detailed information about the shell’s structure and attributes, see the **firewall_standard**.(https://github.com/QualiSystems/cloudshell-standards/blob/master/Documentation/firewall_standard.md) in GitHub.

### Supported OS
▪ **FortiOS**

### Requirements

Release: **FortiGate FortiOS Firewall Shell 2G**

* CloudShell version > 8.3

### Data Model

The shell's data model includes all shell metadata, families, and attributes.

#### **FortiGate Families and Models**

The FortiGate families and models are listed in the following table:

|Family|Model|Description|
|:---|:---|:---|
|CS_Firewall|FortiGate FortiOS Firewall Shell 2G|Generic FortiGate FortiOS Firewall Shell 2G|
|CS_Chassis|Generic Chassis|Default Firewall chassis|
|CS_Port|Generic Port|Interface|
|CS_Port_Channel|Generic Port Channel|Group of interfaces|
|CS_Power_Port|Generic Power Port|Power Supply module|

#### **FortiGate Attributes**

The attribute names and types are listed in the following table:

|Attribute|Type|Default value|Description|
|:---|:---|:---|:---|
|User|String| |Username for CLI (should be privileged user)|
|Password|Password| |Password for CLI|
|Enable Password|Password| |Enable password for CLI|
|Session Concurrency Limit|Numeric|1|Number of sessions that can be opened to the device. Defines the number of commands that can run concurrently|
|System Name|String| |Device hostname|
|Contact Name|String| |Device contact name|
|OS Version|String| |Operation system version|
|Vendor|String| |Device manufacturer|
|Location|String| |Device Location|
|Model|String| |The device model. This information is typically used for abstract resource filtering|
|Enable SNMP|Boolean|True|If set to True and SNMP isn’t enabled yet in the device the Shell will automatically enable SNMP in the device when Autoload command is called, using the SNMP Write or Read Community value. If Value is empty, relevant error will be raised. SNMP must be enabled on the device for the Autoload command to run successfully.|
|Disable SNMP|Boolean|False|If set to True SNMP will be disabled automatically by the Shell after the Autoload command execution is completed.|
|SNMP Read Community|Password| |Read Only SNMP community, used for Autoload functionality|
|SNMP Write Community|Password| |Read Write SNMP community|
|SNMP V3 User|String| |Snmp version 3 user name
|SNMP V3 Password|Password| |SNMP version 3 password|
|SNMP V3 Private Key|String| |SNMP version 3 private key|
|SNMP Version|String|v2c|Specifies version of SNMP, Autoload will use to load attributes|
|Console Server IP Address|String| |Shell allows to connect to the device through Console server. IP Address of Console server|
|Console User|String| |User name for the Console server|
|Console Password|Password| |Password for Console server|
|Console Port|Numeric| |Port for the Console server|
|CLI Connection Type|Lookup|Auto|The protocol which the Shell will use to connect to the Device. Available methods: Auto, Console, SSH, Telnet, TCP|
|CLI TCP Port|Numeric| |TCP Port to user for CLI connection. If kept empty a default CLI port will be used based on the chosen protocol, for example Telnet will use port 23.|
|Power Management|Boolean|False|Used by the power management service|
|Backup Type|String|File System|Supported protocols for saving and restoring of configuration and firmware files. Possible values are "File System", "FTP" and "TFTP".|
|Backup Location|String| |Default Location, where files will be saved by Save method|
|Backup User|String| |Username for the storage server used for saving and restoring of configuration and firmware files.|
|Backup Password|Password| |Password for the storage server used for saving and restoring of configuration and firmware files.|
|VRF Management Name|String| |The default VRF Management to use if configured in the network and no such input was passed to the Save, Restore or Load Firmware commands|
|Model|String| |Element model (Module or Chassis, etc.)|
|Serial Number|String| |Element serial number (Module or Chassis, etc.)|
|Version|String| |Element version (Module or Chassis, etc.)|
|Mac Address|String| |Interface mac address|
|L2 Protocol Type|String| |Interface protocol type|
|IPv4 Address|String| |Interface IPv4 address|
|IPv6 Address|String| |Interface IPv6 address|
|Port Description|String| |Interface description|
|Bandwidth|Numeric|0|Interface speed|
|MTU|Numeric|0|Interface mtu|
|Duplex|Lookup|Half|Interface duplex (half or full)|
|Adjacent|String| |If lldp is enabled on port, Adjacent shows connected device name and interface|
|Protocol Type|Lookup|Transparent|Attribute for internal usage|
|Auto Negotiation|Boolean|False|Shows if Auto negotiation is enabled on the interface|
|Associated Ports|String| |Interfaces added to certain Port-channel|

### Automation
This section describes the automation (drivers) associated with the data model. The shell’s driver is provided as part of the shell package. There are two types of automation processes, Autoload and Resource. Autoload is executed when creating the resource in the Inventory dashboard, while resource commands are run in the Sandbox, providing that the resource has been discovered and is online.

|Command|Description|
|:-----|:-----|
|Autoload|Discovers the device, it's hierarchy and attributes|
|Send Custom Command|Sends command to the device, and prints output. All commands will be executed in the enable mode, However it will not allow to enter configuration mode.|
|Send Custom Config Command|Sends command to the device in configuration mode, and prints output. All commands will be executed in the enable mode, accessible only via the API.|
|Load Firmware|Uploads and updates firmware|
|Save|Backs up running or startup configuration of the device|
|Restore|Restores running or startup configurations from file|
	
# Downloading the Shell
The **FortiGate FortiOS Firewall Shell 2G** is available from the [Quali Community Integrations](https://community.quali.com/integrations) page. 

Download the files into a temporary location on your local machine. 

The shell comprises:

|File name|Description|
|:---|:---|
|FortiGateFortiOSFirewallShell2G.zip|FortiGate shell package|
|cloudshell-firewall-fortinet-fortios-shell-2g-dependencies-package-1.0.0.zip|Shell Python dependencies (for offline deployments only)|

# Importing and Configuring the Shell
This section describes how to import the **FortiGate FortiOS Firewall Shell 2G 1.0.0** and configure and modify the shell’s devices.

### Importing the shell into CloudShell

**To import the shell into CloudShell:**
  1. Make sure you have the shell’s zip package. If not, download the shell from the [Quali Community's Integrations](https://community.quali.com/integrations) page.
  
  2. In CloudShell Portal, as Global administrator, open the **Manage – Shells** page.
  
  3. Click **Import**.
  
  4. In the dialog box, navigate to the shell's zip package, select it and click **Open**.

The shell is displayed in the **Shells** page and can be used by domain administrators in all CloudShell domains to create new inventory resources, as explained in [Adding Inventory Resources](http://help.quali.com/Online%20Help/9.0/Portal/Content/CSP/INVN/Add-Rsrc-Tmplt.htm?Highlight=adding%20inventory%20resources). 

### Offline installation of a shell

**Note:** Offline installation instructions are relevant only if CloudShell Execution Server has no access to PyPi. You can skip this section if your execution server has access to PyPi. For additional information, see the online help topic on offline dependencies.

In offline mode, import the shell into CloudShell and place any dependencies in the appropriate dependencies folder. The dependencies folder may differ, depending on the CloudShell version you are using:

* For CloudShell version 8.3 and above, see [Adding Shell and script packages to the local PyPi Server repository](#adding-shell-and-script-packages-to-the-local-pypi-server-repository).

* For CloudShell version 8.2, perform the appropriate procedure: [Adding Shell and script packages to the local PyPi Server repository](#adding-shell-and-script-packages-to-the-local-pypi-server-repository) or [Setting the python pythonOfflineRepositoryPath configuration key](#setting-the-python-pythonofflinerepositorypath-configuration-key).

* For CloudShell versions prior to 8.2, see [Setting the python pythonOfflineRepositoryPath configuration key](#setting-the-python-pythonofflinerepositorypath-configuration-key).

### Adding shell and script packages to the local PyPi Server repository
If your Quali Server and/or execution servers work offline, you will need to copy all required Python packages, including the out-of-the-box ones, to the PyPi Server's repository on the Quali Server computer (by default *C:\Program Files (x86)\QualiSystems\CloudShell\Server\Config\Pypi Server Repository*).

For more information, see [Configuring CloudShell to Execute Python Commands in Offline Mode](http://help.quali.com/Online%20Help/9.0/Portal/Content/Admn/Cnfgr-Pyth-Env-Wrk-Offln.htm?Highlight=Configuring%20CloudShell%20to%20Execute%20Python%20Commands%20in%20Offline%20Mode).

**To add Python packages to the local PyPi Server repository:**
  1. If you haven't created and configured the local PyPi Server repository to work with the execution server, perform the steps in [Add Python packages to the local PyPi Server repository (offlinemode)](http://help.quali.com/Online%20Help/9.0/Portal/Content/Admn/Cnfgr-Pyth-Env-Wrk-Offln.htm?Highlight=offline%20dependencies#Add). 
  2. For each shell or script you add into CloudShell, do one of the following (from an online computer):
      * Connect to the Internet and download each dependency specified in the *requirements.txt* file with the following command: 
`pip download -r requirements.txt`. 
     The shell or script's requirements are downloaded as zip files.

      * In the [Quali Community's Integrations](https://community.quali.com/integrations) page, locate the shell and click the shell's **Download** link. In the page that is displayed, from the Downloads area, extract the dependencies package zip file.

3. Place these zip files in the local PyPi Server repository.
 
### Setting the python PythonOfflineRepositoryPath configuration key
Before PyPi Server was introduced as CloudShell’s python package management mechanism, the `PythonOfflineRepositoryPath` key was used to set the default offline package repository on the Quali Server machine, and could be used on specific Execution Server machines to set a different folder. 

**To set the offline python repository:**
1. Download the *cloudshell-firewall-fortinet-fortios-shell-2g-dependencies-package-1.0.0.zip* file, see [Downloading the Shell](#downloading-the-shell).

2. Unzip it to a local repository. Make sure the execution server has access to this folder. 

3.  On the Quali Server machine, in the *~\CloudShell\Server\customer.config* file, add the following key to specify the path to the default python package folder (for all Execution Servers):  
	`<add key="PythonOfflineRepositoryPath" value="repository 
full path"/>`

4. If you want to override the default folder for a specific Execution Server, on the Execution Server machine, in the *~TestShell\Execution Server\customer.config* file, add the following key:  
	`<add key="PythonOfflineRepositoryPath" value="repository 
full path"/>`

5. Restart the Execution Server.
 
### Configuring a new resource
This section explains how to create a new resource from the shell.

In CloudShell, the component that models the device is called a resource. It is based on the shell that models the device and allows the CloudShell user and API to remotely control the device from CloudShell.

You can also modify existing resources, see [Managing Resources in the Inventory](https://github.com/QualiSystems/cloudshell-shells-documentaion-templates/blob/master/create_a_resource_device.png).

**To create a resource for the device:**
  1. In the CloudShell Portal, in the **Inventory** dashboard, click **Add New**. 
     ![](https://github.com/stsuberi/SaraTest/blob/master/create_a_resource_device.png)
     
  2. From the list, select **FortiGateFortiOSFirewallShell2G**.
  
  3. Enter the **Name** and **IP address** of the **FortiGate** (if applicable).
  
  4. Click **Create**.
  
  5. In the **Resource** dialog box, enter the device's settings, see [Device Name Attributes](*device-name-attributes).
  
  6. Click **Continue**.

CloudShell validates the device’s settings and updates the new resource with the device’s structure (if the device has a structure).

# Updating Python Dependencies for Shells
This section explains how to update your Python dependencies folder. This is required when you upgrade a shell that uses new/updated dependencies. It applies to both online and offline dependencies.

### Updating offline Python dependencies
**To update offline Python dependencies:**
1. Download the latest Python dependencies package zip file locally.

2. Extract the zip file to the suitable offline package folder(s).

3. Restart any execution server that has a live instance of the relevant driver or script. This requires running the Execution Server's configuration wizard, as explained in the [Configure the Execution Server](http://help.quali.com/doc/9.0/CS-Install/content/ig/configure%20cloudshell%20products/cfg-ts-exec-srver.htm?Highlight=configure%20the%20execution%20server) topic of the CloudShell Suite Installation guide. 

### Updating online Python dependencies
In online mode, the execution server automatically downloads and extracts the appropriate dependencies file to the online Python dependencies repository every time a new instance of the driver or script is created.

**To update online Python dependencies:**
* If there is a live instance of the shell's driver or script, restart the execution server, as explained above. If an instance does not exist, the execution server will download the Python dependencies the next time a command of the driver or script runs.

# Typical Workflows 
(edit as necessary depending on the shell)

**Workflow 1 - _Save configuration_** 
1. In CloudShell Portal, add the device resource to an active sandbox.

2. Run the **Save** command on the device with the following inputs:
    * **Folder Path**: For example, *tftp://ipaddress/shared folder* 
    * **Configuration Type**: **Running** or **Startup**

The configuration is saved to a file named *<ResourceName><startup/running-config>-<timestamp>*, which will reside in the folder path you entered.    

**Workflow 2 - _Restore Configuration_**
1. In CloudShell Portal, reserve the device resource.

2. Run the **Restore** resource command.

3. Enter the following parameters:
    * **Path** (mandatory): Enter the full path of the configuration file. 
    * **Restore Method** (optional): **Append** or **Override**. If you do not enter any value in this field, the **Append** method will be used. 
    * **Configuration Type** (mandatory): **Startup** or **Running**. 
	
**Workflow 3 - _Load firmware_**
1. In CloudShell Portal, reserve the device resource.

2. Run the **Load Firmware** resource command.

3. Enter the following parameters:
    * **Path** (mandatory): Enter the full path of the firmware file on the remote host. For example, *tftp://10.1.1.1/PanOS_200-5.0.5*. 

**Workflow 4 - _Send custom command_**
1. In CloudShell Portal, reserve the device resource.

2. Run the **Send custom command** resource command.

3. Enter the following parameters:
    * **Command** (mandatory): Enter the command you want to run

# References
To download and share integrations, see [Quali Community's Integrations](https://community.quali.com/integrations). 

For instructional training and documentation, see [Quali University](https://www.quali.com/university/).

To suggest an idea for the product, see [Quali's Idea box](https://community.quali.com/ideabox). 

To connect with Quali users and experts from around the world, ask questions and discuss issues, see [Quali's Community forums](https://community.quali.com/forums). 

# Release Notes 

### Known Issues
* Firewall standard doesn't support SNMP v3 Authentication and Privacy Protocols
