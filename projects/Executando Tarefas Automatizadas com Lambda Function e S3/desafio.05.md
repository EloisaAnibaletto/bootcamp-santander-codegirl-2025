# Executando Tarefas Automatizadas com Lambda Function e S3

##  O que é o AWS Lambda?  

O AWS Lambda é um serviço serverless que possibilita rodar código automaticamente em resposta a eventos, como envios de arquivos para o S3, mudanças em bancos de dados ou requisições HTTP via API Gateway.

Basta criar a função, configurar o gatilho desejado, e o Lambda se encarrega de executar o código, escalar conforme a demanda e gerenciar a infraestrutura necessária.

##  O que é o Amazon S3?  

O Amazon S3 (Simple Storage Service) é um serviço de armazenamento de objetos confiável e escalável, projetado para guardar diversos tipos de dados, como arquivos, imagens, logs, backups e conteúdos estáticos.

Ele pode ser integrado ao AWS Lambda, permitindo que ações automáticas sejam executadas sempre que arquivos forem adicionados, modificados ou removidos no bucket.

## Hands-On: Upload de Arquivos com Processamento e Registro no DynamoDB

### **Fluxo de execução**

1. O usuário faz **upload de um arquivo** (por exemplo, dados.csv) em um bucket do S3.
2. O evento ObjectCreated é disparado, **acionando automaticamente a função Lambda**.
3. A função Lambda **lê o arquivo**, processa as informações necessárias e **armazena os metadados** (como nome, tamanho e data do processamento) em uma tabela do **DynamoDB**.
4. O resultado do processamento pode ser salvo em outro bucket S3 ou usado em outros serviços (como SNS ou CloudWatch).

## Serviços AWS utilizados

- **S3** → Armazenamento e gatilho de evento.
- **Lambda** → Execução automatizada de código.
- **DynamoDB** → Registro e persistência de metadados.
- **IAM** → Controle de permissões e roles de acesso.
- **CloudWatch** → Logs e monitoramento.
- **LocalStack** → Ambiente local para testes sem custos AWS reais.

## AWS Local com LocalStack

O **LocalStack** simula localmente os serviços da AWS, permitindo desenvolver e testar a integração Lambda + S3 + DynamoDB sem custo.

### Exemplo de configuração (`docker-compose.yml`)

```yaml
version: "3.8"
services:
  localstack:
    image: localstack/localstack:2.1
    environment:
      - SERVICES=s3,lambda,dynamodb,iam,cloudwatch
      - DEFAULT_REGION=us-east-1
    ports:
      - "{porta:porta}"
    volumes:
      - "./localstack:/tmp/localstack"
      - "/var/run/docker.sock:/var/run/docker.sock"
```

## Passo a passo da implementação

1. **Criar recursos básicos**
   - Bucket S3 (`meu-bucket-uploads`)
   - Tabela DynamoDB (`Processos`) com chave primária `FileId`.
2. **Criar função Lambda**
   - Código processa o evento do S3, extrai metadados e grava registro no DynamoDB.
3. **Configurar trigger**
   - Adicionar evento `s3:ObjectCreated:*` para invocar a Lambda.
4. **Testar fluxo**
   - Fazer upload de arquivo → Lambda executa → Registro criado no DynamoDB.
5. **Verificar logs**
   - Monitorar saídas e erros no CloudWatch Logs ou console local.

## Fontes

- [AWS Lambda - Documentação Oficial](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
- [Amazon S3 - Documentação Oficial](https://docs.aws.amazon.com/s3/index.html)
- [Amazon DynamoDB - DOcumentação Oficial](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html)
- [LocalStack - Documentação Oficial](https://docs.localstack.cloud/)
- [Exemplo AWS - S3 Trigger Lambda](https://docs.aws.amazon.com/lambda/latest/dg/with-s3-example.html)