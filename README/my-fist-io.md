MY FIST IO
==============================
==== Resultado oficial ====

```
var fs = require('fs')  

var contents = fs.readFileSync(process.argv[2
var lines = contents.toString().split('\n').length - 1  
console.log(lines)

```

==== Minha solução ====

```
var fs = require('fs');

var filename = process.argv[2];

file = fs.readFileSync(filename);

contents = file.toString();

console.log(contents.split('\n').length - 1);

```

Para usar a operção de sistema de arquivo é necessário instanciar o ``fs module`` da biblioteca do note.
Agora você~tem todos os módulos de leitura de arquivos na variável ``fs``
com o ``process.argv[2]`` é possivel acessar o arquivo de texto que voçê deseja fazer a leitura
