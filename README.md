# Traffic Analysis 2

Deploy Netflow and Stenographer to analyze network traffic based on Traffic Analysis.

### Prometheus
Because we want to store the data for a long time, we build a customized docker based on the offical docker file. Also you can build it by yourself.
- tasks/prometheus.yml files/prometheus.yml(config) files/prometheus.service(service)

### Grafana
We use json files to make the dashboards, so you can't edit them in the WebUI.  
You only can directly modify the json file.
- tasks/grafana.yml files/grafana.ini(config) files/grafana.service(service)
- files/stenographer.json files/snmp.json files/netflow.json(dashboards)

### Cadvisor
The monitor of docker containers. You can find document at https://github.com/google/cadvisor
- tasks/cadvisor.yml files/cadvisor.service(service)

### SNMP
You should use the snmp-generator to produce the config file for snmp-exporter   
The detail instruction is the comments in snmp.yml
- tasks/snmp.yml files files/snmp\_exporter.service(service)
- files/snmp.json(produced by snmp-generator)

### Stenographer
Customized config you can find at https://github.com/google/stenographer.
We provide server pem and you also can generate them by yourself.
- tasks/stenographer.yml files/stenographer\_config.yml(config) files/stenographer.service(service)
- files/ca\_cert.pem files/server\_cert.pem files/server\_key.pem(authentication key)

### Netflow
Start the netflow nfdump
- netflow.yml

### Blackbox-exporter
Use ICMP to test whether your servicers are alive or not.  
Document is here: https://github.com/prometheus/blackbox\_exporter
- blackbox.yml
