# Xray-core init.d Service for Keenetic

This repository contains an init.d script for managing the **xray-core** service on Keenetic devices. The script enables you to start, stop, restart, and check the status of the service.

## Prerequisites

- A Keenetic device with opkg package management.
- Command-line access.
- The **xray-core** package installed.

## Installation and Setup

1. **Update and Install xray-core**

   Run the following commands to update the package list, upgrade your system, and install **xray-core**:
   ```sh
   opkg update
   opkg upgrade
   opkg install xray-core
   ```

2. **Deploy the Script**

   Copy the provided init.d script to the proper directory:
   ```sh
   cp S51xray /opt/etc/init.d/S51xray
   ```

3. **Set Execution Permissions**

   Make the script executable:
   ```sh
   chmod +x /opt/etc/init.d/S51xray
   ```

4. **Configure the Service**

   Create the configuration directory if it doesn't exist:
   ```sh
   mkdir -p /opt/etc/xray
   ```
   
   Place your configuration file (`config.json`) in the directory:
   ```sh
   cp config.json /opt/etc/xray/config.json
   ```
   
   Set the proper permissions for the configuration file:
   ```sh
   chmod 644 /opt/etc/xray/config.json
   ```

## Available Service Commands

Manage the **xray-core** service using the following commands:

- **Start the Service:**
  ```sh
  /opt/etc/init.d/S51xray start
  ```

- **Stop the Service:**
  ```sh
  /opt/etc/init.d/S51xray stop
  ```

- **Restart the Service:**
  ```sh
  /opt/etc/init.d/S51xray restart
  ```

- **Check Service Status:**
  ```sh
  /opt/etc/init.d/S51xray status
  ```

## Log Files

The service logs are recorded in:
```
/opt/var/log/xray.log
```
Use this log file for monitoring and troubleshooting.

## Notes

- **Path Verification:** Ensure the paths to the xray binary, configuration file, and log directory are correct for your system. Adjust the script as necessary.
- **Brief Disruption:** A restart may cause a short interruption in connectivity—plan accordingly.
