**Jenkins Hands-On Lab: End-to-End CI/CD Pipeline Implementation**
Overview:
In this hands-on lab, I successfully set up and executed a complete CI/CD pipeline using Jenkins and AWS instances. Here's a step-by-step breakdown of the process:

Steps:
**1. AWS Instance Setup**
Created two EC2 instances in AWS:

Jenkins Master: For managing Jenkins and pipeline configurations.
Worker (Slave): For executing the builds and running Docker containers.
Gained SSH access to both instances for package installations and configuration.
![1 two instance creation](https://github.com/user-attachments/assets/add64e69-1047-4c26-97eb-adc14f361b5e)


**2. Installed Required Software**
On both instances, installed the following tools:
Java: Required for Jenkins and Maven.
Jenkins: Installed on the master instance to manage CI/CD pipelines.
Maven: For building and packaging the code.
SonarQube: Deployed as a Docker container on the slave instance for static code analysis.

_Jenkins installation:_
![2 Jenkins installation](https://github.com/user-attachments/assets/67143ef7-06d8-460e-b07d-561e9f034c24)

_Docker installation & Verification:_
![3 Docker installation in worker machine](https://github.com/user-attachments/assets/82b1281b-6ae1-4823-9b23-6680f7d61e43)
![4 Docker verification](https://github.com/user-attachments/assets/9912e757-e411-4509-90c2-60c8fd541517)

_Sonarqube installation and verification:_
![5 Sonarqube installation](https://github.com/user-attachments/assets/6738a4a9-8fdb-4cec-b97e-0bebf601dbb9)
![6 Running sonarqube container](https://github.com/user-attachments/assets/afb92528-df24-4558-ac33-0460068f7e0b)


**3. Configured Jenkins**
In the Jenkins GUI:
Configured the slave machine for distributed builds.
Added credentials for:
GitHub (for accessing repositories).
DockerHub (for pushing Docker images).
SonarQube (for integrating static code analysis).
Maven (for managing dependencies and build lifecycle).

_Accessing Jenkins GUI:_
![7 Jenkins gui access](https://github.com/user-attachments/assets/a4c2455b-4d6d-44a0-a3f8-5d2c5705621b)

_Accessing Sonarqube GUI:_
![8 sonarqube gui acces](https://github.com/user-attachments/assets/1cf8ea20-7190-428f-bf7c-5857dbd78c52)

_Installing Neccessary plugin in Jenkins:_
![9 installing necessary plugin in jenkins](https://github.com/user-attachments/assets/6e1c2ae9-60bd-4072-a58c-0a1727097642)

_Adding Worker node in Jenkins:_
![10 adding worker node to jenkins](https://github.com/user-attachments/assets/6b921d95-af2f-4884-9458-97d2a60bb710)

_SSH Key pair generation in Worker machine:_
![11 keygen in worker node](https://github.com/user-attachments/assets/b026197f-e066-41b0-8207-d4cfc4ff1d2b)

_Adding worker node credentials in Jenkins:_
![12 adding worker node credentials](https://github.com/user-attachments/assets/d0bb7dfc-de08-4f33-a40d-d3522897a4c2)
![12a addig workeer node](https://github.com/user-attachments/assets/72e75d01-fb3b-41c5-a5bb-56ee3359a3c4)

_Configuring worker node in Jenkins:_
![13 adding worker node to jenkins](https://github.com/user-attachments/assets/6e8a36ab-c17e-454b-a087-5cd664456cba)
![13a](https://github.com/user-attachments/assets/ca2432b2-a000-45cf-b2b7-9113c15db463)

_Unable to connect to Worker node and troubleshooting it(It because of SSH key issue):_
![14 ssh error](https://github.com/user-attachments/assets/ad12fada-3175-4c35-a579-7c90a78440b7)
![15 copying pub key to auth key](https://github.com/user-attachments/assets/6a69202b-b5eb-4880-b6fa-aefd14e2cf9b)

_Worker node added sucessfully:_
![16 worked node added sucessfully](https://github.com/user-attachments/assets/2cda3d3d-f626-49fb-887e-85e49e60bcdb)

_Adding github tokens in Jenkins:_
![17 Creating tokens in github](https://github.com/user-attachments/assets/3c340c07-3315-4ced-be66-43a032fcdf5c)
![18 Github credentials in jenkins](https://github.com/user-attachments/assets/de1c7b91-1bbe-4403-af07-e37a8bb2e3bb)

_Sonarqube configuration in Jenkins:_
![19 sonarqube tool config in jenknins](https://github.com/user-attachments/assets/dff0b1da-d9e7-4a21-b662-33daf37c6eeb)

_Maven Configuration in Jenkins:_
![20,maven installation in jenkins](https://github.com/user-attachments/assets/ede1ce6d-8ea9-4add-9312-9a6805cec0d0)

_Docker related configuration in Jenkins:_
![21 Docker tool config in jenkins](https://github.com/user-attachments/assets/e6c28beb-489f-41ee-9bc9-12698b94648e)

_Docker hub credentials config in Jenkins:_
![22 Docker hub crendtials](https://github.com/user-attachments/assets/7b445729-031f-43af-a81d-90c843009510)

_Sonarqube credentials config in Jenkins:_
![23 sonarqube cred in jenkins](https://github.com/user-attachments/assets/b77ea8d5-518c-48fb-8eba-614ebe36cf0d)


**4. Pipeline Creation**
Created a Jenkins pipeline project and wrote a complete CI/CD pipeline script. The pipeline included the following stages:

Git Checkout: Pulled the latest code from GitHub.
Compile & Package: Used Maven to clean, compile, and package the code.
SonarQube Scan: Integrated SonarQube to perform static code analysis.
Docker Build & Push: Built a Docker image from the packaged application and pushed it to DockerHub.
Deploy & Run: Pulled the Docker image on the slave machine, ran it, and accessed the application.

_CI/CD Pipeline Creation:_
![24 Creating first pipeline](https://github.com/user-attachments/assets/551faed6-e8fe-4a51-935a-4e8561662f46)


**5. Executed the CI/CD Pipeline**
Triggered the pipeline to execute all the stages sequentially.
Successfully:
Pulled code from GitHub.
Compiled and packaged the application with Maven.
Built and pushed the Docker image to DockerHub.
Pulled and ran the Docker image on the slave machine.
Verified the application by accessing it in a web browser.

**Outcome:**
This hands-on lab demonstrated how to set up an automated CI/CD pipeline using Jenkins, AWS, Docker, and other essential tools. The process ensures seamless integration and deployment, enabling faster development cycles.

_Docker image uploaded to Dockerhub:_
![25 Docker images pushed to repo](https://github.com/user-attachments/assets/4f7cc0bc-32cd-453a-b318-94b85a6679bd)
Pipeline successfull :
![26 pipeline sucessful](https://github.com/user-attachments/assets/0886d14f-dd42-4cd1-85df-237336efc88a)

_Getting access to application:_
![27 checking applications](https://github.com/user-attachments/assets/b52fe152-e8c2-4be2-bec3-d65439b4c3a4)




