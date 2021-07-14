# API Catálogo de Jogos

Desafio proposto pela Digital Inovation One durante um bootcamp preparatório. Desenvolvido seguindo orientações do instrutor Thiago Oliveira com algumas alterações durante o processo. 

Durante o processo, optei pela não utilização do Swagger pois quis ver como é uma integração de API utilizando o Postman. Além do Postman, neste projeto utilizei um banco de dados em um container do Docker. 

Estarei incluindo abaixo as instruções de como utilizar tanto o banco de dados quanto o docker.



### Criando o banco de dados no Docker:

* O primeiro passo é a realização do download do SQL Server utilizando o comando: 

  > ```
  > docker pull mcr.microsoft.com/mssql/server
  > ```

* Para o próximo passo, é necessário rodar o container, utilizando a imagem do SQL Server, com este comando:

  > ```
  > docker run --name sqlserver -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=1q2w3e4r@#$" -p 1433:1433 -d mcr.microsoft.com/mssql/server
  > ```
  * Caso esteja sendo utilizado o WSL2, o comando "-v" (criação de um volume) no comando a cima.

* Em seguida, deve ser utilizado o software de sua preferencia para se conectar ao banco de dados (no meu caso, utilizei o Azure Data Studio) usando as seguintes credenciais:

  > server: localhost, 1433
  >
  >  user: sa
  >
  >  password: 1q2w3e4r@#$

* No código estão disponibilizados os arquivos .SQL para a criação do banco, criação da tabela jogos e um script para popular a tabela, já contendo alguns registros, no arquivo **banco.zip**. 

  

### Rodando o código:

* Caso não esteja sendo utilizado o Visual Studio, deve ser usado o seguinte comando no CMD (deve estar na pasta do projeto):

  > dotnet run

* Caso esteja utilizando o Visual Studio, selecione o projeto da API como um projeto de inicialização e rode-o como servidor do IIS Express.