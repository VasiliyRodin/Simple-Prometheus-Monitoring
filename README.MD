Simple Monitoring Installation

Requirements:1x Ubuntu Server (20.04 LTS)
Docker Engine installed.
Docker Compose installed.

Installation:

1. 	Install latest version of Docker CE from  

2. 	Install Docker Compose.

3. 	Execute the following commands on the Linux Host.
		sudo curl -L https://github.com/docker/compose/releases/download/1.23.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
		sudo chmod +x /usr/local/bin/docker-compose

4. 	Copy over SimpleMonitoring directory provided to /home/user/ in the Ubuntu Environment.

5. 	Open SimpleMonitoring directory.
		cd simpleMonitoring

6. 	Run docker-compose up to start simplemonitoring_web, cadvisor, prometheus, grafana, node_exporter.
		sudo docker-compose up -d

7. 	Verify all services started correctly.
		Starting simplemonitoring_web_1   ... done
		Starting monitoring_cadvisor      ... done
		Starting monitoring_prometheus    ... done
		Starting monitoring_grafana       ... done
		Starting monitoring_node_exporter ... done
	
8. 	Access the web application by going to localhost:8080. You can use privateIP:8080 if you aren't hosting it locally. 
		"Hello World!" should be at the top of the screen.
		
9.	Access Prometheus at localhost:9090 or privateIP:9090
10. Access Grafan at localhost:3000 or privateIP:3000
		Login with credentials: admin/MYPASSWORT
11. 