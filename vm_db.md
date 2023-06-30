### Database to run VM

**#!/bin/bash**

Step 1:

**sudo apt update -y**

Step 2:

**sudo apt upgrade -y**

Step 3:

**wget -qO - https://www.mongodb.org/static/pgp/server-3.2.asc | sudo apt-key add -**

Step 3:

**echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mong$sudo apt update -y**

Step4:

**sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20**

Step 5:

**sudo sed -i 's/bindIp: 127.0.0.1/bindIp: 0.0.0.0/g' /etc/mongod.conf**

Step 6:

**sudo systemctl start mongod**

Step 7:

**sudo systemctl enable mongod**


#!/bin/bash


App to VM

Step 1:

**sudo apt update -y**

Step 2:

**sudo apt upgrade -y**

Step 3:

**sudo apt install nginx -y**

Step 4:

**sudo systemctl enable nginx**

Step 5:

**sudo systemctl start nginx**

Step 6:

**sudo systemctl restart nginx**

Step 7:

**sudo systemctl enable nginx**

Step 8:

**curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -**

Step 9:

**export DB_HOST=mongodb://172.187.178.145:27017/posts**

Step 10:

**sudo apt install nodejs -y**

Step 11:

**sudo apt update -y**

Step 12:

**sudo npm install -g pm2**

Step 13:

**git clone https://github.com/jungjinggg/tech241_sparta_app app-github-automation**

Step 14:

**cd ~/app-github-automation/app**

Step 15:

**npm install -y**

Step 16:
**pm2 start app.js --name "sparta app"**