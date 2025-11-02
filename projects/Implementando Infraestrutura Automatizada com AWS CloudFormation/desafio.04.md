# Implementando Infraestrutura Automatizada com AWS CloudFormation

## O que é?

O AWS CloudFormation é um serviço que permite criar, configurar e gerenciar recursos da AWS de forma automatizada.
Ele utiliza templates em YAML ou JSON para descrever toda a infraestrutura, como instâncias EC2, bancos de dados RDS, VPCs, entre outros, garantindo padronização e consistência na implantação de ambientes.

## Principais Benefícios

Automação: Criação e gerenciamento de recursos sem intervenção manual, reduzindo erros.

Integração nativa: Funciona com diversos serviços AWS sem necessidade de plugins externos.

Rollback automático: Se ocorrer falha durante a criação da Stack, o CloudFormation reverte os recursos para o estado anterior.

Infraestrutura como Código (IaC): Permite versionar, auditar e controlar alterações na infraestrutura.

Reutilização: Templates podem ser usados em múltiplos ambientes, como desenvolvimento, teste e produção.

## Estrutura Básica de um Template

Um template do CloudFormation é composto por seções principais:

- AWSTemplateFormatVersion: Define a versão do template.

- Description: Breve descrição da Stack.

- Parameters: Variáveis que permitem personalizar a criação de recursos.

- Resources: Elemento principal, onde todos os recursos a serem criados são definidos.

- Outputs: Valores retornados após a criação, como IDs ou URLs.

- Mappings / Conditions / Metadata: Permitem adicionar lógica, organização e informações adicionais ao template.

## Anotação do Fluxo Prático de Uso

1. Criação do Template: Descreva a infraestrutura em YAML/JSON.
2. Upload no CloudFormation Console ou CLI.
3. Definição de parâmetros e nome da Stack.
4. Implantação: CloudFormation provisiona os recursos automaticamente.
5. Monitoramento: Acompanhe o status da Stack (CREATE_IN_PROGRESS, COMPLETE etc.).
6. Gerenciamento: Atualize ou exclua a Stack conforme necessário.

## CloudFormation x Terraform

| Critério                | AWS CloudFormation         | Terraform                              |
| ----------------------- | -------------------------- | -------------------------------------- |
| Provedor                | Exclusivo da AWS           | Multi-cloud (AWS, Azure, GCP, etc.)    |
| Linguagem               | YAML/JSON                  | HCL (HashiCorp Configuration Language) |
| Rollback                | Automático em caso de erro | Necessita configuração manual          |
| Gerenciamento de estado | Interno (na AWS)           | Arquivo de estado (.tfstate)           |
| Integração com AWS      | Nativa                     | Boa, mas via API                       |
| Curva de aprendizado    | Menor para quem usa AWS    | Maior, porém mais flexível             |

##  Insights adquiridos durante o projeto  

Templates em YAML são mais fáceis de ler, embora o JSON também seja compatível.

Stacks ajudam a organizar e gerenciar recursos que fazem parte de um mesmo projeto ou aplicação.

O CloudFormation é ideal para ambientes exclusivamente na AWS, oferecendo integração nativa e suporte oficial.

Reutilizar templates ajuda a minimizar erros humanos e acelera a criação de recursos.

É possível versionar templates usando Git e seguir práticas de DevOps.

O CloudFormation Designer é útil para iniciantes, enquanto a escrita manual dos templates proporciona maior controle e flexibilidade.

## Fontes

- [Documentação Oficial AWS CloudFormation](https://docs.aws.amazon.com/cloudformation)
- [AWS CloudFormation Developer Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)