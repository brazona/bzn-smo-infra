# SERVIDORES DE MONITORAMENTO [ SMO ]

__[descrição do repositório: ]__ Projeto que visa implementar os aplicativos de mercado para observabilidade e monitoramento de sistemas.

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

## Identificadores da Aplicação

| Sigla | Descrição do Projeto | Nome Aplicativo |
| --- | --- | --- |
| SMO | Servidor de Monitoramento | bzn-smo-infra |

__[relação das versões de aplicativos externos: ]__ A aplicação utiliza as seguintes versões:

| Software | Versão |
| --- | --- |
| Vscode | 1.99.3 |
| Docker | 27.5.1 |
| Docker Compose | v2.32.4 |
| Git | 2.45.1 |
| Windows | 10 |

## Deploy da Aplicação

__[descrição do processo de deploy em ambiente cloud: ]__ *NÃO SE APLICA*

### Tabela Branch x Ambiente

| Branch | Ambiente |
| --- | --- |
| develop | Aplica no ambiente __DSV__ |
| release/** | Aplica no ambiente __HMG__ |
| pre-release/** | Aplica no ambiente __STG__ |
| main | Aplica no ambiente __PRD__ |

## Estrutura do projeto

__[descrição da estrutura do diretório: ]__

``` text

├── .github
│   └── workflows
│       └── bzn-smo-infra-grafana.yml
│       └── bzn-smo-infra-jaeger.yml
│       └── bzn-smo-infra-prometheus.yml
│       └── script
│           └── manifest.sh
│    └── branch_ruleset.yml
│    └── dependabot.yml
├── app
│   └── grafana
│      └── deployment.yml
│   └── jaeger
│      └── deployment.yml
│   └── prometheus
│      └── deployment.yml
│   └── compose.yml
├── docs
│   └── CONTRIBUTING.md
│   └── CODE_OF_CONDUCT.md
│   └── PULL_REQUEST_TEMPLATE.md
│   └── SECURITY.md
└── .gitignore
└── README.md
```

## Execução docker compose

__[descrição do processo de execução da aplicação localhost com docker compose: ]__ Para atender a necessidade de executar a os servidor em ambiente local, foi criado um manifesto compose que inicia as configurações iniciais dos servidores, proporcionando os recursos da arquitetura em ambiente **localhost.**

Para executar essa instrução basta abrir o terminal no diretório /app e executar com exemplo abaixo:

```bash
docker compose --env-file .env up -d --build --force-recreate
```

> [!NOTE]
> Para executar o comando acima citado, é necessário incluir no diretório **app/**, o arquivo .env, que fornecerá ao docker compose as variáveis de ambiente.
> Procure o arquiteto do projeto e solicite o arquivo **.env**.

### Verifying Services

Jaeger UI: http://localhost:16686
Hotrod UI: http://localhost:8087
Prometheus: http://localhost:9090
Grafana: http://localhost:3000 (User: admin, Password: admin)

## Licença

> [!IMPORTANT]
> *O código fonte neste projeto não possui licença de uso.*

É terminantemente proibido reproduzir, distribuir, alterar, utilizar engenharia reversa ou valer-se de qualquer tentativa de reverter ao seu código-fonte qualquer dos componentes que compõem o SOFTWARE, bem como utilizar subterfúgios para burlar a quantidade de usuários licenciados.
