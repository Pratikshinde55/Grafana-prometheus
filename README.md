# Grafana interact with Prometheus and Prometheus is connected to Linux-os

### Step-1: Grafana Download

Grafana is downloaded on aws ec2 AMI-amazon linux2.

Edit inbound rule of Grafana instance.

Command for download Grafana:

      wget https://dl.grafana.com/enterprise/release/grafana-enterprise-11.2.0.linux-amd64.tar.gz

extract Grafana:

       tar -zxvf grafana-enterprise-11.2.0.linux-amd64.tar.gz

Start Grafana server :
     
       ./grafana-server

![image](https://github.com/user-attachments/assets/b1128cfe-818f-4210-9dd8-f98c2016e4d8)


### Step-2:  Prometheus download 

Prometheus is used for monitoring metrics and Alerting. Prometheus collect data and store at own DataBase(TSDB).

Prometheus collect metrics from any system with help of Agent or Agentless.

Prometheus download on AWS EC2 instance using amazon linux-2 AMI.

Edit inbound rule of prometheus for access.

Command for download Prometheus:

[Prometheus-link](https://prometheus.io/download/) , open link copy link adress and download tar file.

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

   Prometheus protocol = "HTTP"

 ![image](https://github.com/user-attachments/assets/214060d2-1ba9-4e28-ba59-dd6383cbd0c7)

### Step-3: Grafana connect with Prometheus

On Grafana DashBoard Go to "Connection" option and serach Prometheus and Click on "Add new DataSource" Button.

![image](https://github.com/user-attachments/assets/4e20d69d-4fb7-47ce-b250-f1fd7cbad2cd)

- Put Protocol name + Public Ip + port no of prometheus system -->> http://3.111.57.86:9090
  
![image](https://github.com/user-attachments/assets/f1878fa5-40eb-4a4c-8947-7dc327d909b1)

Save and test, Now Grafana Connected to Prometheus.


### Step-4: Linux OS configure and install Node_exporter

I use amazon linux2 EC2 instance for linux operating system and i collect metrics of this instance/OS.

##### Prometheus Node_exporter:

This is Prometheus agent which is installed on target system, and this Node_exporter collect metrics of target system and expose to the Prometheus system.

Install Node exporter (https://prometheus.io/download/) Refer this link for download Node_exporter for linux and Copy link address and download tar file.

Command Download Node_exporter:

    wget https://github.com/prometheus/node_exporter/releases/download/v1.8.2/node_exporter-1.8.2.linux-amd64.tar.gz


Extract Note_exporter:

    tar -xvzf node_exporter-1.8.2.linux-amd64.tar.gz

Go to Node_exporter:

     cd node_exporter-1.8.2.linux-amd64

Start Prometheus Node_exporter command:

     ./node_exporter &


- Note:

 Prometheus Node_exporter exposes metrics on port no = "9100"

 Prometheus Node_exporter protocol = "HTTP"


 We can Access node exporter from google also ->> protocol name + public Ip of Instance + port no -->>  http://65.0.131.182:9100/metrics

 ![image](https://github.com/user-attachments/assets/e39b30df-6eac-40c5-98be-78821a2a25bf)


 ### Add Linux OS to Prometheus:

 On Prometheus EC2 terminal we add target node that linux OS where i installed Prometheus Node_exporter.

 - Note:

   "promethus.yml" this is prometheus config file here we add target node details.
 
![image](https://github.com/user-attachments/assets/2fd90053-efca-4690-a5dc-2512b15e6b25)

![image](https://github.com/user-attachments/assets/3e1a35bf-233b-400f-ada9-63a24b595397)


 
After doing change in prometheus.yml config file then need restart Prometheus server for apply change:

Command for delete prometheus process :

    pkill prometheus

Command for Start Prometheus server:

    ./prometheus &

![image](https://github.com/user-attachments/assets/2c807b28-ba35-49dd-8e00-995b29062c2f)

 Added  Linux OS to prometheus using Node_exporter

![image](https://github.com/user-attachments/assets/97dc88f8-fade-48bc-acd0-f461255eae74)


### Grafana

Grafana is connected to prometheus and Prometheus is connected to Linux OS. Here i create Dashboard of Linux OS metrics.

![image](https://github.com/user-attachments/assets/871cae3d-cf07-45bf-a85f-addf596cdc76)

       

      
     

    
