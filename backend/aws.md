# AWS
- amazon web services
- amazon's cloud service
- It let's you
	- rent servers
	- manage domains
	- upload objects(mp4 files, jpgs, mp3s,...)
	- autoscale servers
	- create k8s servers
# EC2
- VMs on AWS are called EC2 servers
- EC2 - Elastic Compute Version 2
	- *Elastic* : Can increase/decrease the size of the machine
	- *Compute* : It is a machine

> We can't run our server locally because we don't have a public IP address and so not everyone can access our website, only the ones who are connected to the same network such as wifi. For that reason, we try to get `instances` from AWS to run our server on, because anyone in the world can access our website by going to a particular Public IP Address pointed to by some URL.

![[Pasted image 20240912200504.png]]
Here, we can choose the kind of instance we want based on our requirements. We can also use key pairs for login purposes. A key pair is generated(public key and a private key) and it is used for the login.

![[Pasted image 20240912200618.png]]
Any of the encryption techniques can be used.


![[Pasted image 20240912200400.png]]
Here, we explicitly mention the port at that public IP address on which we want our application to run. 
SSH stands for Secure Shell. It is a protocol for remote connection between 2 devices. The SSH port on AWS is port 22.

We don't want the visitors of our websites to visit on `www.website.com:3000`. Instead, we just want them to visit `www.website.com`. We use HTTP for this. The website is `www.website.com` is stored at port 80 and can also be called `www.website.com:80`.  We use 80 because it is the default http port and so if we don't mention any port, the URL routes to port 80 by default and this way, our URL looks clean.
HTTP - port 80
HTTPS - port 443(more secure version of HTTP)

>Best practice is to only have port 443 open and all the others closed so that no one get access to our site.

![[Pasted image 20240912201853.png]]
This is an AWS instance. 

# SSH
![[Pasted image 20240912220615.png]]
![[Pasted image 20240912220630.png]]

# Reverse Proxy
![[Pasted image 20240912223647.png]]

We can have multiple backends and want to deploy them, but as there is only one port 80, we cannot deploy multiple backends at the same port, and if we choose other ports, then the port number will get displayed in the URL. To avoid this, we use reverse proxy.

Using reverse proxy, we can keep different backends at different ports other than `port 80` (eg. 8080, 8081, etc.), and according to the incoming request, `port 80` just routes that request to the port where the requisite backend is stored. 

Reverse proxy runs on `port 80` and it is not a NodeJS/Java process, but some other process entirely.

![[Pasted image 20240912224207.png]]

- Proxy : A proxy server, sometimes referred to as a forward proxy, is a server that routes traffic between client(s) and another system, usually external to the network. By doing so, it can regulate traffic according to preset policies, convert and mask client IP addresses, enforce security protocols, and block unknown traffic.
- Reverse Proxy : A reverse proxy is a type of proxy server. Unlike a traditional proxy server, which is used to protect clients, a reverse proxy is used to protect servers. A reverse proxy is a server that accepts a request from a client, forwards the request to another one of many other servers, and returns the results from the server that actually processed the request to the client as if the proxy server had processed the request itself. The client only communicates directly with the reverse proxy server and it does not know that some other server actually processed its request.

![[Pasted image 20240912225029.png]]

# nginx
- helps in doing reverse proxy
- ![[Pasted image 20240912230602.png]]

# certificate management
- use certbot
- basically, we want to deploy our app over a secure port, i.e. `port 443`(default https port). we can't just put our server to listen on `port 443` for this, and instead need to generate SSL certificates for this as well as public-private key pair.
- ![[Pasted image 20240912233338.png]] We want to run nginx on `port 443`. 






