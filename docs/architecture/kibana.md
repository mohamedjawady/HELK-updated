# Kibana

![](../images/KIBANA-Design.png)

## Visualize your logs

### Discover

Make sure you have logs being sent to your HELK first (At least Windows security and Sysmon events). Then, go to `https://<HELK's IP>` in your preferred browser. If you don’t see logs right away then update your time picker (in the top right) to include a farther back window. Additionally, if you just started sending logs then wait a minute and check again.

Currently, HELK creates automatically 7 index patterns for you and sets **logs-endpoint-winevent-sysmon-*** as your default one:

* "logs-*"
* "logs-endpoint-winevent-sysmon-*"
* "logs-endpoint-winevent-security-*"
* "logs-endpoint-winevent-application-*"
* "logs-endpoint-winevent-system-*"
* "logs-endpoint-winevent-powershell-*"
* "logs-endpoint-winevent-wmiactivity-*"

![](../images/KIBANA-Discovery.png)

## Dashboards

Currently, the HELK comes with 3 dashboards:

### Global_Dashboard

![](../images/KIBANA-GlobalDashboard.png)

### Network_Dashboard

![](../images/KIBANA-NetworkDashboard.png)

### Sysmon_Dashboard

![](../images/KIBANA-SysmonDashboard.png)

## Monitoring Views (x-Pack Basic Free License)

### Kibana Initial Overview

![](../images/MONITORING-Kibana-Overview.png)

### Elasticsearch Overview

![](../images/MONITORING-Elasticsearch-Overview.png)

### Logstash Overview

![](../images/MONITORING-Logstash-Overview.png)

![](../images/MONITORING-Logstash-Nodes-Overview.png)

## Troubleshooting

Apart from running `docker ps` and `docker logs --follow --tail 25 helk-kibana`, additionally you can look at logs located at `/usr/share/kibana/config/kibana.log`.

Example: `docker exec helk-kibana tail -f /usr/share/kibana/config/kibana.log`

Many times Kibana will not be "working" because elasticsearch is still starting up or has ran into an error.
