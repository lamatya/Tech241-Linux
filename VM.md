WEEK 4

AZURE AND VM MACHINE-Continuing

Commands to get the Sparta app running on VM machines.


 1. git clone https://github.com/jungjinggg/tech241_sparta_app.git:- Clones a Git repository with the specified URL.


 2. ls:- Lists the contents of the current directory.


 3. git clone https://github.com/jungjinggg/tech241_sparta_app.git Sparta_app:- Clones the Git repository into a directory named "Sparta_app."


 4. rm -r tech241_sparta_app -y:- Deletes the directory "tech241_sparta_app" and its contents forcefully (-r) without asking for confirmation (-y).


 5. rm -r tech241_sparta_app:- Deletes the directory "tech241_sparta_app" and its contents.


 6. rm -rf tech241_sparta_app/:- Deletes the directory "tech241_sparta_app" and its contents forcefully (-f) recursively (-r).


 7. nano provision.sh:- Opens the file "provision.sh" for editing using the nano text editor.


 8. curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -:- Downloads and executes a script that adds the Node.js package repository to the system.


 9. sudo apt install nodejs -y:- Installs Node.js on the system.


 10. sudo npm install pm2 -g:- Installs the pm2 process manager globally using npm (Node Package Manager).


 11. cd Sparta_app:-  Changes the current directory to "Sparta_app."


 12. cd app:- Changes the current directory to "app.


 13. npm install:- Lists the contents of the current directory.


 14. node app.js:- Executes the "app.js" file using the Node.js runtime.


 15. npm start:- Starts the Node.js application using the defined "start" script in the package.json file.


 16. ps:- Lists currently running processes.


 17. ps aux:- Lists detailed information about all running processes.


 18. kill -1 4516:- Sends the SIGHUP signal (1) to the process with ID 4516, indicating that it should reload its configuration or restart.


 19. kill 4516:- Sends the default signal (SIGTERM) to the process with ID 4516, requesting it to terminate gracefully.


 20. kill -9 4516:- Sends the SIGKILL signal (9) to the process with ID 4516, forcing it to terminate immediately.


 21. npm start:- Starts the Node.js application using the defined "start" script in the package.json file.


 22. Ctrl Z:- Suspends currently running process. The process is stopped but it remains running in the background


 23. Ctrl C:- It iterrupts the process and requests to terminate it. Stops a running process.



Requirements to run DB in VM

1. Linux VM- Ubuntu 18.04 LTS
2. Update & Upgrade
3. Install mongo db - Version 3.2.x (latest)
  a. Download key for the right version
  b. Source list- specify mongo db version
  c. Update and Uprade
  d. Install mongo db
4. Configure mongo db to accept connection from app VM
  a. Change bindIp
  b. Start mongo db
  c. Enable mongo db


Mongo DB Commands

    1.  ls:- Lists the contents of the current directory.

    2.  ls -a:-  Lists all files and directories, including hidden ones, in the current directory.

    3.  sudo apt update -y:- Updates the package lists for available software updates.

    4.  sudo apt upgrade -y:- Upgrades installed packages to their latest versions.

    5.  wget -qO - https://www.mongodb.org/static/pgp/server-3.2.asc | sudo apt-key add - :-  Downloads the MongoDB GPG key and adds it to the keyring.

    6. echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list:- Adds the MongoDB repository to the system's sources list.

    7.  sudo apt update -y:- Updates the package lists again to include the MongoDB repository.

    8.  sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20:- Installs specific versions of MongoDB packages.

    9.  sudo nano /etc/mongod.conf:- Opens the MongoDB configuration file "mongod.conf" for editing using the nano text editor and with superuser (sudo) privileges.

    10.  cat /etc/mongod.conf:- Displays the content of the MongoDB configuration file.

    11.  sudo systemctl status mongod:-  Checks the status of the MongoDB service.

    12.  sudo systemctl start mongod:- Starts the MongoDB service.

    13.  sudo systemctl status mongod:- Checks the status of the MongoDB service again.

    14.  sudo systemctl enable mongod:- Enables the MongoDB service to start on system boot.

     15.  sudo systemctl status mongod:- Checks the status of the MongoDB service once more.


To run the bash script to run the sparta app Task 1


#!/bin/bash

# update
 sudo apt update -y

# upgrade
sudo apt upgrade -y

# install nginx
sudo apt install nginx -y

# restart nginx
sudo systemctl restart nginx

# enable nginx - enable makes sure when your vm is restarted it boots up again the nginx will automatically start
sudo systemctl enable nginx   # enable nginx - will auto start or reboot

# start nginx
#sudo systemctl start nginx

# restart nginx
#sudo systemctl restart nginx

# install node.js (corect version)

curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt install node.js -y
sudo apt update -y
#sudo npm install -g pm2

# copying app folder to the Virtual Machine
git clone https://github.com/jungjinggg.tech241_sparta_app.git app2

# running Sparta test app
cd /app2/app
npm install -y

# to start the app
#pm2 start app.js --name "sparta app"
node app.js


Blocker- 

My VM was working but when I used the script it was showing error preventing me from running the app, I had to try few times changing my script to make it work. I will complete my Task 2 as soon as I get the Task 1 running. 