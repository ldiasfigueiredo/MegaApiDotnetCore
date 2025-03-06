# 🤖 Robots API - MegaMan Bosses

## 📖 Descrição
A **Robots API** é uma API RESTful desenvolvida em **ASP.NET Core 3.1**, dedicada a fornecer dados dos icônicos **Bosses do universo MegaMan**.  
Com essa API, é possível:

- 🔍 Listar todos os Bosses cadastrados
- 📋 Consultar detalhes específicos de um Boss pelo seu identificador
- 📤 Enviar dados para cadastro de novos Bosses (em desenvolvimento)

---

## 🎮 Contexto
Esta API foi criada para servir como uma base de consulta sobre os chefes (Bosses) da série **MegaMan**, trazendo informações como:

- Código de Identificação
- Nome do Boss
- Pontos de Vida (HP)
- Imagem ilustrativa

---

## 🛠️ Tecnologias Utilizadas
- **Linguagem:** C# com **ASP.NET Core 3.1**
- **Arquitetura:** RESTful
- **Paradigma:** Programação Orientada a Objetos (POO)
- **Técnicas:**
    - Injeção de Dependência (Dependency Injection)
    - Tratamento de erros com códigos HTTP apropriados
    - Serialização e Desserialização de objetos JSON usando **Newtonsoft.Json**
    - Separação de responsabilidades entre **Controller** e **Service**

---

## 📊 Tabela de Endpoints

| Verbo HTTP | Endpoint               | Descrição                                           |
|------------|------------------------|-----------------------------------------------------|
| 🟢 GET     | `/api/v1/robots`       | Retorna a lista de todos os Bosses                  |
| 🟢 GET     | `/api/v1/robots/{id}`  | Retorna os detalhes de um Boss específico            |
| 🟠 POST    | `/api/v1/robots`       | Envia dados para cadastro de um novo Boss (em desenvolvimento) |

---

## 📦 Dependências

| Dependência                             | Versão  | Link Oficial |
|-----------------------------------------|---------|--------------------------------------------------------------------------------------------------|
| Microsoft.EntityFrameworkCore          | 3.1.8   | [🔗 EF Core](https://learn.microsoft.com/en-us/ef/core/)                                        |
| Microsoft.EntityFrameworkCore.Design   | 3.1.8   | [🔗 EF Core Design](https://learn.microsoft.com/en-us/ef/core/)                                 |
| Microsoft.EntityFrameworkCore.SqlServer | 3.1.8   | [🔗 EF Core SQL Server](https://learn.microsoft.com/en-us/ef/core/providers/sql-server/)        |
| Newtonsoft.Json                        | 12.0.2  | [🔗 Newtonsoft.Json](https://www.newtonsoft.com/json)                                           |

---

## 💻 Exemplo de Utilização

### ➡️ Buscar todos os Bosses - Endpoint: *GetAllRobots*
**Requisição**
```http
GET /api/v1/robots HTTP/1.1
Host: localhost:5000
```

**Resposta**
```
[
    { 
        "id": 1,
        "code": "DLN/DRN-003",
        "name": "Cutman",
        "hp": 150,
        "picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
    },
    { 
        "id": 2,
        "code": "112",
        "name": "Gutman",
        "hp": 150,
        "picture": ""
    },
    { 
        "id": 3,
        "code": "112",
        "name": "Iceman",
        "hp": 150,
        "picture": ""
    }
]
```
### ➡️ Buscar Boss por ID - Endpoint: *GetCommandById*
**Requisição**

```
GET /api/v1/robots/1 HTTP/1.1
Host: localhost:5000
```

**Resposta**

```
{
    "id": 0,
    "code": "112",
    "name": "Cutman",
    "hp": 150,
    "picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```
**Quando o Boss não é encontrado**

```
{
    "message": "Nenhum robo encontrado"
}
```

## 📌 Observações
- ✅ A API é inspirada no universo MegaMan.

- ✅ O endpoint de POST ainda não possui implementação para cadastro real.

- ✅ A estrutura pode ser facilmente adaptada para receber novos campos ou integração com banco de dados.
## 👨‍💻 Autor
- API - Desenvolvido por FelipeAguiar -
[Github](https://github.com/felipeAguiarCode)

- 🚀 Projeto de exemplo para consulta e gerenciamento de Bosses do MegaMan usando ASP.NET Core 3.1.

## 📅 Versão
- 1.0.0 - Inicial

