![](attachments/Pasted%20image%2020241108222203.png)
- window - global object
- browser contains all these web APIs
- to access these web APIs in the javascript code, we do so using the window global object
- ![](attachments/Pasted%20image%2020241108222750.png)
- event loop checks if there are processes inside the callback queue and pushes them into the call stack
![](attachments/Pasted%20image%2020241108224946.png)

- microtask queue is given priority
- all the callback functions which come through promises will go to microtask queue
- Processes in callback queue will begin executing only when all the processes in the microtask queue have completed execution
- 