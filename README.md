#                                                 DockJaNetes
This is a funny term coined by me. I drew this term by drawing few letters from the words DOCKer, JAva and kuberNETES.

This is a simple and small microservice java project, which is based on three elements product catalogue, stock manager and shopfront (frontEND) which are deployed as deployments in the cluster.

The two deployment objects stockmanager and product catalogues are identified by the cluster IP type service for enabling seamless communication in between them irrespective of any undesirable problems.

Only shopfront is exposed to the external visibility through an Application Load Balancer (Ingress), as it is the frontend of the intended application.

First, launch docker on any server and install maven on the same server.

Clone this repository into the server and build the jar files for all the three components using maven by executing `mvn clean install`. This builds the code by downloading respective modules and dependencies as per the pom.xml file.

Build docker images from the given Dockerfile and push the images into your dockerhub account or any other image repository.

Now, expose the frontend application to the external traffic through ingress controller, which creates an Application load Balancer in AWS, according it's default behaviour in EKS.

Instead of using the DNS of the ALB, we can create a new record for our domain in the hosted zone of Route 53.