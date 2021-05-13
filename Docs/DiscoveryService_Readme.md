# Discovery Service (Consul)  
For this project, we used [Spring Cloud Consul](https://spring.io/projects/spring-cloud-consul) to integrate [Consul](https://www.consul.io/) from Hashicorp as a Discovery service. We deployed all of our services in Docker containers on seperate VMs with their own virtual networks. We tried running a single instance of Consul on our Gateway VM and managed to get Consul and the Gateway service to communicate with Consul and pass all health checks. Based on this success, we moved forward, but encountered problems when the different instances of Consul were in different virtual networks. As a result, we used the discovery service to register the services in the ecosystem, but were unable to utilize all of its functionality, including getting service addresses.  
## What we Tried  
- Using `--network host` in the docker run configuration to use the hosts network instead of Dockers.
- Running seperate instances of Consul on each VM and registering them as nodes with a leader.

## What to Try  
- Different combination of ip addresses with `-bind`, `-advertise` and `-client` to allow different Consul nodes to communicate locally with services on the same host and with other Consul nodes on different hosts.





