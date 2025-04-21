# VictoriaMetricsLabs

```
NAME                	NAMESPACE 	REVISION	UPDATED                                 	STATUS  	CHART                          	APP VERSION
alloy               	monitoring	12      	2025-04-19 20:38:23.383416834 +0200 CEST	deployed	alloy-1.0.1                    	v1.8.1     
grafana             	monitoring	9       	2025-04-19 21:04:02.461967394 +0200 CEST	deployed	grafana-8.12.1                 	11.6.0     
victoria-logs-single	monitoring	1       	2025-04-19 19:19:20.856860011 +0200 CEST	deployed	victoria-logs-single-0.9.6     	v1.19.0    
vm                  	monitoring	1       	2025-04-19 10:14:26.102163942 +0200 CEST	deployed	victoria-metrics-cluster-0.20.1	v1.115.0   
vmagent             	monitoring	1       	2025-04-19 10:45:07.204807714 +0200 CEST	deployed	victoria-metrics-agent-0.18.2  	v1.115.0   
```


```
$ helm upgrade prometheus prometheus-community/prometheus  --values prometheus.values.yaml 
Release "prometheus" has been upgraded. Happy Helming!
NAME: prometheus
LAST DEPLOYED: Mon Apr 21 17:05:46 2025
NAMESPACE: monitoring
STATUS: deployed
REVISION: 3
TEST SUITE: None
NOTES:
The Prometheus server can be accessed via port 80 on the following DNS name from within your cluster:
prometheus-server.monitoring.svc.cluster.local

From outside the cluster, the server URL(s) are:
http://prometheus.local


The Prometheus alertmanager can be accessed via port 9093 on the following DNS name from within your cluster:
prometheus-alertmanager.monitoring.svc.cluster.local


Get the Alertmanager URL by running these commands in the same shell:
  export POD_NAME=$(kubectl get pods --namespace monitoring -l "app.kubernetes.io/name=alertmanager,app.kubernetes.io/instance=prometheus" -o jsonpath="{.items[0].metadata.name}")
  kubectl --namespace monitoring port-forward $POD_NAME 9093
#################################################################################
######   WARNING: Pod Security Policy has been disabled by default since    #####
######            it deprecated after k8s 1.25+. use                        #####
######            (index .Values "prometheus-node-exporter" "rbac"          #####
###### .          "pspEnabled") with (index .Values                         #####
######            "prometheus-node-exporter" "rbac" "pspAnnotations")       #####
######            in case you still need it.                                #####
#################################################################################


The Prometheus PushGateway can be accessed via port 9091 on the following DNS name from within your cluster:
prometheus-prometheus-pushgateway.monitoring.svc.cluster.local


Get the PushGateway URL by running these commands in the same shell:
  export POD_NAME=$(kubectl get pods --namespace monitoring -l "app=prometheus-pushgateway,component=pushgateway" -o jsonpath="{.items[0].metadata.name}")
  kubectl --namespace monitoring port-forward $POD_NAME 9091

For more information on running Prometheus, visit:
https://prometheus.io/
```