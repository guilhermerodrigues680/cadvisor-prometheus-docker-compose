# Monitorando Docker com [cAdvisor](https://github.com/google/cadvisor), [Prometheus](https://github.com/prometheus/prometheus) e [Grafana](https://github.com/grafana/grafana)

Todos serviços necessários configurados no Docker Compose, permitindo o inicio das métricas com um único comando.

## Executando

```sh
# execute em segundo plano no terminal
$ docker-compose up -d
# ou execute em primeiro plano no terminal
$ docker-compose up
```

## Credenciais

**Grafana**

|  user | password |
|:-----:|:--------:|
| admin |   admin  |

## Métricas

- [cadvisor - prometheus.md](https://github.com/google/cadvisor/blob/master/docs/storage/prometheus.md)

## Referências

<details>
  <summary>Referências</summary>

https://prometheus.io/docs/guides/cadvisor/

https://stackoverflow.com/questions/40327062/how-to-calculate-containers-cpu-usage-in-kubernetes-with-prometheus-as-monitori

https://stackoverflow.com/questions/58895929/how-to-calculate-percentage-of-specific-pod-cpu-usage-on-each-node


MAC

https://gitmemory.com/issue/google/cadvisor/1565/742351042

https://medium.com/@karthi.net/use-google-cadvisor-for-monitoring-your-containers-docker-tutorial-eebbe4ee82da


Grafana

https://grafana.com/grafana/dashboards/893

https://medium.com/@mertcan.simsek276/docker-monitoring-with-cadvisor-prometheus-and-grafana-adefe1202bf8


http://localhost:9090/graph?g0.expr=rate(container_cpu_usage_seconds_total%7Bname%3D%22elastic_euclid%22%7D%5B1m%5D)&g0.tab=0&g0.stacked=0&g0.range_input=5m&g1.expr=sum%20(rate%20(container_cpu_usage_seconds_total%7Bname%3D~%22ela.*%22%7D%5B1m%5D))%20%2F%20sum%20(machine_cpu_cores%7B%7D)%20*%20100&g1.tab=0&g1.stacked=0&g1.range_input=15m&g2.expr=sum(rate(container_cpu_usage_seconds_total%7Bname%3D%22elastic_euclid%22%7D%5B1m%5D))&g2.tab=0&g2.stacked=0&g2.range_input=15m&g3.expr=sum(rate(container_cpu_usage_seconds_total%5B1m%5D))%20by%20(name)&g3.tab=0&g3.stacked=0&g3.range_input=1h&g4.expr=container_memory_usage_bytes%7Bid%3D~%22%2Fdocker%2F.*%22%7D&g4.tab=0&g4.stacked=0&g4.range_input=1h


rate(container_cpu_usage_seconds_total{name="elastic_euclid"}[1m])
sum (rate (container_cpu_usage_seconds_total{name=~"ela.*"}[1m])) / sum (machine_cpu_cores{}) * 100
sum(rate(container_cpu_usage_seconds_total[1m])) by (name)
container_memory_usage_bytes{id=~"/docker/.*"}



sum(rate(container_cpu_usage_seconds_total{id=~"/docker/.*"}[1m])) by (name)
</details>
