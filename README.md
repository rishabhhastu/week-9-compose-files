# Using Docker-Compose to deploy a Nginx webserver communicating with a MongoDB Database engine using PHP
## Learning a basic 2-tier architecture of a webserver using a private db server to display results

### Description:

1. Automates the creation of a two tier topology consisting of a webserver and a database server in the backend.
2. Dynamic building of the images of webserver (Nginx) and DB server (MongoDB) 
3. Running the two images in different containers and inter-networking between them to display output


### Pre-requisites
1. Git Clone the repository into your local machine. 
```
git clone https://github.com/rishabhhastu/week-9-compose-files
```

2. Change the directory to riha4022
```
cd week-9-compose-files/riha4022/
```

3. Install docker-compose in your system. The below commands are for Linux OS. You can find the respective commands for your own flavor of OS
```
sudo curl -L https://github.com/docker/compose/releases/download/1.21.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
```

### USAGE:
Run the following commands after doing the pre-requisites.
```
sudo docker-compose build
sudo docker-compose up -d
```

##### To verify that the containers are running use the below command:
```
sudo docker-compose ps
```

### How to Access the webpage
Type the following in the URL:
```
127.0.0.1/cloudtech.php 
```

##### If you want to add a custom message in the Database try doing the following:
```
sudo sed -i -e 's/hello from db container/YOUR CUSTOM MESSAGE/' cloudtech_insert.php
```

Re-Build the images and run the images in conatiner using:  
```
sudo docker-compose build
sudo docker-compose up -d
```

Push the DB record inside the container:
```
127.0.0.1/cloudtech_insert.php 
```

See the changed output:
```
127.0.0.1/cloudtech.php 
```
