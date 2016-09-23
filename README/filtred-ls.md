 FILTERED LS
 ==============================
 ==== Resultado oficial ====

 ```
 var fs = require('fs')  
   var path = require('path')  

   var folder = process.argv[2]  
   var ext = '.' + process.argv[3]  

   fs.readdir(folder, function (err, files) {  
     if (err) return console.error(err)  
     files.forEach(function(file) {  
         if (path.extname(file) === ext) {  
             console.log(file)  
         }  
     })  
   })

 ```

 ==== Minha solução ====

 ```
  var fs = require('fs');
  var filePath = process.argv[2];
  var fileType = '.' + process.argv[3];

  fs.readdir(filePath, function(err, list) {
  for(var i=0; i<list.length; i++){
     if (list[i].match(fileType)) {
         console.log(list[i]);
     }
  }
  });

 ```
``filePath`` é o primeiro argumento
``fileType`` é o segundo argumento
``readdir`` lê o diretório
