# Rack environment control
____________________________________
Introduction 
____________________________________
This project focuses on configuring and utilizing a Raspberry Pi 4 Compute Module for data 
acquisition and local server functionalities. The implementation includes setting up the operating 
system, establishing a local server, integrating Bluetooth communication, and developing a daemon 
process for continuous data collection. A web crawler was developed to fetch data from a specific IP 
address, store it in a MySQL database hosted on Apache2, and display it on a sample HTML webpage. 
____________________________________
Project Timeline and Key Milestones 
____________________________________
1. November 7, 2024 – Received the Raspberry Pi 4 Compute Module along with accessories for 
initial configuration. 
2. November 8, 2024 – Successfully powered on and verified the proper functioning of the 
board. 
3. November 14, 2024 – Installed the operating system (Ubuntu 24 LTS) onto an NVMe storage 
device integrated into the module. 
4. November 14, 2024 – Successfully set up and launched a local server using Apache2. 
5. November 17, 2024 – Developed a main script operating in daemon mode, along with a 
database and a website hosted on the local server. Implemented a function to retrieve 
temperature data from a specified IP address and store it in the database. 
6. November 26, 2024 – Added a configuration file allowing modification of connection settings 
without altering the source code. 
7. December 9, 2024 – Integrated Bluetooth support, refined configurations for data retrieval 
from a specific IP address. Further work required on decoding data from the Bluetooth 
thermometer. 
8. December 18, 2024 – Final commit. Prepared the program for laboratory testing and 
introduced new configuration options. Basic usage instructions were documented.
____________________________________
#default 

User manual 

Ubuntu: User:pass = fit:alice User:pass = root:1111 

Database http://localhost/phpmyadmin User:pass (privileges) = phpmyadmin:root (all privileges, non 
grant) User:pass (privileges) = root:1111 (all privileges + grant) User:pass (privileges) = fit:alice (~half 
privileges, account for editing suitable databases) 

config.ini explanation [source] section is required for setup the proper connection to the database. 
You can provide an user and password to the database, host name and database name 

[destination_ip] This section introduces the possibility of getting some data from specific IP address ( 
for example in local network ). In addition with section [temp_page] you can specify the parent 
element of html layout and id of child element. 

[interval] This section is slightly important. You can provide the maximul interval time (in days) the 
data in database is held. If yolu give e.g. number 1, one day data from actual time (if program is 
running) will be deleted. It calculates the interval within now and time in stored in database. 

Useful commands (Ubuntu) To on/off bluetooth: sudo rfkill toogle Bluetooth To restart/stop/start 
daemon: sudo systemctl restart/start/stop EnvironmentRackControl.service 
____________________________________
Conclusion 
____________________________________
This project successfully configured and implemented a Raspberry Pi 4 Compute Module for real
t
 ime data collection and local server hosting. The system enables efficient data acquisition through 
network and Bluetooth interfaces, ensuring flexibility and scalability for further enhancements. The 
integration of a web crawler allowed automated data retrieval and processing, making the system 
suitable for real-world applications involving continuous data monitoring and analysis.
