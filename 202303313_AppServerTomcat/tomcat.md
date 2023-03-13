# Application Servers

#### What is Application Server?
    - An application server is a software framework that provides a platform for developing, deploying, and managing web applications.

    - It acts as an intermediary between the user's web browser and the database or other back-end systems that store and manage the data used by the application.

    - Application servers typically provide a variety of services and features that facilitate the development and deployment of web applications, including support for multiple programming languages, web services, messaging, and database connectivity. 

    - They also provide a range of administrative tools for managing and monitoring the application, such as security management, load balancing, and performance tuning.

    - Some examples of popular application servers include Apache Tomcat, JBoss, IBM WebSphere, Microsoft IIS, and Oracle WebLogic. These servers can be used to run a wide range of web-based applications, from simple web pages to complex enterprise applications.

#### Purpose Of Application Server?

    The primary purpose of an application server is to provide a platform for developing, deploying, and managing web applications. It acts as an intermediary between the user's web browser and the back-end systems that store and manage the data used by the application.

    Here are some specific purposes of an application server:

        1. Hosting and managing web applications: An application server provides a runtime environment for hosting and managing web applications. This includes handling user requests, managing sessions, and providing a variety of services such as database connectivity, web services, and messaging.

        2. Scalability and reliability: An application server provides tools and features for managing scalability and reliability of web applications. It can handle high volumes of traffic, distribute the load across multiple servers, and provide failover capabilities in case of hardware or software failures.

        3. Security: An application server provides a range of security features to protect web applications from attacks and ensure the integrity and confidentiality of data. This includes user authentication and authorization, data encryption, and protection against cross-site scripting (XSS) and other security vulnerabilities.

        4. Integration with enterprise systems: An application server provides integration with enterprise systems such as databases, messaging systems, and other back-end systems. This allows web applications to access and manipulate data stored in these systems and exchange data with other applications.

    Overall, the purpose of an application server is to provide a comprehensive platform for developing, deploying, and managing web applications, while ensuring scalability, reliability, security, and integration with enterprise systems.

#### Application Server Vendors ?

    There are many vendors that offer application server software. Here are some of the most popular ones:
    
        1. Apache Tomcat: Apache Tomcat is a widely-used open source application server that supports Java Servlet and JavaServer Pages (JSP) technologies.

        2. JBoss: JBoss is a popular open source application server that supports Java EE (Enterprise Edition) technologies. It is developed and maintained by Red Hat.

        3. IBM WebSphere: IBM WebSphere is a commercial application server that supports Java EE technologies. It is widely used in enterprise environments.

        4. Oracle WebLogic Server: Oracle WebLogic Server is a commercial application server that supports Java EE technologies. It is widely used in enterprise environments and is developed and maintained by Oracle.

        5. Microsoft IIS: Microsoft IIS (Internet Information Services) is a web server that also includes application server capabilities. It supports .NET technologies and is widely used in Windows-based environments.

        6. GlassFish: GlassFish is an open source application server that supports Java EE technologies. It is developed and maintained by the Eclipse Foundation.

        7. WildFly: WildFly is an open source application server that supports Java EE technologies. It is developed and maintained by Red Hat.

        8. Apache Geronimo: Apache Geronimo is an open source application server that supports Java EE technologies. It is developed and maintained by the Apache Software Foundation.

#### How Tomcat Works?

    Apache Tomcat is a popular open-source web server and servlet container that provides a runtime environment for Java-based web applications. Here is a brief overview of how Tomcat works:

        - Client sends a request: When a user accesses a web application hosted on Tomcat, their web browser sends a request to the Tomcat server.

        - Tomcat receives the request: The Tomcat server receives the request and processes it using the appropriate servlet container.

        - Servlet container processes the request: The servlet container processes the request and generates a response. This may involve running servlets, JavaServer Pages (JSP), or other components of the web application.

        - Tomcat sends the response: Once the servlet container has generated the response, Tomcat sends it back to the user's web browser.

        - Tomcat manages the application: Tomcat manages the web application by handling requests, managing sessions, and providing a range of services such as database connectivity, security, and clustering.

        - Tomcat can be customized: Tomcat can be customized using configuration files, deployment descriptors, and other tools to optimize performance, security, and other aspects of the web application.

    Overall, Tomcat provides a comprehensive platform for developing, deploying, and managing Java-based web applications. It provides a runtime environment for servlets and JSPs, as well as a range of features and services to support web application development and management.

### Use cases:
    Apache Tomcat is a popular open-source web server and servlet container that provides a flexible and scalable platform for hosting Java-based web applications. Here are some common use cases for Tomcat:

        1. Hosting Java web applications: Tomcat is commonly used for hosting Java-based web applications, including enterprise web applications, e-commerce sites, content management systems, and more.

        2. Development and testing: Tomcat can be used for local development and testing of web applications. Its lightweight architecture and ease of configuration make it a popular choice for developers.

        3. Load balancing: Tomcat can be used in conjunction with other web servers, such as Apache HTTP Server or Nginx, to provide load balancing and failover capabilities for web applications.

        4. High availability and clustering: Tomcat supports clustering and can be used to provide high availability and scalability for web applications in enterprise environments.

        5. Integration with enterprise systems: Tomcat can be integrated with various enterprise systems such as databases, messaging systems, and other back-end systems, making it a popular choice for building complex enterprise web applications.

        6. RESTful web services: Tomcat supports the development and deployment of RESTful web services, making it a popular choice for building and deploying web services.

        7. Servlet container: Tomcat can be used as a standalone servlet container for running servlets and JavaServer Pages (JSP) without the need for a full web server.

    Overall, Tomcat is a versatile and widely-used application server that provides a flexible and scalable platform for hosting and managing Java-based web applications.

# Hands-On:
    

#### Provision Linux i.e. Ubuntu:

```
# Canonical, Ubuntu, 22.04 LTS, amd64 jammy image build on 2023-02-08 | ami-0557a15b87f6559cf

$ aws ec2 run-instances \
--image-id "ami-0557a15b87f6559cf" \
--count 1 \
--instance-type t2.micro \
--key-name "us_east_1_keys" \
--security-group-ids "sg-09e7a75b97f33d7f1" \
--subnet-id "subnet-00a07bb8fefdfcfec" \
--tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=Tomcat},{Key=Environment,Value=dev}]'
```
#### Provision Linux i.e. CentOS/AmazonLinux2/Redhat:

```
# Amazon Linux 2 Kernel 5.10 AMI 2.0.20230221.0 x86_64 HVM gp2 | ami-006dcf34c09e50022

$ aws ec2 run-instances \
--image-id "ami-006dcf34c09e50022" \
--count 1 \
--instance-type t2.micro \
--key-name "us_east_1_keys" \
--security-group-ids "sg-09e7a75b97f33d7f1" \
--subnet-id "subnet-00a07bb8fefdfcfec" \
--tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=Tomcat},{Key=Environment,Value=dev}]'
```

#### Provision Windows:

```
# Microsoft Windows Server 2022 Full Locale English AMI provided by Amazon | ami-0c2b0d3fb02824d92

$ aws ec2 run-instances \
--image-id "ami-0c2b0d3fb02824d92" \
--count 1 \
--instance-type t2.micro \
--key-name "us_east_1_keys" \
--security-group-ids "sg-09e7a75b97f33d7f1" \
--subnet-id "subnet-00a07bb8fefdfcfec" \
--tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=Tomcat},{Key=Environment,Value=dev}]'
```

#### Download Install & Configure Documentation from Tomcat Official Website:

    Download Process: 
        
    Install Process:
        
    Configure Process:
        Windows: 

        Linux :

    Type Of Installation :
        Binary :

    STEP-1 : Go to Apache Tomcat :
        - Documentation
        - Downloads :
        - Hardware
        - Software : java
        - Process
    STEP-2 : Launch a Linux Machine

    STEP-3 : Utility Softwares : git curl wget unzip tree

    STEP-4 : Software : Java

    STEP-5 : Enable Tomcat Pages across Global

    STEP-6 : User, Password, Permissions

    STEP-7 : Access Tomcat & Deploy Java Application

#### Download, Install & Configure Tomcat on Linux Distributions:

    Here are the steps to download, install, and configure Tomcat on Linux Ubuntu using a shell script:

    1. Open a terminal window on your Ubuntu machine.

        Create a shell script file using the following command:

        $ vi tomcat-install.sh

    2. Paste the following code into the shell script file:

    ```
    # Debian/Ubutu
    #!/bin/bash

    # Setup Hostname
    sudo hostnamectl set-hostname "tomcat.cloudbinary.io"

    # Update the hostname part of Host File
    echo "`hostname -I | awk '{ print $1 }'` `hostname`" >> /etc/hosts

    # Update Ubuntu Repository
    sudo apt-get update

    # Download, & Install Utility Softwares
    sudo apt-get install git wget unzip curl tree -y

    # Download, Install Java 11
    sudo apt-get install openjdk-11-jdk -y

    # Backup the Environment File
    sudo cp -pvr /etc/environment "/etc/environment_$(date +%F_%R)"

    # Create Environment Variables
    echo "JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64/" >> /etc/environment

    # Go to /opt directory to download Apache Tomcat 
    cd /opt/

    # Download Apache Tomcat - Application
    sudo wget https://downloads.apache.org/tomcat/tomcat-8/v8.5.87/bin/apache-tomcat-8.5.87.tar.gz

    # Extract the Tomcat File
    sudo tar xvzf apache-tomcat-8.5.87.tar.gz

    # Rename the Tomcat Folder
    sudo mv apache-tomcat-8.5.87 tomcat

    # Go Inside the Tomcat Folder
    cd /opt/tomcat/

    # Take Tomcat Configuration as backup 
    sudo cp -pvr /opt/tomcat/conf/tomcat-users.xml "/opt/tomcat/conf/tomcat-users.xml_$(date +%F_%R)"

    # To delete last line and which contains </tomcat-users>
    sed -i '$d' /opt/tomcat/conf/tomcat-users.xml

    #Add User & Attach Roles to Tomcat 
    echo '<role rolename="manager-gui"/>'  >> /opt/tomcat/conf/tomcat-users.xml
    echo '<role rolename="manager-script"/>' >> /opt/tomcat/conf/tomcat-users.xml
    echo '<role rolename="manager-jmx"/>'    >> /opt/tomcat/conf/tomcat-users.xml
    echo '<role rolename="manager-status"/>' >> /opt/tomcat/conf/tomcat-users.xml
    echo '<role rolename="admin-gui"/>'     >> /opt/tomcat/conf/tomcat-users.xml
    echo '<role rolename="admin-script"/>' >> /opt/tomcat/conf/tomcat-users.xml
    echo '<user username="admin" password="redhat@123" roles="manager-gui,manager-script,manager-jmx,manager-status,admin-gui,admin-script"/>' >> /opt/tomcat/conf/tomcat-users.xml
    echo "</tomcat-users>" >> /opt/tomcat/conf/tomcat-users.xml

    # Start Tomcat Server
    cd /opt/tomcat/bin/

    ./startup.sh

    # Open a Browser and access tomcat : http://public_ip_of_ec2_instance:port(8080)

    ```

```
# vi /opt/tomcat/conf/tomcat-users.xml

<?xml version="1.0" encoding="UTF-8"?>
<tomcat-users xmlns="http://tomcat.apache.org/xml"
              xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
              xsi:schemaLocation="http://tomcat.apache.org/xml tomcat-users.xsd"
              version="1.0">

<role rolename="manager-gui"/>
<role rolename="manager-script"/>
<role rolename="manager-jmx"/>
<role rolename="manager-status"/>
<role rolename="admin-gui"/>
<role rolename="admin-script"/>

<user username="admin" password="redhat@123" roles="manager-gui,manager-script,manager-jmx,manager-status,admin-gui,admin-script"/>

</tomcat-users>
```

```
# vi /opt/tomcat/webapps/host-manager/META-INF/context.xml 


# vi /opt/tomcat/webapps/manager/META-INF/context.xml 


```
