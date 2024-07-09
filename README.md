<h1>Demo Project</h1>

<h2>Project Description</h2>
Deploy Mosquitto message broker with ConfigMap and Secret Volume Types
<br />


<h2>Technologies used</h2>

- <b>Kubernetes</b> 
- <b>Docker</b>
- <b>Mosquitto</b>


<h2>Detailed Description of Project </h2>
Define configuration and password for mosquitto message broker with configMap and Secret Voulume types

<p align="center">
Create mosquitto deployment/pod without attaching volume with configuration file: <br/>
Mosquitto message broker image is pulled from docker hub.
configuration file name "mosquitto-deployment.yaml"
<img src='./src/kimage1.png' height="80%" width="80%" alt="Disk Sanitization Steps">

mosquitto message broker deployment created in minikube
<img src='./src/kimage2.png' height="80%" width="80%" alt="Disk Sanitization Steps">


<br />
<br />
Create yaml configuration files to start mongodb  deployment and service:<br/>
1. Create a mongodb pod/deployment and in order to communicate with the pod, a Service is required <br/>
 create internal service to allow only internal components in the cluster to communicate with each other <br/>
 create ("mod-dpl.yaml") file using the visual studio code editor <br/>
 

     check docker hub for official configuration guide of mongodb image 
     two environmental variables that need to be set are 
     MONGO_INITDB_ROOT_USERNAME:
     MONGO_INITDB_ROOT_PASSWORD:
     NB: Because the configuration file is going to be checked into the repository, it is not a 
     good practice to add username and password in the configuration file 
     therefore: 
     create a secret key in minikube 
     create a new file "mod-secret.yaml" 
     the kind:"Secret" 
     use base64 to generate the key value pair 
     echo -n "username"|base64
     echo -n "password"|base64
create the secret and mogodb deployment using "Kubectl apply command"
<img src='./src/image2.png' height="80%" width="80%" alt="Disk Sanitization Steps">

Create a mongodb Service in same mongodb deployment configuration file <br/>
NB: The "target port in the service should be the same as the deployment port<br/>
create the mongodb service using 'kubectl apply command' <br/>
<img src='./src/image3.png' height="80%" width="80%" alt="Disk Sanitization Steps">

Create mongo express deployment("moe-depl.yaml") and service <br/>
check docker hub for official configuration guide of mongodb image <br/>
three environmental variables that need to be set are <br/>
ME_CONFIG_MONGODB_ADMINUSERNAME  <br/>          
ME_CONFIG_MONGODB_ADMINPASSWORD <br/>
ME_CONFIG_MONGODB_SERVER <br/>
The admin username and password is also reference from the secret key created earlier <br/>
create a new file "moe-deployment.yaml" <br/>
Create a configMap ("moe-configmap")to reference the server <br/>
the name of the mod-deployment server should be used as the value <br/>

create the configMap and mongo express deployment and service using the "kubectl apply command"<br/>

<img src='./src/image4.png' height="80%" width="80%" alt="Disk Sanitization Steps">

starting mongo express in the browser <br/>
get the runing services in the minikube cluster (using the "kubectl get service" command)<br/>
<img src='./src/image5.png' height="80%" width="80%" alt="Disk Sanitization Steps">

start mongoexpress in the browser using "minikube service moe-service"<br/>
<img src='./src/image8.png' height="80%" width="80%" alt="Disk Sanitization Steps">

Opened mongo express in the browser
<img src='./src/image7.png' height="80%" width="80%" alt="Disk Sanitization Steps">









 
   
     

</p>
