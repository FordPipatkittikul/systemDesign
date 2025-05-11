# Networks

# 1 Load Balancer

- Load balancer is a machine that runs a reverse proxy software.

- It is being used for distribute the requests between multiple servers that host the actual application.

## 1.1 algorithm that load balancer use

- Round Robin: works to distribute network traffic across multiple servers in a rotating.

For example, sending req to server 1 and then 2 and then 3 and then come back to one again


## 1.2 types of load balancers

- Layer 4 : Transport layer has access to TCP, UDP, IP, Port

- Layer 7 : Application layer has access to everything layer 4 has and also access to HTTP headers, cookies and payload

## 1.3 benefits

make system more scalable and resilient(E.X. one server fail, load balancer know and dont send req to it).


# 2 CDN

Content delivery network allow placing static assets close to the users. It is good chocie for CSS, Images, HTML and Javascript.

# 2.1 benefits

- decrease latency
- reduces costs