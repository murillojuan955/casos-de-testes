import io.restassured.RestAssured;
import io.restassured.response.Response;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;

public class ReqresAPITests {
    
    @BeforeClass
    public void setup() {
        // Configura a base URI para a API Reqres
        RestAssured.baseURI = "https://reqres.in";
    }

    @Test
    public void testListUsers() {
        // Envia uma solicitação GET para listar os usuários na página 1
        Response response = RestAssured.get("/api/users?page=1");

        // Verifica o status da resposta
        response.then().statusCode(200);

        // Verifica se o número de usuários listados está correto (por exemplo, 6 no caso da página 1)
        response.then().body("data.size()", is(6));
    }

    @Test
    public void testInvalidEndpoint() {
        // Tenta acessar um endpoint inexistente
        Response response = RestAssured.get("/api/nonexistent");

        // Verifica o status da resposta (deve ser 404 - não encontrado)
        response.then().statusCode(404);
    }
}
