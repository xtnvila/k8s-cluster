# Kubernetes cluster

### A deployment created for a microservices Java sample app, containerized with Docker and managed with K8s, with load balancing and ready for rolling updates with zero downtime.

## Installation and usage

First of all you´ll need some dependencies installed:


  [Docker](https://docs.docker.com/get-docker/) and [DockerHub](https://hub.docker.com/) account

  [JDK](https://www.oracle.com/java/technologies/downloads/) and [Maven](https://maven.apache.org/install.html)
  
  [Kubernetes](https://kubernetes.io/docs/setup/) and [Kubectl](https://kubernetes.io/docs/tasks/tools/)


Once you´ve got this covered you need to create the **.jar** files targeted by the Dockerfile, to do so you will need to run Maven:
`mvn clean install` inside of each of this folders: **./shopfront**, **./stockmanager**, **./productcatalogue**.

After that is time to build your containers! you have to run `docker build -t DOCKERHUB_ACCOUNT/IMAGE_NAME:latest`, in the **.yaml** manifests inside of **./kubernetes** folder you will find a comment in every line you need to edit with your account name and image name for the cluster to run properly.

With the containers ready is time to push them into the dockerhub.com repository, run `docker login` from your terminal and enter your account details, you can push the image running the following command: `docker push DOCKERHUB_ACCOUNT/IMAGE_NAME:latest`.

Now you´re good to go! all have to do is boot up your Kubernetes cluster and launch some pods, hope you enjoy.

## Credits

The awesome microservices Java sample app we used was originally developed by Daniel Bryant:

https://github.com/danielbryantuk/oreilly-docker-java-shopping

 https://github.com/danielbryantuk

 Thanks Daniel!
