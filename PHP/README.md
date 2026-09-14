# Curso Completo de PHP — Do Absoluto Zero ao Backend Profissional

> Curso prático para quem nunca programou em PHP e quer aprender desde os fundamentos até formulários, sessões, arquivos, JSON, orientação a objetos, PDO/MySQL, autenticação, segurança, APIs, Composer, MVC e organização de projetos reais.

---

# Sumário

1. O que é PHP
2. Preparando o ambiente
3. Primeiro programa
4. Variáveis e tipos
5. Operadores
6. Strings
7. Arrays
8. Condicionais
9. Laços
10. Funções
11. Include e Require
12. Superglobais
13. GET e POST
14. Formulários
15. Validação
16. Cookies
17. Sessões
18. Upload
19. Arquivos
20. JSON
21. Datas
22. Erros e Exceptions
23. Orientação a Objetos
24. Classes e Objetos
25. Encapsulamento
26. Herança
27. Interfaces
28. Traits
29. Namespaces
30. Enums
31. PDO
32. MySQL
33. CRUD
34. Login
35. Segurança
36. SQL Injection
37. XSS
38. CSRF
39. APIs
40. cURL
41. Composer
42. Autoload
43. MVC
44. Roteamento
45. .env
46. Boas práticas
47. Exercícios
48. Projetos práticos
49. Projeto final
50. Cheat Sheet
51. Checklist
52. Próximos passos

---

# 1. O que é PHP?

PHP é uma linguagem de programação voltada principalmente para desenvolvimento web.

O código PHP roda no servidor.

Exemplo:

```php
<?php

echo "Olá, mundo!";
```

O navegador recebe apenas o resultado gerado pelo servidor.

---

# 2. Onde PHP é usado?

PHP é muito usado em:

- sites;
- sistemas administrativos;
- e-commerce;
- APIs;
- painéis;
- intranets;
- sistemas empresariais;
- WordPress;
- Laravel;
- Symfony;
- integrações;
- automações web.

---

# 3. Preparando o ambiente

No Windows, opções comuns:

- XAMPP;
- Laragon;
- WampServer.

No XAMPP, os projetos normalmente ficam em:

```text
C:\xampp\htdocs\
```

Exemplo:

```text
C:\xampp\htdocs\meuprojeto
```

Depois:

```text
http://localhost/meuprojeto
```

Verifique o PHP pelo terminal:

```bash
php -v
```

Servidor embutido:

```bash
php -S localhost:8000
```

---

# 4. Primeiro programa

Crie:

```text
index.php
```

Conteúdo:

```php
<?php

echo "Olá, PHP!";
```

---

# 5. Como o PHP funciona

```text
Navegador
   ↓
Requisição HTTP
   ↓
Servidor
   ↓
PHP executa
   ↓
HTML ou JSON
   ↓
Resposta
```

---

# 6. Comentários

```php
// comentário
```

```php
# comentário
```

```php
/*
comentário
de várias linhas
*/
```

---

# 7. Variáveis

Variáveis começam com `$`.

```php
$nome = "Ana";
$idade = 25;
$ativo = true;
```

---

# 8. Tipos de dados

String:

```php
$nome = "Carlos";
```

Integer:

```php
$idade = 30;
```

Float:

```php
$preco = 99.90;
```

Boolean:

```php
$ativo = true;
```

Array:

```php
$nomes = ["Ana", "Carlos"];
```

Null:

```php
$valor = null;
```

---

# 9. Constantes

```php
define("APP_NAME", "Meu Sistema");
```

Ou:

```php
const VERSAO = "1.0";
```

---

# 10. Operadores matemáticos

```php
+
-
*
/
%
**
```

Exemplo:

```php
$a = 10;
$b = 3;

echo $a + $b;
```

---

# 11. Comparações

```php
==
===
!=
!==
>
<
>=
<=
```

Prefira comparação estrita quando fizer sentido:

```php
$idade === 18
```

---

# 12. Operadores lógicos

AND:

```php
&&
```

OR:

```php
||
```

NOT:

```php
!
```

---

# 13. Strings

```php
$nome = "Ana";
```

Concatenação:

```php
$mensagem =
    "Olá, " . $nome;
```

Interpolação:

```php
echo "Olá, $nome!";
```

Ou:

```php
echo "Olá, {$nome}!";
```

---

# 14. Funções úteis de string

```php
strlen($texto);
strtolower($texto);
strtoupper($texto);
trim($texto);
str_replace("a", "b", $texto);
```

Separar:

```php
$partes =
    explode(",", "Ana,Carlos,Maria");
```

Juntar:

```php
$texto =
    implode(", ", $partes);
```

---

# 15. Arrays

```php
$nomes = [
    "Ana",
    "Carlos",
    "Maria"
];
```

Acessar:

```php
echo $nomes[0];
```

Adicionar:

```php
$nomes[] = "João";
```

Quantidade:

```php
echo count($nomes);
```

---

# 16. Arrays associativos

```php
$cliente = [
    "nome" => "Ana",
    "email" => "ana@email.com",
    "idade" => 25
];
```

Acessar:

```php
echo $cliente["nome"];
```

---

# 17. Arrays multidimensionais

```php
$clientes = [
    [
        "nome" => "Ana",
        "email" => "ana@email.com"
    ],
    [
        "nome" => "Carlos",
        "email" => "carlos@email.com"
    ]
];
```

Acessar:

```php
echo $clientes[0]["nome"];
```

---

# 18. if, elseif e else

```php
$idade = 20;

if ($idade >= 18) {
    echo "Maior de idade";
} else {
    echo "Menor de idade";
}
```

Com `elseif`:

```php
$nota = 8;

if ($nota >= 9) {
    echo "Excelente";
} elseif ($nota >= 7) {
    echo "Aprovado";
} else {
    echo "Reprovado";
}
```

---

# 19. switch

```php
$opcao = 2;

switch ($opcao) {
    case 1:
        echo "Cadastrar";
        break;

    case 2:
        echo "Listar";
        break;

    default:
        echo "Inválido";
}
```

---

# 20. match

```php
$status = 2;

$texto = match ($status) {
    1 => "Pendente",
    2 => "Pago",
    3 => "Cancelado",
    default => "Desconhecido"
};
```

---

# 21. while

```php
$contador = 1;

while ($contador <= 5) {
    echo $contador . "<br>";

    $contador++;
}
```

---

# 22. do while

```php
$numero = 1;

do {
    echo $numero . "<br>";
    $numero++;
} while ($numero <= 5);
```

---

# 23. for

```php
for ($i = 1; $i <= 10; $i++) {
    echo $i . "<br>";
}
```

---

# 24. foreach

```php
$nomes = [
    "Ana",
    "Carlos",
    "Maria"
];

foreach ($nomes as $nome) {
    echo $nome . "<br>";
}
```

Com chave e valor:

```php
foreach ($cliente as $chave => $valor) {
    echo "$chave: $valor<br>";
}
```

---

# 25. break e continue

```php
for ($i = 1; $i <= 10; $i++) {
    if ($i === 5) {
        break;
    }

    echo $i;
}
```

```php
for ($i = 1; $i <= 5; $i++) {
    if ($i === 3) {
        continue;
    }

    echo $i;
}
```

---

# 26. Funções

```php
function saudacao(): void
{
    echo "Olá!";
}
```

Uso:

```php
saudacao();
```

---

# 27. Parâmetros e retorno

```php
function somar(
    int $a,
    int $b
): int {
    return $a + $b;
}
```

Uso:

```php
$resultado =
    somar(10, 20);
```

---

# 28. Parâmetros opcionais

```php
function saudacao(
    string $nome,
    string $texto = "Olá"
): string {
    return "$texto, $nome!";
}
```

---

# 29. Funções anônimas

```php
$somar = function (
    $a,
    $b
) {
    return $a + $b;
};
```

---

# 30. Arrow functions

```php
$dobrar =
    fn($numero) =>
        $numero * 2;
```

---

# 31. Tipagem

```php
function calcularTotal(
    float $preco,
    int $quantidade
): float {
    return $preco
        * $quantidade;
}
```

Modo estrito:

```php
<?php

declare(strict_types=1);
```

---

# 32. include e require

```php
include "header.php";
```

```php
require "config.php";
```

Versões que impedem inclusão repetida:

```php
include_once "arquivo.php";
require_once "config.php";
```

---

# 33. Superglobais

Principais:

```text
$_GET
$_POST
$_FILES
$_SESSION
$_COOKIE
$_SERVER
$_ENV
```

---

# 34. GET

URL:

```text
produto.php?id=10
```

PHP:

```php
$id =
    $_GET["id"]
    ?? null;
```

---

# 35. POST

HTML:

```html
<form method="post">
    <input
        type="text"
        name="nome"
    >

    <button>
        Enviar
    </button>
</form>
```

PHP:

```php
$nome =
    $_POST["nome"]
    ?? "";
```

---

# 36. Detectando método HTTP

```php
if (
    $_SERVER["REQUEST_METHOD"]
    === "POST"
) {
    echo "Formulário enviado";
}
```

---

# 37. Formulário completo

```php
<?php

$mensagem = "";

if (
    $_SERVER["REQUEST_METHOD"]
    === "POST"
) {
    $nome =
        trim(
            $_POST["nome"]
            ?? ""
        );

    if ($nome === "") {
        $mensagem =
            "Informe o nome.";
    } else {
        $mensagem =
            "Olá, "
            . htmlspecialchars(
                $nome,
                ENT_QUOTES,
                "UTF-8"
            );
    }
}
?>

<form method="post">
    <input
        type="text"
        name="nome"
    >

    <button>
        Enviar
    </button>
</form>

<p>
    <?= $mensagem ?>
</p>
```

---

# 38. Validação de email

```php
$email =
    trim(
        $_POST["email"]
        ?? ""
    );

if (
    !filter_var(
        $email,
        FILTER_VALIDATE_EMAIL
    )
) {
    echo "Email inválido";
}
```

---

# 39. Null coalescing

```php
$nome =
    $_POST["nome"]
    ?? "Visitante";
```

---

# 40. Cookies

Criar:

```php
setcookie(
    "tema",
    "escuro",
    time() + 3600,
    "/"
);
```

Ler:

```php
$tema =
    $_COOKIE["tema"]
    ?? "claro";
```

---

# 41. Sessões

Iniciar:

```php
session_start();
```

Salvar:

```php
$_SESSION["usuario_id"] = 10;
```

Ler:

```php
echo $_SESSION["usuario_id"];
```

Remover:

```php
unset(
    $_SESSION["usuario_id"]
);
```

Encerrar:

```php
session_destroy();
```

---

# 42. Sessão segura após login

```php
session_regenerate_id(true);
```

Use após autenticação bem-sucedida.

---

# 43. Upload de arquivos

HTML:

```html
<form
    method="post"
    enctype="multipart/form-data"
>
    <input
        type="file"
        name="arquivo"
    >

    <button>
        Enviar
    </button>
</form>
```

PHP:

```php
$arquivo =
    $_FILES["arquivo"]
    ?? null;
```

Mover:

```php
move_uploaded_file(
    $arquivo["tmp_name"],
    "uploads/"
        . basename(
            $arquivo["name"]
        )
);
```

Em projeto real, valide:

- tamanho;
- MIME;
- extensão;
- nome;
- destino.

---

# 44. Arquivos

Escrever:

```php
file_put_contents(
    "dados.txt",
    "Olá mundo"
);
```

Ler:

```php
$conteudo =
    file_get_contents(
        "dados.txt"
    );
```

Adicionar:

```php
file_put_contents(
    "dados.txt",
    PHP_EOL . "Nova linha",
    FILE_APPEND
);
```

---

# 45. Diretórios

Criar:

```php
mkdir("dados");
```

Verificar:

```php
if (is_dir("dados")) {
    echo "Existe";
}
```

Listar:

```php
$arquivos =
    scandir("dados");
```

---

# 46. JSON

```php
$cliente = [
    "nome" => "Ana",
    "email" => "ana@email.com"
];
```

Para JSON:

```php
$json =
    json_encode(
        $cliente,
        JSON_PRETTY_PRINT
        | JSON_UNESCAPED_UNICODE
    );
```

Para array:

```php
$dados =
    json_decode(
        $json,
        true
    );
```

---

# 47. JSON em arquivo

Salvar:

```php
file_put_contents(
    "dados.json",
    json_encode(
        $dados,
        JSON_PRETTY_PRINT
        | JSON_UNESCAPED_UNICODE
    )
);
```

Ler:

```php
$dados =
    json_decode(
        file_get_contents(
            "dados.json"
        ),
        true
    );
```

---

# 48. Datas

```php
echo date("d/m/Y");
```

Data e hora:

```php
echo date(
    "d/m/Y H:i:s"
);
```

---

# 49. DateTime

```php
$data =
    new DateTime();

echo $data->format(
    "d/m/Y"
);
```

Adicionar:

```php
$data->modify(
    "+7 days"
);
```

---

# 50. Tratamento de erros

Em desenvolvimento:

```php
ini_set(
    "display_errors",
    "1"
);

error_reporting(
    E_ALL
);
```

Em produção, não exiba detalhes técnicos ao usuário.

---

# 51. Exceptions

```php
try {
    throw new Exception(
        "Algo deu errado"
    );
} catch (Exception $e) {
    echo $e->getMessage();
}
```

---

# 52. Throwable

```php
try {
    // código
} catch (Throwable $e) {
    echo "Erro";
}
```

---

# 53. Orientação a objetos

Conceitos principais:

- classe;
- objeto;
- propriedade;
- método;
- encapsulamento;
- herança;
- polimorfismo;
- interface;
- abstração.

---

# 54. Classes e objetos

```php
class Pessoa
{
    public string $nome = "";
    public int $idade = 0;
}
```

Objeto:

```php
$pessoa =
    new Pessoa();

$pessoa->nome = "Ana";
$pessoa->idade = 25;
```

---

# 55. Construtor

```php
class Pessoa
{
    public function __construct(
        public string $nome,
        public int $idade
    ) {
    }
}
```

Uso:

```php
$pessoa =
    new Pessoa(
        "Ana",
        25
    );
```

---

# 56. Encapsulamento

```php
class Conta
{
    private float $saldo = 0;

    public function depositar(
        float $valor
    ): void {
        if ($valor <= 0) {
            throw new InvalidArgumentException(
                "Valor inválido"
            );
        }

        $this->saldo += $valor;
    }

    public function getSaldo(): float
    {
        return $this->saldo;
    }
}
```

---

# 57. Herança

```php
class Animal
{
    public function emitirSom(): void
    {
        echo "Som";
    }
}
```

```php
class Cachorro extends Animal
{
    public function emitirSom(): void
    {
        echo "Au au!";
    }
}
```

---

# 58. Interfaces

```php
interface Pagamento
{
    public function pagar(
        float $valor
    ): void;
}
```

```php
class PagamentoPix
    implements Pagamento
{
    public function pagar(
        float $valor
    ): void {
        echo "PIX: R$ $valor";
    }
}
```

---

# 59. Classes abstratas

```php
abstract class Funcionario
{
    abstract public function
        calcularSalario(): float;
}
```

---

# 60. Traits

```php
trait Logavel
{
    public function log(
        string $mensagem
    ): void {
        echo $mensagem;
    }
}
```

Uso:

```php
class Usuario
{
    use Logavel;
}
```

---

# 61. Namespaces

```php
namespace App\Models;

class Produto
{
}
```

Importar:

```php
use App\Models\Produto;
```

---

# 62. Enums

```php
enum StatusPedido: string
{
    case Pendente =
        "pendente";

    case Pago =
        "pago";

    case Cancelado =
        "cancelado";
}
```

---

# 63. Banco de dados

PHP pode trabalhar com:

- MySQL;
- MariaDB;
- PostgreSQL;
- SQLite;
- SQL Server.

Neste curso, usaremos PDO.

---

# 64. PDO

PDO:

```text
PHP Data Objects
```

É uma interface de acesso a banco de dados.

---

# 65. Conexão MySQL

```php
$host = "localhost";
$db = "loja";
$user = "root";
$pass = "";

$pdo = new PDO(
    "mysql:host=$host;dbname=$db;charset=utf8mb4",
    $user,
    $pass,
    [
        PDO::ATTR_ERRMODE
            => PDO::ERRMODE_EXCEPTION,

        PDO::ATTR_DEFAULT_FETCH_MODE
            => PDO::FETCH_ASSOC
    ]
);
```

---

# 66. SELECT

```php
$stmt =
    $pdo->query(
        "SELECT *
         FROM clientes"
    );

$clientes =
    $stmt->fetchAll();
```

---

# 67. SELECT com parâmetro

```php
$stmt =
    $pdo->prepare(
        "SELECT *
         FROM clientes
         WHERE id = :id"
    );

$stmt->execute([
    ":id" => $id
]);

$cliente =
    $stmt->fetch();
```

---

# 68. INSERT

```php
$stmt =
    $pdo->prepare(
        "INSERT INTO clientes
        (nome, email)
        VALUES
        (:nome, :email)"
    );

$stmt->execute([
    ":nome" => $nome,
    ":email" => $email
]);
```

---

# 69. UPDATE

```php
$stmt =
    $pdo->prepare(
        "UPDATE clientes
         SET nome = :nome
         WHERE id = :id"
    );

$stmt->execute([
    ":nome" => $nome,
    ":id" => $id
]);
```

---

# 70. DELETE

```php
$stmt =
    $pdo->prepare(
        "DELETE FROM clientes
         WHERE id = :id"
    );

$stmt->execute([
    ":id" => $id
]);
```

---

# 71. Prepared Statements

Nunca faça:

```php
$sql =
    "SELECT *
     FROM usuarios
     WHERE email = '$email'";
```

Prefira:

```php
$stmt =
    $pdo->prepare(
        "SELECT *
         FROM usuarios
         WHERE email = :email"
    );

$stmt->execute([
    ":email" => $email
]);
```

---

# 72. Transações

```php
try {
    $pdo->beginTransaction();

    // operações

    $pdo->commit();
} catch (Throwable $e) {
    $pdo->rollBack();

    throw $e;
}
```

---

# 73. CRUD

CRUD significa:

```text
Create
Read
Update
Delete
```

Estrutura simples:

```text
clientes/
├── index.php
├── criar.php
├── editar.php
├── excluir.php
└── salvar.php
```

---

# 74. Login

Fluxo:

```text
1. usuário envia email e senha
2. PHP busca o usuário
3. password_verify valida
4. sessão é criada
5. páginas protegidas verificam sessão
```

---

# 75. password_hash

```php
$hash =
    password_hash(
        $senha,
        PASSWORD_DEFAULT
    );
```

Salve o hash no banco.

Nunca a senha pura.

---

# 76. password_verify

```php
if (
    password_verify(
        $senhaDigitada,
        $hashDoBanco
    )
) {
    echo "Senha correta";
}
```

---

# 77. Exemplo de login

```php
session_start();

$stmt =
    $pdo->prepare(
        "SELECT *
         FROM usuarios
         WHERE email = :email"
    );

$stmt->execute([
    ":email" => $email
]);

$usuario =
    $stmt->fetch();

if (
    $usuario
    && password_verify(
        $senha,
        $usuario["senha"]
    )
) {
    session_regenerate_id(true);

    $_SESSION["usuario_id"] =
        $usuario["id"];
}
```

---

# 78. Segurança

Pontos essenciais:

- prepared statements;
- validação;
- escape de HTML;
- hash de senha;
- sessões seguras;
- HTTPS;
- CSRF;
- validação de upload;
- não expor erros;
- segredos fora do código.

---

# 79. SQL Injection

Perigoso:

```php
$sql =
    "SELECT *
     FROM usuarios
     WHERE email = '$email'";
```

Seguro:

```php
$stmt =
    $pdo->prepare(
        "SELECT *
         FROM usuarios
         WHERE email = :email"
    );
```

---

# 80. XSS

Perigoso:

```php
echo $_GET["nome"];
```

Melhor:

```php
echo htmlspecialchars(
    $_GET["nome"]
        ?? "",
    ENT_QUOTES,
    "UTF-8"
);
```

---

# 81. CSRF

Criar token:

```php
session_start();

if (
    empty(
        $_SESSION["csrf_token"]
    )
) {
    $_SESSION["csrf_token"] =
        bin2hex(
            random_bytes(32)
        );
}
```

Formulário:

```php
<input
    type="hidden"
    name="csrf_token"
    value="<?= htmlspecialchars(
        $_SESSION['csrf_token'],
        ENT_QUOTES,
        'UTF-8'
    ) ?>"
>
```

Validar:

```php
if (
    !hash_equals(
        $_SESSION["csrf_token"],
        $_POST["csrf_token"]
            ?? ""
    )
) {
    die("Token inválido");
}
```

---

# 82. Upload seguro

Não confie no nome original.

```php
$nomeSeguro =
    bin2hex(
        random_bytes(16)
    )
    . ".jpg";
```

Validar MIME:

```php
$finfo =
    new finfo(
        FILEINFO_MIME_TYPE
    );

$mime =
    $finfo->file(
        $_FILES["arquivo"]["tmp_name"]
    );
```

---

# 83. APIs

Uma API permite comunicação entre sistemas.

Resposta:

```json
{
  "id": 1,
  "nome": "Ana"
}
```

---

# 84. Criando API JSON

```php
header(
    "Content-Type: application/json; charset=utf-8"
);

$dados = [
    "id" => 1,
    "nome" => "Ana"
];

echo json_encode(
    $dados,
    JSON_UNESCAPED_UNICODE
);
```

---

# 85. Status HTTP

```php
http_response_code(200);
```

Criado:

```php
http_response_code(201);
```

Não encontrado:

```php
http_response_code(404);
```

Erro de validação:

```php
http_response_code(422);
```

---

# 86. Métodos REST

```text
GET
POST
PUT
PATCH
DELETE
```

Exemplo:

```text
GET    /api/produtos
GET    /api/produtos/1
POST   /api/produtos
PUT    /api/produtos/1
DELETE /api/produtos/1
```

---

# 87. Consumindo API

```php
$json =
    file_get_contents(
        "https://api.exemplo.com/dados"
    );

$dados =
    json_decode(
        $json,
        true
    );
```

---

# 88. cURL

```php
$ch =
    curl_init(
        "https://api.exemplo.com/dados"
    );

curl_setopt(
    $ch,
    CURLOPT_RETURNTRANSFER,
    true
);

$resposta =
    curl_exec($ch);

curl_close($ch);
```

---

# 89. Composer

Composer é o gerenciador de dependências do PHP.

Verificar:

```bash
composer --version
```

Criar configuração:

```bash
composer init
```

Instalar pacote:

```bash
composer require vendor/pacote
```

---

# 90. Autoload

No PHP:

```php
require __DIR__
    . "/vendor/autoload.php";
```

`composer.json`:

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

Depois:

```bash
composer dump-autoload
```

---

# 91. Estrutura de projeto

```text
projeto/
├── public/
│   └── index.php
├── src/
│   ├── Controllers/
│   ├── Models/
│   ├── Services/
│   └── Repositories/
├── config/
├── routes/
├── views/
├── storage/
├── vendor/
├── composer.json
└── .env
```

---

# 92. MVC

MVC significa:

```text
Model
View
Controller
```

## Model

Dados e regras.

## View

Interface apresentada.

## Controller

Recebe requisição, chama serviços e escolhe resposta.

---

# 93. Roteamento simples

```php
$uri =
    parse_url(
        $_SERVER["REQUEST_URI"],
        PHP_URL_PATH
    );

if ($uri === "/clientes") {
    require "clientes.php";
} elseif ($uri === "/produtos") {
    require "produtos.php";
} else {
    http_response_code(404);

    echo "Não encontrado";
}
```

---

# 94. .env

Nunca salve segredos diretamente no código.

Exemplo:

```text
DB_HOST=localhost
DB_NAME=loja
DB_USER=root
DB_PASS=
```

`.gitignore`:

```text
.env
/vendor/
```

---

# 95. Repository

```php
interface ClienteRepository
{
    public function todos(): array;

    public function buscar(
        int $id
    ): ?array;

    public function salvar(
        array $dados
    ): void;
}
```

---

# 96. Service Layer

```php
class ClienteService
{
    public function __construct(
        private ClienteRepository
            $repository
    ) {
    }

    public function cadastrar(
        array $dados
    ): void {
        if (
            empty(
                $dados["nome"]
            )
        ) {
            throw new InvalidArgumentException(
                "Nome obrigatório"
            );
        }

        $this->repository
            ->salvar($dados);
    }
}
```

---

# 97. Funções de array

## array_map

```php
$dobrados =
    array_map(
        fn($n) => $n * 2,
        [1, 2, 3]
    );
```

## array_filter

```php
$pares =
    array_filter(
        [1, 2, 3, 4],
        fn($n) =>
            $n % 2 === 0
    );
```

## array_reduce

```php
$total =
    array_reduce(
        [1, 2, 3],
        fn($soma, $n) =>
            $soma + $n,
        0
    );
```

---

# 98. Spread operator

```php
$a = [1, 2];
$b = [3, 4];

$todos = [
    ...$a,
    ...$b
];
```

---

# 99. Nullsafe

```php
$nome =
    $usuario?->perfil?->nome;
```

---

# 100. Readonly

```php
class Produto
{
    public function __construct(
        public readonly int $id,
        public string $nome
    ) {
    }
}
```

---

# 101. Generators

```php
function numeros(): Generator
{
    for ($i = 1; $i <= 5; $i++) {
        yield $i;
    }
}
```

Uso:

```php
foreach (
    numeros()
    as $numero
) {
    echo $numero;
}
```

---

# 102. Boas práticas

## Prepared statements

Sempre use com dados externos.

## Escape HTML

```php
htmlspecialchars(
    $texto,
    ENT_QUOTES,
    "UTF-8"
);
```

## Senhas

Use:

```php
password_hash()
password_verify()
```

## Separe responsabilidades

Não coloque:

- SQL;
- HTML;
- autenticação;
- regra de negócio;

tudo em um arquivo gigante.

## Nomes claros

Bom:

```php
buscarClientePorId()
```

Ruim:

```php
busca()
```

---

# 103. Erros comuns

## Esquecer `$`

Errado:

```php
nome = "Ana";
```

Certo:

```php
$nome = "Ana";
```

## Confundir `=` e `==`

```php
$idade = 20;
```

versus:

```php
$idade == 20;
```

## Salvar senha pura

Nunca faça isso.

## Imprimir entrada do usuário diretamente

Evite:

```php
echo $_GET["nome"];
```

## Montar SQL concatenando usuário

Evite sempre que houver parâmetro externo.

---

# 104. Projeto prático — Cadastro com JSON

Estrutura:

```text
cadastro/
├── index.php
├── salvar.php
└── dados.json
```

Implemente:

- cadastro;
- validação;
- salvar em JSON;
- listar;
- editar;
- excluir.

---

# 105. Projeto prático — Login

Tabela:

```sql
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(150) UNIQUE NOT NULL,
    senha VARCHAR(255) NOT NULL
);
```

Requisitos:

- cadastro;
- hash de senha;
- login;
- sessão;
- logout;
- página protegida.

---

# 106. Projeto prático — CRUD MySQL

Tabela:

```sql
CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(120) NOT NULL,
    preco DECIMAL(10,2) NOT NULL,
    estoque INT NOT NULL DEFAULT 0
);
```

Implemente:

- cadastrar;
- listar;
- buscar;
- editar;
- excluir;
- filtrar;
- ordenar.

---

# 107. Projeto prático — API REST

Endpoints:

```text
GET    /api/produtos
GET    /api/produtos/1
POST   /api/produtos
PUT    /api/produtos/1
DELETE /api/produtos/1
```

Resposta padrão:

```json
{
  "success": true,
  "data": {}
}
```

---

# 108. Exercícios básicos

1. Mostre `Olá, mundo`.
2. Crie variáveis.
3. Some dois números.
4. Descubra se é maior de idade.
5. Faça tabuada.
6. Crie array com nomes.
7. Conte elementos.
8. Mostre pares.
9. Calcule média.
10. Inverta uma string.
11. Conte caracteres.
12. Faça calculadora.

---

# 109. Exercícios intermediários

1. Formulário de contato.
2. Validação de email.
3. Salvar em JSON.
4. Ler JSON.
5. Cookie de tema.
6. Login simulado com sessão.
7. Upload.
8. Classe Produto.
9. Interface Pagamento.
10. Trait de log.
11. Enum de status.
12. Namespace.

---

# 110. Exercícios avançados

1. Conecte com MySQL.
2. Faça CRUD.
3. Faça login real.
4. Use hash de senha.
5. Implemente CSRF.
6. Proteja XSS.
7. Use prepared statements.
8. Crie API REST.
9. Consuma API.
10. Use Composer.
11. Use PSR-4.
12. Estruture MVC.

---

# 111. Projeto final

Crie um sistema completo de vendas.

Entidades:

```text
Usuario
Cliente
Produto
Categoria
Pedido
ItemPedido
Pagamento
Endereco
```

Funcionalidades:

- login;
- logout;
- usuários;
- clientes;
- produtos;
- categorias;
- estoque;
- pedidos;
- pagamentos;
- relatórios;
- API;
- painel administrativo.

Requisitos:

- PHP moderno;
- strict_types;
- OOP;
- PDO;
- MySQL;
- prepared statements;
- sessões;
- password_hash;
- CSRF;
- XSS protection;
- validação;
- Composer;
- PSR-4;
- namespaces;
- MVC;
- JSON;
- API REST;
- tratamento de erros.

Estrutura:

```text
SistemaVendas/
├── public/
│   └── index.php
├── src/
│   ├── Controllers/
│   ├── Models/
│   ├── Services/
│   ├── Repositories/
│   └── Middlewares/
├── routes/
├── views/
├── config/
├── storage/
├── vendor/
├── composer.json
└── .env
```

---

# 112. Cheat Sheet

Echo:

```php
echo "Olá";
```

Variável:

```php
$nome = "Ana";
```

IF:

```php
if ($idade >= 18) {
}
```

FOREACH:

```php
foreach ($itens as $item) {
}
```

Função:

```php
function somar(
    int $a,
    int $b
): int {
    return $a + $b;
}
```

GET:

```php
$id =
    $_GET["id"]
    ?? null;
```

POST:

```php
$nome =
    $_POST["nome"]
    ?? "";
```

Sessão:

```php
session_start();

$_SESSION["usuario_id"] = 1;
```

JSON:

```php
$json =
    json_encode($dados);
```

PDO:

```php
$pdo =
    new PDO(
        $dsn,
        $usuario,
        $senha
    );
```

Prepared:

```php
$stmt =
    $pdo->prepare(
        "SELECT *
         FROM clientes
         WHERE id = :id"
    );

$stmt->execute([
    ":id" => $id
]);
```

Hash:

```php
$hash =
    password_hash(
        $senha,
        PASSWORD_DEFAULT
    );
```

Verify:

```php
password_verify(
    $senha,
    $hash
);
```

Escape:

```php
htmlspecialchars(
    $texto,
    ENT_QUOTES,
    "UTF-8"
);
```

---

# 113. Checklist

## Básico

- [ ] Sei criar um arquivo PHP.
- [ ] Sei usar echo.
- [ ] Sei usar variáveis.
- [ ] Sei usar strings.
- [ ] Sei usar arrays.
- [ ] Sei usar if.
- [ ] Sei usar loops.
- [ ] Sei criar funções.
- [ ] Sei usar include e require.

## Intermediário

- [ ] Sei usar GET.
- [ ] Sei usar POST.
- [ ] Sei criar formulário.
- [ ] Sei validar entrada.
- [ ] Sei usar sessão.
- [ ] Sei usar cookie.
- [ ] Sei fazer upload.
- [ ] Sei trabalhar com JSON.
- [ ] Sei usar OOP.

## Avançado

- [ ] Sei usar PDO.
- [ ] Sei fazer CRUD.
- [ ] Sei usar prepared statements.
- [ ] Sei criar login.
- [ ] Sei usar password_hash.
- [ ] Entendo SQL Injection.
- [ ] Entendo XSS.
- [ ] Entendo CSRF.
- [ ] Sei criar API.
- [ ] Sei consumir API.
- [ ] Sei usar Composer.
- [ ] Sei usar namespaces.
- [ ] Entendo MVC.
- [ ] Sei estruturar projeto real.

---

# 114. Como estudar

## Etapa 1

Aprenda:

```text
variáveis
tipos
arrays
if
loops
funções
```

## Etapa 2

Aprenda:

```text
GET
POST
formulários
sessões
cookies
arquivos
JSON
```

## Etapa 3

Aprenda:

```text
OOP
PDO
MySQL
CRUD
login
```

## Etapa 4

Aprenda:

```text
segurança
APIs
Composer
autoload
namespaces
```

## Etapa 5

Aprenda:

```text
MVC
testes
frameworks
arquitetura
```

---

# 115. Próximos passos

Depois deste curso:

- Laravel;
- Symfony;
- PHPUnit;
- Pest;
- Doctrine;
- PSR standards;
- Redis;
- filas;
- JWT;
- OAuth;
- Docker;
- Nginx;
- Apache;
- CI/CD;
- Clean Architecture;
- DDD;
- cache;
- testes de integração;
- deploy.

---

# Regra de ouro

Sempre pergunte:

```text
Esse dado foi validado?
Essa saída foi escapada?
Essa query usa prepared statement?
Essa senha está com hash?
Essa rota deveria exigir login?
Esse formulário tem CSRF?
Esse segredo está fora do código?
Essa responsabilidade está no arquivo certo?
```

---

# Desafio final

Crie um sistema para um destes temas:

- restaurante;
- delivery;
- e-commerce;
- CRM;
- estoque;
- agenda;
- escola;
- oficina;
- biblioteca;
- imobiliária.

Use obrigatoriamente:

- autenticação;
- CRUD;
- MySQL;
- PDO;
- prepared statements;
- sessões;
- upload;
- JSON;
- API REST;
- Composer;
- autoload;
- namespaces;
- MVC;
- CSRF;
- proteção contra XSS;
- password_hash.

Se conseguir desenvolver isso sem depender de um tutorial passo a passo, você já terá uma base muito sólida de PHP backend.

---

# Conclusão

Ao terminar e praticar este material, você deve conseguir:

- criar aplicações PHP;
- processar formulários;
- trabalhar com GET e POST;
- usar sessões e cookies;
- manipular arquivos;
- trabalhar com JSON;
- criar classes;
- usar orientação a objetos;
- acessar MySQL;
- usar PDO;
- criar CRUD;
- autenticar usuários;
- armazenar senhas corretamente;
- evitar SQL Injection;
- reduzir riscos de XSS e CSRF;
- criar APIs;
- consumir APIs;
- usar Composer;
- organizar projetos com namespaces;
- estruturar aplicações em MVC.

> PHP é fácil para começar. O salto profissional acontece quando você aprende segurança, organização, banco de dados e arquitetura.

Crie projetos, teste, leia os erros, use logs e refatore seu próprio código.
