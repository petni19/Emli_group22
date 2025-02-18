# Emli_group22
The project was done by Benjamin Longet, Peter Nielsen and Thor Opstrup.

# Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Usage](#usage)

## Introduction <a name="introduction"></a>
This Git repository was created as a part of the Embedded Linux course at University of Southern Denmark. The purpose of the project was to create an Embedded Plant Watering System, consisting of a Raspberry Pi, Raspberry Pico and an ESP8266. The project definition with Functional- and Nonfunctional requirements can be found in the [Requirements.pdf](emli_2023_project_info_v2-1.pdf).

## Features <a name="features"></a>
A list with describtion the main folders of the project, with a short description of the functionality of each folder can be read here.
Normally each folder would have it own read me, but it has been written on the main page, so everything the different folders include can be read here down in usage. 

| File Path        | Functionality                                 |
| ---------------- | --------------------------------------------- |
| `health_monitor`  | The folder includes the bash scripts for monitoring the health status of our Raspberry Pi     |
| `html` | The folder includes the php, html, .log, and .csv files in the project for our webserver.  |
| `log` | The folder includes different .csv files used for logging|
| `log_backup`  | The folder includes backup of the data used for logging the visible tests in the report.     |
| `plants` | The folder used to save informations for multiple plants. Only 1 file right now, as we only have one plant |
| `scripts`  |  The folder includes the bash scripts for all the message topics.      |


## Usages <a name=usage></a>
A short descripton of each file in each path. 

### health_monitor
- cpu_load.sh: Bash script, cpu load
- cpu_temp.sh: Bash script, cpu temperature
- disk_space: Bash script, disk space
- log_to_csv.sh: Bash script that executesd the other bash scripts and save them in a .csv
- network_traffic.sh: Bash script, network traffic
- ram_usage.sh: Bash script, ram usage
- system_info.csv: log file

### html
- all1.csv: CSV file hard linked to the csv file in log.
- chart.js: Javascript for showing the graph ofline.
- Fail2ban.log: Hard link to the log file for fail2ban.
- graphv2.php: Graph of sensors and alarm with download bottom.
- index.html: Welcome page.
- login.php: Safety side with password to see the log for fail2ban.
- plot2_csv.php: Shows the RPI healt moniting data.
- plot_pump.php: Shows when the pump was activated in graph form.
- pump1.csv: CSV file hard linked to the csv file in lag.
- system_info.csv CSV file hard linked to the health monitoring log
- uptime.php: Shows the uptime linux command

### log
- all1.csv: CSV file with id for logging timestamp, ambient light, moisture, pump and water alarm for one plant.
- ambient_light_topic1.csv: Log file.
- moisture_topic1.csv: Log file.
- plant_alarm_topic1.csv: Log file.
- water_alarm_topic1.csv: Log file.
- pump1.csv: Logfile with timestampt for when the pump is used.
- time1.csv: Logfile of the timestamp. 

### log_backup
Same as above.

### plants
- plant1: Unique IP and id for the only plant active

### scripts
- btn_press.sh: Publisher node for bottom press.
- check_last_pump.sh: Publisher node for logging when the pump is activate.
- generate_colected_log.sh: Uses the for message topics for sensors and time, and generates a .csv file
- kill_ros_nodes.sh: Iterate through the list and unsubscripe or stop pubslishing on each topic
- log_sensor.sh: Subscriper node that logs the different topics publishing to each own .csv file
- plant_node.sh: Reads data from UART and publish it on 4 different message topics for the 2 alarms and two sensors with an ID attached for the possibility of multiple plants.
- pump_controller.sh: Subscriber node, that sends signal to the Pico to water the plant, whenever appropriate to the functional requirements.
- remote_node.sh: Subscriper node led control on ESP8266
- show_data.sh: Subscriper node for debugging tool to show the data of the different topics.
