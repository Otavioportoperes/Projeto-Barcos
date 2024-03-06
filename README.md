# Projeto-Barcos

## Requisitos

- [ ] CRUD de Embarcacoes 
- [ ] CRUD de Praias
- [ ] CRUD de Usuários
- [ ] Validação
- [ ] Dashboard

## Documentação

### Endpoints

- [Listar Barcos](#listar-Barcos)
- [Cadastrar Praias](#cadastrar-Praias)
- [Usuários](#Usuários)
- [Validaçao](#Validar-val)
- [Dashboard](#Dashboard)

### Listar Categorias

`GET` /categoria

Retorna um array com todas as categorias cadastradas.

#### Exemplo de Resposta

```js
[
    {
        "id": 1,
        "nome": "Embarcacoes",
        "icone": "Barco"
    },
    {
        "id": 2,
        "nome": "Lanchas",
        "icone": "Lancha"
    }
]
```

#### Código de Status

| código | descrição
|--------|-----------
|200|Categorias retornadas com sucesso
|401|Usuário não autenticado. Realize autenticação em /login

---

### Cadastrar Barco

`POST` /Barco

Cadastrar nova categoria de Barco

#### Corpo da Requisição

| campo | tipo | obrigatório | descrição
|-------|------|:-------------:|-----------
|nome|string|✅| Um nome curto para a categoria
|icone| string | ❌ | O nome do ícone conforme Material Icons

```js
{
    "nome": "Embarcacao",
    "icone": "Barco"
}
```

#### Exemplo de Resposta

```js
{
    "id": 1,
    "nome": "Lancha",
    "icone": "Lancha"
}
```

#### Código de Status

| código | descrição
|--------|-----------
|201|Categoria cadastrada com sucesso
|400|Validação falhou. Verifique as regras para o corpo da requisição
|401|Usuário não autenticado. Realize autenticação em /login

---

### Detalhes da Categoria

`GET` /categoria/`{id}`

Retorna os dados detalhados da categoria com o `id` informado no parâmetro de path.

### Exemplo de Resposta
```js
// requisição para /categoria/1
{
    "id": 1,
    "nome": "Embarcacoes",
    "icone": "Barco"
}
```

#### Código de Status

| código | descrição
|--------|-----------
|200|Dados da categoria retornados com sucesso
|401|Usuário não autenticado. Realize autenticação em /login
|404|Não existe categoria com o `id` informado. Consulte lista em /categoria

---

### Apagar Categoria

`DELETE` /categoria/`{id}`

Apaga a categoria indicada pelo `id` enviado no parâmetro de path.

#### Código de Status

| código | descrição
|--------|-----------
|204|Categoria apagada com sucesso
|401|Usuário não autenticado. Realize autenticação em /login
|404|Não existe categoria com o `id` informado. Consulte lista em /categoria

---

### Atualizar Categoria

`PUT` /categoria/`{id}`

Atualizar os dados da categoria com o `id` informado no path, utilizando os novos dados enviados no corpo da requisição.

#### Corpo da Requisição

| campo | tipo | obrigatório | descrição
|-------|------|:-------------:|-----------
|nome|string|✅| Um nome curto para a categoria
|icone| string | ✅ | O nome do ícone conforme Material Icons

```js
{
    "nome": "Barcos",
    "icone": "Barco"
}

'''

'''
#### Código de Status

| código | descrição
|--------|-----------
|200|Categoria atualizada com sucesso
|400|Validação falhou. Verifique as regras para o corpo da requisição
|401|Usuário não autenticado. Realize autenticação em /login
|404|Não existe categoria com o `id` informado. Consulte lista em /categoria
---


