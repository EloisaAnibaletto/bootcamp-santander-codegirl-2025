# Explorando Workflows Automatizados com AWS Step Functions

## O que é?

O **AWS Step Functions** é um serviço da **Amazon Web Services** que possibilita organizar e automatizar vários serviços e funções dentro de um fluxo de trabalho visual, chamado de máquina de estados (state machine).
Ele é bastante usado para orquestrar funções **Lambda**, executar tarefas de forma assíncrona ou paralela e gerenciar decisões em aplicações distribuídas, tudo isso sem a necessidade de administrar servidores.

## Como funciona?

O Step Functions atua como um orquestrador de tarefas, determinando a ordem de execução de funções, chamadas de APIs ou outros serviços AWS, mantendo o estado e os dados entre cada etapa.

O fluxo é definido em JSON usando a Amazon States Language (ASL), onde você especifica:

- A sequência das etapas (states);

- Condições para transição entre etapas;

- Tratamento de erros e exceções;

- Lógica de repetição e execução paralela.

Durante a execução, o Step Functions registra cada etapa, permitindo monitoramento visual e depuração diretamente no console da AWS.

## Componentes de um Workflow no AWS Step Funtions

| Componente | Descrição |
| ---------- | --------- |
| State Machine | Representa o fluxo completo de execução (workflow). |
| State (Estado) | Cada etapa individual do fluxo, podendo ser uma tarefa, decisão, espera, entre outros. |
| Task State | Executa uma tarefa específica, como chamar uma função Lambda ou outro serviço AWS. |
| Choice State | Permite definir caminhos alternativos com base em condições (if/else). |
| Parallel State | Executa múltiplas tarefas ao mesmo tempo. |
| Wait State | Insere uma pausa antes da próxima etapa. |
| Pass State | Transfere dados adiante sem executar nenhuma ação. |
| Fail/Succeed State | Define o término do fluxo, seja por sucesso ou falha. |

## Benefícios

- **Serverless e totalmente gerenciado**: sem necessidade de gerenciar infraestrutura.
- **Monitoramento visual**: acompanha cada execução em tempo real.
- **Integração nativa com diversos serviços AWS**: Lambda, DynamoDB, ECS, SNS, SQS, Glue, entre outros.
- **Tolerância a falhas**: permite reexecução automática, catch e retry.
- **Escalabilidade automática**: ajusta-se à demanda sem intervenção manual.
- **Baixo acoplamento**: facilita a manutenção e evolução das aplicações.

## Insights adquiridos

- Step Functions vai além de um simples orquestrador: oferece clareza, rastreabilidade e resiliência para fluxos complexos.
- A linguagem declarativa (ASL) torna a manutenção e documentação mais simples.
- Funções Lambda se encaixam de maneira natural nesse modelo, reduzindo a complexidade do código.
- A visualização gráfica ajuda a identificar gargalos e problemas rapidamente.
- É ideal para arquiteturas baseadas em microserviços, event-driven e pipelines de dados.

## Fontes

- [AWS Step Functions](https://aws.amazon.com/pt/step-functions/)
- [AWS Step Functions Developer Guide(Amazon States Languages)](https://states-language.net/spec.html)
- [AWS Samples on GitHub](https://github.com/aws-samples)