# Projeto Docker de Microsserviços com Nginx, Apache e MySQL

## Descrição

Este projeto é uma implementação local do cenário de microsserviços apresentado por Denilson Bonatti (DIO), substituindo os serviços AWS por containers Docker. A arquitetura consiste em:

- **1 Container MySQL**: Banco de dados

- **3 Containers Apache/PHP**: Aplicação web

- **1 Container Nginx**: Load balancer

## Pré-requisitos

- Docker instalado

- Docker Compose instalado

- Git (para clonar o repositório)

## Como Executar

1. **Clone o repositório** (se aplicável):

bash

```bash
git clone https://github.com/seu-usuario/repositorio.git
cd repositorio
```

2. **Construa e inicie os containers**:

bash

```bash
docker-compose up --build -d
```

3. **Acesse a aplicação**:\
   Abra no navegador:

```html
http://localhost:8080
```

## Verificação

1. **Verifique os containers em execução**:

bash

```bash
docker-compose ps
```

2. **Teste o balanceamento de carga**:

bash

```bash
watch -n 1 curl -s http://localhost:8080
```

Observe como as requisições são distribuídas entre os 3 containers da aplicação (app1, app2, app3).

3. **Verifique os dados no banco**:

bash

```bash
docker-compose exec db mysql -u root -pSenha123 meubanco -e "SELECT * FROM dados;"
```

Isso mostrará os registros inseridos pela aplicação PHP.

## Como Parar

Para encerrar os containers:

bash

```bash
docker-compose down
```
