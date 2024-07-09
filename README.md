<h1>Demo Project</h1>

<h2>Project Description</h2>
Deploy Mosquitto message broker with ConfigMap and Secret Volume Types
<br />


<h2>Technologies used</h2>

- <b>Kubernetes</b> 
- <b>Docker</b>
- <b>Mosquitto</b>


<h2>Detailed Description of Project </h2>
Define configuration and password for mosquitto message broker with configMap and Secret Voulume types<br/>

   <p align="">
   <h2>step1</h2>
   Create mosquitto deployment/pod without attaching volume with configuration file: <br/>
   Mosquitto message broker image is pulled from docker hub.<br/>
   configuration file name "mosquitto-deployment.yaml" <br/>
   <img src='./sp/kimage1.png' height="80%" width="80%" alt="Disk Sanitization Steps">

   mosquitto message broker deployment created in minikube 
   <img src='./sp/kimage2.png' height="80%" width="80%" alt="Disk Sanitization Steps">

<h2>step2</h2>
   Create configMap and Secret volume types
   <img src='./sp/kimage7.png' height="80%" width="80%" alt="Disk Sanitization Steps">

   ConfigMap and secret volumes created in minikube
   <img src='./sp/kimage6.png' height="80%" width="80%" alt="Disk Sanitization Steps">

<h2>step3</h2>
  Add created configMap and secret volume to mosquitto pod configuration file<br/>
  create the volumes in the configuration file and mount the volume to the container<br/>
  * readOnly: true  this prevents app from modifying the content of the file<br/>
  * mountPath is the location in the container where the file will be mounted
 <img src='./sp/kimage8.png' height="80%" width="80%" alt="Disk Sanitization Steps">


  the secret and configMap volume files are available in the container<br/>
 files ('mosquitto.config' and 'secret.file')
 <img src='./sp/kimage10.png' height="80%" width="80%" alt="Disk Sanitization Steps">

   
    
    
   
     

</p>
