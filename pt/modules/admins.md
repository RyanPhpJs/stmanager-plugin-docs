## Users

```js
class AdminManager
```

O modulo só fica disponível se a permissão `ADD_ADMIN`, `EDIT_ADMIN` ou `REMOVE_ADMIN` for concedida.

Pode ser importada usando a função require com o modulo `@stmanager/admins`

### Métodos

```ts
addAdmin(user: UserOptions) : void
```

Para executar essa função necessita ter a permissão `ADD_ADMIN`, ela adiciona um administrador no banco de dados, o primeiro parametro deve ser um objeto com os seguintes parametros

| **Chave**   |   Tipo   | Descrição |
|-------------|:--------:|-----------|
| username    | `string`   | Uma string informando qual vai ser o username do novo usúario |
| password    | `string`   | Uma string informando qual vai ser a senha do novo usúario |
| email       | `?string`   | Uma string informando qual vai ser o e-mail do novo usúario |
| external_id | `?string`   | Uma string informando um id externo para identificação na api |
| notes       | `?string`   | Uma string informando um texto de notas para indentificar o usúario no paínel |

---------

```ts
editAdmin(id: number, user: UserOptions) : number
```

?> **Atenção** plugins com essa permissão podem alterar qualquer usúario administrador

Para executar essa função necessita ter a permissão `EDIT_ADMIN`, ela edita um administrador existente, o primeiro parametro deve ser um número informando o id do administrador e o segundo os valores que vão ser alteados

O retorno da função é o número de linhas afetadas

| **Chave**   |   Tipo   | Descrição |
|-------------|:--------:|-----------|
| username    | `?string`   | Uma string informando qual vai ser o username do usúario |
| password    | `?string`   | Uma string informando qual vai ser a senha do usúario |
| email       | `?string`   | Uma string informando qual vai ser o e-mail do usúario |
| external_id | `?string`   | Uma string informando um id externo para identificação na api |
| notes       | `?string`   | Uma string informando um texto de notas para indentificar o usúario no paínel |

---------

```ts
removeAdmin(id: number) : boolean
```

?> **Atenção** plugins com essa permissão podem alterar qualquer usúario administrador

Para executar essa função é necessario ter a permissão `REMOVE_ADMIN`, ela deleta um administrador existente, seu parametro é o id do administrador que vai ser excluido e retorna um boleano indicando se a operação foi um sucesso ou não