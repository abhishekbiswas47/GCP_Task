# GCP_Task

### Task Description
1. Create multiple projects namely developer and production

2. Create VPC network for both the projects

3. Create a link between both the VPC networks using VPC Peering

4. Create a Kubernetes Cluster in developer project and launch any web application with the Load balancer

5. Create a SQL server in the production project and create a database

6. Connect the SQL database to the web application launched in the Kubernetes cluster

### What is Google Cloud Platform ( GCP ) ?

Google Cloud is a suite of Cloud Computing services offered by Google. The platform provides various services like compute, storage, networking, Big Data , and many more that run on the same infrastructure that Google uses internally for its end users like Google Search and YouTube.

Google server hasn’t gone down in years. So, if you are planning to run your application on the Google Cloud infrastructure, then you can be assured of your applications being safe and secure.


### What is VPC ?

Virtual Private Cloud (VPC) provides networking functionality to Compute Engine virtual machine (VM) instances, Google Kubernetes Engine (GKE) clusters, and the App Engine flexible environment also provides networking for our cloud-based resources and services that is global, scalable, and flexible.


### What is Cloud SQL?

Cloud SQL is a fully-managed database service that helps us to set up, maintain, manage, and administer our relational databases in cloud platform.


### What is Kubernetes ?

Kubernetes is an open-source system that allows organizations to deploy and manage containerized applications like platforms as a service (PaaS), batch processing workers, and micro services in the cloud at scale. Through an abstraction layer created on top of a group of hosts, development teams can let Kubernetes manage a host of functions — including load balancing, monitoring, deployment , providing the storage and controlling resource consumption by team or application, limiting resource consumption and leveraging additional resources from new hosts added to a cluster, and other workflows.


##### Step 1: Create two projects one for developer & another for production.-:

Create one project for the developer from in which developer can work.Create one project for the production department from where production guys can work in their our own projects.

Projects can be created in two ways, i.e using GUI(graphical user interface) and CLI (command line interface).


##### Step 2: Creating a VPC network for the projects.-:

We'll create two VPC's, One for kubernetes cluster and other for database. go to GCP console and then click on VPC Network then Click on Create VPC Network and Create two VPCs in different regions by clicking on create button.


##### Step 3: Creating the VPC peering for both the network.

It is a network connection between two VPCs which allows traffic routing between VPCs. To create VPC peering we'll go to VPC Network Peering under VPC Network, fill the details and it'll create vpc peering.


##### Step 4: Createing a Kubernetes Cluster.

First we have to enable the kubernetes engine API from the API library.

To create K8s cluster, gcp provides a service called Google Kubernetes Engine, which is under compute services. we'll fill the details as per requirement like name, location type, master version, size/number of nodes, surge, networking, machine configuration etc. and then use the service efficiently.


##### Step 5: Creating Wordpress deployment.

 to create the deployment we have to use command -:

     kubectl create deployment wordpressos --image=wordpress 

we can also check that our pods & deployments are successfully launched or not with the help of command

     kubectl get pods kubectl get deploy 

If we want that the client can also connect to our server than we have to expose our deployent and for that we need a Load balancer to balance the load. Load balancer will create an external IP which can be given to our clients to access the wordpress. to expose our deployment we will use a command-:

     kubectl expose deployment wordpressos --type=LoadBalancer --port=80 


##### Step 6: Creating a SQL server.

To create mysql instance, we'll go in the storage section and choose sql option and then click on the create instance option it will create a SQL instances for us.

now we have to set change some settings, and we have to create a user to access our database .


##### Step 7: Connect the SQL database to the web application launched in the Kubernetes cluster.

 launch the wordpress by copying the External IP address provided by the load balancer and paste it on our browser. We've to give the database credentials which we set at the time of launching MySql instance, then our wordpress have been successfully launched using gcp cloud.

![alt text](https://github.com/abiswah/GCP_Task/blob/master/IMG-20200929-WA0008.jpg)
![alt text](https://github.com/abiswah/GCP_Task/blob/master/IMG-20200929-WA0007.jpg)
![alt text](https://github.com/abiswah/GCP_Task/blob/master/IMG-20200929-WA0006.jpg)
![alt text](https://github.com/abiswah/GCP_Task/blob/master/IMG-20200929-WA0005.jpg)
![alt text](https://github.com/abiswah/GCP_Task/blob/master/IMG-20200929-WA0004.jpg)
