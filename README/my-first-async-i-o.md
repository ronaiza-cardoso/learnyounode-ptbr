MY FIST I/O ASYNC
==============================
==== Resultado oficial ====

```
var fs = require('fs')  
   var file = process.argv[2]  

   fs.readFile(file, function (err, contents) {  
     var lines = contents.toString().split('\n').length - 1  
     console.log(lines)  
   })  


```

==== Minha solução ====

```
var fs = require('fs');
var path = process.argv[2];

fs.readFile(path, 'utf8', function(err,data) {
  var lines = data.split('\n');
  console.log(lines.length-1);
});

```

A diferença desse desafio do anterior acontece no modo assincrono em que ele é feito, que é a forma como o Node trabalha. Deve-se utilizar callbacks
