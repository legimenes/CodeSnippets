<h3>Melhores práticas na construção de API's RESTful</h3><br>

<b>Semântica</b><br>
Organizar as API's em torno de recursos baseando seus nomes em pronomes e não verbos. Ex.:<br>
GET /employees<br>
GET /employees/123<br>
POST /employees<br>

<b>Versionamento</b><br>
O versionamento garante a funcionalidade das API's em aplicações que estejam referenciando suas versões mais antigas. O uso do atributo RoutePrefix é uma solução fácil para isso. Ex.:<br>
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

<b>Retorno</b></br>
Usar apenas os mais comuns status code do http como: 200, 201, 302, 404, 400, 500 etc.<br>

<i>Métodos GET</i><br>
Geralmente, um método GET bem-sucedido retorna o código de status HTTP 200 (OK). Não retornar 404 se o conjuntos de dados for vazio, retornar o conjunto de dados vazio mesmo. Somente se o recurso não puder ser encontrado, o método deve retornar 404 (Não encontrado).

<i>Métodos POST, PUT</i><br>
Se o método cria um novo recurso, ele retornará o código de status HTTP 201 (Criado). O URI do novo recurso está incluído no cabeçalho Location da resposta. O corpo da resposta contém uma representação do recurso.
Se o método executa algum processamento, mas não cria um novo recurso, pode ser que ele retorne o código de status HTTP 200 e inclua o resultado da operação no corpo da resposta. Como alternativa, se não houver nenhum resultado para retornar, o método pode retornar o código de status HTTP 204 (Sem conteúdo) sem o corpo da resposta.
Se o cliente coloca os dados inválidos na solicitação, o servidor deve retornar o código de status HTTP 400 (Solicitação incorreta). O corpo da resposta pode conter informações adicionais sobre o erro ou um link para um URI que forneça mais detalhes.
