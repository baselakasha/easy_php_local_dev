# Set up an easy-to-use development environment for PHP using docker. 🐘

> PHP version: 5.6
>
> MYSQL version: 5.7
>
> Webserver: Apache

## Install Docker 🐳
You need to install docker-desktop. It is available on most operating systems. If you use windows then you may need to enable WSL or hyper-v. 
Download link: https://www.docker.com/products/docker-desktop/. 

Docker is a containerization tool (kind of very small VMs) that allows you to run many different small VMs on your machine. You can read more about docker if you want to learn or just follow this tutorial to set up a local development environment for now.

## Check that you have docker installed
After you have installed docker:
you can check if docker is running by running the following command in your terminal:
```bash
docker ps
```
Also check that you have docker-compose installed by running:
```bash
docker-compose --version
```

If they execute successfully then you are good to go.

## Setup your project 🏗️
1- Clone this repo or download it in a folder.

2- Then move your code which has the PHP files to the 'code' folder.

## SQL connection 🔗
This docker-compose file is configured to have a MySQL server inside it. You should update your PHP code to use the following:
> Host Name: database
> 
> Port: 3306
>
> Database: database
> 
> User: user
> 
> Password: password

You can change these by editing the docker-compose.yml file.

If you want to connect to the database from outside the PHP container you can use localhost as a hostname with the same port. 



## Run the project 🏃
1- Open your terminal and change directories to the folder where you have the docker-compose.yml file.

2- Run the following command:

```bash
docker-compose up
```
The first time you run this command it will download the needed images. It may take some time depending on your internet connection.

3- Open your browser and go to http://localhost:8000. You should see your website as long as everything is configured correctly.

To stop the project, press ctrl+c in the terminal. You can also quit docker desktop as it may consume your pc resources.

## Notes about MySQL
- When you do 'docker-compose up'. MySQL takes 5-10 seconds to fully load. so wait for some time before you visit your website
- The data is stored in the 'data' folder in the same directory.

## General Notes
- If your project has a different environment in production, then you are risking compatibility issues. So make sure to test your code in the same environment as production.
- When you move to a different environment, you will have to replicate your database manually or by writing an SQL script. Moving the data folder without using this docker configuration will not move the data unless you have the same MySQL version and access to the MySQL server config.
- This should also work on ARM (Raspberry Pi and Mac M1, M2, etc.) 
