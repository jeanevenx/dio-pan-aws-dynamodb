<h1>BOOTCAMP BANCO PAN JAVA DEVELOPER</h1>

<h4>Criar uma tabela no DynamoDB e aplicar as boas práticas.</h4>
<p>Para realizar este projeto, criei uma tabela chamada "ebook" e também utilizei as seguintes ferramentas:</p>

- AWS DynamoDB
- AWS CLI
  
<h3>A tabela tem a seguinte estrutura:</h3>

<p>Para criar a tabela e inserir itens nela, eu uso um arquivo JSON.</p>

<p>Para criar a tabela, já com o caminho do diretório atual do PowerShell na pasta em que o arquivo JSON está armazenado, executei o seguinte comando:</p>

```
aws dynamodb create-table --cli-input-json file://create-table.json
```

<p>Na mesma condição acima, para inserir itens na tabela, executei o comando a seguir:</p>

```
aws dynamodb batch-write-item --request-items file://put-items.json
```
