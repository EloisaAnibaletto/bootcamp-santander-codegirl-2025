# Criando sua Primeira Stack com AWS CloudFormation

## O que é?

O AWS CloudFormation é um serviço que possibilita criar, configurar e gerenciar recursos da AWS de maneira automatizada, usando templates em YAML ou JSON. Ele segue o conceito de Infraestrutura como Código (IaC), permitindo versionar, replicar e atualizar toda a infraestrutura de forma segura e padronizada.

## Principais benefícios

Automatização: cria e configura recursos automaticamente sem intervenção manual.

Controle de versões: os templates podem ser versionados junto ao código da aplicação.

Rollback automático: desfaz alterações caso alguma etapa de criação da Stack falhe.

Reprodutibilidade: possibilita reproduzir ambientes idênticos a partir de um mesmo template.

Gerenciamento simplificado: permite criar, atualizar ou excluir múltiplos recursos em um único passo.

Integração com outros serviços AWS: funciona junto com Lambda, EC2, S3, IAM e outros serviços.

## O que é uma Stack?

Uma Stack (pilha) é um grupo de recursos da AWS (como instâncias EC2, buckets S3, funções Lambda, entre outros) que são criados e gerenciados de forma conjunta através de um template do CloudFormation.

Cada Stack é baseada em um template que define a infraestrutura desejada.

É possível atualizar ou remover todos os recursos de uma Stack de uma só vez.

Exemplo: uma Stack pode conter todos os recursos necessários para rodar um ambiente de aplicação completo, incluindo rede, servidores, banco de dados e permissões.

## Como criar uma Stack pelo Console AWS

- Acesse o Console da AWS e abra o CloudFormation.

- Clique em Create stack → With new resources (standard).

- Escolha como deseja criar a Stack:

    - Usando um template pronto da AWS,

    - Fazendo upload de um arquivo YAML/JSON,

    - Ou informando a URL de um template armazenado no S3.

- Defina o nome da Stack e os parâmetros necessários (valores variáveis do template).

- Revise as configurações, autorize a criação de recursos IAM se necessário, e clique em Create stack.

- Acompanhe o progresso na aba Events até que o status seja CREATE_COMPLETE.

- Visualize todos os recursos criados na aba Resources.

## Fontes

- [AWS CloudFormation - Documentação Oficial](https://docs.aws.amazon.com/pt_br/AWSCloudFormation/latest/UserGuide/Welcome.html)
- [AWS CloudFormation - Conceitos Básicos](https://aws.amazon.com/pt/cloudformation/faqs)