### basic flow
log in to aws -> get an ec2 instance -> generate an ssh key -> ssh into the ec2 instance using the command line(`ssh -i <key-name>.pem ubuntu@<publicIP>`) -> install node using nvm -> clone github repo -> npm install -> run the backend server(`npm start)` -> edit the security groups on the ec2 instance and make it allow traffic from both IPv4 and IPv6 addresses on the port backend is running on -> open the dns(url) of the ec2 instance and write the port where the backend is running(`:<port_no.>`) to check if it's running -> install nginx on the ec2 instance -> do the necessary stuff using nginx to provide reverse proxy -> now no need to provide the port number after the ec2 instance url -> go to certbot to generate ssl certificates -> as certbot only generates ssl certificates for public domains, and i dont have money to buy one, ill use a dynamic dns service(`no-ip.com` in this case)  -> dynamic dns service provides me with a public domain url which points to the IP of my ec2 instance -> now i need to add this url to the nginx file instead of the url of ec2 instance i provided earlier for proxying -> now i can generate ssl certificates for this url -> backend ready 
- using nginx
```
sudo apt update
sudo apt install nginx
```

![](attachments/Pasted%20image%2020241011095622.png)

![](attachments/Pasted%20image%2020241011102045.png)
- I installed nginx, pasted the above code into the newly created `/etc/nginx/nginx.conf` file, after removing the original one which has a lot of default stuff in it that came with installation.


![](attachments/Pasted%20image%2020241011102416.png)
- 502 Bad Gateway because I haven't run my nodeJS server yet.

