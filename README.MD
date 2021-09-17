Simple Monitoring Installation

Requirements:1x Ubuntu Server (20.04 LTS)
Docker Engine installed.
Docker Compose installed.

Installation:
1. 	Open SSH terminal to your Ubuntu Host.

2. 	Install latest version of Docker CE from  https://docs.docker.com/engine/install/ubuntu/

3. 	Install Docker Compose.
		sudo curl -L https://github.com/docker/compose/releases/download/1.23.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
		sudo chmod +x /usr/local/bin/docker-compose
		
	Test the installation 
		docker-compose --version

4. 	Copy SimpleMonitoring directory provided to /home/user/ in the Ubuntu Environment.

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
		
	You can check the individual logs by checking
		sudo docker logs ##container name##
	
8. 	Access the web application by accesing localhost:8080 or privateIP:8080 in a browser. 
		"Hello World!" should be at the top of the screen.
		
9.	Access Prometheus at localhost:9090 or privateIP:9090

10. Access Grafan at localhost:3000 or privateIP:3000
		Login with credentials: admin/MYPASSWORT

Import Custom Grafana Dashboard
1.	Login to Grafana,

2.	On the left click the "+" symbol and click Import.

3. 	Copy and paste the contents of simpleMonitoringDashboard.json included to load the dashboard. This will take you directly to the imported dashboard.