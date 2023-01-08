## Users

```js
class UserManager
```

O modulo só fica disponível se a permissão `ADD_USER`, `EDIT_USER` ou `REMOVE_USER` for concedida.

Pode ser importada usando a função require com o modulo `@stmanager/users`

### Métodos

```ts
addUser(user: UserOptions) : void
```

Para executar essa função necessita ter a permissão `ADD_USER`, ela adiciona um usúario no banco de dados, o primeiro parametro deve ser um objeto com os seguintes parametros

| **Chave**   |   Tipo   | Descrição |
|-------------|:--------:|-----------|
| username    | `string`   | Uma string informando qual vai ser o username do novo usúario |
| password    | `string`   | Uma string informando qual vai ser a senha do novo usúario |
| plan_id     | `number`   | Uma número inteiro informando o plano no qual o usúario faz parte |
| email       | `?string`   | Uma string informando qual vai ser o e-mail do novo usúario |
| external_id | `?string`   | Uma string informando um id externo para identificação na api |
| notes       | `?string`   | Uma string informando um texto de notas para indentificar o usúario no paínel |

---------

```ts
editUser(id: number, user: UserOptions) : number
```

Para executar essa função necessita ter a permissão `EDIT_USER`, ela edita um usúario existente, o primeiro parametro deve ser um número informando o id do usúario e o segundo os valores que vão ser alteados

O retorno da função é o número de linhas afetadas

| **Chave**   |   Tipo   | Descrição |
|-------------|:--------:|-----------|
| username    | `?string`   | Uma string informando qual vai ser o username do usúario |
| password    | `?string`   | Uma string informando qual vai ser a senha do usúario |
| plan_id     | `?number`   | Uma número inteiro informando o plano no qual o usúario faz parte |
| email       | `?string`   | Uma string informando qual vai ser o e-mail do usúario |
| external_id | `?string`   | Uma string informando um id externo para identificação na api |
| notes       | `?string`   | Uma string informando um texto de notas para indentificar o usúario no paínel |

---------

```ts
removeUser(id: number) : boolean
```

Para executar essa função é necessario ter a permissão `REMOVE_USER`, ela deleta um usúario existente, seu parametro é o id do usúario que vai ser excluido e retorna um boleano indicando se a operação foi um sucesso ou não