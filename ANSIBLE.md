.We first Configure the Ansible server on an AMAZON LINUX 2 (AMI) Machine form the AWS and configured it using putty 

  amazon-linux-extras install ansible2
  
.Docker package was aso installed on the ansible server

yum install docker 

systemctl enable docker

systemctl start docker


.The server was made password less with both jenkins server before it and the docker container on which the dockerimage was deployed in the similar manner as shown in the ansible .odt file in this repository.

.A playbook was created on the ansible server name docker.yml
 which was defined as follows
 
-hosts: all


tasks:


- name: stop container


shell: docker container stop PIPELINE-container


- name: remove container


shell: docker container rm PIPELINE container


- name: create container


shell: docker container run -itd --name PIPELINE-container -p 9000:80  mohan1809/pipeline2
       
       (It is to be noted that the name of the job in the jenkins PIPELINE was later changed to pipeline2 )
       
 .While adding the ansible server in the PIPELINE in the building actions and post building action following commands were given in the commands for execution column
 
 cd /opt
 
 
docker image build -t $JOB_NAME:v1.$BUILD_ID 


docker image tag $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:v1.$BUILD_ID


docker image tag $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:latest


docker image push mohan1809/$JOB_NAME:v1.$BUILD_ID


docker image push mohan1809/$JOB_NAME:latest


docker image rmi  $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:v1.$BUILD_ID  mohan1809/$JOB_NAME:latest


.In the post buil actions


ansible-playbook /sourcecode/docker.yml   



. The DockerHub was logged in on the Ansible server 
 
