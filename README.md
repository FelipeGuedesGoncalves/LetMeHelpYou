# HelpMeOut
API do projeto LetMeHelpYou

## Tarefas

- [ ] CRUD de CATEGORIAS
- [ ] CRUD de MOVIMENTAÇÕES
- [ ] CRUD de USUÁRIOS
- [ ] Dashboard

## Documentação da API

### Endpoint
- [Listar todos os serviços](#listar-todos-os-serviços)
- [Listar Todos os Serviços](#Listar-todos-os-serviços)
- [Atualizar Serviço](#Atualizar-serviço)

### Listar todos os serviços

`GET` /categoria

Retorna um array com todos os serviços ativos.

#### Exemplo de Resposta

```js
[
    {
        "id": 1,
        "nome": "Serviço de marcenaria",
        "icone": "strong-arm"
    }
]

```

#### Código de Status

|código|descrição|
|------|---------|
|200|Os dados das categorias foram retornados com suceesso
|401|Acesso negado. Você deve de autenticar
|500|No geral são erros do servidor e não há nada para o cliente fazer

### Cadastrar serviço

`POST` /serviço

Cria um novo serviço com os dados combinados entre os envolvidos no corpo da requisição

#### Corpo da Requisição

|campo|tipo|obrigatório|descrição|
|-----|----|:---------:|---------|
|nome|string|✔|Um nome curto para o serviço|
|envolvidos|string|✔|Nomes dos envolvidos no serviço em questão|
|icone|string|❌|O nome do icone de acordo com a biblioteca Material Icons

```js
    {
        "nome": "Serviço de marcenaria",
        "icone": "strong-arm"
    }
```

#### Exemplo de Resposta

```js
    {
        "id": 1,
        "nome": "Serviço de marcenaria",
        "icone": "strong-arm"
    }
```

#### Código de Status

|código|descrição|
|------|---------|
|201|Serviço cadastrado com sucesso.
|400|Dados enviados são inválidos. Verifique o corpo da requisição.
|401|Acesso negado. Você deve de autenticar

### Detalhes do Serviço

`GET` /servico/`{id}`

Retornar os detalhes do serviço com o `id` informado como parâmetro de path

#### Exemplo de Resposta

```js
//requisição para /categoria/1
    {
        "id": 1,
        "nome": "Serviço de marcenaria",
        "icone": "strong-arm"
    }
```

#### Código de Status

|código|descrição|
|------|---------|
|200|Os dados do serviço
 foram retornados com suceesso
|401|Acesso negado. Você deve de autenticar
|404|Não existe serviço com o `id` informado

### Mandar Mensagem

A DEFINIR

### Apagar Serviço

`DELETE` /servico/`{id}`

Apaga o serviço com o `id` especificado no parâmetro de path.

#### Código de Status

|código|descrição|
|------|---------|
|204|Serviço foi apagado com sucesso
|401|Acesso negado. Você deve de autenticar
|404|Não existe serviço com o `id` informado

### Atualizar Serviço

`PUT` /servico/`{id}`

Altera os dados do serviço especificado no `id`,
utilizando as informações enviadas no corpo da requisição da requisição.

#### Corpo da Requisição

|campo|tipo|obrigatório|descrição|
|-----|----|:---------:|---------|
|nome|string|✔|Um nome curto para o serviço|
|icone|string|✔|O nome do icone de acordo com a biblioteca Material Icons

```js
    {
        "nome": "Serviço de marcenaria",
        "icone": "strong-arm"
    }
```
#### Exemplo de Resposta

```js
    {
        "id": 1,
        "nome": "Serviço de marcenaria",
        "icone": "strong-arm"
    }
```

#### Código de Status

|código|descrição|
|------|---------|
|200|Serviço alterado com sucesso.
|400|Dados enviados são inválidos. Verifique o corpo da requisição.
|401|Acesso negado. Você deve de autenticar
|404|Não existe serviço com o `id` informado