## Users

```js
class PluginClient extends EventEmitter
```

O modulo só fica disponível se a permissão `REQUEST`, `ADD_PAGE`, `ADD_MENU_ITEM` ou `ADD_WIDGET_PANEL` for concedida.

Pode ser importada usando a função require com o modulo `@stmanager/client`

### Eventos

-----

```js
"startRequest", requestInfo: RequestStartInfoInterface
```

Esse evento só é executado se a permissão `REQUEST` for concedida, é emitido sempre que um novo request é iníciado para o paínel, 

Seus parametros são um objeto com os seguintes atributos

| **Chave**   |   Tipo   | Descrição |
|-------------|:--------:|-----------|
| headers    | `Map<string, string>`   | Contem um objeto Map com os headers da pagína |
| ip         | `string`   | IP no qual o paínel está sendo acessado |
| request_key | `string`   | Indentificador unico para o request |

-----

```js
"endRequest", requestInfo: RequestEndInfoInterface
```

Esse evento só é executado se a permissão `REQUEST` for concedida, é emitido sempre que um novo request é finalizado pelo paínel, 

Seus parametros são um objeto com os seguintes atributos

| **Chave**   |   Tipo   | Descrição |
|-------------|:--------:|-----------|
| headers    | `Map<string, string>`   | Contem um objeto Map com os headers de resposta |
| bodySize   | `number`   | Tamanho da resposta enviada |
| request_key | `string`   | Indentificador unico para o request |

### Métodos

-----

```ts
addPage(role: "ADMIN"|"USER", url: string, callback: (req: StRequest, res: StResponse) => void) : void
```

Para executar essa função necessita ter a permissão `ADD_PAGE`, ela adiciona uma nova pagína no paínel.

O primeiro parametro é o cargo que o usúario deve ter para acessar a pagina, o segundo parametro é a url necessaria para acessar pagina, o terceiro é uma função que vai ser executada quando a pagína for acessada

-----

```ts
addMenuItem(name: string, icon: string, category: string, target: string) : void
```

Para executar essa função necessita ter a permissão `ADD_MENU_ITEM`, ela adiciona um novo item no menu no paínel do administrador.

O primeiro parametro é o o nome do item, como ele aparecerá no menu; O segundo é o icone usado, são permitido icones do fontawesome, informe a classe que será adicionada; O terceiro parametro informa a categoria na qual ele será adicionado, o quarto parametro informa a url na qual ele será redirecionado

?> Caso a categoria não exista ela será criada.

-----

```ts
addWidgetItem(name: string, category: string, image: string, target: string, category_icon ?: string) : void
```

Para executar essa função necessita ter a permissão `ADD_WIDGET_ITEM`, ela adiciona um novo widget no menu no paínel do usúario.

O primeiro parametro é o o nome do item, como ele aparecerá no widget; O segundo parametro informa a categoria na qual ele será adicionado; o terceiro informa a imagem do widget; o quarto informa a url na qual ele será redirecionado, o quinto informa o icone da categoria que será usado caso não exista

?> Caso a categoria não exista ela será criada.