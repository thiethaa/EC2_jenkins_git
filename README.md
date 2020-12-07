# EC2_jenkins_git

1.  create ec2 instance:
    - choose amazone machine image (choose free tier )
    - choose instance type (t2micro)
    - configure instance detail (size,if want to integrate with saclingGroup to scale in and scale out the instance)
    - add storage (if want to attach the intance wirth particular storage)
    - add tag (related with case-sensitive for key-value pair)
    - configure security group (adding one alltrafic group here and allow it to be access from anywhere)
    - review and launch the instance, we need the key pair
2. its take few second before our instance up and running, now we want to connect and go inside our instance
3. go to directory where we keep the pem key
4. i will copy  the ssh-i 
5. "we want to integrate jenkins and git to perform continues integration" ===> need to install java, jenkins, and git
6. ensure our softaware package up to date 
        
        sudo yum update -y
       
7. install java

        sudo yum install java-1.8.0-openjdk

8. install jenkins 2 step 
      - download latest jenkins package
      
            sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo
      
      - import the key to enable intallation from that package
      
            sudo rpm --import https://pkg.jenkins.io/redhat/jenkins.io.key
        
            sudo yum install jenkins -y
        
     - run jenkins server
     
            sudo service jenkins start
   
   .Access initialPasswork
   
            sudo su -
            cd /var/lib/jenkins/secrets/
            cat initialAdminPassword 

9. install Git

          sudo yum install git -y
