# Indo além do console.log 

Durante o desenvolvimento web é muito comum utilizar o método `console.log` para depurar um código JavaScript, mas você sabia que o `console` é um objeto? E é este objeto que fornece acesso ao console de debug do navegador. 

De acordo com o portal  [developer.mozilla.org](developer.mozilla.org):

> O funcionamento dessa console API varia de navegador para navegador.

Neste artigo foi utilizado o navegador Chrome  😉.

Para visualizar quais são os métodos possíveis do console, basta digitar `console.log(console)` no terminal e você terá um retorno parecido com esse:

```javascript
console {debug: ƒ, error: ƒ, info: ƒ, log: ƒ, warn: ƒ, …}
assert: ƒ assert()
clear: ƒ clear()
context: ƒ context()
count: ƒ count()
countReset: ƒ countReset()
debug: ƒ debug()
dir: ƒ dir()
dirxml: ƒ dirxml()
error: ƒ error()
group: ƒ group()
groupCollapsed: ƒ groupCollapsed()
groupEnd: ƒ groupEnd()
info: ƒ info()
log: ƒ log()
memory: (...)
profile: ƒ profile()
profileEnd: ƒ profileEnd()
table: ƒ table()
time: ƒ time()
timeEnd: ƒ timeEnd()
timeLog: ƒ timeLog()
timeStamp: ƒ timeStamp()
trace: ƒ trace()
warn: ƒ warn()
Symbol(Symbol.toStringTag): "Object"
get memory: ƒ ()
set memory: ƒ ()
__proto__: Object
```

Este retorna a lista de métodos existente da API console, aqui neste artigo irei abordar os seguintes métodos: table, clear, warn, log, dir, error e info.


