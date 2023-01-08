## Permissões

Para controlar o que um plugin pode ou não fazer possuimos um sistema de permissões, que são definidas no arquivo extension.json, elas podem ser:

#### ADD_USER

Permite que o plugin adicione usúarios no paínel usando o pacote [@stmanager/users](pt/modules/users.md)

#### EDIT_USER

Permite que o plugin edite usúarios no paínel usando o pacote [@stmanager/users](pt/modules/admins.md)

#### REMOVE_USER

Permite que o plugin remova usúarios no paínel usando o pacote [@stmanager/users](pt/modules/admins.md)

#### ADD_ADMIN

Permite que o plugin adicione administradores no paínel usando o pacote [@stmanager/admins](pt/modules/users.md)

#### EDIT_ADMIN

Permite que o plugin edite administradores no paínel usando o pacote [@stmanager/admins](pt/modules/admins.md)

Obs: Essa permissão pode afetar seu usúario

#### REMOVE_ADMIN

Permite que o plugin remova administradores no paínel usando o pacote [@stmanager/admins](pt/modules/admins.md)

Obs: Essa permissão pode afetar seu usúario

#### FILE

Permite que o plugin manipule os arquivos da sua pasta, as chamadas as pastas foram reescritas para accessarem sua pasta local, em outras palavras o codigo abaixo:

```js
fs.readdirSync("/");
```

é executado como:

```js
fs.readdirSync("/server/plugins/plugin_folder/") 
```

O acesso a arquivos fica disponível pelos modulos fs e path

[fs](https://nodejs.com/api/fs.html)
[path](https://nodejs.com/api/path.html)

#### REQUEST

Permite que o plugin detecte requests efetuados para o paínel [@stmanager/client](pt/modules/client.md?id=on_request)

#### ADD_PAGE

Permite que o plugin adicione pagínas no paínel [@stmanager/client](pt/modules/client.md?id=addPage)

#### ADD_MENU_ITEM

Permite que o plugin adicione novos itens no menu  [@stmanager/client](pt/modules/client.md?id=addMenuItem)

#### ADD_WIDGET_PANEL

Permite que o plugin adicione widget no paínel [@stmanager/client](pt/modules/client.md?id=addWidgetItem)