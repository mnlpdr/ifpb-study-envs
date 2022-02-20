# Ambientes de estudo das disciplinas dockerizados

A maioria das disciplinas do curso de Sistemas para Internet do IFPB exige a instalação de servidores e SDKs das linguagens de programação lecionadas no curso.
Em algum momento as instalações acabam sendo processos bem maçantes, perdendo seu potencial didático.
Com esta solução, pretendemos evitar as instalações de recursos em máquinas virtuais, usando, para isso, containers.


## Contexto

Para quem ainda não entende bem o que são containers, mas já estão familiarizados com máquinas virtuais, esclarecemoss que são praticamente a mesma coisa, sendo uma das principais diferenças a desnecessidade de instalar um sistema operacional em um hardware virtual, como no caso das VMS.
Os containers executam como processos compartilhando os recursos do host.

Alguns podem crer que o uso desta solução pode ser detrimental, alegando que substituiria o conhecimento de configurar cada um dos componentes manualmente, mas para quem procura economizar tempo pode ser bastante útil.

Sintam-se à vontade para solicitar um ambiente ou tirar dúvidas.


## Como usar

Dentro da pasta de cada discplina existe um arquivo README.md explicando como poderá ser utilizado para o desenvolvimento das atividades.

## Sobre o docker-compose.yml

- Em cada diretório de disciplina é possível encontrar um arquivo chamado `docker-compose.yml`;
- Esse arquivo define a infraestrutura do ambiente de desenvolvimento;
- O docker trabalha com containers, que são similares a máquinas virtuais;
- O arquivo `docker-compose.yml` geralmente vai definir 3 chaves na raiz:
    - **version**: versão da linguagem utilizada no docker-compose
    - **services**: serviços que serão criados (equivalente a VMs)
    - **networks**: define uma rede na qual os containers serão inseridos
- Dentro de services você vai encontrar a definição dos containers, por exemplo:
    - O serviço **pgadmin** define o nosso cliente web para o gerenciar o servidor
    - O serviço **db** define o container que conterá nosso servidor de banco de dados postgres
- Dentro de cada **serviço** no `docker-compose.yml` você poderá encontrar algumas definições, como:
    - **image**: É a nossa *blueprint* de como construir aquele container
    - **ports**: Mapeia a porta do host (sua máquina) para uma porta do container, permitindo acessar containers em localhost
    - **environment**: São variáveis de ambiente que estarão disponíveis dentro do container
    - **volumes**: Os volumes sincronizam pastas no host para dentro do container
