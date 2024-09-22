# Grafana-prometheus
Grafana interact with Prometheus and Prometheus is connected to Linux-os


### Grafana Download

Grafana is downloaded on aws ec2 AMI-amazon linux2.

Edit inbound rule of Grafana instance.

Command for download Grafana:

      wget https://dl.grafana.com/enterprise/release/grafana-enterprise-11.2.0.linux-amd64.tar.gz

extract Grafana:

       tar -zxvf grafana-enterprise-11.2.0.linux-amd64.tar.gz

Start Grafana server :
     
       ./grafana-server

![image](https://github.com/user-attachments/assets/b1128cfe-818f-4210-9dd8-f98c2016e4d8)


### Prometheus download 

Prometheus download on AWS EC2 instance using amazon linux-2 AMI.

Edit inbound rule of prometheus for access.

Command for download Prometheus:

(Link- https://prometheus.io/download/) copy link adress and download tar file.

      wget https://github.com/prometheus/prometheus/releases/download/v2.53.2/prometheus-2.53.2.linux-amd64.tar.gz

Extract Prometheus:

      tar -xvzf prometheus-2.53.2.linux-amd64.tar.gz
      
Go Prometheus:

      cd prometheus-2.53.2.linux-amd64

Start Prometheus server:

       ./ prometheus

Access on google->> public Ip + port no

- Note:

   Prometheus work on port number = "9090"

   Prometheus protocol = "Http"

 ![image](https://github.com/user-attachments/assets/214060d2-1ba9-4e28-ba59-dd6383cbd0c7)
 
     
       

      
     

    
