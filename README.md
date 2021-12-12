# elastic-workspace
Workspace for experimenting with ElasticSearch and ELK stack components

### Git config for temp git workspace
+ git config --global user.email "richardaskew@yahoo.com"
+ git config --global user.name "Richard Askew"

### Create EC2 Key Pair
+ aws ec2 create-key-pair --key-name MyKeyPair --query 'KeyMaterial' --output text > MyKeyPair.pem
+ chmod 400 MyKeyPair.pem

### Set some envs based on your AWS account
STACK_NAME=elastic-demo-host-1
VPC_ID=vpc-???
SUBNET_ID=subnet-???
KEY_PAIR=MyKeyPair

### Create Ubuntu 18 LTS EC2
+ aws cloudformation validate-template --template-body file://elastic-host.yml
+ aws cloudformation create-stack --template-body file://elastic-host.yml --stack-name ${STACK_NAME} --region us-east-1 --capabilities CAPABILITY_NAMED_IAM --parameters ParameterKey=KeyNameParameter,ParameterValue=${KEY_PAIR} ParameterKey=SubnetIdParameter,ParameterValue=${SUBNET_ID} ParameterKey=VpcIdParameter,ParameterValue=${VPC_ID}
+ aws cloudformation delete-stack --stack-name ${STACK_NAME} --region us-east-1

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
