.The Docker container is our main deployment point of the pipeline.

.The docker container was created in the Amazon Web Services AWS account on an Amazon Linux 2 (AMI) Instance .

yum install docker 

systemctl enable docker

systemctl start docker


.The Container was created on the Docker container server and the docker image deployed on it. 

docker container ls


docker container run

docker container rm (id)


.While adding the ansible server in the PIPELINE in the building actions and post building action following commands were given in the commands for execution column

cd /opt

docker image build -t $JOB_NAME:v1.$BUILD_ID

docker image tag $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:v1.$BUILD_ID

docker image tag $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:latest

docker image push mohan1809/$JOB_NAME:v1.$BUILD_ID

docker image push mohan1809/$JOB_NAME:latest

docker image rmi $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:latest

.With every new deployment of docker image a new container is created image dployed on it and later removed.





