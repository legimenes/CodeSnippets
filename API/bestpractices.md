<h1>Melhores práticas na construção de API's RESTful</h1>

<h2>Semântica</h2>
Organizar as API's em torno de recursos baseando seus nomes em pronomes e não verbos. Ex.:

```
GET /employees
GET /employees/123
POST /employees
```

<h2>Versionamento</h2>
O versionamento garante a funcionalidade das API's em aplicações que estejam referenciando suas versões mais antigas. O uso do atributo RoutePrefix é uma solução fácil para isso. Ex.:

```
[RoutePrefix("api/v2/Persons")]
public class PersonsController : ApiController
{
    public IHttpActionResult Get()
    {
      //...
    }
}
```

<h2>Retorno</h2>
Usar preferencialmente os <i>status code</i> do http mais comuns como:<br>
<i>200 OK</i> - Processamento efetuado com sucesso.<br>
<i>201 OK</i> - Um novo recurso foi criado.<br>
<i>204 OK</i> - O recurso foi deletado com sucesso.<br>
<i>304 Not Modified</i> - O cliente pode usar os dados cacheados.<br>
<i>400 Bad Request</i> - A requisição estava inválida ou não pode ser processada. O erro deve ser informado.<br>
<i>401 Unauthorized</i> - A requisição requer uma autenticação do usuário.<br>
<i>403 Forbidden</i> - O servidor entendeu a requisição mas está foi recusada ou o acesso não é permitido.<br>
<i>404 Not found</i> - Não há recurso por trás da URI.<br>
<i>500 Internal Server Error</i> - O stacktrace deve ser logado e não retornado na resposta.<br>

<h3>Métodos GET</h3>
Geralmente, um método GET bem-sucedido retorna o código de status HTTP 200 (OK). Não retornar 404 se o conjuntos de dados for vazio, retornar o conjunto de dados vazio mesmo. Somente se o recurso não puder ser encontrado, o método deve retornar 404 (Não encontrado).

<h3>Métodos POST, PUT</h3>
Se o método cria um novo recurso, ele retornará o código de status HTTP 201 (Criado). O URI do novo recurso está incluído no cabeçalho Location da resposta. O corpo da resposta contém uma representação do recurso.
Se o método executa algum processamento, mas não cria um novo recurso, pode ser que ele retorne o código de status HTTP 200 e inclua o resultado da operação no corpo da resposta. Como alternativa, se não houver nenhum resultado para retornar, o método pode retornar o código de status HTTP 204 (Sem conteúdo) sem o corpo da resposta.
Se o cliente coloca os dados inválidos na solicitação, o servidor deve retornar o código de status HTTP 400 (Solicitação incorreta). O corpo da resposta pode conter informações adicionais sobre o erro ou um link para um URI que forneça mais detalhes.
