<div align="center">

# 🚗 API REST — Sistema de Estacionamento

> Projeto acadêmico desenvolvido na disciplina de **Desenvolvimento Web 3**  
> 👨‍🏫 **Professor:** Mário de Jesus

![Node.js](https://img.shields.io/badge/Node.js-16+-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-5.2.1-000000?style=for-the-badge&logo=express&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Sequelize](https://img.shields.io/badge/Sequelize-6.37.8-52B0E7?style=for-the-badge&logo=sequelize&logoColor=white)

</div>

## 📋 Sobre o Projeto

API RESTful para gerenciamento de um sistema de estacionamento, permitindo o cadastro, consulta, atualização e remoção de **proprietários** e **veículos** associados a eles.

A arquitetura segue os princípios de **SOA (Arquitetura Orientada a Serviços)**, onde cada recurso possui seu próprio controlador e rotas, com o `index.js` atuando como gateway central.

---

## 🛠️ Tecnologias

| Tecnologia | Versão |
|------------|--------|
| Node.js | 16+ |
| Express.js | ^5.2.1 |
| Sequelize (ORM) | ^6.37.8 |
| MySQL2 | ^3.20.0 |
| Body-Parser | ^2.2.2 |
| CORS | ^2.8.6 |

---

## 📁 Estrutura do Projeto

```
BackEnd/
├── 📄 index.js                      # Ponto de entrada e gateway de rotas
├── 📦 package.json
├── 📁 models/
│   ├── 🔗 db.js                     # Conexão com o banco de dados
│   ├── 👤 Proprietario.js           # Modelo de Proprietário
│   └── 🚘 Veiculo.js                # Modelo de Veículo
└── 📁 controllers/
    ├── 👤 ProprietarioControlls.js  # Rotas CRUD de Proprietário
    └── 🚘 VeiculoControlls.js       # Rotas CRUD de Veículo
```

---

## ⚙️ Como Executar

### Pré-requisitos

- ✅ Node.js instalado
- ✅ MySQL rodando localmente

### 1. Instale as dependências

```bash
npm install
```

### 2. Crie o banco de dados no MySQL

```sql
CREATE DATABASE estacionamento;
USE estacionamento;
```

### 3. Crie as tabelas

```bash
cd models
node Proprietario.js
node Veiculo.js
cd ..
```

> ⚠️ **Importante:** Após criar as tabelas, comente a linha `sync({ force: true })` em ambos os arquivos.

### 4. Inicie o servidor

```bash
npx nodemon index.js
```

🚀 O servidor estará disponível em `http://localhost:8081`

---

## 🔌 Endpoints

### 👤 Proprietário

| Método | Rota | Descrição |
|--------|------|------------|
| `GET` | `/proprietario` | Lista todos os proprietários |
| `POST` | `/proprietario` | Cadastra um novo proprietário |
| `GET` | `/proprietario/:id` | Busca proprietário pelo ID |
| `PUT` | `/proprietario/:id` | Atualiza proprietário pelo ID |
| `DELETE` | `/proprietario/:id` | Remove proprietário pelo ID |

### 🚘 Veículo

| Método | Rota | Descrição |
|--------|------|------------|
| `GET` | `/veiculo` | Lista todos os veículos |
| `POST` | `/veiculo` | Cadastra um novo veículo |
| `GET` | `/veiculo/:id` | Busca veículo pelo ID |
| `PUT` | `/veiculo/:id` | Atualiza veículo pelo ID |
| `DELETE` | `/veiculo/:id` | Remove veículo pelo ID |

---

### 📦 Exemplos de Body (JSON)

**POST /proprietario**

```json
{
  "nome": "Maria Silva",
  "cpf": "123.456.789-00"
}
```

**POST /veiculo**

```json
{
  "placa": "ABC-1234",
  "ano": 2022,
  "mensalidade": 350.00,
  "fk_proprietario": 1
}
```

---

## 🗄️ Modelos de Dados

### 👤 Proprietário

| Campo | Tipo | Descrição |
|-------|------|-------------|
| `id_proprietario` | INTEGER | Chave primária (auto incremento) |
| `nome` | TEXT | Nome do proprietário |
| `cpf` | TEXT | CPF do proprietário |

### 🚘 Veículo

| Campo | Tipo | Descrição |
|-------|------|-------------|
| `id_veiculo` | INTEGER | Chave primária (auto incremento) |
| `placa` | TEXT | Placa do veículo |
| `ano` | INTEGER | Ano de fabricação |
| `mensalidade` | DECIMAL(10,2) | Valor da mensalidade |
| `fk_proprietario` | INTEGER | Chave estrangeira (Proprietário) |

---

## 🧪 Testando a API

Recomenda-se utilizar as seguintes ferramentas:

<div align="center">

[![Insomnia](https://img.shields.io/badge/Insomnia-5849BE?style=for-the-badge&logo=insomnia&logoColor=white)](https://insomnia.rest/download)
[![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)](https://www.postman.com/)

</div>

Configure a **base URL** como `http://localhost:8081` e teste os endpoints listados acima.

---

<div align="center">
  
**Desenvolvido com 💙 para a disciplina de Desenvolvimento de APIs**

</div>

O conteúdo permaneceu 100% intacto, apenas a apresentação visual foi aprimorada para um visual mais moderno e profissional.
