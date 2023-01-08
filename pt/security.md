## Segurança

O Painel é executado como root, então não seria seguro permitir que um plugin execute um código "desconhecido" no servidor, temos três coisas que queremos evitar que um plugin malicioso faça



## Usar require com qualquer biblioteca

Um plugin malicioso pode acessar o terminal e executar código no servidor como root, permitir isso é uma falta de segurança total e facilita totalmente um hacker usar engenharia social ou conseguir acesso a um plugin publico e alterar o código para algo malicioso e (após atualizar nos servidores) ter acesso a um terminal só para ele.



## Acessar arquivos que não deveria

Um plugin malicioso poderia obter a senha do banco de dados apenas lendo o arquivo de configuração do painel, podendo obter todos os bancos de dados dos usuários do servidor



## Memoria



Um plugin também poderia acabar com a memória do servidor, ao executar um bonito código como o abaixo



```js
const storage = [];

const twoMegabytes = 1024 * 1024 * 2;

while (true) {


    const array = new Uint8Array(twoMegabytes);

    for (let ii = 0; ii  twoMegabytes; ii += 4096) {


        array[ii] = 1;

    }

    storage.push(array);

}
```



Esse código rapidamente iria acabar com a memória do servidor, tornando inutilizável e dificultando recuperar qualquer dado da máquina






## Como resolver?




A solução é rodar os plugins em uma sandbox, dessa forma os dois primeiros problemas desaparecem, e para o terceiro problema é executar limitando a memória do plugin, uma funcionalidade que a biblioteca worker_theads do nodejs permite de forma fácil

Assim, rodamos o plugin em um ambiente completamente isolado, utilizando uma biblioteca confiável para isso ([vm2](https://npmjs.com/package/vm2)) e um sistema de permissões, para só permitir que o plugin faça o que ele foi realmente feito para fazer