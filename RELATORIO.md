# Relatório – Criação de Ambiente de Testes na AWS

## Introdução

Durante a realização desta atividade foi criado um ambiente de testes na plataforma Amazon Web Services (AWS) utilizando recursos de rede e computação. O objetivo foi compreender como esses componentes se relacionam para permitir que uma aplicação ou servidor seja acessado pela internet de forma segura.

Foram criados os seguintes recursos: VPC, Subnet, Internet Gateway, Route Table, Security Group e uma instância EC2 executando o sistema operacional Amazon Linux.

## VPC (Virtual Private Cloud)

A VPC é uma rede virtual privada criada dentro da AWS. Ela funciona como o ambiente principal onde todos os demais recursos serão hospedados. Ao criar uma VPC, é possível definir uma faixa de endereços IP e controlar como os recursos se comunicam entre si e com a internet.

Nesta atividade foi utilizada a rede 10.0.0.0/16, permitindo a criação de diversas sub-redes dentro do mesmo ambiente.

## Subnet (Sub-rede)

A subnet é uma divisão da VPC. Sua função é organizar os recursos da rede e definir onde as instâncias serão implantadas.

Foi criada uma sub-rede pública com o endereço 10.0.1.0/24. Essa configuração permite que os recursos nela hospedados possam receber um endereço IP público e, consequentemente, serem acessados pela internet quando devidamente configurados.

## Internet Gateway

O Internet Gateway é o componente responsável por conectar a VPC à internet. Sem ele, os recursos criados dentro da rede privada não conseguiriam enviar ou receber tráfego externo.

Após sua criação, o Internet Gateway foi associado à VPC para permitir a comunicação entre a instância EC2 e a internet.

## Route Table (Tabela de Rotas)

A tabela de rotas define o caminho que os pacotes de rede devem seguir para alcançar seus destinos.

Nesta atividade foi adicionada uma rota padrão (0.0.0.0/0) apontando para o Internet Gateway. Isso significa que todo o tráfego destinado a endereços externos será encaminhado para a internet.

Além disso, a tabela foi associada à sub-rede pública, permitindo que os recursos nela hospedados utilizem essa rota.

## Security Group

O Security Group funciona como um firewall virtual para controlar o tráfego de entrada e saída das instâncias.

Foi criada uma regra permitindo acesso SSH pela porta 22 apenas a partir do endereço IP do próprio usuário. Essa configuração aumenta a segurança do ambiente, evitando acessos não autorizados ao servidor.

## Instância EC2

A Amazon EC2 (Elastic Compute Cloud) é um serviço que permite criar máquinas virtuais na nuvem.

Foi criada uma instância utilizando o sistema operacional Amazon Linux e uma configuração gratuita compatível com a conta AWS. A instância recebeu um endereço IP público e foi associada ao Security Group criado anteriormente.

Através dessa instância foi possível realizar acesso remoto utilizando o protocolo SSH, comprovando que todos os recursos da infraestrutura estavam configurados corretamente.

## Conclusão

A atividade permitiu compreender o funcionamento dos principais componentes de rede da AWS e como eles trabalham em conjunto para disponibilizar recursos na internet de forma segura.

A VPC forneceu o ambiente de rede, a subnet organizou os recursos, o Internet Gateway permitiu a comunicação externa, a tabela de rotas definiu os caminhos do tráfego, o Security Group garantiu a segurança dos acessos e a instância EC2 forneceu o servidor virtual utilizado nos testes.

O resultado final foi um ambiente funcional e acessível via SSH, demonstrando na prática os conceitos fundamentais de computação em nuvem utilizando a AWS.

