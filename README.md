## add logstash pipelines
todo
## setup winlogbeat
### configure winlogbeat.yml
1 setup templates, dashboards etc in elastcisearch/kibana  
1.1 configure elasticsearch output and kibana
```
setup.dashboards.enabled: true
setup.kibana:
  host: "http://<kibana>:5601"
output.elasticsearch:
  hosts: ["http://<elasticsearch>:9200"]
```  
1.2 start setup ```winlogbeat.exe setup```   
1.3 disable elasticsearch output 
```
# output.elasticsearch:
#  hosts: ["http://<elasticsearch>:9200"]
```
2 enable and configure logstash output in winlogbeat.yml
```
output.logstash:
  hosts: ["<logstash>:5044"]
```
### install service
1 run powershell script ```install-service-winlogbeat```
2 star service ```winlogbeat```