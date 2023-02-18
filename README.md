# Docker compose yaml file for my Homeassistant server. 
It is use to run mainly Home Assistant and required containers in my setup. 
- [Duplicati](https://www.duplicati.com)
- [ESPHome](https://esphome.io/index.html)
- [Grafana](https://grafana.com)
- [Homeassistant](https://www.home-assistant.io)
- [InfluxDB](https://www.influxdata.com)
- [Mariadb](https://mariadb.org)
- [Mosquitto](https://mosquitto.org)
- [Node-RED](https://nodered.org)
- [phpMyAdmin](https://www.phpmyadmin.net)
- [Portainer](https://www.portainer.io)
- [Tasmota](https://tasmota.github.io/docs/)
- [Zigbee2MQTT](https://www.zigbee2mqtt.io)

The server has grown to more than HA. The following services were added.
- [Barcode Budy](https://github.com/Forceu/barcodebuddy)
- [Freshrss](https://freshrss.org)
    The RSS to Text requires to give permisions to the cache folder. Run in the container terminal:
    ```bash
    chmod 777 -R /var/www/html/cache
    ```
- [Grocy](https://grocy.info)
- [Traggo](https://traggo.net)

The *"server"* is overkill and at the same time under setup. But, it is hardware that I had in hand. 
- CPU: AMD Ryzen 5 2400G  
- RAM: 16GB  
- Motherboard: Asrock Fatal1ty X370 Gaming K4  
- SSD: Sandisk 256 GB  
- HD: Seagate 1T

### Update 20230219
The Maria database throws the following errors:
```
[ERROR] Incorrect definition of table mysql.event: expected column 'definer' at position 3 to have type varchar(, found type char(141).

[ERROR] mariadbd: Event Scheduler: An error occurred when initializing system tables. Disabling the Event Scheduler.
```

to solve it run in batch:
```batch
mariadb-upgrade -u root -p
```
it requries the root pwd. 

