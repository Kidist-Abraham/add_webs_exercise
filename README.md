### AddWebs Exercise

### Docker configuration for PHP app

[docker-compose.yml](/docker-compose.yml) - contains a docker compose configuration for Nginx, PGP, and MySql containers.

[nginx](/nginx) - contains a configuration for nginx

You can find the deployed Application at https://addwebs.3.137.215.113.nip.io/

###### SSL configuration

[Letsencrypt](https://letsencrypt.org/)  is used to configure ssl to the domain. 



### Montioring

[Prometheus](https://prometheus.io/) is used to scrap metrics for docker containers. 

[cAdvisor](https://digital.ai/technology/cadvisor) is used for exporting the docker container data from our server

[Grafana](https://grafana.com/) is used for visualizing and aleritg 

Grafana dashboard [id 1482](https://grafana.com/grafana/dashboards/14282) is used for a cAdvisor dashboard.

Email will be send on high memory usage of containers. A custom `grafana.ini` file is used for adding smtp server configuration for gmail. 


### Navigating through the server

* To ssh use the command `ssh -i <ssh identitiy key> ubuntu@3.137.215.113`. 

* Linux screen is used for different sessions.

`screen -r prom` will resume the session that is running promethus,cAdvisor and grafana

`screen -r try` will resume the session that is running php application 

#### TODO
* Add SSL for grafana and promethus console url. 
* Make PHP a dynamic app instad of static 
