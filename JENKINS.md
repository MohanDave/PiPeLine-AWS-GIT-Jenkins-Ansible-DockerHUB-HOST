1.We first Configure the jenkins server on an AMAZON LINUX 2 (AMI) Machine form the AWS.
2.Using putty software the jenkins server was configured on command line
3.Configuration of jenkins server , the first step included installing java using the command :
         yum install java* -y
4. After that the jenkins package was installed on the machine using the following command:
    {
    
    [root@ip-172-31-46-97 ~]# wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
--2021-07-26 11:46:55--  https://pkg.jenkins.io/redhat-stable/jenkins.repo
Resolving pkg.jenkins.io (pkg.jenkins.io)... 151.101.202.133, 2a04:4e42:50::645
Connecting to pkg.jenkins.io (pkg.jenkins.io)|151.101.202.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 85
Saving to: ‘/etc/yum.repos.d/jenkins.repo’

100%[======================================>] 85          --.-K/s   in 0s

2021-07-26 11:46:55 (5.56 MB/s) - ‘/etc/yum.repos.d/jenkins.repo’ saved [85/85]

[root@ip-172-31-46-97 ~]# rpm --import https://pkg.jenkins.io/redhat-stable/jenk                                                                             ins.io.key
[root@ip-172-31-46-97 ~]# yum install jenkins
 
    }
    systemctl enable jenkins
    systemctl start jenkins

    
 5. Followed by Installing github with command:
         yum install git* -y
   
   
