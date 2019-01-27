#  Administer and Use **ownCloud** (A Quick Start Guide) #

With ownCloud, you can access your data where you are and know that is on a highly secure platform. This product runs on standard databases and web servers plus reliable enterprise operating systems such as Red Hat Enterprise Linux. Administering and using **ownCloud** may seem complex at first, but over 25 million users succeed in working with this open source content collaboration platform. 

## Get Started ##  
To streamline your use of this product, the ***Quick Start Guide***  answers questions for two audiences:  

- **Administrators** -- See the <a href="#admin">Administrator Setup</a> section so you can make **ownCloud** available to users.  
- **Users** -- See the <a href="#user">ownCloud User Access</a> section to connect to **ownCloud** from a desktop system or mobile device .  
> **Note**: If you are reading this guide on a smart phone, you may choose to turn the phone horizontally for best viewing.

## Find More Help ##
You can find full details on working with **ownCloud** in the [OwnCloud documentation](https://owncloud.org/help/). Look for this documentation icon.  
![documentation](Graphics\docs.JPG)

<h2 id="admin">Administrator Setup</h2>

To make **ownCloud** available to users, you perform these procedures:
- <a href="#install">Install and Configure</a> an ownCloud server.  
- <a href="#connect">Enable Users to Connect</a> to the ownCloud server.  
- <a href="#account">Add User Accounts.</a>.  

<h3 id="install">Install and Configure an ownCloud Server</h3>

To quickly installation and configure the ownCloud Server, consider installing the docker version. The docker version provides the fastest installation option. You may want to install it initiallyi in a test environment to see if it fits the needs of your organization.  

Start by downloading the [ownCloud server image](https://hub.docker.com/r/owncloud/server/) to your local system.
![docker](Graphics\docker-image.jpg)

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

For more detail, see [this topic](https://doc.owncloud.org/server/10.0/admin_manual/installation/deployment_recommendations.htm) in the ownCloud documentation.

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