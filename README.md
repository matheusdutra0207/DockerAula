# Contêiner

Um container é um ambiente isolado utilizado para empacotar aplicações. Containers têm o objetivo de segregar e facilitar a portabilidade de aplicações em diferentes ambientes. Um container contém um conjunto de processos que são executados a partir de uma imagem, imagem esta que fornece todas as dependências necessárias.

# Vantagens em utilizar contêineres 

### Portabilidade 

Os contêineres encapsulam aplicativos e todas as suas dependências em um pacote isolado. Isso torna os contêineres altamente portáteis, permitindo que os aplicativos sejam executados consistentemente em qualquer ambiente que suporte contêineres, desde ambientes de desenvolvimento local até nuvens públicas ou privadas.

### Consistência de Ambiente

Os contêineres garantem que os aplicativos sejam executados de maneira consistente em diferentes ambientes, eliminando problemas causados por diferenças na configuração do sistema operacional ou nas bibliotecas de software. Isso simplifica o desenvolvimento, teste e implantação de aplicativos, garantindo uma experiência uniforme em todos os estágios do ciclo de vida do desenvolvimento de software.

### Eficiência de Recursos

Os contêineres compartilham o kernel do sistema operacional hospedeiro e são mais leves que as máquinas virtuais tradicionais. Isso resulta em uma utilização mais eficiente dos recursos de hardware, permitindo que mais contêineres sejam executados em um único servidor físico e reduzindo os custos operacionais associados ao provisionamento e gerenciamento de infraestrutura.

### Escalabilidade

Os contêineres podem ser implantados e dimensionados rapidamente conforme a demanda, permitindo que os aplicativos respondam de maneira ágil a picos de tráfego ou carga de trabalho. Ferramentas de orquestração de contêineres, como Kubernetes, Docker Swarm e Amazon ECS, facilitam a automação do dimensionamento horizontal e vertical dos contêineres, garantindo uma escalabilidade eficiente e confiável.

### Isolamento

Os contêineres fornecem isolamento de recursos entre aplicativos, garantindo que eles não interfiram uns com os outros e evitando conflitos de dependências. Isso permite que diferentes versões de uma mesma biblioteca ou serviço sejam executadas simultaneamente em contêineres separados, sem causar conflitos ou complicações.

### Facilidade de Implantação e Atualização

Os contêineres simplificam o processo de implantação e atualização de aplicativos, permitindo que eles sejam empacotados juntamente com todas as suas dependências e configurações em um único artefato. Isso facilita a distribuição de novas versões de aplicativos e a implementação de atualizações de segurança de forma rápida e consistente.

# Docker

## O que são containers?

Container é o nome dado para a segregação de processos no mesmo kernel, de forma que o processo
seja isolado o máximo possível de todo o resto do ambiente.
Em termos práticos são File Systems, criados a partir de uma "imagem" e que podem possuir
também algumas características próprias.

## O que são imagens Docker ?

Uma imagem Docker é a materialização de um modelo de um sistema de arquivos, modelo este
produzido através de um processo chamado build.
Esta imagem é representada por um ou mais arquivos e pode ser armazenada em um repositório.

## Construção de uma imagem

Processo para gerar uma nova imagem a partir de um arquivo de instruções. O comando docker
build é o responsável por ler um Dockerfile e produzir uma nova imagem Docker.

## Exemplo

Aplicação: Um servidor em flask que exibe o texto "Olá, eu gosto de docker" [ao clicar aqui](http://127.0.0.1:8080/Boas-vindas).
A aplicação completa encontra-se nesse diretório.

### Image

- Requirements: flask==2.0.1

- Dockerfile:

```
FROM python:3.7-alpine
COPY . /app

WORKDIR /app

RUN pip install -r requirements.txt

```
- Build the image:

```
docker build --tag=flaskboasvindas .
```
### Containers
- Run the Container

```  
sudo docker run -it --rm --name flaskboasvindasContainer -p 8080:8000 flaskboasvindas python3 serverFlask.py
```

## Outros repositórios

- [Exemplo do luiz](https://github.com/luizcarloscf/docker-basic)
- [Trabalho final da disciplina laboratorio de redes](https://github.com/matheusdutra0207/MonitoringLabRedes)

