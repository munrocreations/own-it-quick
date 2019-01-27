#  Administer and Use **ownCloud**<br>(A Quick Start Guide) #

With ownCloud, you can access your data where you are and know that is on a highly secure platform. This product runs on standard databases and web servers plus reliable enterprise operating systems such as Red Hat Enterprise Linux. Administering and using **ownCloud** may seem complex at first, but over 25 million users succeed in working with this open source content collaboration platform. 

## Get Started ##  
To streamline your use of this product, the ***Quick Start Guide***  answers questions for two audiences:  

- **Administrators** -- See the <a href="#admin">Administrator Setup</a> section so you can make **ownCloud** available to users.  
- **Users** -- See the <a href="#user">User Access</a> section to connect to **ownCloud** from a desktop system or mobile device .  
> **Note**: For optimal use of this guide on a smart phone, turn the phone horizontally (landscape mode).

## Find More Help ##
You can find full details on working with **ownCloud** in the [OwnCloud documentation](https://owncloud.org/help/). Look for this documentation icon.  
![documentation](Graphics\docs.JPG)

<h2 id="admin">Administrator Setup</h2>

To make **ownCloud** available to users, you perform these procedures:
- <a href="#install">Install</a> an ownCloud server.  
- <a href="#connect">Enable Users to Connect</a> to the ownCloud server.  
- <a href="#account">Add User Accounts</a>.  

<h3 id="install">Install an ownCloud Server</h3>

If you are comfortable using docker, consider installing the docker version of the ownCloud Server. This version is the fastest installation option. You may want to install it in a test environment to verify that it fits your organizational needs.  

The docker image has a data volume in the host filesystem and separate MariaDB and Redis containers. This configuration allows for HTTP connections by exposing port 8080. It also provides persistent storage by mounting the data and MySQL data directories on the host.

#### Install ownCloud Locally ####
To begin the installation, first create a new project directory.

Then download docker-compose.yml from the [ownCloud Docker GitHub repository](https://hub.docker.com/r/owncloud/server/) and store in your new directory.  
![docker](Graphics\docker-image.jpg)

Next, create an ENV configuration file and assign values to the following settings.  
![settings](Graphics\settings.jpg)

After assigning these values can start the container at the Docker command-line. This sequence shows how to start the container using [Docker Compose](https://hub.docker.com/r/owncloud/server/).  If you prefer, you can use [plain docker](https://github.com/owncloud-docker/server#launch-with-plain-docker).


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

When the process completes, verify that all containers started by running docker-compose ps. Look for output similar to this example to confirm success. 

![docker](Graphics\docker-out.jpg)

In this example, notice that in lines one and three show the database, ownCloud, and Redis containers are running. Also, the sedond line shows that ownCloud can be accessed by port 8080 on your local system.

For more detail, see [this topic](https://doc.owncloud.org/server/10.0/admin_manual/installation/docker/index.html?highlight=docker) in the ownCloud documentation.

The final step is run the following command:  
    docker-compose logs --follow owncloud 
If see many messages being logged to the console, please wait until the messages slow down. Then you can log into the ownCloud UI to verify a successful installation.
#### Log into the ownCloud UI  ####
To log in to the ownCloud UI, open http://localhost in a web browser of choice. See the following example. Enter admin username and password that you stored in ENV file.  
![ui](Graphics\ui.jpg)

<h3 id="connect">Enable Users to Connect to the ownCloud Server</h3>  
Enable users to connect to the Owncloud server using the  server's IP address and port 8080


<h3 id="account">Add User Accounts</h3>  

For more detail, see [this topic](https://doc.owncloud.org/server/10.0/admin_manual/configuration/user/user_configuration.html#creating-a-new-user) in the ownCloud documentation.
.
<h2 id="user">ownCloud User Access</h2>  

<h3 id="desktop">Desktop</h3>
For more detail, see [this topic](https://doc.owncloud.org/desktop/2.5/introduction.html) in the ownCloud documentation.
<h3 id="desktop">Desktop</h3>
![mobile](Graphics\mobile-device.JPG)  

For more detail, see [this topic](https://owncloud.org/download/#owncloud-mobile-apps) in the ownCloud documentation.
# ownCloud Credits #
All references to ownCloud are either trademarks or registered trademarks of ownCloud GmbH. Also ownCloud images are copyright protected by ownCloud GmbH.