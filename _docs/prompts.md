# 📄 Prompts.MD

## Conversa Completa

---

### Leandro: 

Crie uma documentação para o projeto abaixo criando um arquivo Readme.md na linguagem markdown;  
No arquivo deve conter uma breve descrição do projeto;  
Informar a linguagem utilizada no desenvolvimento da API;  
Criar uma tabela com os verbos e endpoints que a api possui;  
Descrever as técnicas utilizadas no desenvolvimento da API;  
Descrever as dependências o projeto utiliza e coloque um link para a pagina oficial da dependência que é utilizada no projeto;  
Crie um trecho de código de como utilizar os endpoints da API  
Crie um trecho de código com um exemplo de retorno dos endpoints da API  

Classe Controller com os EndPoints:

```csharp
[ApiController]
[Route("api/v1/robots")]
public class RobotsController : ControllerBase
{
    private readonly IRobotServices _services;
    public RobotsController(IRobotServices services)
    {
        _services = services;
    }

    //GET api/robots
    [HttpGet] 
    public ActionResult<IEnumerable<RobotReadDTO>> GetAllRobots()
    {
        var robotItems = _services.SearchAll();
        return Ok(robotItems);
    }

    //GET api/v1/robots/{id}
    [HttpGet]
    [Route("{id:int}")]
    public object GetCommandById([FromRoute]int id)
    {   
        var robot = _services.SearchById(id);

        if(robot != null)
            return Ok(robot);
        
            return NotFound( 
                    new { message = "Nenhum robo encontrado" }
            );
    }

    //POST api/v1/robots
    [HttpPost]
    public ActionResult RobotSend(){
        return Ok();
    }
}

Complemento: Arquivo csproj com as dependências utilizadas na API:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.8" />
    <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="3.1.8">
      <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
      <PrivateAssets>all</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.EntityFrameworkCore.SqlServer" Version="3.1.8" />
    <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
  </ItemGroup>

</Project>
```

Exemplo de Retorno endpoint GetAllRobots:

```json
{ 
        Id =1,
        Code = "DLN/DRN-003",
        Name = "Cutman",
        HP = 150,
        Picture = "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
},
{ 
        Id =2,
        Code = "112",
        Name = "Gutman",
        HP = 150,
        Picture = ""
},
{ 
        Id =2,
        Code = "112",
        Name = "Iceman",
        HP = 150,
        Picture = ""
}
```

Exemplo de retorno do endpoint GetCommandById:

```json
{ 
        Id =0,
        Code = "112",
        Name = "Cutman",
        HP = 150,
        Picture = "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

Atenção: Caso seja preciso mais alguma informação me pergunte, não invente nenhum dado referente a API que não esteja nos dados que te forneci.

---

### ChatGPT:
Com certeza! Aqui está o conteúdo completo do README.md, todo em markdown, com ícones e um design moderno, bonito e profissional:

```markdown
# 🤖 Robots API

## 📖 Descrição
A **Robots API** é uma API RESTful desenvolvida em **ASP.NET Core 3.1** para gerenciamento de robôs.  
Com ela, é possível:
- 🔍 Listar todos os robôs cadastrados
- 📋 Consultar os detalhes de um robô específico pelo seu identificador
- 📤 Enviar dados de novos robôs (em construção)

... (resposta completa do README que já te enviei)


```

---

### Leandro:
Complemento: essa API retorna dados dos Bosses do game MegaMan

---

### ChatGPT:
Perfeito! Aqui está o README.md atualizado, incluindo o complemento de que a API retorna dados dos Bosses do game MegaMan e com o mesmo visual moderno e profissional:

```markdown
# 🤖 Robots API - MegaMan Bosses

## 📖 Descrição
A **Robots API** é uma API RESTful desenvolvida em **ASP.NET Core 3.1**, dedicada a fornecer dados dos icônicos **Bosses do universo MegaMan**.  
Com essa API, é possível:

- 🔍 Listar todos os Bosses cadastrados
- 📋 Consultar detalhes específicos de um Boss pelo seu identificador
- 📤 Enviar dados para cadastro de novos Bosses (em desenvolvimento)

... (resposta completa do README atualizado que já te enviei)


```
