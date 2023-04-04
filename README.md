<h1>BOOTCAMP BANCO PAN JAVA DEVELOPER</h1>

<h3>Criar uma tabela no DynamoDB e aplicar as boas práticas.</h3>
<p>Para realizar este projeto, criei uma tabela chamada "ebook" e também utilizei as seguintes ferramentas:</p>

- AWS DynamoDB
- AWS CLI
  
<h4>A tabela tem a seguinte estrutura:</h4>
<!DOCTYPE html>
<html>
<head>
<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}
</style>
</head>
<body>
<table>
  <tr>
    <th>Nome da coluna</th>
    <th>Tipo de atributo</th>
    <th>Tipo de dado</th>
    <th>Descrição</th>
  </tr>
  <tr>
    <td>genre</td>
    <td>AttributeName</td>
    <td>S</td>
    <td>O gênero do livro</td>
  </tr>
  <tr>
    <td>id</td>
    <td>AttributeName</td>
    <td>S</td>
    <td>O identificador único do livro.</td>
  </tr>
  <tr>
    <td>published_year</td>
    <td>AttributeName</td>
    <td>N</td>
    <td>O ano em que o livro foi publicado.</td>
  </tr>
  <tr>
    <td>author</td>
    <td>AttributeName</td>
    <td>S</td>
    <td>O autor do livro.</td>
  </tr>
  <tr>
    <td>genre</td>
    <td>KeyType</td>
    <td>HASH</td>
    <td>A chave hash para a tabela.</td>
  </tr>
  <tr>
    <td>id</td>
    <td>KeyType</td>
    <td>RANGE</td>
    <td>A chave de intervalo para a tabela.</td>
  </tr>
  <tr>
    <td>author_published_year_index</td>
    <td>IndexName</td>
    <td>-</td>
    <td>O nome do Índice Secundário Global.</td>
  </tr>
  <tr>
    <td>author</td>
    <td>KeyType</td>
    <td>HASH</td>
    <td>A chave hash para o Índice Secundário Global.</td>
  </tr>
  <tr>
    <td>published_year</td>
    <td>KeyType</td>
    <td>RANGE</td>
    <td>A chave de intervalo para o Índice Secundário Global.</td>
  </tr>
  <tr>
    <td>ProjectionType</td>
    <td>Projection</td>
    <td>-</td>
    <td>O tipo de projeção a ser usado</td>
  </tr>
  <tr>
    <td>All</td>
    <td>Projection</td>
    <td>-</td>
    <td>Todos os atributos da tabela são projetados no índice</td>
  </tr>
  <tr>
    <td>ReadCapacityUnits</td>
    <td>ProvisionedThroughput</td>
    <td>-</td>
    <td>O número máximo de leituras consistentes por segundo que podem ser executadas.</td>
  </tr>
  <tr>
    <td>WriteCapacityUnits</td>
    <td>ProvisionedThroughput</td>
    <td>-</td>
    <td>O número máximo de gravações por segundo que podem ser executadas</td>
  </tr>
</table>

</body>
</html>



<p>Para criar a tabela e inserir itens nela, eu uso um arquivo JSON.</p>

<p>Para criar a tabela, já com o caminho do diretório atual do PowerShell na pasta em que o arquivo JSON está armazenado, executei o seguinte comando:</p>

```
aws dynamodb create-table --cli-input-json file://create-table.json
```

<p>Na mesma condição acima, para inserir itens na tabela, executei o comando a seguir:</p>

```
aws dynamodb batch-write-item --request-items file://put-items.json
```

