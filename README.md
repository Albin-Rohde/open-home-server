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
