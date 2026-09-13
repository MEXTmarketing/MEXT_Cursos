# Curso Completo de C# — Do Absoluto Zero ao Uso Profissional

> Um curso prático para quem nunca programou em C# e quer sair do zero sabendo criar aplicações, trabalhar com orientação a objetos, coleções, arquivos, JSON, LINQ, APIs, tarefas assíncronas, testes e projetos reais com .NET.

---

## 📚 Sumário

1. O que é C# e .NET
2. Preparando o ambiente
3. Primeiro programa
4. Estrutura de um projeto
5. Variáveis e tipos
6. Entrada e saída
7. Operadores
8. Condicionais
9. Laços de repetição
10. Strings
11. Arrays
12. Listas e coleções
13. Métodos
14. Exceções
15. Orientação a objetos
16. Classes e objetos
17. Propriedades e construtores
18. Encapsulamento
19. Herança e polimorfismo
20. Interfaces e classes abstratas
21. Enums, structs e records
22. Generics
23. Nullable
24. Datas
25. LINQ
26. Delegates e lambdas
27. Eventos
28. Arquivos
29. JSON
30. Async/Await
31. HttpClient
32. NuGet
33. Organização de projetos
34. SOLID
35. Testes
36. Banco de dados
37. Entity Framework Core
38. ASP.NET Core
39. API simples
40. Projetos práticos
41. Exercícios
42. Projeto final
43. Cheat Sheet
44. Checklist
45. Próximos passos

---

# 1. O que é C#?

C# é uma linguagem de programação moderna da plataforma .NET.

Com ela você pode criar:

- aplicações de console;
- APIs;
- sites;
- sistemas empresariais;
- aplicações desktop;
- jogos;
- automações;
- serviços;
- aplicativos móveis;
- sistemas em nuvem.

Seu primeiro código:

```csharp
Console.WriteLine("Olá, mundo!");
```

---

# 2. O que é .NET?

Pense assim:

```text
C# = linguagem
.NET = plataforma
```

O .NET oferece:

- compilador;
- runtime;
- bibliotecas;
- ferramentas;
- gerenciamento de pacotes;
- recursos web;
- acesso a arquivos;
- acesso a banco de dados;
- recursos de rede.

---

# 3. Preparando o ambiente

Você pode usar:

- Visual Studio;
- Visual Studio Code;
- JetBrains Rider.

Instale o .NET SDK.

Verifique:

```bash
dotnet --version
```

Crie um projeto:

```bash
dotnet new console -n MeuProjeto
```

Entre na pasta:

```bash
cd MeuProjeto
```

Execute:

```bash
dotnet run
```

---

# 4. Seu primeiro programa

Arquivo `Program.cs`:

```csharp
Console.WriteLine("Olá, C#!");
```

Saída:

```text
Olá, C#!
```

---

# 5. Estrutura de um projeto

Exemplo:

```text
MeuProjeto/
├── Program.cs
├── MeuProjeto.csproj
├── bin/
└── obj/
```

O `.csproj` contém informações do projeto.

Você não precisa decorar sua estrutura agora.

---

# 6. Saída no console

```csharp
Console.WriteLine("Olá!");
```

Sem pular linha:

```csharp
Console.Write("Nome: ");
```

---

# 7. Comentários

Uma linha:

```csharp
// comentário
```

Várias linhas:

```csharp
/*
comentário
de várias linhas
*/
```

---

# 8. Variáveis

```csharp
string nome = "Ana";
int idade = 25;
double altura = 1.70;
bool ativo = true;
```

Estrutura:

```text
tipo nome = valor;
```

---

# 9. Tipos de dados

## string

```csharp
string nome = "Carlos";
```

## int

```csharp
int idade = 30;
```

## long

```csharp
long numeroGrande = 9000000000;
```

## float

```csharp
float peso = 70.5f;
```

## double

```csharp
double altura = 1.82;
```

## decimal

Ideal para dinheiro:

```csharp
decimal preco = 199.90m;
```

## bool

```csharp
bool ativo = true;
```

## char

```csharp
char letra = 'A';
```

---

# 10. var

```csharp
var nome = "Ana";
var idade = 25;
var ativo = true;
```

O compilador deduz o tipo.

`var` não cria uma variável de tipo dinâmico.

---

# 11. Constantes

```csharp
const double Pi = 3.14159;
```

Depois de definida, ela não pode ser alterada.

---

# 12. Conversões de tipo

Automática:

```csharp
int numero = 10;
double valor = numero;
```

Explícita:

```csharp
double valor = 10.8;
int numero = (int)valor;
```

Com `Convert`:

```csharp
string texto = "25";
int idade = Convert.ToInt32(texto);
```

Com `Parse`:

```csharp
int idade = int.Parse("25");
```

Forma segura:

```csharp
if (int.TryParse("25", out int idade))
{
    Console.WriteLine(idade);
}
```

---

# 13. Entrada de dados

```csharp
Console.Write("Digite seu nome: ");

string? nome = Console.ReadLine();

Console.WriteLine($"Olá, {nome}!");
```

Número:

```csharp
Console.Write("Idade: ");

if (int.TryParse(Console.ReadLine(), out int idade))
{
    Console.WriteLine($"Idade: {idade}");
}
else
{
    Console.WriteLine("Valor inválido.");
}
```

---

# 14. Operadores matemáticos

```csharp
int a = 10;
int b = 3;
```

```csharp
a + b
a - b
a * b
a / b
a % b
```

Incremento:

```csharp
a++;
```

Decremento:

```csharp
a--;
```

---

# 15. Operadores de comparação

```csharp
==
!=
>
<
>=
<=
```

Exemplo:

```csharp
int idade = 20;

bool maior = idade >= 18;
```

---

# 16. Operadores lógicos

AND:

```csharp
&&
```

OR:

```csharp
||
```

NOT:

```csharp
!
```

Exemplo:

```csharp
if (idade >= 18 && possuiDocumento)
{
    Console.WriteLine("Entrada permitida.");
}
```

---

# 17. if, else e else if

```csharp
int idade = 20;

if (idade >= 18)
{
    Console.WriteLine("Maior de idade.");
}
else
{
    Console.WriteLine("Menor de idade.");
}
```

Várias condições:

```csharp
int nota = 8;

if (nota >= 9)
{
    Console.WriteLine("Excelente");
}
else if (nota >= 7)
{
    Console.WriteLine("Aprovado");
}
else
{
    Console.WriteLine("Reprovado");
}
```

---

# 18. switch

```csharp
int opcao = 2;

switch (opcao)
{
    case 1:
        Console.WriteLine("Cadastrar");
        break;

    case 2:
        Console.WriteLine("Listar");
        break;

    case 3:
        Console.WriteLine("Sair");
        break;

    default:
        Console.WriteLine("Opção inválida");
        break;
}
```

Switch expression:

```csharp
string mensagem = opcao switch
{
    1 => "Cadastrar",
    2 => "Listar",
    3 => "Sair",
    _ => "Inválido"
};
```

---

# 19. Operador ternário

```csharp
string resultado =
    idade >= 18
        ? "Maior de idade"
        : "Menor de idade";
```

---

# 20. while

```csharp
int contador = 1;

while (contador <= 5)
{
    Console.WriteLine(contador);
    contador++;
}
```

---

# 21. do while

```csharp
int numero = 1;

do
{
    Console.WriteLine(numero);
    numero++;
}
while (numero <= 5);
```

---

# 22. for

```csharp
for (int i = 1; i <= 10; i++)
{
    Console.WriteLine(i);
}
```

---

# 23. foreach

```csharp
string[] nomes =
{
    "Ana",
    "Carlos",
    "Maria"
};

foreach (string nome in nomes)
{
    Console.WriteLine(nome);
}
```

---

# 24. break e continue

`break` interrompe o loop:

```csharp
for (int i = 1; i <= 10; i++)
{
    if (i == 5)
        break;

    Console.WriteLine(i);
}
```

`continue` pula uma iteração:

```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 3)
        continue;

    Console.WriteLine(i);
}
```

---

# 25. Strings

```csharp
string nome = "Eduardo";
```

Concatenação:

```csharp
string mensagem = "Olá, " + nome;
```

Interpolação:

```csharp
string mensagem = $"Olá, {nome}!";
```

---

# 26. Métodos de string

```csharp
string nome = "  Carlos Silva  ";
```

```csharp
nome.Length
nome.ToUpper()
nome.ToLower()
nome.Trim()
nome.Contains("Carlos")
nome.StartsWith("C")
nome.EndsWith("a")
nome.Replace("Carlos", "João")
```

Separar:

```csharp
string texto = "Ana,Carlos,Maria";

string[] nomes = texto.Split(',');
```

---

# 27. Arrays

Tamanho fixo:

```csharp
int[] numeros = new int[3];

numeros[0] = 10;
numeros[1] = 20;
numeros[2] = 30;
```

Forma curta:

```csharp
int[] numeros = { 10, 20, 30 };
```

Acessar:

```csharp
Console.WriteLine(numeros[0]);
```

---

# 28. List

Lista possui tamanho dinâmico:

```csharp
List<string> nomes = new();

nomes.Add("Ana");
nomes.Add("Carlos");
nomes.Add("Maria");
```

Remover:

```csharp
nomes.Remove("Carlos");
```

Quantidade:

```csharp
Console.WriteLine(nomes.Count);
```

---

# 29. Dictionary

Chave e valor:

```csharp
Dictionary<int, string> clientes = new();

clientes.Add(1, "Ana");
clientes.Add(2, "Carlos");
```

Acessar:

```csharp
Console.WriteLine(clientes[1]);
```

Forma segura:

```csharp
if (clientes.TryGetValue(1, out string? nome))
{
    Console.WriteLine(nome);
}
```

---

# 30. HashSet

Valores únicos:

```csharp
HashSet<string> cidades = new();

cidades.Add("Caxias do Sul");
cidades.Add("Farroupilha");
cidades.Add("Caxias do Sul");
```

O valor duplicado não é inserido novamente.

---

# 31. Queue e Stack

Fila:

```csharp
Queue<string> fila = new();

fila.Enqueue("Ana");
fila.Enqueue("Carlos");

string primeiro = fila.Dequeue();
```

Pilha:

```csharp
Stack<string> pilha = new();

pilha.Push("Ana");
pilha.Push("Carlos");

string ultimo = pilha.Pop();
```

---

# 32. Métodos

```csharp
static void Saudacao()
{
    Console.WriteLine("Olá!");
}

Saudacao();
```

Com parâmetro:

```csharp
static void Saudacao(string nome)
{
    Console.WriteLine($"Olá, {nome}!");
}
```

Com retorno:

```csharp
static int Somar(int a, int b)
{
    return a + b;
}
```

Uso:

```csharp
int resultado = Somar(10, 20);
```

---

# 33. Parâmetros opcionais

```csharp
static void Saudacao(
    string nome,
    string texto = "Olá")
{
    Console.WriteLine($"{texto}, {nome}!");
}
```

---

# 34. params

```csharp
static int Somar(params int[] numeros)
{
    int total = 0;

    foreach (int numero in numeros)
    {
        total += numero;
    }

    return total;
}
```

```csharp
Console.WriteLine(
    Somar(1, 2, 3, 4, 5)
);
```

---

# 35. ref e out

`ref`:

```csharp
static void Dobrar(ref int numero)
{
    numero *= 2;
}

int valor = 5;

Dobrar(ref valor);
```

`out`:

```csharp
bool sucesso =
    int.TryParse("25", out int idade);
```

---

# 36. Escopo

```csharp
if (true)
{
    int numero = 10;
    Console.WriteLine(numero);
}
```

`numero` não existe fora desse bloco.

---

# 37. Tratamento de erros

Código que pode falhar:

```csharp
int numero = int.Parse("abc");
```

Use `try/catch`:

```csharp
try
{
    int numero = int.Parse("abc");
}
catch (FormatException)
{
    Console.WriteLine("Formato inválido.");
}
```

Com mensagem:

```csharp
try
{
    // código
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
finally
{
    Console.WriteLine("Finalizado");
}
```

---

# 38. throw

Você pode lançar uma exceção:

```csharp
static void Sacar(decimal saldo, decimal valor)
{
    if (valor > saldo)
    {
        throw new InvalidOperationException(
            "Saldo insuficiente."
        );
    }
}
```

---

# 39. Orientação a objetos

Objetos representam coisas do sistema:

```text
Cliente
Produto
Pedido
Pagamento
Funcionario
Veiculo
Conta
```

Um objeto possui:

- dados;
- comportamento.

---

# 40. Classes e objetos

```csharp
class Pessoa
{
    public string Nome { get; set; } = "";
    public int Idade { get; set; }
}
```

Objeto:

```csharp
Pessoa pessoa = new()
{
    Nome = "Ana",
    Idade = 25
};
```

---

# 41. Propriedades

```csharp
class Conta
{
    public string Titular { get; set; } = "";

    public decimal Saldo { get; private set; }
}
```

---

# 42. Construtores

```csharp
class Pessoa
{
    public string Nome { get; set; }

    public Pessoa(string nome)
    {
        Nome = nome;
    }
}
```

Uso:

```csharp
Pessoa pessoa = new("Ana");
```

---

# 43. Encapsulamento

Evite:

```csharp
public decimal Saldo;
```

Prefira:

```csharp
public decimal Saldo { get; private set; }

public void Depositar(decimal valor)
{
    if (valor <= 0)
    {
        throw new ArgumentException(
            "Valor inválido."
        );
    }

    Saldo += valor;
}
```

---

# 44. Modificadores de acesso

## public

Acessível externamente.

## private

Somente dentro da classe.

## protected

Classe e classes filhas.

## internal

Mesmo assembly/projeto.

---

# 45. static

Pertence à classe:

```csharp
class Calculadora
{
    public static int Somar(int a, int b)
    {
        return a + b;
    }
}
```

Uso:

```csharp
int resultado =
    Calculadora.Somar(10, 20);
```

---

# 46. this

Representa a instância atual:

```csharp
class Pessoa
{
    public string Nome { get; set; }

    public Pessoa(string nome)
    {
        this.Nome = nome;
    }
}
```

---

# 47. Herança

```csharp
class Animal
{
    public string Nome { get; set; } = "";
}
```

```csharp
class Cachorro : Animal
{
    public void Latir()
    {
        Console.WriteLine("Au au!");
    }
}
```

---

# 48. Polimorfismo

```csharp
class Animal
{
    public virtual void EmitirSom()
    {
        Console.WriteLine("Som");
    }
}

class Cachorro : Animal
{
    public override void EmitirSom()
    {
        Console.WriteLine("Au au!");
    }
}
```

---

# 49. Classes abstratas

```csharp
abstract class Funcionario
{
    public string Nome { get; set; } = "";

    public abstract decimal CalcularSalario();
}
```

```csharp
class FuncionarioCLT : Funcionario
{
    public decimal Salario { get; set; }

    public override decimal CalcularSalario()
    {
        return Salario;
    }
}
```

---

# 50. Interfaces

Contrato:

```csharp
interface IPagamento
{
    void Pagar(decimal valor);
}
```

Implementação:

```csharp
class PagamentoPix : IPagamento
{
    public void Pagar(decimal valor)
    {
        Console.WriteLine(
            $"Pagamento PIX: {valor:C}"
        );
    }
}
```

---

# 51. Composição

```csharp
class Motor
{
    public void Ligar()
    {
        Console.WriteLine("Motor ligado");
    }
}
```

```csharp
class Carro
{
    private readonly Motor motor = new();

    public void Ligar()
    {
        motor.Ligar();
    }
}
```

---

# 52. Enums

```csharp
enum StatusPedido
{
    Pendente,
    Pago,
    Enviado,
    Cancelado
}
```

Uso:

```csharp
StatusPedido status =
    StatusPedido.Pago;
```

---

# 53. Structs

```csharp
struct Ponto
{
    public int X { get; set; }
    public int Y { get; set; }
}
```

Structs são tipos por valor.

---

# 54. Records

```csharp
public record Cliente(
    int Id,
    string Nome,
    string Email
);
```

Uso:

```csharp
Cliente cliente = new(
    1,
    "Ana",
    "ana@email.com"
);
```

Records são muito úteis para representar dados.

---

# 55. Generics

```csharp
class Caixa<T>
{
    public T? Valor { get; set; }
}
```

```csharp
Caixa<int> caixaNumero = new();
caixaNumero.Valor = 10;

Caixa<string> caixaTexto = new();
caixaTexto.Valor = "Olá";
```

---

# 56. Nullable

```csharp
string? nome = null;
int? idade = null;
```

Valor padrão:

```csharp
int valor = idade ?? 0;
```

Verificação:

```csharp
if (nome is not null)
{
    Console.WriteLine(nome);
}
```

---

# 57. Datas

```csharp
DateTime agora = DateTime.Now;
DateTime hoje = DateTime.Today;
```

Criando:

```csharp
DateTime data =
    new DateTime(2026, 9, 13);
```

Adicionar:

```csharp
DateTime amanha =
    DateTime.Now.AddDays(1);
```

Diferença:

```csharp
DateTime inicio =
    new(2026, 1, 1);

DateTime fim =
    new(2026, 1, 10);

TimeSpan diferenca =
    fim - inicio;

Console.WriteLine(
    diferenca.TotalDays
);
```

---

# 58. LINQ

LINQ permite consultar coleções.

```csharp
List<int> numeros =
    new() { 1, 2, 3, 4, 5, 6 };
```

Pares:

```csharp
var pares =
    numeros
        .Where(n => n % 2 == 0)
        .ToList();
```

---

# 59. Where

```csharp
var caros =
    produtos
        .Where(p => p.Preco > 100)
        .ToList();
```

---

# 60. Select

```csharp
var nomes =
    produtos
        .Select(p => p.Nome)
        .ToList();
```

Objeto anônimo:

```csharp
var resumo =
    produtos
        .Select(p => new
        {
            p.Nome,
            p.Preco
        })
        .ToList();
```

---

# 61. OrderBy

```csharp
var crescente =
    produtos
        .OrderBy(p => p.Preco)
        .ToList();
```

```csharp
var decrescente =
    produtos
        .OrderByDescending(p => p.Preco)
        .ToList();
```

---

# 62. First e FirstOrDefault

```csharp
var primeiro = produtos.First();
```

```csharp
var produto =
    produtos
        .FirstOrDefault(
            p => p.Id == 10
        );
```

---

# 63. Any e All

```csharp
bool existeSemEstoque =
    produtos.Any(
        p => p.Estoque == 0
    );
```

```csharp
bool todosAtivos =
    produtos.All(
        p => p.Ativo
    );
```

---

# 64. Count, Sum, Average, Min e Max

```csharp
int quantidade =
    produtos.Count;
```

```csharp
decimal total =
    produtos.Sum(p => p.Preco);
```

```csharp
decimal media =
    produtos.Average(p => p.Preco);
```

```csharp
decimal menor =
    produtos.Min(p => p.Preco);
```

```csharp
decimal maior =
    produtos.Max(p => p.Preco);
```

---

# 65. GroupBy

```csharp
var grupos =
    produtos
        .GroupBy(p => p.Categoria);

foreach (var grupo in grupos)
{
    Console.WriteLine(grupo.Key);

    foreach (var produto in grupo)
    {
        Console.WriteLine(produto.Nome);
    }
}
```

---

# 66. Distinct

```csharp
var cidadesUnicas =
    clientes
        .Select(c => c.Cidade)
        .Distinct()
        .ToList();
```

---

# 67. Join com LINQ

```csharp
var resultado =
    clientes.Join(
        pedidos,
        cliente => cliente.Id,
        pedido => pedido.ClienteId,
        (cliente, pedido) => new
        {
            Cliente = cliente.Nome,
            Pedido = pedido.Id
        }
    );
```

---

# 68. Delegates

```csharp
delegate int Operacao(int a, int b);

static int Somar(int a, int b)
{
    return a + b;
}

Operacao operacao = Somar;

Console.WriteLine(
    operacao(10, 20)
);
```

---

# 69. Action e Func

`Action`:

```csharp
Action<string> mostrar =
    texto => Console.WriteLine(texto);
```

`Func`:

```csharp
Func<int, int, int> somar =
    (a, b) => a + b;
```

---

# 70. Lambdas

```csharp
x => x * 2
```

Exemplo:

```csharp
var dobrados =
    numeros
        .Select(x => x * 2)
        .ToList();
```

---

# 71. Eventos

```csharp
class Pedido
{
    public event Action? PedidoPago;

    public void Pagar()
    {
        Console.WriteLine("Pedido pago.");

        PedidoPago?.Invoke();
    }
}
```

```csharp
Pedido pedido = new();

pedido.PedidoPago += () =>
{
    Console.WriteLine(
        "Enviar confirmação."
    );
};

pedido.Pagar();
```

---

# 72. Arquivos

Escrever:

```csharp
File.WriteAllText(
    "dados.txt",
    "Olá mundo"
);
```

Ler:

```csharp
string conteudo =
    File.ReadAllText("dados.txt");
```

Adicionar:

```csharp
File.AppendAllText(
    "dados.txt",
    "\nNova linha"
);
```

Verificar:

```csharp
if (File.Exists("dados.txt"))
{
    Console.WriteLine("Existe");
}
```

---

# 73. Diretórios

```csharp
Directory.CreateDirectory("dados");
```

```csharp
bool existe =
    Directory.Exists("dados");
```

```csharp
string[] arquivos =
    Directory.GetFiles("dados");
```

---

# 74. JSON

```json
{
  "nome": "Ana",
  "idade": 25
}
```

Use:

```csharp
using System.Text.Json;
```

Classe:

```csharp
class Cliente
{
    public string Nome { get; set; } = "";
    public string Email { get; set; } = "";
}
```

Serializar:

```csharp
Cliente cliente = new()
{
    Nome = "Ana",
    Email = "ana@email.com"
};

string json =
    JsonSerializer.Serialize(
        cliente,
        new JsonSerializerOptions
        {
            WriteIndented = true
        }
    );
```

Desserializar:

```csharp
Cliente? cliente =
    JsonSerializer
        .Deserialize<Cliente>(json);
```

Salvar:

```csharp
File.WriteAllText(
    "cliente.json",
    json
);
```

---

# 75. Async e Await

```csharp
static async Task ExecutarAsync()
{
    await Task.Delay(1000);

    Console.WriteLine("Finalizado");
}
```

```csharp
await ExecutarAsync();
```

Com retorno:

```csharp
static async Task<int> ObterNumeroAsync()
{
    await Task.Delay(500);

    return 10;
}
```

---

# 76. HttpClient

```csharp
using HttpClient client = new();

string resposta =
    await client.GetStringAsync(
        "https://exemplo.com"
    );
```

---

# 77. Consumindo APIs

Resposta:

```json
{
  "id": 1,
  "nome": "Ana"
}
```

Classe:

```csharp
class Cliente
{
    public int Id { get; set; }
    public string Nome { get; set; } = "";
}
```

Código:

```csharp
using System.Text.Json;

using HttpClient client = new();

string json =
    await client.GetStringAsync(
        "https://api.exemplo.com/clientes/1"
    );

Cliente? cliente =
    JsonSerializer
        .Deserialize<Cliente>(json);
```

---

# 78. NuGet

Instalar pacote:

```bash
dotnet add package NomeDoPacote
```

Listar:

```bash
dotnet list package
```

Remover:

```bash
dotnet remove package NomeDoPacote
```

---

# 79. Organização de projetos

```text
MeuProjeto/
├── Models/
│   ├── Cliente.cs
│   └── Produto.cs
├── Services/
│   ├── ClienteService.cs
│   └── ProdutoService.cs
├── Repositories/
│   └── ClienteRepository.cs
├── Interfaces/
├── Utils/
└── Program.cs
```

---

# 80. Namespaces

```csharp
namespace Loja.Models;

public class Produto
{
}
```

Uso:

```csharp
using Loja.Models;
```

---

# 81. Bibliotecas

Criar:

```bash
dotnet new classlib -n MinhaBiblioteca
```

Referenciar:

```bash
dotnet add reference ../MinhaBiblioteca/MinhaBiblioteca.csproj
```

---

# 82. Boas práticas

Use nomes claros:

```csharp
CalcularTotalPedido()
```

em vez de:

```csharp
Calc()
```

Padrões comuns:

```text
Classe         PascalCase
Método         PascalCase
Propriedade    PascalCase
variável       camelCase
parâmetro      camelCase
```

Evite:

- métodos gigantes;
- classes gigantes;
- código duplicado;
- números mágicos;
- lógica toda no `Program.cs`.

---

# 83. SOLID

## S — Single Responsibility

Uma classe deve ter uma responsabilidade principal.

## O — Open/Closed

Código deve ser extensível sem exigir alteração constante do que já funciona.

## L — Liskov Substitution

Tipos derivados devem poder substituir os tipos base corretamente.

## I — Interface Segregation

Evite interfaces gigantes.

## D — Dependency Inversion

Dependa de abstrações.

---

# 84. Dependency Injection

Sem DI:

```csharp
class PedidoService
{
    private EmailService email =
        new EmailService();
}
```

Com DI:

```csharp
class PedidoService
{
    private readonly IEmailService email;

    public PedidoService(
        IEmailService email)
    {
        this.email = email;
    }
}
```

---

# 85. Testes automatizados

Exemplo:

```csharp
public class Calculadora
{
    public int Somar(int a, int b)
    {
        return a + b;
    }
}
```

Teste com xUnit:

```csharp
[Fact]
public void Somar_DeveRetornarCinco()
{
    Calculadora calc = new();

    int resultado =
        calc.Somar(2, 3);

    Assert.Equal(5, resultado);
}
```

Ferramentas:

- xUnit;
- NUnit;
- MSTest.

---

# 86. Banco de dados

C# pode trabalhar com:

- SQL Server;
- PostgreSQL;
- MySQL;
- SQLite;
- Oracle.

Você pode usar:

1. SQL diretamente;
2. micro ORM;
3. ORM.

Um ORM muito usado em .NET é o Entity Framework Core.

---

# 87. Entity Framework Core

Modelo:

```csharp
public class Cliente
{
    public int Id { get; set; }

    public string Nome { get; set; } = "";

    public string Email { get; set; } = "";
}
```

Contexto:

```csharp
public class AppDbContext : DbContext
{
    public DbSet<Cliente> Clientes { get; set; }
}
```

Adicionar:

```csharp
Cliente cliente = new()
{
    Nome = "Ana",
    Email = "ana@email.com"
};

context.Clientes.Add(cliente);

await context.SaveChangesAsync();
```

Consultar:

```csharp
List<Cliente> clientes =
    await context.Clientes
        .ToListAsync();
```

Filtrar:

```csharp
Cliente? cliente =
    await context.Clientes
        .FirstOrDefaultAsync(
            c => c.Id == 1
        );
```

---

# 88. ASP.NET Core

Usado para:

- APIs;
- sites;
- serviços;
- aplicações web.

Criar API:

```bash
dotnet new webapi -n MinhaApi
```

Executar:

```bash
dotnet run
```

---

# 89. API simples

Minimal API:

```csharp
var builder =
    WebApplication.CreateBuilder(args);

var app =
    builder.Build();

app.MapGet("/", () =>
{
    return "API funcionando!";
});

app.Run();
```

Endpoint:

```csharp
app.MapGet("/clientes", () =>
{
    return new[]
    {
        new
        {
            Id = 1,
            Nome = "Ana"
        },

        new
        {
            Id = 2,
            Nome = "Carlos"
        }
    };
});
```

POST:

```csharp
app.MapPost(
    "/clientes",
    (Cliente cliente) =>
    {
        return Results.Ok(cliente);
    }
);
```

---

# 90. DTOs

DTO significa `Data Transfer Object`.

Request:

```csharp
public record CriarClienteRequest(
    string Nome,
    string Email
);
```

Response:

```csharp
public record ClienteResponse(
    int Id,
    string Nome,
    string Email
);
```

---

# 91. Repository Pattern

```csharp
public interface IRepository<T>
{
    void Adicionar(T item);

    List<T> Listar();

    T? BuscarPorId(int id);
}
```

Implementação:

```csharp
class ClienteRepository
    : IRepository<Cliente>
{
    private readonly List<Cliente>
        clientes = new();

    public void Adicionar(
        Cliente cliente)
    {
        clientes.Add(cliente);
    }

    public List<Cliente> Listar()
    {
        return clientes;
    }

    public Cliente? BuscarPorId(int id)
    {
        return clientes
            .FirstOrDefault(
                c => c.Id == id
            );
    }
}
```

---

# 92. Projeto prático — Cadastro de clientes

Modelo:

```csharp
class Cliente
{
    public int Id { get; set; }

    public string Nome { get; set; } = "";

    public string Email { get; set; } = "";
}
```

Lista:

```csharp
List<Cliente> clientes = new();
```

Menu:

```csharp
while (true)
{
    Console.WriteLine("1 - Cadastrar");
    Console.WriteLine("2 - Listar");
    Console.WriteLine("3 - Buscar");
    Console.WriteLine("4 - Excluir");
    Console.WriteLine("0 - Sair");

    string? opcao =
        Console.ReadLine();

    if (opcao == "0")
        break;
}
```

Cadastro:

```csharp
Console.Write("Nome: ");
string nome =
    Console.ReadLine() ?? "";

Console.Write("Email: ");
string email =
    Console.ReadLine() ?? "";

Cliente cliente = new()
{
    Id = clientes.Count + 1,
    Nome = nome,
    Email = email
};

clientes.Add(cliente);
```

Listar:

```csharp
foreach (Cliente cliente in clientes)
{
    Console.WriteLine(
        $"{cliente.Id} - {cliente.Nome} - {cliente.Email}"
    );
}
```

Buscar:

```csharp
Console.Write("ID: ");

if (
    int.TryParse(
        Console.ReadLine(),
        out int id))
{
    Cliente? cliente =
        clientes.FirstOrDefault(
            c => c.Id == id
        );

    if (cliente is null)
    {
        Console.WriteLine(
            "Cliente não encontrado."
        );
    }
    else
    {
        Console.WriteLine(
            cliente.Nome
        );
    }
}
```

---

# 93. Projeto prático — Sistema de estoque

Modelo:

```csharp
class Produto
{
    public int Id { get; set; }

    public string Nome { get; set; } = "";

    public decimal Preco { get; set; }

    public int Estoque { get; set; }

    public bool Ativo { get; set; } = true;
}
```

Menu:

```text
1 - Cadastrar produto
2 - Listar produtos
3 - Buscar produto
4 - Entrada de estoque
5 - Saída de estoque
6 - Produtos sem estoque
7 - Estoque baixo
8 - Valor total do estoque
0 - Sair
```

Valor total:

```csharp
decimal total =
    produtos.Sum(
        p => p.Preco * p.Estoque
    );

Console.WriteLine(
    $"Total: {total:C}"
);
```

Sem estoque:

```csharp
var semEstoque =
    produtos
        .Where(p => p.Estoque == 0)
        .ToList();
```

---

# 94. Exercícios — Básico

1. Mostre `Olá, mundo!`.
2. Crie variáveis nome, idade e cidade.
3. Leia dois números e mostre a soma.
4. Leia idade e informe se é maior de idade.
5. Mostre de 1 a 10 com `for`.
6. Crie array com cinco nomes.
7. Mostre apenas números pares.
8. Faça uma tabuada.
9. Leia dez números e calcule a média.
10. Descubra o maior de três números.

---

# 95. Exercícios — Intermediário

1. Crie uma classe `Produto`.
2. Crie uma lista de produtos.
3. Mostre produtos acima de R$ 100.
4. Descubra o produto mais caro.
5. Calcule a média dos preços.
6. Agrupe por categoria.
7. Salve em JSON.
8. Leia novamente o JSON.
9. Crie uma classe `ContaBancaria`.
10. Implemente depósito e saque com validação.

---

# 96. Exercícios — Avançado

1. Crie `IPagamento`.
2. Crie `PagamentoPix`.
3. Crie `PagamentoCartao`.
4. Crie `PagamentoBoleto`.
5. Faça um serviço que receba `IPagamento`.
6. Consuma uma API.
7. Crie testes.
8. Crie uma API ASP.NET Core.
9. Adicione Entity Framework Core.
10. Implemente CRUD completo.

---

# 97. Projeto final

Crie um sistema completo de vendas.

Entidades:

```text
Cliente
Produto
Categoria
Pedido
ItemPedido
Pagamento
Usuario
Endereco
```

## Cliente

```text
Id
Nome
Email
Telefone
Cidade
Ativo
```

## Produto

```text
Id
CategoriaId
Nome
Descricao
Preco
Estoque
Ativo
```

## Categoria

```text
Id
Nome
```

## Pedido

```text
Id
ClienteId
DataPedido
Status
Total
```

## ItemPedido

```text
Id
PedidoId
ProdutoId
Quantidade
PrecoUnitario
```

## Pagamento

```text
Id
PedidoId
Forma
Valor
Status
DataPagamento
```

Funcionalidades:

- cadastro;
- edição;
- exclusão;
- busca;
- listagem;
- filtros;
- controle de estoque;
- criação de pedido;
- cálculo de total;
- pagamento;
- relatórios.

O projeto deve usar:

- classes;
- interfaces;
- enums;
- encapsulamento;
- LINQ;
- exceptions;
- JSON;
- async/await;
- HttpClient;
- banco de dados;
- Entity Framework Core;
- ASP.NET Core;
- testes.

Estrutura sugerida:

```text
SistemaVendas/
├── Models/
├── DTOs/
├── Interfaces/
├── Services/
├── Repositories/
├── Data/
├── Controllers/
├── Tests/
└── Program.cs
```

---

# 98. Cheat Sheet

Variável:

```csharp
string nome = "Ana";
```

Número:

```csharp
int idade = 25;
```

Decimal:

```csharp
decimal preco = 99.90m;
```

Bool:

```csharp
bool ativo = true;
```

IF:

```csharp
if (idade >= 18)
{
}
```

FOR:

```csharp
for (int i = 0; i < 10; i++)
{
}
```

FOREACH:

```csharp
foreach (var item in lista)
{
}
```

Método:

```csharp
static int Somar(int a, int b)
{
    return a + b;
}
```

Classe:

```csharp
class Cliente
{
    public string Nome { get; set; } = "";
}
```

Objeto:

```csharp
Cliente cliente = new()
{
    Nome = "Ana"
};
```

Lista:

```csharp
List<string> nomes = new();
```

LINQ:

```csharp
var resultado =
    lista.Where(x => x.Ativo);
```

JSON:

```csharp
string json =
    JsonSerializer.Serialize(objeto);
```

Arquivo:

```csharp
File.WriteAllText(
    "arquivo.txt",
    "conteúdo"
);
```

Async:

```csharp
await MinhaFuncaoAsync();
```

HTTP:

```csharp
using HttpClient client = new();

string resposta =
    await client.GetStringAsync(url);
```

Exception:

```csharp
try
{
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

Interface:

```csharp
interface IServico
{
    void Executar();
}
```

Enum:

```csharp
enum Status
{
    Ativo,
    Inativo
}
```

---

# 99. Conceitos avançados para conhecer

## Extension Methods

```csharp
public static class StringExtensions
{
    public static bool EstaVazia(
        this string? texto)
    {
        return string.IsNullOrWhiteSpace(texto);
    }
}
```

Uso:

```csharp
string nome = "";

bool vazia =
    nome.EstaVazia();
```

## Pattern Matching

```csharp
object valor = 10;

if (valor is int numero)
{
    Console.WriteLine(numero * 2);
}
```

## Tuplas

```csharp
(string Nome, int Idade) pessoa =
    ("Ana", 25);
```

## Desestruturação

```csharp
var (nome, idade) = pessoa;
```

## using e IDisposable

```csharp
using StreamReader leitor =
    new("dados.txt");

string conteudo =
    leitor.ReadToEnd();
```

## Garbage Collector

O .NET gerencia memória automaticamente, mas recursos externos ainda podem precisar de descarte.

## Value Types

```text
int
double
bool
enum
struct
```

## Reference Types

```text
class
string
array
delegate
```

## Imutabilidade

```csharp
record Produto(
    int Id,
    string Nome,
    decimal Preco
);

Produto produto =
    new(1, "Mouse", 80);

Produto atualizado =
    produto with
    {
        Preco = 90
    };
```

## IEnumerable e IQueryable

`IEnumerable` normalmente trabalha em memória.

`IQueryable` é comum no Entity Framework e pode ser convertido em SQL.

## CancellationToken

```csharp
static async Task ExecutarAsync(
    CancellationToken token)
{
    await Task.Delay(
        5000,
        token
    );
}
```

## ConcurrentDictionary

```csharp
using System.Collections.Concurrent;

ConcurrentDictionary<int, string>
    dados = new();

dados.TryAdd(1, "Ana");
```

## Attributes

```csharp
[Obsolete("Use o novo método.")]
public void MetodoAntigo()
{
}
```

## Reflection

```csharp
Type tipo =
    typeof(Cliente);

foreach (
    var propriedade
    in tipo.GetProperties())
{
    Console.WriteLine(
        propriedade.Name
    );
}
```

---

# 100. Erros comuns

## Esquecer ponto e vírgula

Errado:

```csharp
int idade = 20
```

Certo:

```csharp
int idade = 20;
```

## Confundir `=` com `==`

Atribuição:

```csharp
idade = 20;
```

Comparação:

```csharp
idade == 20
```

## NullReferenceException

Perigoso:

```csharp
Cliente? cliente = null;

Console.WriteLine(
    cliente.Nome
);
```

Melhor:

```csharp
if (cliente is not null)
{
    Console.WriteLine(
        cliente.Nome
    );
}
```

## Parse em entrada desconhecida

Evite:

```csharp
int idade =
    int.Parse(
        Console.ReadLine()!
    );
```

Prefira:

```csharp
if (
    int.TryParse(
        Console.ReadLine(),
        out int idade))
{
}
```

## Tudo no Program.cs

À medida que o sistema crescer, use classes, services, repositories e interfaces.

---

# 101. Como estudar

## Etapa 1

Aprenda:

```text
variáveis
tipos
if
switch
loops
métodos
```

## Etapa 2

Aprenda:

```text
arrays
List
Dictionary
LINQ
```

## Etapa 3

Aprenda:

```text
classes
objetos
encapsulamento
interfaces
herança
```

## Etapa 4

Aprenda:

```text
JSON
arquivos
async/await
HttpClient
```

## Etapa 5

Aprenda:

```text
Entity Framework
ASP.NET Core
APIs
testes
```

---

# 102. Checklist de domínio

## Básico

- [ ] Sei criar um projeto.
- [ ] Sei executar `dotnet run`.
- [ ] Sei criar variáveis.
- [ ] Conheço tipos básicos.
- [ ] Sei usar `if`.
- [ ] Sei usar `switch`.
- [ ] Sei usar `for`.
- [ ] Sei usar `while`.
- [ ] Sei usar `foreach`.
- [ ] Sei criar métodos.
- [ ] Sei usar strings.
- [ ] Sei usar arrays.
- [ ] Sei usar List.

## Intermediário

- [ ] Sei criar classes.
- [ ] Sei criar objetos.
- [ ] Sei usar construtores.
- [ ] Entendo encapsulamento.
- [ ] Sei usar propriedades.
- [ ] Sei usar herança.
- [ ] Sei usar interfaces.
- [ ] Sei usar enums.
- [ ] Sei tratar exceptions.
- [ ] Sei usar LINQ.
- [ ] Sei trabalhar com JSON.
- [ ] Sei manipular arquivos.

## Avançado

- [ ] Sei usar generics.
- [ ] Sei usar delegates.
- [ ] Sei usar lambdas.
- [ ] Sei usar eventos.
- [ ] Sei usar async/await.
- [ ] Sei usar HttpClient.
- [ ] Sei consumir APIs.
- [ ] Sei organizar projetos.
- [ ] Entendo SOLID.
- [ ] Sei criar testes.
- [ ] Conheço Entity Framework Core.
- [ ] Conheço ASP.NET Core.
- [ ] Consigo criar uma API.

---

# 103. Próximos passos

Depois deste curso, estude:

- ASP.NET Core em profundidade;
- Controllers;
- Minimal APIs;
- Entity Framework Core;
- migrations;
- autenticação;
- JWT;
- Identity;
- dependency injection;
- middleware;
- logging;
- Docker;
- Redis;
- RabbitMQ;
- SignalR;
- gRPC;
- testes de integração;
- Clean Architecture;
- DDD;
- CQRS;
- background services;
- Azure;
- CI/CD.

---

# Regra de ouro

Não tente decorar C# inteiro.

Pense:

> O que eu preciso fazer?

Depois:

> Qual recurso da linguagem resolve isso?

Exemplo:

> Preciso encontrar produtos acima de R$ 100.

Você tem uma coleção e precisa filtrar.

```csharp
var produtosCaros =
    produtos
        .Where(p => p.Preco > 100)
        .ToList();
```

---

# Desafio final

Crie um sistema completo para um destes temas:

- restaurante;
- delivery;
- e-commerce;
- CRM;
- agenda;
- estoque;
- biblioteca;
- escola;
- oficina;
- imobiliária.

Inclua no mínimo:

- 8 classes;
- 3 interfaces;
- 3 enums;
- encapsulamento;
- validações;
- exceptions;
- coleções;
- LINQ;
- JSON;
- arquivos;
- async/await;
- consumo de API;
- banco de dados;
- Entity Framework Core;
- API ASP.NET Core;
- testes automatizados.

Se conseguir desenvolver isso sem depender de um tutorial passo a passo, você já terá deixado de ser iniciante em C#.

---

# Conclusão

Ao terminar e praticar este material, você deve conseguir:

- criar projetos .NET;
- entender a sintaxe de C#;
- trabalhar com variáveis e tipos;
- controlar fluxo;
- criar métodos;
- usar coleções;
- criar classes e objetos;
- aplicar orientação a objetos;
- trabalhar com interfaces;
- tratar erros;
- usar LINQ;
- manipular arquivos;
- trabalhar com JSON;
- usar programação assíncrona;
- consumir APIs;
- organizar projetos;
- criar testes;
- acessar banco de dados;
- usar Entity Framework Core;
- começar com ASP.NET Core;
- criar APIs.

> Programação se aprende programando.

Crie projetos, erre, depure, refatore e construa novamente.
