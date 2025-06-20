# bzn-smo-infra
Projeto que visa implementar os aplicativos de mercado para observabilidade e monitoramento de sistemas


#######################

## Diferenças entre Monitoramento e Observabilidade

| Característica | Monitoramento | Observabilidade |
| --- | --- | --- |
| Objetivo | Detectar falhas e garantir o bom funcionamento do sistema. | Compreender previamente algo que possa acarretar num problema para o sistema. |
| Dados coletados | Métricas como CPU, RAM, tempo de resposta. | Logs, métricas e traces. |
| Resolução de problemas | Compreender um erro de sistema. | Permite identificar a causa do erro. |
| Escopo | Focado em informações conhecidas e problemas comuns. | Aprofunda no entendimento de eventos incomuns. |
| Ação proativa | Configuração de alertas para comunicar problemas. | Informações detalhadas de um problema complexa. |

## Ferramentas de Monitoramento e Observabilidade [ opções ]

- Jaeger
- OpenLens
- Graylog
– Dynatrace
– DataDog
- Elastic Stack (ELK)
- Prometheus
- Grafana

## Ferramentas de Monitoramento e Observabilidade

### JAEGER

- https://www.jaegertracing.io/
- https://hub.docker.com/r/jaegertracing/jaeger

### GRAFANA / PROMETHEUS

- https://grafana.com/docs/grafana/latest/getting-started/get-started-grafana-prometheus/
- https://medium.com/xp-inc/monitorando-aplica%C3%A7%C3%B5es-docker-com-prometheus-e-grafana-593f507fc17

### Build Compose

```bash
sudo git pull && sudo docker compose --env-file .env up -d --build --force-recreate
```

### Verifying Services

Jaeger UI: http://localhost:16686
Prometheus: http://localhost:9090
Grafana: http://localhost:3000 (User: admin, Password: admin)