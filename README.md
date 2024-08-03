# PfSense_Dashboard
  
Included is the Docker-Compose installer for the PfSense Dashboard system. 
This system pulls in data from specified PfSense instances on your network providing, providing a central web-app dashboard with the following features:
- Machine Learning Analysis of all PfSense logs, determining abnormal or potential malicious network activity
- Automatic updating and consolidation of PfSense configuration and details
  - Interfaces
  - IP Addresses
  - Firewall Policies
  - IPSec Connections
  - Instance Users
- Monitoring of OpenVPN server activity
- Dynamic geographic map showing location of PfSense instances, and IPSec tunnels between them
- Email reporting of log entries flagged by machine learning algorithm 
  
## Setup Instructions
After running the Docker Compose script the data collection server will automatically configure the underlying MySQL database, however the frontend and reporting server will require some simple setup in order to be ready for operation.
  
  
### 1. Dashboard Frontend Configuration
  a. Restart the Dashboard Frontend container

  b. Navigate to the address for your Dashboard Frontend "http://<docker_host_ip>:8080" and log in with the default admin, admin credentials
  
  c. Use the "Add PfSense Instance" and "Dashboard User Manager" options to add your PfSense instances to the dashboard and setup users on the system
  
  d. Alter the "NOMINATIM_USER" ENV variable for Dashboard Frontend container to an appropriate email address to be affiliated to the systems Nominatim (https://wiki.openstreetmap.org/wiki/Nominatim) requests.

### 2. Reporting Server Configuration
  a. Replace the placeholder email in the "SEND_ADDRESS" ENV variable for the reporting server, with one that could be used by the reporting system
  
  b. Replace the placeholder password in the "SEND_PASSWORD" ENV variable for the reporting server, with the password for the new "SEND_ADDRESS"
  
  c. Replace the placeholder smtp address in the "SMTP_ADDRESS" ENV variable for the reporting server, to one relevant for your new "SEND_ADDRESS" email
  
  d. Replace the placeholder smtp port in the "SMTP_PORT" ENV variable for the reporting server, to one relevant for your new "SMTP_ADDRESS" entry

## Compatibility
All versions of PfSense 2.5.x Community Edition and PfSense 21.x and later are tested and supported, and although earlier 2.4.x versions of PfSense have been tested, compatibility has been found to be limited, due to widespread bugs and formatting issues with log entries in this version of PfSense, 
and the underlying BSD version it uses.
