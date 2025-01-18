#Autor: Fagner Geraldes Braga  
#Data de criação: 17/01/2025  
#Data de atualização: 17/01/2025  
#Versão: 0.01

## Testando múltiplos projetos

#### 1. Baixando projetos do GitHub 
#### 2. Criando DockerFile 
#### 3. Construindo as imagens
#### 4. Executando os containers
#### 5. Fazendo o upload das images ao Docker Hub
#### 6. Criando o compose.yaml com todas as imagens
#### 7. Executando o docker compose
#### 8. Limpeza


### Conectando ao Docker Hub
```bash
docker login
```
<h2>Mini APP que faz o sorteio de uma carta<br>
Criador: Professor José de Assis</h2>

<a href="https://github.com/professorjosedeassis/carta.git" target="_blank">GitHub</a>   
[Dockerfile](carta/Dockerfile)

```bash

docker build -t fagnerfgb/carta:v1 ./carta
docker tag fagnerfgb/carta:v1 fagnerfgb/carta:latest
docker container run --name web-carta -d -p 8080:80 fagnerfgb/carta:v1
docker push fagnerfgb/carta:v1 && docker push fagnerfgb/carta:latest
```
<h2>Game Pedra - Papel - Tesoura<br>
Criador: Professor José de Assis</h2>

<a href="https://github.com/professorjosedeassis/jokenpow.git" target="_blank">GitHub</a>   
[Dockerfile](jokenpow/Dockerfile)

```bash

docker build -t fagnerfgb/jokenpow:v1 ./jokenpow/
docker tag fagnerfgb/jokenpow:v1 fagnerfgb/jokenpow:latest
docker container run --name web-jokenpow -d -p 8081:80 fagnerfgb/jokenpow:v1
docker push fagnerfgb/jokenpow:v1 && docker push fagnerfgb/jokenpow:latest
```
<h2>Simples app para simular uma lâmpada<br>
Criador: Professor José de Assis</h2>

<a href="https://github.com/professorjosedeassis/lamp.git" target="_blank">GitHub</a>   
[Dockerfile](lamp/Dockerfile)

```bash
docker build -t fagnerfgb/lamp:v1 ./lamp/
docker tag fagnerfgb/lamp:v1 fagnerfgb/lamp:latest
docker container run --name web-lamp -d -p 8082:80 fagnerfgb/lamp:v1
docker push fagnerfgb/lamp:v1 && docker push fagnerfgb/lamp:latest
```
<h2>Cálculo do combustivel mais vantajoso<br>
Criador: Professor José de Assis</h2>

<a href="https://github.com/professorjosedeassis/etagas.git" target="_blank">GitHub</a>   
[Dockerfile](etagas/Dockerfile)

```bash
docker build -t fagnerfgb/etagas:v1 ./etagas/
docker tag fagnerfgb/etagas:v1 fagnerfgb/etagas:latest
docker container run --name web-etagas -d -p 8083:80 fagnerfgb/etagas:v1
docker push fagnerfgb/etagas:v1 && docker push fagnerfgb/etagas:latest
```
<h2>Site Robótica Prática<br>
Criador: Professor José de Assis</h2>

<a href="https://github.com/professorjosedeassis/roboticapratica.git" target="_blank">GitHub</a>   
[Dockerfile](roboticapratica/Dockerfile)

```bash
docker build -t fagnerfgb/robotica:v1 ./roboticapratica/
docker tag fagnerfgb/robotica:v1 fagnerfgb/robotica:latest
docker container run --name web-robotica -d -p 8084:80 fagnerfgb/robotica:v1
docker push fagnerfgb/robotica:v1 && docker push fagnerfgb/robotica:latest
```
<h2>Site Astro Júpiter<br>
Criador: Fagner Geraldes Braga</h2>

<a href="https://github.com/fagnerfgb/astrojupiter.git" target="_blank">GitHub</a>   
[Dockerfile](astrojupiter/Dockerfile)

```bash
docker build -t fagnerfgb/astro:v1 ./astrojupiter/
docker tag fagnerfgb/astro:v1 fagnerfgb/astro:latest
docker container run --name web-astro -d -p 8085:80 fagnerfgb/astro:v1
docker push fagnerfgb/astro:v1 && docker push fagnerfgb/astro:latest
```
<h2>Conversão de Temperatura<br>
Criador: Fabricio Veronez</h2>

<a href="https://github.com/KubeDev/conversao-temperatura.git" target="_blank">GitHub</a>   
[Dockerfile](conversao-temperatura/src/Dockerfile)

```bash
docker build -t fagnerfgb/conversao:v1 ./conversao-temperatura/src
docker tag fagnerfgb/conversao:v1 fagnerfgb/conversao:latest
docker container run --name web-conversao -d -p 8086:8080 fagnerfgb/conversao:v1
docker push fagnerfgb/conversao:v1 && docker push fagnerfgb/conversao:latest
```
### Limpeza
```bash
docker container rm -f $(docker container ls -qa)
```

### Executando os containers com o Docker compose

[Compose](compose.yaml)
```bash
docker compose up -d
```

### Encerrando os containers com o Docker compse
```bash
docker compose down
```

### Limpeza
```bash
docker container rm -f $(docker container ls -qa)
docker image rm -f $(docker image ls -qa)
docker image prune
docker system prune
```



