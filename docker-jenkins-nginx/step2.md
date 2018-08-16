Next you will launch Nginx in a container using an image that has been configured to provide a simple reverse proxy to any
application running on port 8080 in a container. The application to be proxied has to be visible to the Nginx container with
the name "webapp". To make that possible, you will link the Jenkins container and give it the internal name "webapp".

`docker run -d -p 80:80 --link jenkins:webapp --name jenkins-proxy jvandusen/nginx-proxy-webapp`{{execute}}

You can now access Jenkins in your browser: https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/