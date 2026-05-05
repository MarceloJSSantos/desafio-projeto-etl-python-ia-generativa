# 🔃 Desafio ETL com Python e IA Generativa

![ETL Pipeline](https://img.shields.io/badge/ETL-Pipeline-blue?style=for-the-badge&logo=python)
![Gemini AI](https://img.shields.io/badge/Gemini-AI-orange?style=for-the-badge&logo=google)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)
![Docker](https://img.shields.io/badge/Docker-Container-blue?style=for-the-badge&logo=docker)

## 📋 Descrição do Projeto

Este projeto implementa um pipeline ETL (Extract, Transform, Load) utilizando Python e Inteligência Artificial Generativa para personalizar mensagens de marketing para clientes bancários. O objetivo é envolver os clientes de forma mais personalizada, enfatizando a importância dos investimentos através de mensagens geradas por IA.

O desafio foi desenvolvido como parte do **Bootcamp DIO - TOTVS - Fundamentos de Engenharia de Dados e Machine Learning**, utilizando uma API Java modificada (**Santander Dev Week 2023**) para simular dados de um ambiente bancário real.

## 🎯 Objetivo

Como cientista de dados de um grande banco, a tarefa é:
- **Personalizar** o engajamento com clientes através de mensagens de marketing direcionadas.
- **Utilizar IA Generativa** (Gemini) para criar conteúdo relevante e personalizado.
- **Integrar** com APIs REST para extração e atualização de dados.

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Descrição |
|------------|-----------|
| ![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat&logo=python) | Linguagem principal para o pipeline ETL |
| ![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange?style=flat&logo=jupyter) | Ambiente de desenvolvimento e execução |
| ![Gemini AI](https://img.shields.io/badge/Gemini-AI-orange?style=flat&logo=google) | IA Generativa para criação de mensagens |
| ![Requests](https://img.shields.io/badge/Requests-HTTP-green?style=flat&logo=python) | Biblioteca para requisições HTTP |
| ![Pandas](https://img.shields.io/badge/Pandas-Data--Analysis-blue?style=flat&logo=pandas) | Manipulação de dados CSV |
| ![Docker](https://img.shields.io/badge/Docker-Container-blue?style=flat&logo=docker) | Containerização da API |
| ![Java](https://img.shields.io/badge/Java-API-red?style=flat&logo=java) | API Santander (backend) |

## 📊 Pipeline ETL

### 📥 Extract (Extração)
1. **Leitura do CSV**: Carrega lista de IDs de usuários do arquivo `ids-clientes.csv`
2. **Requisições GET**: Para cada ID, consome a API `GET /users/{id}` para obter dados do cliente

### ⚙️ Transform (Transformação)
1. **IA Generativa**: Utiliza Google Gemini para gerar mensagens personalizadas
2. **Personalização**: Mensagens enfatizam investimentos baseadas no perfil do cliente
3. **Enriquecimento**: Adiciona conteúdo relevante à lista "news" de cada usuário

### 📤 Load (Carregamento)
1. **Atualização**: Envia mensagens via `PUT /users/{id}` para atualizar dados na API
2. **Persistência**: Salva as mudanças no banco de dados H2 da aplicação

## 🚀 Como Executar

### Pré-requisitos
- Docker e Docker Compose instalados
- Conta Google Cloud com API Gemini habilitada
- Chave da API Gemini configurada

### Passos de Execução

1. **Clone o repositório da API**:
   ```bash
   git clone https://github.com/MarceloJSSantos/santander-dev-week-2023-api-copia-pipeline-dados
   ```

2. **Configure a rede Docker**:
   ```bash
   docker network create rede_pipeline_etl_python
   ```

3. **Suba a API**:
   ```bash
   cd santander-dev-week-2023-api-copia-pipeline-dados
   docker-compose up -d
   ```

4. **Popule a API**:
   Use oda dos do arquivo: `dados/dados-a-serem-populados.md` ou gere seus próprios.
     - Swagger UI: `http://api-santander:8080/swagger-ui/index.html`


4. **Configure a API Key do Gemini** no notebook:
   ```python
   GOOGLE_API_KEY = "sua-chave-aqui"
   ```

5. **Execute o notebook**:
   - Abra `notebooks/desafio-etl-jupyter-notebook.ipynb`
   - Execute todas as células sequencialmente

## 📁 Estrutura do Projeto

```
📦 desafio-etl-python
├── 📂 dados/
│   ├── 📄 dados-a-serem-populados.md    # Dados auxiliares para população da API
│   └── 📄 ids-clientes.csv              # Lista de IDs dos clientes
├── 📂 notebooks/
│   └── 📄 desafio-etl-jupyter-notebook.ipynb  # Pipeline ETL principal
└── 📄 README.md                         # Este arquivo
```

## 📈 Resultados Esperados

Após a execução bem-sucedida, cada cliente terá sua lista "news" atualizada com uma mensagem personalizada gerada por IA, como:

> 💡 **Investimento Inteligente**: Mariana, com seu saldo atual, considere diversificar seus investimentos. Uma carteira equilibrada pode ajudar a proteger seu patrimônio contra a inflação!

## 🔗 APIs Utilizadas

- **Santander API**: `http://api-santander:8080`
  - `GET /users/{id}` - Obter dados do cliente
  - `PUT /users/{id}` - Atualizar dados do cliente
  - Swagger UI: `http://api-santander:8080/swagger-ui/index.html`

- **Google Gemini API**: Para geração de texto com IA

## 🤝 Contribuição

Este projeto foi desenvolvido como desafio individual, mas sugestões e melhorias são bem-vindas!

## 📄 Licença

Este projeto é parte do **Bootcamp DIO - TOTVS - Fundamentos de Engenharia de Dados e Machine Learning** e foi desenvolvido para o desafio de projeto **Explorando IA Generativa em um Pipeline de ETL com Python**.

---

⭐ **Dica**: Execute o notebook célula por célula para acompanhar o progresso do pipeline ETL e visualizar os dados sendo processados em tempo real!