# open-home-server

### Homeassistant
After deploying homeassistant go to localhost(or server ip):8123 where you'll be met 
with the installation process. You will be asked about location 
(for timezone sun-up/-down automations).

#### mqtt
Next up mqtt for homeassistant there is a somewhat nice guide [here](https://www.homeautomationguy.io/blog/docker-tips/configuring-the-mosquitto-mqtt-docker-container-for-use-with-home-assistant)
the guide sets up mqtt from portainer, in this repo, we'll do it in docker-compose but 
the connection and general process is the same. Worth mentioning is that they set a 
password for mqtt in the guide. Something you absolutely could do, i did not find an 
easy way to this without getting a shell on the container and doing it manually. So it
will not be a part of the compose file. I would regardless put firewall rules to only 
allow 80, 443 and ssh from within lan subnet. So the password wont be critical anyhow.

#### Nodered
Adding nodered to the project and starting it is quiet straight forward. However, 
connecting it to ha takes a few steps i found a usefull guide [here](https://sequr.be/blog/2022/09/home-assistant-container-part-5-node-red/).
The guide describes setting up "panel_iframe". Something i tried but didnt find that 
useful. Node-red flows tend to take up some screen space, i did not see the point in 
showing it iframed within ha.

Don't forget to create the node-red directory before starting the container for the
first time, since docker won't be able to mapp the volume, it'll throw an error.

#### HACS
HACS is an open source third party plugin to ha, it will make it possible to listen for
events from devices set-up from within ha, in node-red. Personally i found it to be the
easiest and smoothest way to control iot devices with node-red. It requires a few steps
to get working but their [github](https://github.com/zachowj/hass-node-red) has excellent 
instructions.
