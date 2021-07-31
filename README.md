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
- Dynamic geogrphic map showing location of PfSense instances, and IPSec tunnels between them
- Email reporting of log entries flagged by machine learning algorithm 
  
## Setup Instructions
After running the Docker Compose script the next step is to complete the configuration of the underlying MySQL database
  
#### MySQL Database Configuration
1. Connect to the MySQL database setup by the docker-compose script on your docker host. This can be done using your docker hosts IP address, the username and password
"dashdbclient" & "pfsense" and a MySQL client application such as MySQL Workbench (https://dev.mysql.com/downloads/workbench/)
