
# Ambiente de estudos para disciplina de Banco de Dados II - IFPB
Rapidamente constrói o ambiente de estudos com o Docker e docker-compose.

## Dependências

- Docker Compose 
- Docker 

## Como usar

- Copie este repositório
- Acesse a pasta do repositório clonado para sua máquina
- Execute o comando abaixo:
```sh
docker-compose up
```
- Acesse o Pgadmin em localhost:8081 
    - O login e senha estão definidos no `docker-compose.yml`. São esses:
        - PGADMIN_DEFAULT_EMAIL=postgres@admin.com
        - PGADMIN_DEFAULT_PASSWORD=postgres

- Clique em **Add New Server**
    - Em connection o hostname será **db**
    - A senha e login também estarão no `docker-compose.yml`
        - POSTGRES_PASSWORD=postgres
        - POSTGRES_USERNAME=postgres

## Explicação

- Neste repositório você vai encontrar um arquivo chamado `docker-compose.yml`;
- Esse arquivo define a infraestrutura do ambiente de desenvolvimento;
- O docker trabalha com containers, que são similares a máquinas virtuais;
- O arquivo `docker-compose.yml` vai definir 3 chaves na raiz:
  - **version** = versão do docker
  - **services** = serviços que serão criados (equivalentes a VMs)
  - **networks** = define uma rede na qual os containers serão inseridos
- Dentro de services você vai encontrar a definição dos containers;
    - O serviço **pgadmin** define o nosso cliente web para o gerenciar o servidor
    - O serviço **db** define o container que conterá nosso servidor de banco de dados postgres
- Dentro de cada serviço dede `docker-compose.yml` você encontrará
    - image = É a nossa *blueprint* de como construir aquele container
    - ports = Mapeia a porta do host (sua máquina) para uma porta do container, permitindo acessar containers em localhost
    - environment = São variáveis de ambiente que estarão disponíveis dentro do container.

