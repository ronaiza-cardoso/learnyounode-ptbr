==== Resultado oficial ====

```
var result = 0

     for (var i = 2; i < process.argv.length; i++)
       result += Number(process.argv[i])

     console.log(result)
```

==== Minha solução ====

```
var total = 0;

process.argv.forEach(function(item) {
  //we need to exclude first and second items
  //so we could just filter them as NAN
  total += +item ? +item : 0;
});

console.log(total);

```

Primeiro devemos declarar uma variável, depois usar o forEach para passar em cada item do array. Após isso iterar a variável ```total``` com o operador ternário. Caso o item seja falso (NaN) itera com 0 e caso seja verdadeiro itera com 1.
