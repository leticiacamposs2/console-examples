# Indo além do console.log 

Durante o desenvolvimento web é muito comum utilizar o método `console.log` para depurar um código JavaScript, mas você sabia que o `console` é um objeto? E é este objeto que fornece acesso ao console de debug do navegador. 

De acordo com o portal  [developer.mozilla.org](developer.mozilla.org):

> O funcionamento dessa console API varia de navegador para navegador.

Neste artigo foi utilizado o navegador Chrome  😉.

Para visualizar quais são os métodos possíveis do console, basta digitar `console.log(console)` no terminal e você terá um retorno parecido com esse:

Para visualizar a lista de métodos possíveis do console, basta digitar `console.log(console)` no terminal e você terá o seguinte retorno:

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

Aqui neste artigo irei abordar somente os seguintes métodos: table, clear, warn, log, dir, error e info, mas fique a vontade para pesquisar e questionar sobre algum método que não foi abordado aqui mas que você ainda tem dúvidas.

## console.log

O método log() existe essencialmente para permitir o envio de dados para o console de depuração do navegador. Pode ser enviada qualquer informação, normalmente com o intuito de depurar código.

```javascript
console.log([
    { name: "JavaScript", fileExtension: ".js" }, 
    { name: "TypeScript", fileExtension: ".ts" }, 
    { name: "Python", fileExtension: ".py" }
]);
```
saída:
```javascript
0: {name: "JavaScript", fileExtension: ".js"}
1: {name: "TypeScript", fileExtension: ".ts"}
2: {name: "Python", fileExtension: ".py"}
length: 3
__proto__: Array(0)
```
