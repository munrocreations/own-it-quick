# How to Manage and Use **ownCloud** #

Administering and use **ownCloud** may seem complex at first, but over 25 million users succeed in working with this open source content collaboration platform. You can access your data where you are and know that is on a highly secure platform. This product runs on standard databases, web servers, and enterprise operating systems such as Red Hat Enterprise Linux. 

## Get Started ##  
To get going quickly, see the topics in this ***Quick Start Guide***.  This guide answers these questions for two audiences:  

- For administrators, see the <a href="#admin">Initial Setup</a> section so you can make **ownCloud** available to users.  
- For users, see the <a href="#user">ownCloud Access</a> section to connect to **ownCloud** from a desktop system or mobile device .  
> **Note**: If you are reading this guide on a smart phone, you may prefer to turn the phone to a horizontal position.

## Find More Help ##
You can find full details on working with **ownCloud** here: [https://owncloud.org/help/](https://owncloud.org/help/ "OwnCloud help"). Look for the documentation icon.  
![docs](Graphics\docs.JPG)

<h2 id="admin">Initial Setup</h2>

- install and configure an Owncloud server
- enable users to connect to the Owncloud server   
- add a user account
- 
<h2 id="install">Install and Configure</h2>

To streamline the installation process, consider installing the docker version.  This version provide the chance to experiment
A very simple method so you can experiment in a test environment.  Take advantage a complete image in one package.

Here is an example 

    # Create a new project directory
    mkdir owncloud-docker-server
    
    cd owncloud-docker-server
    
    # Copy docker-compose.yml from the GitHub repository
    wget https://raw.githubusercontent.com/owncloud-docker/server/master/docker-compose.yml
    
    # Create the environment configuration file
    cat << EOF > .env
    OWNCLOUD_VERSION=10.0
    OWNCLOUD_DOMAIN=localhost
    ADMIN_USERNAME=admin
    ADMIN_PASSWORD=admin
    HTTP_PORT=8080
    EOF
    
    # Build and start the container
    docker-compose up -d


<h2 id="user">ownCloud Access</h2>  
More info  ![mobile](Graphics\mobile-device.JPG)  
To gain access

<h3 id="desktop">Desktop</h3>
