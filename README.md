# TccInspetorCore

- Application to check if a given document follows the Brazilian standard for academic papers (ABNT). Corresponds to the **TccInspetorCore** component of the following architecture:

[//]: # (- É uma Aplicação para verificar se um documento segue o padrão da ABNT. Corresponde ao componente TccInspetorCore da arquitetura abaixo:)
 
 ![](https://github.com/ericknilsen/TccInspetorCore/blob/master/docs/Arquitetura_TccInspetor.png)

- It was developed in Python.
- It is deployed to AWS as a Lambda function and made available as a REST API by the AWS API Gateway.

## Setup

### Deployment Environment

A implantação na AWS é feita da seguinte forma:

- Crie um Bucket no S3 e inclua um diretório para armazenar os documentos que devem ser verificados
- Baixe o repositório:
```shell
$ git clone https://github.com/ericknilsen/TccInspetorCore
```
- Comprima o conteúdo do diretório _lambda_ no formato _.zip_
- Crie uma função Lambda
- Faça o upload do arquivo _.zip_ criado no código da função
- Crie uma API Gateway para a função
- Adicione um método GET na API
- Navegue para _Integration Request -> Mapping Templates_ e adicione um Content-Type _application/json_ com o seguinte conteúdo:
```json
{ "file": "$input.params('file')" }
```
- Habilite o CORS da API
- Faça o deploy da API
- Edite o código da função Lambda
- Renomeie o arquivo _credentials_example.json_ para _credentials.json_ e insira os dados de acesso:
```json
{
  "bucketName": "BUCKET-NAME",
  "folder": "BUCKET-FOLDER",
  "region": "REGION",
  "accessKeyId": "ACCESS-KEY-ID",
  "secretAccessKey": "SECRET-ACCESS-KEY"
}
```


### Development Evironment

- Baixe o repositório:
```shell
$ git clone https://github.com/ericknilsen/TccInspetorCore
```
- Crie um arquivo _lambda/main.py_ para testar localmente a aplicação com o seguinte conteúdo:
```python

```

- Execute o programa:
```shell
$ python main.py
```

