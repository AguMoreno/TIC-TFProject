influxdb database
-> user: admin
-> password: password
-> database: iotdb

-- -- -- -- influx command -- -- -- -- 
influx -username admin -password password
show databases
use iotdb
show measurements
select * from sensorGen order by time desc limit 5
// delete from sensorGen	
-------------------
grafana
-> user: admin
-> password: password
-> measurement: temperature, humidity, vibrations, batteryVoltage
-------------------
docker run -it -p 1883:1883 -p 9001:9001 \
-v /srv/mqtt/config:/mqtt/config:ro \
-v /srv/mqtt/log:/mqtt/log \
-v /srv/mqtt/data/:/mqtt/data/ \
--name mymosquitto toke/mosquitto
-------------------



