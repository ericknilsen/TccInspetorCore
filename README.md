# TccInspetorCore

 - É uma Aplicação para verificar se um documento segue o padrão da ABNT. Corresponde ao componente TccInspetorCore da arquitetura abaixo:
 
 ![](https://github.com/ericknilsen/TccInspetorCore/blob/master/docs/Arquitetura_ABNT.png)

- Desenvolvida na linguagem Python.
- Está implantada na AWS como uma função Lambda e disponibilizada como uma API REST pela AWS API Gateway.

## Configuração

### Implantação

A implantação na AWS é feita da seguinte forma:

- Baixe o repositório:
```shell
$ git clone https://github.com/ericknilsen/TccInspetorCore
```
- Comprima o conteúdo do diretório _lambda_ no formato _.zip_
- Crie uma função Lambda
- Faça o upload do arquivo _.zip_ criado no código da função
- Crie uma API Gateway para a função
- Adicione um método GET na API
- Navegue para _Integration Request -> Mapping Templates_ e adicione um Content-Type com o seguinte conteúdo:
```json
{ "file": "$input.params('file')" }
```

### Desenvolvimento

- Baixe o repositório:
```shell
$ git clone https://github.com/ericknilsen/TccInspetorCore
```

- Execute o programa:
```shell
$ python main.py
```

