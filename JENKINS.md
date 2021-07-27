1.We first Configure the jenkins server on an AMAZON LINUX 2 (AMI) Machine form the AWS.


2.Using putty software the jenkins server was configured on command line


3.Configuration of jenkins server , the first step included installing java using the command :
         yum install java* -y
         
         
4. After that the jenkins package was installed on the machine using the following command:
    
    
  wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
--2021-07-26 11:46:55--  https://pkg.jenkins.io/redhat-stable/jenkins.repo




 rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
 
 
 yum install jenkins
 
    
 systemctl enable jenkins
 
 systemctl start jenkins

    
 5. Followed by Installing github with command:
         yum install git -y
         
 6. The connection between the jenkins and ansible server was made passwordless by generating the key on jenkins sharing it on ansible server and enabling root login and userauthentication in the sshd_config file on the ansible server
 
  ssh-keygen
  
  
  
  
  ssh-copy-id root@172.31.45.85  (Private IP of the jenkins server ).
         
 7. The jenkins server sends few additional commands along with the Docker image file for its building arrangements in the ansible server itself .
Commands required from the jenkins server for the operations in the ansible server are:



docker image build -t myimage:v1


docker  image tag myimage:v1 (id)/myimage:v1



docker image push (id)/myimage:v1







   
   
