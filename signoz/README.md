## SigNoz

* Dashboards
    Copy the dashboards from the `dashboards` folder and import them to signoz.
## Steps to run
* Run docker-compose.yaml of signoz-server in one VM.
* Copy the ip of that VM and replace the value of `endpoint` in `signoz-client/otel-collector-config.yaml`
* Run docker-compose.yaml of signoz-client in the other VMs.