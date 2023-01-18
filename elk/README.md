## ELK stack

* Dashboards
    * Import elasticsearch dashboard with ID : 6483
    * Import node exporter dashboard with ID : 13978
    
* Removing the default heap limit, without setting it manually https://stackoverflow.com/a/71929849.
    Default value got set to   "-Xms15706m",
          "-Xmx15706m",
          curl localhost:9200/_nodes/_all/jvm

## Credits
Most of these configurations has been adapted from https://github.com/deviantony/docker-elk

## Steps to run
* Run docker-compose.yaml of elk-server in one VM.
* Copy the ip of that VM and replace the value of host in `elk-client/pipeline/logstash.conf`
* Run docker-compose.yaml of elk-client in the other VMs.