#### Session Video:
    https://s3.amazonaws.com/kesavkummari.aws/8am_AWSDevOps20230207/20230314_CIServer/video1033654276.mp4

# Continuous Integration

#### What is CI?
    CI stands for Continuous Integration, which is a software development practice where developers frequently integrate their code changes into a shared repository, and then an automated build and testing process is triggered to detect and resolve any issues or conflicts that may arise.

#### Purposse CI?
    The purpose of CI is to catch and fix problems in the code as early as possible, which reduces the risk of errors being introduced into the software and increases the speed of delivery. 
    It also enables faster and more frequent releases of software.

#### CI Vendors ?
    There are many CI vendors that offer tools and services for implementing CI, such as:

        Jenkins: An open-source automation server that provides hundreds of plugins to support building, testing, and deploying software.

        Travis CI: A cloud-based CI service that supports testing and deploying software projects hosted on GitHub.

        CircleCI: A cloud-based CI/CD platform that supports building, testing, and deploying software projects hosted on GitHub, Bitbucket, and GitLab.

        GitLab CI/CD: A built-in CI/CD platform that comes with GitLab, a web-based Git repository manager.

        TeamCity: A CI server developed by JetBrains that supports building and testing software for various platforms and programming languages.

        Bamboo: A CI/CD server developed by Atlassian that supports building, testing, and deploying software for various platforms and programming languages.

    These CI vendors provide a range of features and integrations to support different types of software development workflows and teams.

#### How CI works?
     Continuous Integration (CI) is a software development practice that involves continuously integrating code changes into a shared repository and then automatically building and testing the software to ensure that the changes are compatible with the existing codebase.

     Here is how Continuous Integration works:
        1. Developers write code and commit their changes to a shared code repository, such as Git.

        2. The Continuous Integration server monitors the repository for changes and automatically pulls the latest code changes.

        3. The Continuous Integration server runs automated builds and tests on the code changes to check for any issues or conflicts.

        4. If any issues are found during the build or testing process, the Continuous Integration server notifies the development team and prevents the changes from being merged into the main codebase until the issues are resolved.

        5. If the build and tests pass successfully, the changes are merged into the main codebase, and the process starts over again.

    By continuously integrating code changes, developers can catch and fix issues early in the development process, reducing the risk of introducing errors into the software and improving the overall quality of the codebase. 
    It also enables faster feedback and faster delivery of new features to end-users.    

### Use cases:
    Continuous Integration (CI) has several use cases, including:

        1. Ensuring Code Quality: 
        CI helps ensure that code changes are tested and reviewed before they are merged into the main codebase, improving overall code quality and reducing the risk of bugs.

        2. Improving Collaboration: 
        CI promotes collaboration between developers by providing a shared code repository and automated testing, enabling developers to work together more efficiently.

        3. Speeding Up Development Cycles: 
        CI enables faster feedback cycles, allowing developers to catch issues earlier in the development process, reducing the time required to fix bugs and delivering new features more quickly.

        4. Minimizing Risks: 
        By continuously integrating and testing code changes, CI helps to minimize the risk of introducing errors into the software, preventing deployment failures, and reducing overall project risks.

        5. Building Reliable Releases: 
        CI enables automated building, testing, and deployment, ensuring that software releases are reliable and consistent across different environments.

        6. Supporting Agile Development: 
        CI is well-suited for Agile development methodologies, enabling teams to quickly integrate changes and iterate on features.

        7. Providing Visibility and Traceability: 
        CI provides visibility into the development process by tracking changes and ensuring that builds and tests are consistently executed, providing traceability throughout the development cycle.

    Overall, CI is an essential tool for modern software development, helping teams to build better-quality software faster and more reliably while reducing overall project risks.

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
--tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=CI-Jenkins},{Key=Environment,Value=dev}]'
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
--tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=CI-Jenkins},{Key=Environment,Value=dev}]'
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
--tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=CI-Jenkins},{Key=Environment,Value=dev}]'
```

#### Download Install & Configure Documentation from Jenkins Official Website:

    Download Process: 
        https://www.jenkins.io/download/

    Install Process:
        https://www.jenkins.io/doc/

    Configure Process:
        Windows: https://www.jenkins.io/doc/book/installing/windows/

        Linux : https://www.jenkins.io/doc/book/installing/linux/

#### Download, Install & Configure Jenkins on Linux Distributions:

    Here are the steps to download, install, and configure Jenkins on Linux Ubuntu using a shell script:

    1. Open a terminal window on your Ubuntu machine.

        Create a shell script file using the following command:

        $ vi jenkins-install.sh

    2. Paste the following code into the shell script file:

    ```
    # Debian/Ubutu
    #!/bin/bash

    # Setup Hostname
    sudo hostnamectl set-hostname "jenkins.cloudbinary.io"

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

    # Download, Install Maven 
    sudo apt-get install maven -y

    # Backup the Environment File
    sudo cp -pvr /etc/environment "/etc/environment_$(date +%F_%R)"

    # Create Environment Variables
    echo "MAVEN_HOME=/usr/share/maven" >> /etc/environment

    # Compile the Configuration
    source /etc/environment

    # Add Jenkins repository key
    wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -

    # Add Jenkins repository to apt sources
    echo deb https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list

    # Update apt and install Jenkins
    sudo apt-get update
    sudo apt-get install -y jenkins

    # Start Jenkins service
    sudo systemctl start jenkins

    # Enable Jenkins service to start on boot
    sudo systemctl enable jenkins

    # Note: The above script is for installing Jenkins on Ubuntu with OpenJDK 11. 
    # If you have a different version of Ubuntu or want to use a different version of Java, you may need to modify the script accordingly.
    ```

    ```
    # CentOS/AmazonLinux2/Redhat
    #!/bin/bash

    # Setup Hostname
    sudo hostnamectl set-hostname "jenkins.cloudbinary.io"

    # Update the hostname part of Host File
    echo "`hostname -I | awk '{ print $1 }'` `hostname`" >> /etc/hosts

    # Update Repository
    sudo yum update

    # Download, & Install Utility Softwares
    sudo yum install git wget unzip curl tree -y

    # Install Java Development Kit (JDK)
    sudo yum install -y java-1.8.0-openjdk-devel
    
    # Backup the Environment File
    sudo cp -pvr /etc/environment "/etc/environment_$(date +%F_%R)"

    # Create Environment Variables
    echo "JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64/" >> /etc/environment

    # Download, Install Maven 
    sudo yum install maven -y

    # Backup the Environment File
    sudo cp -pvr /etc/environment "/etc/environment_$(date +%F_%R)"
        
    # Create Environment Variables
    echo "MAVEN_HOME=/usr/share/maven" >> /etc/environment

    # Compile the Configuration
    source /etc/environment

    # Add Jenkins repository to yum configuration
    sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins.io/redhat-stable/jenkins.repo

    # Import Jenkins repository key
    sudo rpm --import http://pkg.jenkins.io/redhat-stable/jenkins.io.key

    # Install Jenkins
    sudo yum install -y jenkins

    # Start Jenkins service
    sudo systemctl start jenkins

    # Enable Jenkins service to start on boot
    sudo systemctl enable jenkins

    # Note: The above script is for installing Jenkins on CentOS 7 with OpenJDK 8. 
    # If you have a different version of CentOS or want to use a different version of Java, you may need to modify the script accordingly.
    ```

    3. Save and close the shell script file.

    4. Make the shell script file executable using the following command:

        $ chmod +x jenkins-install.sh

    5. Run the shell script file using the following command:

        $ ./jenkins-install.sh

    6. Wait for the installation process to complete.

    7. Once the installation is complete, open a web browser and navigate to http://localhost:8080.

        `http://<your_linux_server_ip_address>:8080`

    8. Follow the prompts to complete the Jenkins setup wizard, including creating an admin user and installing any necessary plugins.

    9. Once the setup is complete, Jenkins will be ready to use.

    
    Download Install Configure Jenkins on Windows using powershell script:

        Here are the steps to download, install, and configure Jenkins on Windows using a PowerShell script:

        1. Open PowerShell as an administrator.

        2. Create a new directory for Jenkins installation using the following command:

        ```
        New-Item -ItemType Directory -Path "C:\Program Files\Jenkins" -Force
        ```
        3. Change the directory to the Jenkins installation directory using the following command:
        
        ```
        cd "C:\Program Files\Jenkins"
        ```
        4. Download the Jenkins installation package using the following command:

        ```
        Invoke-WebRequest -Uri "https://get.jenkins.io/war-stable/latest/jenkins.war" -OutFile "jenkins.war"
        ```

        5. Install the Jenkins service using the following command:

        ```
        java -jar .\jenkins.war --install-service
        ```

        6. Start the Jenkins service using the following command:

        ```
        Start-Service Jenkins
        ```

        7. Open a web browser and navigate to http://localhost:8080

        8. Follow the prompts to complete the Jenkins setup wizard, including creating an admin user and installing any necessary plugins.

        9. Once the setup is complete, Jenkins will be ready to use.

        Note: The above script is for installing Jenkins on Windows using the built-in Windows service wrapper. If you prefer to install Jenkins as a Windows service using a separate service wrapper, you will need to modify the script accordingly. Additionally, you may need to adjust the firewall settings to allow incoming traffic to port 8080.

####
    Jenkins supports two types of pipelines: 
    Scripted Pipeline and Declarative Pipeline. 
    Here's a brief overview of the differences between the two:

    Scripted Pipeline:
        - Uses a Groovy-based domain-specific language (DSL) to define pipelines
        - Allows for more fine-grained control and flexibility in pipeline execution
        - Supports conditional statements, loops, and other programming constructs
        - Requires a more advanced understanding of Groovy and Jenkins pipeline syntax
        - Can be more difficult to read and maintain, especially for larger pipelines

    Declarative Pipeline:
        - Uses a simpler, more structured syntax for defining pipelines
        - Provides a more standardized, easier-to-read format for pipeline code
        - Supports pre-defined stages, steps, and post actions for common pipeline tasks
        - Allows for easier integration with external tools and services
        - Is more accessible to less experienced Jenkins users
        - May require more effort to customize for specific use cases

    In general, Scripted Pipeline is a better choice for complex pipelines with advanced logic and customization needs, while Declarative Pipeline is better for simpler pipelines with standardized workflows and easier maintenance requirements.


#### Scripted Pipeline


```
node {
    stage('Checkout') {
        // Checkout the code from a version control system
        // For example, from a Git repository:
        git 'https://github.com/username/repo.git'
    }

    stage('Build') {
        // Set up the environment
        def javaHome = tool 'JDK'
        env.JAVA_HOME = javaHome
        env.PATH = "${javaHome}/bin:${env.PATH}"

        // Build the application using Maven
        sh "${mvnHome}/mvn clean package"
    }

    stage('Test') {
        // Run unit and integration tests
        sh "${mvnHome}/mvn test"
    }

    stage('Deploy') {
        // Deploy the application to a test environment
        sh "${mvnHome}/mvn deploy"
    }
}

```

```
node {
   def mvnHome
  stage('Prepare') {
      git url: 'https://github.com/kesavkummari/javacodescan.git', branch: 'main'
      mvnHome = tool 'maven'
   }
  stage ('Code Quality') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore sonar:sonar"
  }

  stage ('Clean') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean"
  }
  stage ('Validate') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore validate"
  }
  stage ('Compile') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore compile"
  }
  stage ('Test') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore test"
  }
  stage ('Package') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore package"
  }
  stage ('Verify') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore verify"
  }
  stage ('Install') {
      sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore install"
  }
  stage ('Deliver & Deployment') {
      sh 'curl -u admin:redhat@123 -T target/**.war "http://3.87.125.112:8080/manager/text/deploy?path=/kesav&update=true"'
  }
  stage ('SmokeTest') {
      sh 'curl --retry-delay 10 --retry 5 "http://3.87.125.112:8080/kesav"'
  }
}
```

#### Declarative Pipeline

```
pipeline {
    agent any

    tools {
        // Configure the JDK and Maven tools
        jdk 'JDK'
        maven 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from a version control system
                // For example, from a Git repository:
                git 'https://github.com/username/repo.git'
            }
        }

        stage('Build') {
            steps {
                // Build the application using Maven
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Run unit and integration tests
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application to a test environment
                sh 'mvn deploy'
            }
        }
    }
}

```

```
pipeline {
    agent any 
    tools {
         maven 'maven'
         jdk 'java'
    }
    stages {
         stage('Stage-0 : Static Code Analysis Using SonarQube') { 
           steps {
                sh 'mvn clean verify sonar:sonar -DskipTests'
            }
        }
        stage('Stage-1 : Clean') { 
            steps {
                sh 'mvn clean'
            }
        }
         stage('Stage-2 : Validate') { 
            steps {
                sh 'mvn validate'
            }
        }
         stage('Stage-3 : Compile') { 
            steps {
                sh 'mvn compile'
            }
        }
         stage('Stage-4 : Test') { 
            steps {
                sh 'mvn test -DskipTests'
            }
        }
          stage('Stage-5 : Install') { 
            steps {
                sh 'mvn install -DskipTests'
            }
        }
          stage('Stage-6 : Verify') { 
            steps {
                sh 'mvn verify -DskipTests'
            }
        }
          stage('Stage-7 : Package') { 
            steps {
                sh 'mvn package -DskipTests'
            }
        }

           stage('Stage-8 : Deploy an Artifact to Artifactory Manager i.e. Nexus/Jfrog') { 
            steps {
                sh 'mvn deploy -DskipTests'
            }
        }

          stage('Stage-9 : Deployment - Deploy a Artifact devops-3.0.0-SNAPSHOT.war file to Tomcat Server') { 
            steps {
                sh 'curl -u admin:Str0ngAdminPassw3rd -T target/**.war "http://54.166.230.167:8080/manager/text/deploy?path=/devops&update=true"'
            }
        } 
  
          stage('Stage-10 : SmokeTest') { 
            steps {
                sh 'curl --retry-delay 10 --retry 5 "http://54.166.230.167:8080/devops"'
            }
        }

  
    }
}
```
