<h1>BOOTCAMP BANCO PAN JAVA DEVELOPER</h1>

<h3>Boas práticas com DynamoDB</h3>

<p>Para criar a tabela e inserir itens nela, eu uso um arquivo JSON.</p>

<p>Para criar a tabela, já com o caminho do diretório atual do PowerShell na pasta em que o arquivo JSON está armazenado, executei o seguinte comando:</p>

```
aws dynamodb create-table --cli-input-json file://create-table.json
```


