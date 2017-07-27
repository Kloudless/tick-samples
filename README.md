# tick-samples
Sample [TICKscripts](https://docs.influxdata.com/kapacitor/v1.3/introduction/)
for use with the Kloudless Enterprise Appliance. For more reference scripts
that are meant to work with the data collected by Telegraf, please refer to the
[Kapacitor repository](https://github.com/influxdata/kapacitor/tree/master/examples/telegraf)

## Configuration
All of these scripts default to referencing the `telegraf` database and
`two_weeks` retention policy that are configured by default on the Kloudless
Enterprise Appliance. These can be easily modified according to the needs of
your deployment. By default the scripts output alerts to the Chronograf alert
series and to a log file `/tmp/alerts.log`. Additional actions can be added to
the `.alert` clause. The measurements referenced here are also show without
their prefix, so that would need to be added if it is in use.

## Loading Scripts
In order to load any of the scripts from this repository, they should be copied
to the host running Kapacitor. The following command can be used to load the
script:
```
kapacitor define <TASK_NAME> -tick /PATH/TO/SCRIPT.tick
```
