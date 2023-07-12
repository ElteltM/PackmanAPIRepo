## PackmanAPI

**Website to scrap data from online stores and provide them in one place.**

Scraping scripts is in crawler folder using python and silenium library.

Backend API is written using NodeJs and Python.
---

Download [NodeJs Version 18](https://nodejs.org/en/).

Install [MongoDB](https://www.mongodb.com/try/download/community)

To run crawler : install python 3.11 and libraries in **requirements.txt**

Chrome and chromedriver are required to run crawler, chromedriver exists in controllers/fetching/ .

or download it  [here](https://sites.google.com/a/chromium.org/chromedriver/downloads) .
---

### **Commands to set up environment on Linux**

#you can set it up manually.. Dockerfile might be added later.

**#modify commands and yum to apt-get or for any other package managers or Os.**

`sudo yum update -y`

#Set up mongodb on your machine and make sure to start mongo service and enable mongo on boot.

#Start Mongo Service

`sudo service mongod start`

#enable mongodb on boot

`sudo chkconfig mongod on`


Install python and pip

`sudo yum install python37`

`curl -O https://bootstrap.pypa.io/get-pip.py`

`python3 get-pip.py --user`

#add path to env
`export PATH='LOCAL_PATH':$PATH`

#libraries

`python3 -m pip install urllib3==1.26`

`python3 -m pip install selenium==4.9.1 webdriver-manager==3.8.5`

**OR**
`pip install urllib3==1.26`

`pip install selenium==4.9.1 webdriver-manager==3.8.5`

Install chrome and chromedriver

`wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm`

`sudo yum localinstall google-chrome-stable_current_x86_64.rpm -y`

#check chrome version **chrome version MUST be compatible with chromedriver**

`google-chrome-stable --version`

#required lib
`sudo yum install libxcb`

`sudo yum install -y unzip`

`wget https://chromedriver.storage.googleapis.com/113.0.5672.63/chromedriver_linux64.zip`

`unzip chromedriver_linux64.zip`

#Set executable permissions

`sudo chmod +x chromedriver`

#Move ChromeDriver to /usr/local/bin

`sudo mv chromedriver /usr/local/bin/`

#set up env path

`export PATH=$PATH:'/path/to/chromedriver'`

`export LD_LIBRARY_PATH='/path/to/lib':$LD_LIBRARY_PATH`

#set up NodeJs

`curl -sL https://rpm.nodesource.com/setup_18.x | sudo bash -`

`sudo yum install -y nodejs`

#this commands should be executed in the rooot directory of the project

`npm install`

**AND**

`npm install expressjs mongoose`

#API runs on port 8000, create redirect from port 80 to 8000 AND set up iptables so it's working everytime server reboots:

`sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-ports 8000`

#to run server (or use whatever server manager/docker commands to run node)

`node server.js`

