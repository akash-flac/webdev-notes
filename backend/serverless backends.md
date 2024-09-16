"Serverless" is a backend deployment in which a cloud provider dynamically manages the allocation and provisioning of servers. The term "serverless" doesn't mean there are no servers involved. Instead, it means that developers and operators do not have to worry about the servers. 

### Easier defination

What if you could just write your `express routes` and run a command. The app would automatically

1. Deploy
2. Autoscale
3. Charge you on a `per request` basis (rather than you paying for VMs)

### Problems with this approach

1. More expensive at scale
2. Cold start problem : When it's been a while and there have been no requests sent to your server, as soon as the first request is sent, the server takes some time to start and respond. This is the cold start problem in simple words.

### Famous serverless providers
- AWS Lambda
- Google Cloud Functions
- Cloudflare Workers

