# TccInspetorCore

- Application to check if a given document follows the Brazilian standard for academic papers (ABNT). It corresponds to the **TccInspetorCore** component of the following architecture:

[//]: # (- É uma Aplicação para verificar se um documento segue o padrão da ABNT. Corresponde ao componente TccInspetorCore da arquitetura abaixo:)
 
 ![](https://github.com/ericknilsen/TccInspetorCore/blob/master/docs/Arquitetura_TccInspetor.png)

- It was developed in Python.
- It is deployed to AWS as a Lambda function and made available as a REST API by the AWS API Gateway.

## Setup

### Deployment Environment

The deployment in AWS is done as follows:

- Create a Bucket in S3 and include a directory to store the documents that need to be checked
- Clone the repository:
```shell
$ git clone https://github.com/ericknilsen/TccInspetorCore
```
- Compress the content in _lambda_ directory to a _.zip_ file format
- Create a Lambda function
- Upload the _.zip_ file in the function's code
- Create a Gateway API for the function
- Add a GET method in the API
- Navigate to _Integration Request -> Mapping Templates_ and add a Content-Type _application/json_ with the following content:
```json
{ "file": "$input.params('file')" }
```
- Enable API CORS
- Deploy the API
- Edit the Lambda function's code
- Rename the file _credentials_example.json_ to _credentials.json_ and insert the access data as follows:
```json
{
  "bucketName": "BUCKET-NAME",
  "folder": "BUCKET-FOLDER",
  "region": "REGION",
  "accessKeyId": "ACCESS-KEY-ID",
  "secretAccessKey": "SECRET-ACCESS-KEY"
}
```


### Development Environment

- Clone the repository:
```shell
$ git clone https://github.com/ericknilsen/TccInspetorCore
```
- Criate the file _lambda/main.py_ to test the application locally with the following content:
```python

```

- Run the program:
```shell
$ python main.py
```

