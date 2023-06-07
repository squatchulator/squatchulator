---
description: Step-by-step guide to properly installing and configuring the ELK Stack
---

# Configuring the ELK Stack

Prerequisites:

**Virtual Machine**

* Ubuntu 22.04 LTS
* 4-8gb RAM
* 40gb Hard Drive
* Bridged Network Interface

**Windows Machine**

* Windows 10 22H2
* 8-16gb RAM
* 500gb-1tb Hard Drive

```
## Installing Elasticsearch
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
sudo apt install curl
echo "deb https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-8.x.list
sudo apt-get update && sudo apt-get install elasticsearch
sudo service elasticsearch start
sudo service elasticsearch status
sudo nano /etc/elasticsearch/elasticsearch.yml
** Edit 'Network' section **
- 'network.host: virtual_machine_ip'
- Uncomment 'http.port'
** Edit 'Discovery' section **
- discovery.seed_hosts: ["virtual_machine_ip"]
** Edit 'Begin Security Auto Configuration' section **
- Set 'xpack.security.enabled' to false
sudo systemctl restart elasticsearch
** On Windows PC **
- curl virtual_machine_ip:9200

## Installing Kibana
sudo apt install -y kibana
sudo nano /etc/kibana/kibana.yml
- Edit name of server.host if you want, would need to be IP address of virtual machine
- Edit 'elasticsearch.hosts: ["http://virtual_machine_ip:9200"]'

# Installing Auditbeat
sudo apt install -y auditbeat
sudo nano /etc/auditbeat/auditbeat.yml
- Edit 'hosts' under 'output.elasticsearch'
     - hosts: ["virtual_machine_ip:9200"]
sudo service start kibana
sudo service start elasticsearch
sudo auditbeat -e setup
```
