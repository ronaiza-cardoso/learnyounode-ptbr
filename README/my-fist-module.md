MAKE IT MODULAR
==============================
==== Resultado oficial ====

```
(program.js)
var filterFn = require('./solution_filter.js')  
var dir = process.argv[2]  
var filterStr = process.argv[3]  

filterFn(dir, filterStr, function (err, list) {  
  if (err)  
    return console.error('There was an error:', err)  

  list.forEach(function (file) {  
    console.log(file)  
  })  
})  

(module.js)
var fs = require('fs')  
 var path = require('path')  

 module.exports = function (dir, filterStr, callback) {  

   fs.readdir(dir, function (err, list) {  
     if (err)  
       return callback(err)  

     list = list.filter(function (file) {  
       return path.extname(file) === '.' + filterStr  
     })  

     callback(null, list)  
   })  
 }  


```

==== Minha solução ====

```
(program.js)
var mymodule = require('/home/ronaiza/Documentos/mymodule.js') \\exportando modulo usado

var dir = process.argv[2] \\ setando o diretório
var ext = process.argv[3] \\ setando a extensão

mymodule(dir, ext, function(err, list) { \\usando o modulo
  if (err) { \\usando o callback
   throw err; \\apresentando possível erro
  }
  else list.forEach(function (file) {
   console.log(file); \\listando os arquivos
  })
});

(mymodule.js)
var fs = require('fs')

module.exports = function(dirname, filter, callback) { \\setando as funções com os parametros esperados
var regex = new RegExp('\\.' + filter + '$') \\setando a variavel regex para identificar a extensão

var filelist = []
var i = 0

fs.readdir(dirname, function (err, list)
{
    if (err)
    {
      return callback(err);
    }
    else
    list.forEach(function (file){
    if (regex.test(file)) \\ testando as extensões dos arquivos
        filelist[i] = file; 
        i++;
    })
    return callback(null, filelist)
})

};

```
