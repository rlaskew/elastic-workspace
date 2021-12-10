# elastic-workspace
Workspace for experimenting with ElasticSearch and ELK stack components


### Create EC2 Key Pair
aws ec2 create-key-pair --key-name MyKeyPair --query 'KeyMaterial' --output text > MyKeyPair.pem

### Create Ubuntu 18 LTS EC2
TODO

### Installation Guide URL
https://www.elastic.co/guide/en/elasticsearch/reference/current/deb.html

### Installation Steps
+ wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
+ sudo apt-get install apt-transport-https
+ echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-7.x.list
+ sudo apt-get update && sudo apt-get install elasticsearch
+ sudo /bin/systemctl daemon-reload 
+ sudo /bin/systemctl enable elasticsearch.service
+ sudo /bin/systemctl start elasticsearch.service
+ curl http://localhost:9200
