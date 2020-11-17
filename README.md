# Conex-o-de-Java-com-banco-de-dados-postGreeSQL



/*
A conexão é estabelecida de seguinte forma:
– Carregamento do driver JDBC específico
– Criação da conexão com o BD

*/
// situa o package ou "pacote" está a classe
package Factory;
// faz as importações de classes necessárias para o funcionamenro do programa
import java.sql.Connection;
//conexão SQL para java
import java.sql.DriverManager;
//driver de conexão SQL para Java
import java.sql.SQLException;
//classe para tratamento de exceções







/**
 *
 * @author isaura
 */
public class ConnectionFactory
{
    // Declarações da variáveis, responsáveis para a conexão do Java com o Postgresql
    
    private String url;  
    private String user;   
    private String senha;   
    
    public Connection getConnection()
    {
        url ="jdbc:postgresql://localhost:5432/projeto1";     // Variável que especifica o tipo e o caminho da BD
        user = "postgres";    // Especifica o usuário da BD
        senha = "0726";       // a senha para logar na BD
        
        try     //Tratamento de exceções, ou seja, erros que possivelmente surgira durante a execução do programa
        {
                return DriverManager.getConnection(url,user,senha); // retorna a conexão com BD
               // DriverManager- gerencia o driver e cria uma conexão com o banco
                // Connection é a classe que representa a conexão com o banco de dados, getConnection pega a conexão do BD
            
        }
        catch (SQLException excecao) 
        {
            // Tratamento das exceções
            throw new RuntimeException(excecao);
           
        }
    }
    
}
