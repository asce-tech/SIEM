# Steps:

Step 1: Set up the ELK Stack
- Elasticsearch installation command:
```bash
sudo apt update
sudo apt install elasticsearch
```
- After installation, start and enable Elasticsearch
```bash
sudo systemctl start elasticsearch
sudo systemctl enable elasticsearch
```

- Logstash Installation:
```bash
sudo apt install logstash
```
- Configure Logstash to collect logs from multiple sources (firewalls, servers, endpoints).
  
- Kibana installation:
```bash
sudo apt install kibana
```
- Start and enable it
```bash
sudo systemctl start kibana
sudo systemctl enable kibana
```

Step 2: Configure Logstash
- Create a Logstash Configuration File named `logstash.conf`
- Start Logstash with the configuration file
```bash
logstash -f logstash.conf
```

Step 3: Collect logs from various sources
- logs from Windows and Linux
- Linux:
```bash
sudo cp /var/log/auth.log /path/to/logs/
sudo cp /var/log/syslog /path/yo/logs/
```
- Windows: Use Event Viewer to export logs to a file named `.evtx`

- Application Logs: Collect from web servers, Databases, and other applications.
```bash
sudo cp /var/log/apache2/access.log /path/to/logs/
sudo cp /var/log/apache2/error.log /path/to/logs/
```

Step 4: Analyze logs in Kibana 
- Open Kibana in a web browser at `http://localhost:5601`
- Configure Kibana to connect to Elasticsearch and create an index pattern for your logs.

- Create Dashboards and Visualizations:
- Use Kibana to create visualizations and dashboards for monitoring log data.
- Example:
   - Failed login attempts.
   - Unusual Network Activity.

Step 5:
- Set up Alerts: Configure alerts in Kibana to notify you of suspicious activity.
- Example
   - Multiple failed login attempts.
   - high network traffic.
- Investigate Suspicious activity:
   - Use Kibana to dig down into logs and investigate suspicious activity
   - Example
      - Identify the source IP address, usernames, and timestamps of failed login attempts.
      - Determine the source and destination IP addresses, ports, and protocols involved in unusual network traffic
