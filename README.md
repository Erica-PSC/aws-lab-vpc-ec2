# aws-lab-vpc-ec2
# Laboratório AWS – VPC, Rede e EC2

## Objetivo

Criar manualmente um ambiente de testes na AWS utilizando recursos de rede e computação, permitindo o acesso remoto a uma instância EC2 através do protocolo SSH.

## Recursos Criados

* VPC (10.0.0.0/16)
* Subnet Pública (10.0.1.0/24)
* Internet Gateway
* Route Table
* Security Group
* Instância EC2 Amazon Linux

## Etapas Realizadas

1. Criação da VPC.
2. Criação da Subnet pública.
3. Configuração do Internet Gateway.
4. Configuração da tabela de rotas.
5. Criação do Security Group.
6. Implantação da instância EC2.
7. Teste de acesso SSH.

## Evidências

As capturas de tela do laboratório estão disponíveis na pasta `imagens`.

## Resultado

A instância EC2 foi criada com sucesso e ficou acessível via SSH através do endereço IP público fornecido pela AWS.
