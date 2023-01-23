
### Logs Benchmark

This repo contains the setup for the all the three stacks i.e SigNoz, ELK and PLG used for benchmarking.

Each of the folders contains it's own set of instructions on how to run them.

The results of the benchmark are published here [benchmark](https://signoz.io/blog/logs-performance-benchmark/?utm_source=github&utm_medium=logs-benchmark)

### Benchmark Key Findings: A summary
For any log management tool to be efficient, the following three factors are very important.

#### Ingestion
Distributed cloud-native applications can generate logs at a humungous scale. Log management tools should be efficient at ingesting log data at scale.

#### Query
Logs help in troubleshooting, and troubleshooting should be fast. The end-user experience depends on how fast a user can query relevant logs.

#### Storage
Storage is costly and logs data is often huge. Log management tools need to be efficient in storing logs.

#### Findings
- For ingestion, we found SigNoz to be 2.5x faster than ELK and consumed 50% less resources.
- For querying benchmarks, we tested out different types of commonly used queries. While ELK was better at performing queries like COUNT, SigNoz is 13x faster than ELK for aggregate queries.
- Storage used by SigNoz for the same amount of logs is about half of what ELK uses.
- Loki doesn’t perform well if you want to index and query high cardinality data. In our setup for Loki we were not able to push it to ingest high cardinality labels/indexes.

### Version Info :
* Logstash: 8.4.3
* Elasticsearch: 8.4.3
* Promtail:2.6.1
* Loki: 2.6.1
* Grafana: 9.2.1
* Signoz-otel-collector: 0.55.3
* Clickhouse-server: 22.4.5

---

Note: We saw Loki team has [recently shared](https://twitter.com/sukhanisandeep/status/1615243908241588224) some improvements in querying speed, but this benchmark is not updated based on this update and we have not verified if it would help in high cardinality data. If anyone in the community has been able to get good performance for high cardinality data, we would love to learn more.
