# ace11-helm
ACE 11 Helm chart for ICP 2.1.0.2

Steps:

1. Clone this repository 

2. Login to ICP from Bluemix CLI

bx pr login  

3. Upload the helm chart archive to your ICP instance

bx pr load-helm-chart --archive ace11-dev-1.0.0.tgz

4. Go to ICP Catalog -> Helm Charts, and deploy the helm chart ace11-dev

5. Click on configure.  Select the following values
     Release Name: (any name, eg: rel1)
     Target namespace: default
     Accept the license 
     (optional) reduce limits.cpu to 1
     Install
     
6. Once installed, click on the network access -> services, and select the service (eg: rel1-ace11-dev)
Access the server listener URL. This opens the Web UI of ACE 11.

7. Click on the deploy button. Select the BAR file that you cloned -> HelloREST.bar

8. Once the BAR file is deployed, click from the network access -> services select the service and access the http listener URL. (you should get a not found page). 

Append the URL with /helloace/v1/sayHello?name=Francis  (for example, http://10.0.0.50:30270/helloace/v1/sayHello?name=Francis )

You should see the REST service response. 
