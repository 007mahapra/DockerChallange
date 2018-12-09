# DockerChallange
Install Latest Drupal using Docker with LAMP stack


# Step 1) Install Docker on Ubuntu 16.04 LTS 

Reference to install and execute can be found here  : https://docs.docker.com/install/linux/docker-ce/ubuntu/



# Step 2) Install docker composer

Reference : https://docs.docker.com/compose/install/#install-compose

1) Run this command to download the latest version of Docker Compose

sudo curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

2) Apply executable permissions to the binary:
sudo chmod +x /usr/local/bin/docker-compose


3) Test the docker-compose version
docker-compose --version

# Step 3) Once Docker-Compose is up and running write docker-compose.yml script to 

Choose version carefully : you may use following command to check your Docker and Docker-Compose versions

docker --version
Docker version 18.09.0, build 4d60db4

docker-compose  --version
docker-compose version 1.23.1, build b02f1306


I'm using 3.3 becuase mine is latest as per current date .


# Step 4) Build containers using docker-compose command


You may keep docker-compose.yml under your project directory , ideally you must create a user who must have sufficient permission to execute the docker-compose commands .

cd /home/salt/GoBearProject/docker-compose 
(your docker-compose.yml must be here or you can also provide any custom name just provide the path with -f option)

Execute docker-compose command to build the containers 

sudo docker-compose up -d --force-recreate

-d puts container running in background  

if you are running it for the first time use following command , this will display the ongoing operations and errors :

sudo docker-compose up 


Once the containers are built successfully , you can see container names as below :

Recreating php7.2_container    ... done
Recreating apache_container    ... done
Recreating mysql_5.7_container ... done
Recreating drupal_latest_container ... done


# Step 5) Cope paste http://localhost:8080/ in your browser on same machine/server to view Drupal default config page









