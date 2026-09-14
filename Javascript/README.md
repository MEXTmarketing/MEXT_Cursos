# Curso Completo de JavaScript — Do Absoluto Zero ao Uso Profissional

> Curso completo para quem nunca programou em JavaScript e quer aprender desde lógica e sintaxe até DOM, eventos, APIs, programação assíncrona, Node.js, Express e projetos reais.

---

# Sumário

1. O que é JavaScript
2. Preparando o ambiente
3. Primeiro código
4. Variáveis e tipos
5. Operadores
6. Strings
7. Condicionais
8. Loops
9. Funções
10. Arrays
11. Objetos
12. Métodos de array
13. Desestruturação e Spread
14. Erros
15. DOM
16. Eventos
17. Formulários
18. LocalStorage
19. Módulos
20. Classes
21. Promises
22. Async/Await
23. Fetch e APIs
24. Node.js
25. npm
26. Express
27. API REST
28. Segurança
29. Boas práticas
30. Exercícios
31. Projetos práticos
32. Projeto final
33. Cheat Sheet
34. Checklist
35. Próximos passos

---

# 1. O que é JavaScript?

JavaScript é uma linguagem de programação muito usada para criar interatividade e lógica em aplicações web.

Pode ser usada para:

- sites;
- sistemas web;
- dashboards;
- formulários;
- jogos;
- APIs;
- servidores;
- automações;
- aplicações mobile;
- aplicações desktop.

Exemplo:

```javascript
console.log("Olá, mundo!");
```

---

# 2. Onde JavaScript roda?

## Navegador

JavaScript roda em navegadores como:

- Chrome;
- Firefox;
- Edge;
- Safari.

## Servidor

Com Node.js, JavaScript também roda no backend.

---

# 3. Preparando o ambiente

Você pode usar:

- Visual Studio Code;
- navegador moderno;
- Node.js para backend.

Crie:

```text
index.html
script.js
```

HTML:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>JavaScript</title>
</head>
<body>
    <script src="script.js"></script>
</body>
</html>
```

No `script.js`:

```javascript
console.log("JavaScript funcionando!");
```

---

# 4. Console

```javascript
console.log("Mensagem");
console.warn("Aviso");
console.error("Erro");
```

Tabela:

```javascript
console.table([
    { nome: "Ana", idade: 25 },
    { nome: "Carlos", idade: 30 }
]);
```

---

# 5. Comentários

```javascript
// comentário de uma linha
```

```javascript
/*
comentário
com várias linhas
*/
```

---

# 6. Variáveis

## const

Use quando a variável não será reatribuída.

```javascript
const nome = "Ana";
```

## let

Use quando o valor será alterado.

```javascript
let idade = 20;
idade = 21;
```

## var

Forma antiga:

```javascript
var cidade = "Caxias";
```

Em código moderno, prefira `const` e `let`.

---

# 7. Tipos de dados

## String

```javascript
const nome = "Ana";
```

## Number

```javascript
const idade = 25;
const preco = 99.90;
```

## Boolean

```javascript
const ativo = true;
```

## Null

```javascript
const valor = null;
```

## Undefined

```javascript
let resultado;
```

## Object

```javascript
const pessoa = {
    nome: "Ana",
    idade: 25
};
```

## Array

```javascript
const nomes = ["Ana", "Carlos"];
```

---

# 8. typeof

```javascript
console.log(typeof "Ana");
console.log(typeof 10);
console.log(typeof true);
```

---

# 9. Operadores matemáticos

```javascript
+
-
*
/
%
**
```

Exemplo:

```javascript
const a = 10;
const b = 3;

console.log(a + b);
```

---

# 10. Incremento e decremento

```javascript
let numero = 10;

numero++;
numero--;
```

---

# 11. Strings

```javascript
const nome = "Ana";
```

Concatenação:

```javascript
const mensagem = "Olá, " + nome;
```

Template literal:

```javascript
const mensagem = `Olá, ${nome}!`;
```

---

# 12. Métodos de string

```javascript
const texto = "  JavaScript é legal  ";

texto.length;
texto.toUpperCase();
texto.toLowerCase();
texto.trim();
texto.includes("Java");
texto.startsWith("Java");
texto.endsWith("legal");
texto.replace("legal", "poderoso");
```

---

# 13. Conversão de tipos

```javascript
Number("25");
parseInt("25");
parseFloat("25.5");
String(25);
Boolean(1);
```

---

# 14. Comparações

```javascript
==
===
!=
!==
>
<
>=
<=
```

Prefira:

```javascript
===
!==
```

Exemplo:

```javascript
10 === "10";
```

Resultado:

```text
false
```

---

# 15. Operadores lógicos

AND:

```javascript
&&
```

OR:

```javascript
||
```

NOT:

```javascript
!
```

---

# 16. if, else e else if

```javascript
const idade = 20;

if (idade >= 18) {
    console.log("Maior de idade");
} else {
    console.log("Menor de idade");
}
```

Com `else if`:

```javascript
const nota = 8;

if (nota >= 9) {
    console.log("Excelente");
} else if (nota >= 7) {
    console.log("Aprovado");
} else {
    console.log("Reprovado");
}
```

---

# 17. switch

```javascript
const opcao = 2;

switch (opcao) {
    case 1:
        console.log("Cadastrar");
        break;

    case 2:
        console.log("Listar");
        break;

    default:
        console.log("Inválido");
}
```

---

# 18. Operador ternário

```javascript
const resultado = idade >= 18
    ? "Maior"
    : "Menor";
```

---

# 19. while

```javascript
let contador = 1;

while (contador <= 5) {
    console.log(contador);
    contador++;
}
```

---

# 20. do while

```javascript
let numero = 1;

do {
    console.log(numero);
    numero++;
} while (numero <= 5);
```

---

# 21. for

```javascript
for (let i = 1; i <= 10; i++) {
    console.log(i);
}
```

---

# 22. for...of

```javascript
const nomes = ["Ana", "Carlos", "Maria"];

for (const nome of nomes) {
    console.log(nome);
}
```

---

# 23. for...in

```javascript
const pessoa = {
    nome: "Ana",
    idade: 25
};

for (const chave in pessoa) {
    console.log(chave, pessoa[chave]);
}
```

---

# 24. break e continue

```javascript
for (let i = 1; i <= 10; i++) {
    if (i === 5) {
        break;
    }

    console.log(i);
}
```

```javascript
for (let i = 1; i <= 5; i++) {
    if (i === 3) {
        continue;
    }

    console.log(i);
}
```

---

# 25. Funções

```javascript
function saudacao() {
    console.log("Olá!");
}

saudacao();
```

Com parâmetros:

```javascript
function saudacao(nome) {
    console.log(`Olá, ${nome}!`);
}
```

Com retorno:

```javascript
function somar(a, b) {
    return a + b;
}
```

---

# 26. Parâmetros padrão

```javascript
function saudacao(nome, texto = "Olá") {
    return `${texto}, ${nome}!`;
}
```

---

# 27. Funções anônimas

```javascript
const somar = function(a, b) {
    return a + b;
};
```

---

# 28. Arrow functions

```javascript
const somar = (a, b) => {
    return a + b;
};
```

Forma curta:

```javascript
const somar = (a, b) => a + b;
```

---

# 29. Escopo

```javascript
if (true) {
    let numero = 10;
    console.log(numero);
}
```

Fora do bloco, `numero` não existe.

---

# 30. Arrays

```javascript
const numeros = [10, 20, 30];
```

Acessar:

```javascript
console.log(numeros[0]);
```

Quantidade:

```javascript
console.log(numeros.length);
```

---

# 31. push, pop, shift e unshift

Adicionar ao fim:

```javascript
numeros.push(40);
```

Remover do fim:

```javascript
numeros.pop();
```

Adicionar no início:

```javascript
numeros.unshift(5);
```

Remover do início:

```javascript
numeros.shift();
```

---

# 32. map

Transforma itens.

```javascript
const numeros = [1, 2, 3];

const dobrados = numeros.map(
    numero => numero * 2
);
```

---

# 33. filter

```javascript
const pares = numeros.filter(
    numero => numero % 2 === 0
);
```

---

# 34. find

```javascript
const produto = produtos.find(
    produto => produto.id === 10
);
```

---

# 35. findIndex

```javascript
const indice = produtos.findIndex(
    produto => produto.id === 10
);
```

---

# 36. some

```javascript
const existeSemEstoque = produtos.some(
    produto => produto.estoque === 0
);
```

---

# 37. every

```javascript
const todosAtivos = produtos.every(
    produto => produto.ativo
);
```

---

# 38. reduce

```javascript
const numeros = [10, 20, 30];

const total = numeros.reduce(
    (soma, numero) => soma + numero,
    0
);
```

---

# 39. sort

```javascript
const numeros = [5, 2, 10, 1];

numeros.sort((a, b) => a - b);
```

Decrescente:

```javascript
numeros.sort((a, b) => b - a);
```

---

# 40. Objetos

```javascript
const cliente = {
    id: 1,
    nome: "Ana",
    email: "ana@email.com"
};
```

Acessar:

```javascript
cliente.nome;
cliente["nome"];
```

---

# 41. Métodos em objetos

```javascript
const pessoa = {
    nome: "Ana",

    apresentar() {
        console.log(`Olá, sou ${this.nome}`);
    }
};
```

---

# 42. Desestruturação

Objeto:

```javascript
const cliente = {
    nome: "Ana",
    idade: 25
};

const { nome, idade } = cliente;
```

Array:

```javascript
const numeros = [10, 20];

const [a, b] = numeros;
```

---

# 43. Spread operator

Array:

```javascript
const a = [1, 2];
const b = [3, 4];

const todos = [...a, ...b];
```

Objeto:

```javascript
const atualizado = {
    ...cliente,
    idade: 26
};
```

---

# 44. Rest operator

```javascript
function somar(...numeros) {
    return numeros.reduce(
        (total, numero) => total + numero,
        0
    );
}
```

---

# 45. Optional chaining

```javascript
const cidade = usuario?.endereco?.cidade;
```

---

# 46. Nullish coalescing

```javascript
const nome = usuario.nome ?? "Visitante";
```

---

# 47. Math

```javascript
Math.round(10.5);
Math.floor(10.9);
Math.ceil(10.1);
Math.max(10, 20, 30);
Math.min(10, 20, 30);
Math.random();
```

Aleatório de 1 a 10:

```javascript
const numero = Math.floor(
    Math.random() * 10
) + 1;
```

---

# 48. Datas

```javascript
const agora = new Date();
```

```javascript
agora.getFullYear();
agora.getMonth();
agora.getDate();
```

---

# 49. JSON

Objeto para JSON:

```javascript
const json = JSON.stringify(cliente);
```

JSON para objeto:

```javascript
const objeto = JSON.parse(json);
```

---

# 50. try, catch e finally

```javascript
try {
    JSON.parse("inválido");
} catch (erro) {
    console.error(erro.message);
} finally {
    console.log("Finalizado");
}
```

---

# 51. throw

```javascript
function sacar(saldo, valor) {
    if (valor > saldo) {
        throw new Error("Saldo insuficiente");
    }
}
```

---

# 52. DOM

DOM significa:

```text
Document Object Model
```

Ele permite manipular o HTML usando JavaScript.

---

# 53. querySelector

HTML:

```html
<h1 id="titulo">Olá</h1>
```

JavaScript:

```javascript
const titulo = document.querySelector("#titulo");
```

Classe:

```javascript
const card = document.querySelector(".card");
```

---

# 54. querySelectorAll

```javascript
const botoes = document.querySelectorAll(".botao");
```

---

# 55. Alterando conteúdo

```javascript
titulo.textContent = "Novo título";
```

```javascript
titulo.innerHTML = "<strong>Novo</strong>";
```

Evite `innerHTML` com conteúdo vindo do usuário.

---

# 56. classList

```javascript
elemento.classList.add("ativo");
elemento.classList.remove("ativo");
elemento.classList.toggle("ativo");
```

---

# 57. Criando elementos

```javascript
const item = document.createElement("li");

item.textContent = "Novo item";

document.querySelector("#lista")
    .appendChild(item);
```

---

# 58. Eventos

```javascript
botao.addEventListener("click", () => {
    console.log("Clicou");
});
```

Eventos comuns:

```text
click
submit
input
change
keydown
keyup
focus
blur
mouseenter
mouseleave
DOMContentLoaded
```

---

# 59. Formulários

HTML:

```html
<form id="form">
    <input id="nome" type="text">
    <button>Enviar</button>
</form>
```

JavaScript:

```javascript
const form = document.querySelector("#form");

form.addEventListener("submit", evento => {
    evento.preventDefault();

    const nome = document.querySelector("#nome").value;

    console.log(nome);
});
```

---

# 60. FormData

```javascript
const dados = new FormData(formulario);

const nome = dados.get("nome");
```

---

# 61. Validação

```javascript
if (nome.trim() === "") {
    alert("Informe o nome");
    return;
}
```

---

# 62. LocalStorage

Salvar:

```javascript
localStorage.setItem("nome", "Ana");
```

Ler:

```javascript
const nome = localStorage.getItem("nome");
```

Remover:

```javascript
localStorage.removeItem("nome");
```

---

# 63. Objetos no LocalStorage

```javascript
localStorage.setItem(
    "cliente",
    JSON.stringify(cliente)
);
```

Ler:

```javascript
const cliente = JSON.parse(
    localStorage.getItem("cliente")
);
```

---

# 64. SessionStorage

```javascript
sessionStorage.setItem("token", "abc");
```

Funciona de forma parecida ao LocalStorage, mas dura apenas durante a sessão da aba.

---

# 65. Módulos

Arquivo `matematica.js`:

```javascript
export function somar(a, b) {
    return a + b;
}
```

Arquivo `app.js`:

```javascript
import { somar } from "./matematica.js";
```

HTML:

```html
<script type="module" src="app.js"></script>
```

---

# 66. Classes

```javascript
class Pessoa {
    constructor(nome, idade) {
        this.nome = nome;
        this.idade = idade;
    }

    apresentar() {
        console.log(`Sou ${this.nome}`);
    }
}
```

Uso:

```javascript
const pessoa = new Pessoa("Ana", 25);
```

---

# 67. Herança

```javascript
class Animal {
    emitirSom() {
        console.log("Som");
    }
}

class Cachorro extends Animal {
    emitirSom() {
        console.log("Au au");
    }
}
```

---

# 68. Campos privados

```javascript
class Conta {
    #saldo = 0;

    depositar(valor) {
        this.#saldo += valor;
    }

    getSaldo() {
        return this.#saldo;
    }
}
```

---

# 69. Promises

```javascript
const promessa = new Promise((resolve, reject) => {
    const sucesso = true;

    if (sucesso) {
        resolve("Tudo certo");
    } else {
        reject(new Error("Falhou"));
    }
});
```

Consumir:

```javascript
promessa
    .then(resultado => console.log(resultado))
    .catch(erro => console.error(erro));
```

---

# 70. async e await

```javascript
async function executar() {
    try {
        const resultado = await promessa;
        console.log(resultado);
    } catch (erro) {
        console.error(erro);
    }
}
```

---

# 71. fetch

```javascript
const resposta = await fetch(
    "https://api.exemplo.com/clientes"
);

if (!resposta.ok) {
    throw new Error(`Erro HTTP: ${resposta.status}`);
}

const dados = await resposta.json();
```

---

# 72. POST com fetch

```javascript
const resposta = await fetch(
    "/api/clientes",
    {
        method: "POST",
        headers: {
            "Content-Type": "application/json"
        },
        body: JSON.stringify({
            nome: "Ana",
            email: "ana@email.com"
        })
    }
);
```

---

# 73. PUT e DELETE

PUT:

```javascript
await fetch("/api/clientes/1", {
    method: "PUT",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify({
        nome: "Ana Silva"
    })
});
```

DELETE:

```javascript
await fetch("/api/clientes/1", {
    method: "DELETE"
});
```

---

# 74. Promise.all

```javascript
const [clientes, produtos] = await Promise.all([
    fetch("/api/clientes").then(r => r.json()),
    fetch("/api/produtos").then(r => r.json())
]);
```

---

# 75. AbortController

```javascript
const controller = new AbortController();

fetch(url, {
    signal: controller.signal
});
```

Cancelar:

```javascript
controller.abort();
```

---

# 76. Node.js

Node.js permite executar JavaScript fora do navegador.

Verifique:

```bash
node -v
```

Arquivo:

```javascript
console.log("Executando no Node.js");
```

Executar:

```bash
node app.js
```

---

# 77. npm

```bash
npm -v
```

Criar projeto:

```bash
npm init -y
```

Instalar pacote:

```bash
npm install express
```

---

# 78. package.json

```json
{
  "name": "meu-projeto",
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "start": "node app.js"
  }
}
```

---

# 79. Node.js — arquivos

```javascript
import { readFile, writeFile } from "node:fs/promises";

const conteudo = await readFile(
    "dados.txt",
    "utf8"
);

await writeFile(
    "saida.txt",
    conteudo
);
```

---

# 80. path

```javascript
import path from "node:path";

const caminho = path.join(
    "dados",
    "clientes.json"
);
```

---

# 81. Express

Instalar:

```bash
npm install express
```

Servidor:

```javascript
import express from "express";

const app = express();

app.use(express.json());

app.get("/", (req, res) => {
    res.send("API funcionando");
});

app.listen(3000, () => {
    console.log("Servidor na porta 3000");
});
```

---

# 82. Rotas

```javascript
app.get("/clientes", (req, res) => {
    res.json([]);
});
```

Parâmetro:

```javascript
app.get("/clientes/:id", (req, res) => {
    const id = req.params.id;

    res.json({ id });
});
```

---

# 83. Query string

URL:

```text
/clientes?cidade=Caxias
```

```javascript
const cidade = req.query.cidade;
```

---

# 84. Body

```javascript
app.post("/clientes", (req, res) => {
    const dados = req.body;

    res.status(201).json(dados);
});
```

---

# 85. Middleware

```javascript
function log(req, res, next) {
    console.log(req.method, req.url);
    next();
}

app.use(log);
```

---

# 86. CRUD em memória

```javascript
let clientes = [];
```

Criar:

```javascript
app.post("/clientes", (req, res) => {
    const cliente = {
        id: Date.now(),
        ...req.body
    };

    clientes.push(cliente);

    res.status(201).json(cliente);
});
```

Listar:

```javascript
app.get("/clientes", (req, res) => {
    res.json(clientes);
});
```

Buscar:

```javascript
app.get("/clientes/:id", (req, res) => {
    const id = Number(req.params.id);

    const cliente = clientes.find(
        cliente => cliente.id === id
    );

    if (!cliente) {
        return res.status(404).json({
            error: "Cliente não encontrado"
        });
    }

    res.json(cliente);
});
```

---

# 87. Banco de dados — introdução

No backend JavaScript você pode usar:

- PostgreSQL;
- MySQL;
- MariaDB;
- SQLite;
- MongoDB.

Ferramentas comuns:

- Prisma;
- Sequelize;
- TypeORM;
- Knex;
- drivers nativos.

---

# 88. Variáveis de ambiente

Nunca coloque segredos no código.

Exemplo `.env`:

```text
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASS=senha
```

No Node:

```javascript
process.env.PORT;
```

---

# 89. Segurança

Cuidados:

- validar dados;
- nunca confiar no frontend;
- evitar `innerHTML` com entrada externa;
- proteger tokens;
- não expor stack trace;
- usar HTTPS;
- configurar CORS corretamente;
- proteger segredos;
- validar uploads;
- usar queries parametrizadas no banco.

---

# 90. XSS

Perigoso:

```javascript
elemento.innerHTML = valorDoUsuario;
```

Para texto:

```javascript
elemento.textContent = valorDoUsuario;
```

---

# 91. CORS

Com Express:

```bash
npm install cors
```

```javascript
import cors from "cors";

app.use(cors());
```

Em produção, evite liberar origens desnecessariamente.

---

# 92. Debugging

Aprenda a usar DevTools:

```text
Console
Sources
Network
Application
Breakpoints
Watch
Call Stack
```

Também existe:

```javascript
debugger;
```

---

# 93. Boas práticas

## Prefira const

```javascript
const nome = "Ana";
```

## Use let quando necessário

```javascript
let contador = 0;
```

## Evite var

## Use nomes claros

Bom:

```javascript
buscarClientePorId();
```

Ruim:

```javascript
buscar();
```

## Divida funções grandes

## Evite estado global

## Trate erros assíncronos

## Valide dados externos

---

# 94. Truthy e Falsy

Valores falsy:

```text
false
0
""
null
undefined
NaN
```

Exemplo:

```javascript
if (!nome) {
    console.log("Nome vazio");
}
```

---

# 95. Set

```javascript
const numeros = new Set([
    1,
    2,
    2,
    3
]);
```

Adicionar:

```javascript
numeros.add(4);
```

---

# 96. Map

```javascript
const mapa = new Map();

mapa.set("nome", "Ana");

console.log(
    mapa.get("nome")
);
```

---

# 97. Object.keys, values e entries

```javascript
Object.keys(cliente);
Object.values(cliente);
Object.entries(cliente);
```

---

# 98. setTimeout

```javascript
setTimeout(() => {
    console.log("Executou depois");
}, 1000);
```

---

# 99. setInterval

```javascript
const id = setInterval(() => {
    console.log("Executando");
}, 1000);
```

Parar:

```javascript
clearInterval(id);
```

---

# 100. Projeto 1 — To-do List

Crie uma aplicação com:

- adicionar tarefa;
- editar;
- concluir;
- excluir;
- pesquisar;
- filtrar;
- salvar em LocalStorage.

Modelo:

```javascript
const tarefa = {
    id: Date.now(),
    texto: "Estudar JavaScript",
    concluida: false
};
```

---

# 101. Projeto 2 — Busca em API

Crie uma tela que:

- recebe pesquisa;
- chama uma API;
- mostra loading;
- trata erro;
- renderiza resultados;
- permite nova pesquisa.

---

# 102. Projeto 3 — CRUD Frontend

Cadastro de clientes:

```text
nome
email
telefone
cidade
```

Use:

- formulário;
- validação;
- LocalStorage;
- edição;
- exclusão;
- busca;
- filtros.

---

# 103. Projeto 4 — API Node.js

Crie:

```text
GET    /produtos
GET    /produtos/:id
POST   /produtos
PUT    /produtos/:id
DELETE /produtos/:id
```

Primeiro use array em memória.

Depois migre para banco de dados.

---

# 104. Exercícios básicos

1. Mostre `Olá, mundo`.
2. Crie variáveis.
3. Some dois números.
4. Descubra se é maior de idade.
5. Verifique par ou ímpar.
6. Faça uma tabuada.
7. Conte de 1 a 100.
8. Calcule média.
9. Inverta uma string.
10. Conte vogais.
11. Descubra maior número de um array.
12. Remova duplicados.

---

# 105. Exercícios intermediários

1. Use `map`.
2. Use `filter`.
3. Use `find`.
4. Use `reduce`.
5. Ordene objetos.
6. Use destructuring.
7. Use spread.
8. Manipule DOM.
9. Crie formulário.
10. Use eventos.
11. Salve no LocalStorage.
12. Crie classe Produto.

---

# 106. Exercícios avançados

1. Consuma API com fetch.
2. Faça POST.
3. Faça PUT.
4. Faça DELETE.
5. Trate erro HTTP.
6. Use async/await.
7. Use Promise.all.
8. Crie módulos.
9. Crie servidor Node.js.
10. Use Express.
11. Crie CRUD REST.
12. Conecte banco de dados.

---

# 107. Projeto final

Crie um sistema completo para um destes temas:

- restaurante;
- delivery;
- e-commerce;
- CRM;
- agenda;
- estoque;
- biblioteca;
- escola;
- sistema de reservas;
- painel administrativo.

O projeto deve ter:

- HTML;
- CSS;
- JavaScript moderno;
- módulos;
- DOM;
- eventos;
- formulários;
- validação;
- arrays e objetos;
- map, filter, find e reduce;
- LocalStorage;
- classes;
- async/await;
- fetch;
- frontend;
- Node.js;
- Express;
- API REST;
- CRUD;
- banco de dados;
- variáveis de ambiente;
- tratamento de erros.

Estrutura sugerida:

```text
projeto/
├── frontend/
│   ├── index.html
│   ├── css/
│   └── js/
│       ├── app.js
│       ├── api.js
│       ├── ui.js
│       └── utils.js
│
└── backend/
    ├── src/
    │   ├── routes/
    │   ├── controllers/
    │   ├── services/
    │   └── repositories/
    ├── package.json
    └── .env
```

---

# 108. Cheat Sheet

Variável:

```javascript
const nome = "Ana";
```

Mutável:

```javascript
let idade = 25;
```

IF:

```javascript
if (idade >= 18) {
}
```

FOR:

```javascript
for (let i = 0; i < 10; i++) {
}
```

Função:

```javascript
function somar(a, b) {
    return a + b;
}
```

Arrow:

```javascript
const somar = (a, b) => a + b;
```

Array:

```javascript
const itens = [];
```

Map:

```javascript
const nomes = clientes.map(
    cliente => cliente.nome
);
```

Filter:

```javascript
const ativos = clientes.filter(
    cliente => cliente.ativo
);
```

Find:

```javascript
const cliente = clientes.find(
    cliente => cliente.id === 1
);
```

Objeto:

```javascript
const cliente = {
    nome: "Ana"
};
```

DOM:

```javascript
const elemento = document.querySelector("#id");
```

Evento:

```javascript
botao.addEventListener("click", () => {
});
```

LocalStorage:

```javascript
localStorage.setItem(
    "dados",
    JSON.stringify(dados)
);
```

Fetch:

```javascript
const resposta = await fetch(url);
const dados = await resposta.json();
```

Node:

```bash
node app.js
```

Express:

```javascript
app.get("/", (req, res) => {
    res.send("OK");
});
```

---

# 109. Checklist de domínio

## Básico

- [ ] Sei usar console.
- [ ] Sei criar variáveis.
- [ ] Sei usar const e let.
- [ ] Conheço os tipos principais.
- [ ] Sei usar if.
- [ ] Sei usar loops.
- [ ] Sei criar funções.
- [ ] Sei usar arrays.
- [ ] Sei usar objetos.

## Intermediário

- [ ] Sei usar map.
- [ ] Sei usar filter.
- [ ] Sei usar find.
- [ ] Sei usar reduce.
- [ ] Sei usar destructuring.
- [ ] Sei usar spread.
- [ ] Sei manipular DOM.
- [ ] Sei usar eventos.
- [ ] Sei validar formulários.
- [ ] Sei usar LocalStorage.
- [ ] Sei usar módulos.

## Avançado

- [ ] Sei criar classes.
- [ ] Entendo Promises.
- [ ] Sei usar async/await.
- [ ] Sei usar fetch.
- [ ] Sei consumir APIs.
- [ ] Sei fazer POST, PUT e DELETE.
- [ ] Sei usar Node.js.
- [ ] Sei usar npm.
- [ ] Sei usar Express.
- [ ] Sei criar API REST.
- [ ] Sei usar middleware.
- [ ] Sei estruturar CRUD.
- [ ] Sei trabalhar com banco de dados.

---

# 110. Como estudar

## Etapa 1

```text
variáveis
tipos
if
loops
funções
```

## Etapa 2

```text
arrays
objetos
map
filter
find
reduce
```

## Etapa 3

```text
DOM
eventos
formulários
LocalStorage
```

## Etapa 4

```text
Promises
async/await
fetch
APIs
módulos
```

## Etapa 5

```text
Node.js
npm
Express
API REST
banco
```

---

# 111. Próximos passos

Depois deste curso, estude:

- TypeScript;
- React;
- Vue;
- Angular;
- Next.js;
- Node.js avançado;
- Express avançado;
- Fastify;
- NestJS;
- PostgreSQL;
- Prisma;
- MongoDB;
- WebSockets;
- autenticação;
- JWT;
- OAuth;
- testes;
- Vitest;
- Jest;
- Playwright;
- Vite;
- Docker;
- CI/CD.

---

# Regra de ouro

Sempre pergunte:

```text
Esse valor precisa ser mutável?
Posso usar const?
Esse array pode ser tratado com map/filter/find?
Esse dado externo foi validado?
Essa chamada assíncrona tem tratamento de erro?
Preciso usar innerHTML ou textContent resolve?
Esse código deveria estar em outro módulo?
```

---

# Desafio final

Crie um sistema completo com:

- frontend;
- formulários;
- validação;
- DOM;
- eventos;
- módulos;
- LocalStorage;
- classes;
- async/await;
- fetch;
- backend Node.js;
- Express;
- API REST;
- CRUD;
- banco de dados;
- tratamento de erros.

Se conseguir fazer isso sem depender de um tutorial passo a passo, você já terá uma base muito sólida em JavaScript.

---

# Conclusão

Ao terminar e praticar este curso, você deve conseguir:

- escrever JavaScript moderno;
- criar lógica;
- trabalhar com funções;
- manipular arrays e objetos;
- usar map, filter, find e reduce;
- manipular DOM;
- trabalhar com eventos;
- validar formulários;
- usar armazenamento local;
- criar módulos;
- entender Promises;
- trabalhar com async/await;
- consumir APIs;
- criar aplicações frontend;
- usar Node.js;
- usar npm;
- criar APIs com Express;
- implementar CRUD;
- preparar-se para frameworks modernos.

> JavaScript fica muito mais fácil quando você domina bem funções, arrays, objetos, DOM e código assíncrono.

Crie projetos, use o debugger, leia os erros do console e refatore seu próprio código.
