Aqui está a versão atualizada do `README.md`, incluindo a nova funcionalidade para exibição do histórico completo em uma página separada.

---

# Sentiment Analyzer

Este é um projeto de análise de sentimentos utilizando **Flask**, **SQLAlchemy** e a biblioteca **VADER Sentiment** para classificar o sentimento de textos como **Positivo**, **Negativo** ou **Neutro**.

## Tecnologias Utilizadas

- **Flask**: Framework web para desenvolvimento de aplicações web em Python.
- **SQLAlchemy**: ORM para trabalhar com bancos de dados relacionais em Python.
- **VADER Sentiment**: Biblioteca para análise de sentimentos de textos, com foco em textos curtos como comentários de redes sociais.
- **SQLite**: Banco de dados local para armazenamento das análises de sentimentos.

## Funcionalidades

- **Análise de Sentimentos**: Permite ao usuário inserir um texto, que será analisado e classificado como "Positivo", "Negativo" ou "Neutro".
- **Armazenamento de Resultados**: Os resultados da análise (texto e sentimento) são armazenados no banco de dados SQLite.
- **Histórico de Análises Resumido**: Exibe os 5 resultados mais recentes diretamente na página inicial.
- **Histórico Completo de Análises**: Possui uma página separada para visualização de todas as análises realizadas, acessível através de um link.

## Como Rodar o Projeto

### 1. Clonar o Repositório

Primeiro, clone o repositório para o seu computador:

```bash
git clone https://github.com/Midress-ui/sentiment-analyzer.git
cd sentiment-analyzer
```

### 2. Criar um Ambiente Virtual

Crie e ative um ambiente virtual para o projeto:

- **Windows**:

  ```bash
  python -m venv venv
  venv\Scripts\activate
  ```

- **Linux/macOS**:

  ```bash
  python3 -m venv venv
  source venv/bin/activate
  ```

### 3. Instalar as Dependências

Instale as dependências do projeto utilizando o `pip`:

```bash
pip install -r requirements.txt
```

Ou, se preferir, instale as dependências manualmente:

```bash
pip install flask flask_sqlalchemy vaderSentiment
```

### 4. Rodar o Projeto

Agora, execute o servidor Flask com o comando:

```bash
python app.py
```

O servidor estará rodando em `http://127.0.0.1:5000`. Abra esse endereço em seu navegador para começar a usar a aplicação.

### 5. Acessar a Aplicação

- Insira um texto na caixa de texto e clique em "Analisar Sentimento".
- O sentimento do texto será exibido como "Positivo", "Negativo" ou "Neutro".
- Os 5 resultados mais recentes serão exibidos na página inicial.
- Para visualizar todo o histórico, clique no link **"Ver histórico completo"** na página inicial.

## Estrutura do Projeto

```
sentiment-analyzer/
│
├── app.py              # Arquivo principal com a lógica da aplicação Flask
├── requirements.txt    # Lista de dependências do projeto
├── templates/          # Pasta com templates HTML
│   ├── index.html      # Página principal com o formulário e histórico resumido
│   └── history.html    # Página de histórico completo
└── static/             # Arquivo(s) de estilo (CSS) e scripts (JS)
    ├── style.css       # Arquivo de estilo
    └── script.js       # Arquivo de script (opcional)
```

## Configuração do Banco de Dados

O banco de dados utilizado é o **SQLite**, e o arquivo será criado automaticamente com o nome `sentiments.db`. A tabela criada no banco de dados tem o seguinte formato:

```sql
CREATE TABLE sentiment (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    text TEXT NOT NULL,
    sentiment TEXT NOT NULL
);
```

### 1. Criação do Banco de Dados

Na primeira execução do projeto, o banco de dados será criado automaticamente utilizando o comando:

```python
db.create_all()
```

## Contribuições

Contribuições são bem-vindas! Se você tiver ideias ou melhorias, sinta-se à vontade para criar um **fork** do projeto, implementar as mudanças e enviar um **pull request**.

## Licença

Este projeto está licenciado sob a **MIT License** - veja o arquivo [LICENSE](LICENSE) para mais detalhes.
