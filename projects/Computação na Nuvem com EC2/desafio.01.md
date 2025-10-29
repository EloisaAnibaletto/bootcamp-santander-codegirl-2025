# Descrição do Desafio

Este laboratório tem como objetivo consolidar seus conhecimentos em gerenciamento de instâncias EC2 na AWS. O entregável é um repositório organizado contendo anotações e insights adquiridos durante a prática, servindo como material de apoio para os seus estudos e futuras implementações.

# Meu Desafio

Para esse desafio eu usei como base apenas as explicações dadas e explicadas nas aulas, onde criei um sistema simples sobre uma clínica médica.

# Arquitetura da Solução

![clinica-medica](bootcamp-santander-codegirl-2025\projects\images\clinica-medica.jpg)

# Esse fluxograma mostra:

- Médico(a) e secretário(a) interagindo com os sistemas.
- **Amazon S3** como repositório central de documentos, exames e atestados.
- **AWS Lambda** processando cadastro/alteração/exlusão/visualização de pacientes e agenda/consultas feitas pelo(a) secretário(a) 
e cadastro/alteração/exlusão/visualização de pacientes, consultas, exames, atestados e históricos feitos pelo(a) médico(a).
- **Amazon RDS** como banco relacional para pacientes, consultas, exames, atestados, históricos e agenda.
