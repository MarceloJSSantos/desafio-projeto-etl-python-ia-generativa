# Arquivo Auxiliar da população de dados na API

## O projeto da API:
[Santander Dev Week 2023 Java API (versão modificada)](https://github.com/MarceloJSSantos/santander-dev-week-2023-api-copia-pipeline-dados)

notas:
1) projeto é uma versão para rodar com devcontainer
2) Como o projeto o BD é o H2, criei esse arquivo para guardar os dados a serem populados ao subir ocontainer

---

## Interface Swagger da API
http://api-santander:8080/swagger-ui/index.html

---

## Criada a rede para uso das aplicações
```
docker network create rede_pipeline_etl_python
```
---
## Rota POST
http://api-santander:8080/users

### Cliente 1
```json
{
	"name": "Mariana Silva",
	"account": {
	"number": "12345-6",
	"agency": "0042",
	"balance": 750.50,
	"limit": 1000.00
	},
	"card": {
	"number": "**** **** **** 4321",
	"limit": 1200.00
	}
}
```
### Cliente 2
```json
{
	"name": "Carlos Eduardo Pereira",
	"account": {
	  "number": "98765-4",
	  "agency": "0002",
	  "balance": 150.25,
	  "limit": 500.00
	},
	"card": {
	  "number": "**** **** **** 8899",
	  "limit": 300.00
	}
}
```
### Cliente 3
```json
{
	"name": "Ana Beatriz Souza",
	"account": {
	  "number": "11223-3",
	  "agency": "0101",
	  "balance": 11420.75,
	  "limit": 1500.00
	},
	"card": {
	  "number": "**** **** **** 5566",
	  "limit": 1500.00
	}
}
```
### Cliente 4
```json
{
	"name": "Ricardo Gomes Silva",
	"account": {
	  "number": "44556-7",
	  "agency": "0005",
	  "balance": 1002.30,
	  "limit": 600.00
	},
	"card": {
	  "number": "**** **** **** 2211",
	  "limit": 100.00
	}
}
```
### Cliente 5
```json
{
	"name": "Fernanda Lima Oliveira",
	"account": {
	  "number": "88990-1",
	  "agency": "0023",
	  "balance": 890.00,
	  "limit": 1000.00
	},
	"card": {
	  "number": "**** **** **** 7733",
	  "limit": 800.00
	}
}
```
### Cliente 6
```json
{
	"name": "Jorge Almeida Santos",
	"account": {
	  "number": "33445-5",
	  "agency": "0001",
	  "balance": 0.00,
	  "limit": 50.00
	},
	"card": {
	  "number": "**** **** **** 0011",
	  "limit": 50.00
	}
}
```
---
## Rota PUT
http://api-santander:8080/users/{id}