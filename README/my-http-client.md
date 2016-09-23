NAME
==============================
==== Resultado oficial ====

```
var http = require('http')  

  http.get(process.argv[2], function (response) {  
    response.setEncoding('utf8')  
    response.on('data', console.log)  
    response.on('error', console.error)  
  }).on('error', console.error)  

```

==== Minha solução ====
Primeiro é necessário instanciar o modulo ``http``
O ``http.get`` recebe dois parametros, o primeiro é o endereço ``process.argv[2]`` e o segundo é o callback onde é setado os dados de resposta.
