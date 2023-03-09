#### Session Video:

# Text Editors in Linux 

####
    1. Insert Mode: 
        - i = inserts the text at current cursor position
        - I = inserts the text at beginning of line
        - A = Appends the text at end of line
        - o = inserts a line below current cursor position
        - O = inserts a line above current cursor position
        - r = replace a single char at current cursor position

    2. Execute Mode:
        - :q       = quit without saving
        - :!       = forcefully
        - :q!	     = quit forcefully without saving
        - :w       = save
        - :wq      = save & quit
        - :wq!     = save, quit forcefully
        - :se nu   = setting line numbers for reading only 
        - :se nonu = Removing the line numbers
        - :20      = Press enter to go to specific line like 20
        - :6,10 w! <new_file> : We can copy desire lines     [ :12,18 w! >>/root/Desktop/mac.txt ] 
        - :%s/cursor/devops/g : Search and Replace 

    3. Command Mode:
        - dd   = Deletes a line 
        - ndd  = Delete 2 lines  # 2dd 
        - yy   = Copy a line
        - nyy  = copies 3 lines  # 3yy # 100yy
        - p    = put (paste deleted or copied text)
        - u    = undo (can undo 1000 times)
        - ctrl+r = Redo
        - G      = Moves cursor to last line of file
        - /<word to find> = To search for a particular word.


#### Use Case : Hosting a Website on AWS 

    - List of WebServers :
        To Hosting a Website, We need to use webservers: i.e. Apache httpd, Apache2, Nginx, IIS etc...
            
    - Host A Website on Linux Distributions :
        - Ubuntu / Amazon Linux 

    - Host A Website on Windows:
        - IIS  

#### Steps 
    - Provision Infrastructure:
        - EC2 Instance 
    
    - AWS CLI:
        $ aws ec2 run-instances --image-id "ami-0dfcb1ef8550277af" --count 1 --instance-type t2.micro --key-name "us_east_1_keys" --security-group-ids "sg-09e7a75b97f33d7f1" --subnet-id "subnet-00a07bb8fefdfcfec"

    - Connect EC2 Instance using Host Machine :
        - Go to Windows :
            - Gitbash :
                - DO SSH to Remote Linux Machine
                $ ssh -i "key_pair.pem" ec2-user@publicip or dnsname

    - Configuration Management:
        - Download, install & Configure Webserver Software :

            WebServer Software:
                - Linux Distribution : AmazonLinux2 

    - Source Code Management :
        - GitHub/GitLab/AWS CodeCommit : 


####
    - whatis httpd
    - whereis httpd
    - man httpd

####
    - What is Package Management?
        - Search a Package 
        - Install a Package
        - Update the package index
        - Upgrade packages
        - Remove a Package
        
    - Package management :
        # AmazonLinux / CentOS / Fedora / RHEL : 
            $ rpm 
            $ yum 
        # https://www.redhat.com/sysadmin/how-manage-packages

        # Debian / Ubuntu :
            $ dpkg
            $ apt       [For Interactive Terminal]
            $ apt-get   [For Scripts]

        # https://ubuntu.com/server/docs/package-management


#### Package Management
    - $ yum install httpd

#### Documentation :
    - Path : /usr/share/man/man1/httpd.1.gz

#### Configuration :
    - Path : /etc/httpd

#### Binary Files:
    - Path : /usr/sbin/httpd

#### DocumentRoot:
    - Path : /var/www/html/

#### Log Files :
    - Path : /var/log/httpd/

#### 
    - Service :
        Path : /usr/lib/systemd/system/httpd.service

    - To Enable a Service at boot level:
        $ systemctl enable httpd
    
    - To check a Service status:
        $ systemctl status httpd

    - To Start a Service:
        $ systemctl start httpd

    - To Restart a Service:
        $ systemctl restart httpd    

        $ netstat -tulpn | grep LISTEN

        $ cat /etc/services | grep -w '80/tcp'

    - Take EC2 Instance Public Ip and Go to Browser and paste:

        http://23.22.33.211/

    - GitHub Source Code : https://github.com/kesavkummari/kesavkummari-website-code
    

#### AWS Help
    - https://docs.aws.amazon.com/cli/latest/userguide/cli-services-ec2.html

    - Topics:
        - Creating, displaying, and deleting Amazon EC2 key pairs:
            $ https://docs.aws.amazon.com/cli/latest/userguide/cli-services-ec2-keypairs.html
        
        - Creating, configuring, and deleting security groups for Amazon EC2
            $ https://docs.aws.amazon.com/cli/latest/userguide/cli-services-ec2-sg.html
        
        - Launching, listing, and terminating Amazon EC2 instances
            $ https://docs.aws.amazon.com/cli/latest/userguide/cli-services-ec2-instances.html
        
        - Change an Amazon EC2 instance type using a bash script
            $ https://docs.aws.amazon.com/cli/latest/userguide/cli-services-ec2-instance-type-script.html    
