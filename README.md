# Indo além do console.log 
Artigo no dev.to: https://dev.to/leticiacamposs2/indo-alem-do-console-log-386b
---

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

Aqui neste artigo irei abordar somente os seguintes métodos:
- [log](#log)
- [log-css](#log-css)
- [warn](#warn)
- [error](#error)
- [table](#table)
- [group](#group)
- [count](#count)
- [time](#time)

## 🗃️ console.log <a id="log"></a>

O método log() existe essencialmente para permitir o envio de dados para o console de depuração do navegador. Pode ser enviada qualquer informação, normalmente com o intuito de depurar código.

```javascript
console.log([
    { book: "Domain-Driven Design: Atacando as Complexidades no Coração do Software", author: "Martin Fowler" }, 
    { book: "Arquitetura Limpa: O guia do artesão para estrutura e design de software", author: "Robert C. Martin" },
    { book: "Por que os generalistas vencem em um mundo de especialistas", author: "David Epstein" }
]);
```

saída:

```javascript
(3) [{…}, {…}, {…}]
0:
author: "Martin Fowler"
book: "Domain-Driven Design: Atacando as Complexidades no Coração do Software"
__proto__: Object
1:
author: "Robert C. Martin"
book: "Arquitetura Limpa: O guia do artesão para estrutura e design de software"
__proto__: Object
2:
author: "David Epstein"
book: "Por que os generalistas vencem em um mundo de especialistas"
__proto__: Object
length: 3
__proto__: Array(0)
```

## 🎨 console.log com css <a id="log-css"></a>

Já imaginou usar o método log() personalizando a mensagem com CSS? Sim, é possível.

![log-css](https://media.giphy.com/media/5BYvjhtjsQdoyx9JT9/giphy.gif)

exemplo:

```javascript
const style = 'color:red; font-size:30px; font-weight: bold; -webkit-text-stroke: 1px black;'
console.log("%c JavaScript é muito maneiro!", style);
```

saída:

![saida-log-css](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/b8rp3whrh1nphl8sto47.png)

## ⚠️ console.warn <a id="warn"></a>

O método warn() possui um comportamento parecido com o .log() em alguns navegadores ele inclui um ícone de warning a mensagem.

```javascript
console.warn('mensagem de warning');
```
saída

![warn](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/65890p2veuushj8calev.PNG)

## ❌ console.error <a id="error"></a>

O método error() possui um comportamento parecido com o .log() em alguns navegadores ele inclui um ícone de erro a mensagem.

```javascript
console.error('mensagem de erro');
```
saída

![erro](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/z8owoibiaqp8j1qqqwxx.PNG)

## 📑 console.table <a id="table"></a>

O método table() exibe qualquer dado do tipo array de array, array de objetos ou um objeto com objetos aninhados formatados em uma tabela.

```javascript
console.table([
    { book: "Domain-Driven Design: Atacando as Complexidades no Coração do Software", author: "Martin Fowler" }, 
    { book: "Arquitetura Limpa: O guia do artesão para estrutura e design de software", author: "Robert C. Martin" },
    { book: "Por que os generalistas vencem em um mundo de especialistas", author: "David Epstein" }
]);
```

saída

![table](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hl3kpvc4g5a25ucbepvb.PNG)

## 👪 console.group <a id="group"></a>

O método group() exibe os dados de forma estruturada, sendo capaz de criar estruturas profundas e recolhíveis em seu console. Dessa forma é possível ocultar e organizar os seus registros. 

Cada chamada de console feita após invocar o método de grupo, encontrará seu lugar dentro do grupo criado. Para finalizar, você deve usar um `console.groupEnd()`

```javascript
console.group();
console.log("Esse é o 1° Grupo");
console.group();
console.log("Esse é o 2° Grupo");
console.groupEnd();
console.groupEnd();
console.log("Sai do escopo de grupos");
```

saída

![group](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vtk7r2f6bkyzs74cjb4j.PNG)

## 🧮 console.count <a id="count"></a>

O método count() conta quantas vezes ele foi chamado, esse é um método muito útil no caso de você ter tantos logs na sua aplicação e não sabe quantas vezes determinadas partes do código foram executadas. Para redefinir o contador utilize o método `console.countReset()`.

```javascript
console.count();
console.count();
console.count();
console.countReset();
console.count();
```

saída

```javascript
default: 1
default: 2
default: 3
default: 1
```

## ⌚ console.time <a id="time"></a>

O método time() serve como uma contagem de tempo, sendo possível fazer testes de desempenho rápidos para partes do seu código. Neste exemplo inicio com um console.time() método que pode receber um argumento opcional como um rótulo ou identificação para o temporizador fornecido. O cronômetro mencionado inicia apenas no momento de invocar este método. Em seguida, uso os métodos console.timeLog() e console.timeEnd() (com argumento de rótulo opcional) para registrar seu tempo (em milissegundos) e encerrar o cronômetro respeitado de acordo.

```javascript
console.time();
// trecho de código 1
console.timeLog(); // default: [time] ms
// trecho de código 2
console.timeEnd(); // default: [time] ms
```

saída

```javascript
default: 0.009033203125 ms
default: 0.151123046875 ms
```

E ai, o que achou? Muito legal né? Caso tenha algum método que não foi abordado aqui mas que você tenha dúvidas de sua implementação e funcionalidade, fique a vontade para me mandar mensagem 😊
