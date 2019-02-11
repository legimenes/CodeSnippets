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
