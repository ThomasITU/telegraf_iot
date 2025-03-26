#

### Docker 
docker-compose up -d

#### Fix wrong IP address, environment variabels

docker-compose stop telegraf
docker-compose rm -f telegraf
docker-compose up -d telegraf 

docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' influxdb

- [ ] To do create network to fix alias


### grafana
http://localhost:3000

Add InfluxDB as a data source:
Go to Configuration > Data Sources
Select InfluxDB
Set URL to http://influxdb:8086

#### listen to mqtt using mosquitto

`mosquitto_sub -h eu1.cloud.thethings.network -p 1883 -t "#" -u <"applicationID@ttn"> -P <"apaToken"">`

### influx config, if authentication fails

`influx config create --active --config-name default-1 -u http://172.26.0.3:8086  --token <influx token> -o itu`
