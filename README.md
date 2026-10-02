# 🗄️ Simulador de Banco de Dados Relacional

> Um simulador educacional e interativo de banco de dados relacional desenvolvido inteiramente em **HTML, CSS e JavaScript**, permitindo executar consultas SQL diretamente no navegador, sem necessidade de instalação ou configuração de um servidor de banco de dados.

---

## 📌 Sobre o Projeto

O **Simulador de Banco de Dados Relacional** foi desenvolvido com o objetivo de facilitar o aprendizado dos principais conceitos de bancos de dados relacionais de maneira **visual, prática e interativa**.

A aplicação simula um pequeno banco de dados de um cenário de **e-commerce**, contendo tabelas relacionadas de clientes e pedidos.

Em vez de utilizar um banco de dados real como MySQL ou PostgreSQL, o projeto utiliza **JavaScript para manipular os dados em memória** e `localStorage` para garantir a persistência das alterações realizadas pelo usuário.

Tudo funciona diretamente no navegador e pode ser executado a partir de **um único arquivo HTML**.

---

## 🎯 Objetivos

O projeto foi criado principalmente para:

- Demonstrar conceitos fundamentais de bancos de dados relacionais.
- Facilitar o aprendizado de comandos SQL.
- Demonstrar relacionamentos entre tabelas.
- Permitir testes de consultas sem instalar um SGBD.
- Apresentar uma interface visual para manipulação dos dados.
- Demonstrar como JavaScript pode simular operações de banco de dados.
- Explorar persistência de dados utilizando `localStorage`.

---

## 🚀 Funcionalidades

### 📊 Banco de Dados Simulado

A aplicação trabalha com duas tabelas principais:

### `clientes`

| Campo   | Descrição                      |
| ------- | ------------------------------ |
| `id`    | Identificador único do cliente |
| `nome`  | Nome do cliente                |
| `email` | E-mail do cliente              |

### `pedidos`

| Campo        | Descrição                     |
| ------------ | ----------------------------- |
| `id`         | Identificador único do pedido |
| `cliente_id` | Referência ao cliente         |
| `produto`    | Produto comprado              |
| `valor`      | Valor do pedido               |

As tabelas possuem uma relação semelhante à encontrada em bancos de dados relacionais reais.

```text
clientes
   │
   │ id
   │
   ▼
pedidos
cliente_id
```

---

## 💻 Console SQL

O sistema disponibiliza um console SQL integrado à interface.

O usuário pode escrever consultas e visualizar os resultados diretamente na aplicação.

### Exemplo de SELECT

```sql
SELECT * FROM clientes;
```

Retorna todos os registros existentes na tabela `clientes`.

---

### Consulta com filtro

```sql
SELECT * FROM clientes WHERE id = 1;
```

Permite buscar registros específicos utilizando uma condição.

---

### INSERT

Também é possível adicionar novos registros através de comandos SQL.

```sql
INSERT INTO clientes (nome, email)
VALUES ('Samuel Lazarin', 'samuel@email.com');
```

Após a execução, o novo cliente é inserido na estrutura de dados simulada e a interface é atualizada.

---

## 🔗 Relacionamentos e JOIN

Um dos principais objetivos do projeto é demonstrar como tabelas relacionadas podem ser consultadas em conjunto.

Exemplo:

```sql
SELECT clientes.nome, pedidos.produto, pedidos.valor
FROM clientes
JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```

Esse tipo de consulta demonstra o conceito de relacionamento entre entidades utilizando uma chave primária e uma chave estrangeira.

---

## ⚡ Exemplos Prontos

Para facilitar a utilização, o sistema disponibiliza consultas pré-configuradas que podem ser executadas rapidamente.

Esses exemplos permitem experimentar diferentes operações SQL sem que o usuário precise escrever os comandos manualmente.

Entre os conceitos demonstrados estão:

- `SELECT`
- `INSERT`
- `WHERE`
- `JOIN`
- Relacionamentos entre tabelas
- Chaves primárias
- Chaves estrangeiras

---

## 💾 Persistência com LocalStorage

Embora o projeto não utilize um banco de dados real, as alterações realizadas pelo usuário podem ser persistidas utilizando o armazenamento local do navegador.

A aplicação utiliza:

```javascript
localStorage;
```

para salvar o estado atual dos dados.

Isso permite que registros adicionados durante a utilização continuem disponíveis mesmo depois de atualizar a página.

Também existe a possibilidade de **restaurar os dados originais**, retornando o simulador ao estado inicial.

---

# 🛠️ Tecnologias Utilizadas

## HTML5

Responsável pela estrutura e organização da aplicação.

Utilizado para criar:

- Layout principal.
- Console SQL.
- Tabelas.
- Botões.
- Painéis.
- Elementos de interação.

---

## Tailwind CSS

Utilizado através de CDN para criação da interface visual.

O projeto utiliza um design inspirado em **painéis administrativos e ferramentas de desenvolvimento**, com foco em:

- Dark Mode.
- Responsividade.
- Componentes visuais.
- Espaçamento consistente.
- Feedback visual.
- Interface semelhante a ferramentas SQL.

---

## FontAwesome

Utilizado para fornecer ícones à interface.

Exemplos de utilização:

- Banco de dados.
- Tabelas.
- Terminal.
- Consultas.
- Ações.
- Status do sistema.

---

## JavaScript — Vanilla JS

É o principal responsável pelo funcionamento da aplicação.

O JavaScript controla:

- Interpretação dos comandos SQL suportados.
- Manipulação dos registros.
- Relacionamento entre tabelas.
- Execução de consultas.
- Atualização dinâmica da interface.
- Persistência no `localStorage`.
- Mensagens de sucesso e erro.
- Restauração dos dados iniciais.

A aplicação não depende de frameworks JavaScript como React, Vue ou Angular.

---

# 🧠 Arquitetura Simplificada

O funcionamento pode ser representado da seguinte maneira:

```text
                 ┌──────────────────────┐
                 │      Interface       │
                 │       HTML/CSS       │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │      JavaScript      │
                 │   Motor do Sistema   │
                 └──────────┬───────────┘
                            │
                ┌───────────┴───────────┐
                ▼                       ▼
        ┌──────────────┐       ┌────────────────┐
        │ Simulador SQL│       │   LocalStorage │
        └──────┬───────┘       └───────┬────────┘
               │                        │
               └───────────┬────────────┘
                           ▼
                  ┌──────────────────┐
                  │ Dados Simulados  │
                  └──────────────────┘
```

---

# 📁 Estrutura do Projeto

Por ser um projeto desenvolvido em um único arquivo, sua estrutura é extremamente simples:

```text
simulador-banco-dados/
│
└── index.html
```

O arquivo `index.html` contém:

```text
HTML
 ├── Estrutura da aplicação
 │
 ├── Tailwind CSS
 │
 ├── FontAwesome
 │
 └── JavaScript
      ├── Dados
      ├── Simulador SQL
      ├── SELECT
      ├── INSERT
      ├── JOIN
      ├── LocalStorage
      └── Atualização da interface
```

---

# ▶️ Como Executar

Como o projeto não possui backend ou banco de dados externo, sua execução é extremamente simples.

### 1. Clone o projeto

```bash
git clone SEU_REPOSITORIO
```

### 2. Entre na pasta

```bash
cd simulador-banco-dados
```

### 3. Abra o arquivo

Basta abrir:

```text
index.html
```

no navegador.

Também é possível utilizar uma extensão como **Live Server** no VS Code para executar o projeto durante o desenvolvimento.

---

# 🔎 Exemplos de Consultas

### Listar clientes

```sql
SELECT * FROM clientes;
```

### Listar pedidos

```sql
SELECT * FROM pedidos;
```

### Buscar cliente específico

```sql
SELECT * FROM clientes WHERE id = 1;
```

### Adicionar cliente

```sql
INSERT INTO clientes (nome, email)
VALUES ('João Silva', 'joao@email.com');
```

### Consultar clientes e pedidos

```sql
SELECT clientes.nome, pedidos.produto, pedidos.valor
FROM clientes
JOIN pedidos
ON clientes.id = pedidos.cliente_id;
```

---

# ⚠️ Limitações

Este projeto é um **simulador educacional**, portanto não substitui um sistema de gerenciamento de banco de dados real.

Entre as limitações estão:

- Não utiliza MySQL, PostgreSQL, SQLite ou outro SGBD real.
- Os dados ficam armazenados localmente no navegador.
- O interpretador SQL possui suporte apenas aos comandos implementados pelo projeto.
- Não existe comunicação com um servidor backend.
- Não existe autenticação de usuários.
- Os dados não são compartilhados entre diferentes dispositivos ou navegadores.

Essas limitações são intencionais, pois o objetivo principal é **demonstrar conceitos de banco de dados de forma simples e acessível**.

---

# 📚 Conceitos Demonstrados

Este projeto permite visualizar na prática conceitos importantes de banco de dados:

- Banco de dados relacional.
- Tabelas.
- Registros.
- Campos.
- Chaves primárias.
- Chaves estrangeiras.
- Relacionamentos.
- Consultas SQL.
- `SELECT`.
- `INSERT`.
- `WHERE`.
- `JOIN`.
- Persistência de dados.
- Manipulação de dados via JavaScript.

---

# 🎓 Finalidade Educacional

O projeto pode ser utilizado como material de apoio para estudantes que estão começando a estudar:

- Banco de Dados.
- SQL.
- Desenvolvimento Web.
- JavaScript.
- Engenharia de Software.
- Estruturas de dados.
- Modelagem relacional.

A proposta é transformar conceitos que normalmente são apresentados apenas de forma teórica em uma experiência **visual e interativa**.

---

# 👨‍💻 Desenvolvedor

**Samuel Lazarin**

Desenvolvedor Full Stack com foco em desenvolvimento de software, automação, qualidade e construção de aplicações web.

---

# 📄 Licença

Este projeto pode ser utilizado para fins de **estudo, aprendizado e demonstração**.

Consulte o arquivo `LICENSE` do repositório para obter informações sobre os termos de utilização.

---

<p align="center">
  Desenvolvido com HTML5, Tailwind CSS e JavaScript.
</p>
```

Se quiser, também posso transformar esse README em uma versão **mais profissional para GitHub**, com badges, preview/demo, screenshots, seção de arquitetura, roadmap e destaque visual para deixar o repositório mais forte como projeto de portfólio.
