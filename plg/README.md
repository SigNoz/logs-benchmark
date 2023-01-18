
## PLG stack
It contains the deployment of grafana and loki which will accept data from promtail running in other VMs

## Steps to run the server
* Run docker-compose inside plg-server
* Add the prometheus datasource in the grafana UI
* import hostmeterics dashboard with id : 1860
    In cpu graph for cpu change stack series to never.
* import loki dashboard : 14055


## Steps to run the clients
It contains the deployment of promtail to collect data from docker containers and push it loki running the server
* Copy the ip of the VM where plg-server is running and replace the value of `url` in `plg-client/promtail.yml`
* Run docker-compose inside plg-client



## Current Problems with Promtail
* One promtail cannot forward to another promtail, it directly writes to loki
* Promtail can only read from a file (won't have been a problem if the above was not an issue)

## FluentD with Loki Plugin
* Promtail will be removed
* FluentD will run on the client machines as well as this machine where loki is running.
* https://grafana.com/docs/loki/latest/clients/fluentd/