## Extension.json

As definições de um plugin como nome, permissão e descrição ficam disponiveis no arquivo extension.json, que deve estar na pasta root do plugin, ela possui a seguinte estrutura

```json
{
    "name": "NOME DO PLUGIN",
    "icon": "CAMINHO PARA O ICON DO PLUGIN",
    "short_description": "Descrição curta para o plugin",
    "long_description": "Arquivo com a descrição longa",
    "main": "arquivo de inicio",
    "language": "Linguagem que a extensão foi produzida (javascript|coffescript)",
    "permissions": ["Permissões que o plugin necessita"]
}
```

Uma explicação detalhada das diretivas abaixo:

#### name (string)

Esse parametro define o nome do plugin, é obrigatoria ser informada e deve ser uma string de pelo menos 1 caracter

#### icon (?string)

Essa parametro define qual o icon no qual o plugin vai ser exibido, é opcional e se informado deve ser uma string para uma imagem local nos formatos png, jpg, jpeg, webp ou gif, caso não seja informada o plugin possuira o icon padrão

### short_description (string)

Esse parametro informa qual a descrição curta do plugin, exibida no paínel ao listar todos os plugins, é obrigatoria ser informada e deve ser uma string de pelo menos 1 caracter

### long_description (?string)

Esse parametro informa qual a descrição completa do plugin, é opcional e se informado deve ser uma string apontando para um arquivo markdown, se não informado a descrição curta é usada

### main (string)

Esse parametro informa qual o arquivo principal do plugin, que vai ser o iniciado, é obrigatorio ser informado e necessita ser uma string apontado para um arquivo

### language (?javascript|coffescript)

Esse parametro informa qual a linguagem que o plugin foi escrito, deve ser uma string com os valores "javascript" ou "coffescript"

### permissions (string[])

Esse parametro informa quais permissões o plugin necessita para funcionar, caso a permissão seja atendida os modulos serão adicionado para serem importados pela função require.
Deve ser uma array contendo as permissões, os valores das permissões podem ser vista [aqui](/pt/permission.md)