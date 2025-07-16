# ThreatHunting
A few configs for a threathunting server consisting Splunk, OpenCTI and etc.
This repository will be completed over time.

## Traefik
In order to use youor server properly, create a traefik on your server first to manage domain names and encryptions and ssl and other stuff.
I have managed all these with cloudflare and traefik.

## OpenCTI
OpenCTI uses Elasticsearch as a core service and it needs lots of RAM (minimum 16GB). also 8 cores of CPU or more.
you need to clone the repository and start the opencti service first. Edit the ```.env``` file with required values and with the guidence explained in the file itself.
Run this in the directory of ```docker-compose.yml``` file
```
git clone https://github.com/Exidilia/ThreatHunting.git
docker compose up -d
```
Now you have a threathunting service up and running.Next step is to start a splunk service.

## Splunk
You need lots of cpu cores (minimum 8 CPU cores) and a reasonable amount of RAM (4GB or more). Storage is also very important to consider for your usecase.
Also it's better to start it as a system service. But using docker is also an option.
After downloading splunk ```.deb``` file from anywhere (splunk itself or digiboy), run this command to install it:
```
sudo dpkg -i splunk_package_name.deb
```
Then run this command to start the service:
```
sudo /opt/splunk/bin/splunk start
```
follow these instructions to answer questions and complete Splunk installation:
[https://docs.splunk.com/Documentation/Splunk/9.4.2/SearchTutorial/StartSplunk](url)

## Splunk licence server
Read instructions in the [splunk-lic-server/README.md](url) 


Now you have also set Splunk and Splunk license server. In the next step, you need to connect these two in a way that splunk log data can be enriched with OpenCTI threat hunting data and knowledge.
You need a splunk openCTI plugin installation in splunk. To set that up, follow instructions in this link:
[https://splunkbase.splunk.com/app/7485](url)
