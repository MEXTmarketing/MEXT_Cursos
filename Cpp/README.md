# Curso Completo de C++ — Do Absoluto Zero ao Uso Profissional

> Curso prático para quem nunca programou em C++ e quer aprender desde a sintaxe básica até memória, ponteiros, orientação a objetos, STL, templates, arquivos, smart pointers, threads e organização de projetos reais.

---

# Sumário

1. O que é C++
2. Preparando o ambiente
3. Primeiro programa
4. Compilação
5. Variáveis e tipos
6. Entrada e saída
7. Operadores
8. Condicionais
9. Laços
10. Funções
11. Strings
12. Arrays
13. std::array
14. std::vector
15. Referências
16. Ponteiros
17. Stack e Heap
18. Memória dinâmica
19. Classes e objetos
20. Encapsulamento
21. Construtores e destrutores
22. Herança
23. Polimorfismo
24. Classes abstratas
25. Structs e enums
26. Templates
27. STL
28. Containers
29. Algoritmos
30. Lambdas
31. Iteradores
32. Arquivos
33. Exceções
34. Smart pointers
35. RAII
36. Copy e Move
37. Operator Overloading
38. Headers e múltiplos arquivos
39. CMake
40. Multithreading
41. Boas práticas
42. Exercícios
43. Projetos práticos
44. Projeto final
45. Cheat Sheet
46. Checklist
47. Próximos passos

---

# 1. O que é C++?

C++ é uma linguagem compilada, de alto desempenho e multiparadigma.

É muito usada em:

- jogos;
- engines;
- sistemas operacionais;
- sistemas embarcados;
- robótica;
- computação gráfica;
- aplicações financeiras;
- navegadores;
- bancos de dados;
- drivers;
- softwares de alto desempenho.

Exemplo:

```cpp
#include <iostream>

int main()
{
    std::cout << "Olá, mundo!\n";
    return 0;
}
```

---

# 2. Preparando o ambiente

Você precisa de um compilador.

Opções:

- GCC;
- Clang;
- MSVC.

IDEs:

- Visual Studio;
- Visual Studio Code;
- CLion;
- Code::Blocks.

No Linux:

```bash
sudo apt install g++
```

Verifique:

```bash
g++ --version
```

---

# 3. Primeiro programa

Crie:

```text
main.cpp
```

```cpp
#include <iostream>

int main()
{
    std::cout << "Olá, C++!\n";
    return 0;
}
```

---

# 4. Compilação

```bash
g++ main.cpp -o programa
```

Com C++20:

```bash
g++ main.cpp -std=c++20 -o programa
```

Executar:

```bash
./programa
```

No Windows:

```bash
programa.exe
```

---

# 5. Comentários

```cpp
// comentário de uma linha
```

```cpp
/*
comentário
de várias linhas
*/
```

---

# 6. Variáveis

```cpp
int idade = 25;
double altura = 1.80;
char letra = 'A';
bool ativo = true;
```

String:

```cpp
#include <string>

std::string nome = "Ana";
```

---

# 7. Tipos de dados

```cpp
int numero = 10;
short pequeno = 5;
long valor = 100000;
long long grande = 9000000000LL;

float peso = 70.5f;
double altura = 1.82;
long double preciso = 10.123L;

char letra = 'A';
bool ativo = true;
```

---

# 8. const

```cpp
const double PI = 3.14159;
```

Não pode ser alterada depois.

---

# 9. auto

O compilador deduz o tipo:

```cpp
auto idade = 25;
auto preco = 99.90;
auto nome = std::string("Ana");
```

---

# 10. Entrada e saída

Saída:

```cpp
std::cout << "Olá!\n";
```

Entrada:

```cpp
int idade;

std::cout << "Idade: ";
std::cin >> idade;
```

Texto com espaços:

```cpp
std::string nome;

std::getline(std::cin, nome);
```

---

# 11. Operadores matemáticos

```cpp
a + b
a - b
a * b
a / b
a % b
```

Incremento:

```cpp
a++;
```

Decremento:

```cpp
a--;
```

---

# 12. Comparações

```cpp
==
!=
>
<
>=
<=
```

---

# 13. Operadores lógicos

AND:

```cpp
&&
```

OR:

```cpp
||
```

NOT:

```cpp
!
```

---

# 14. if e else

```cpp
int idade = 20;

if (idade >= 18)
{
    std::cout << "Maior de idade\n";
}
else
{
    std::cout << "Menor de idade\n";
}
```

---

# 15. else if

```cpp
int nota = 8;

if (nota >= 9)
{
    std::cout << "Excelente\n";
}
else if (nota >= 7)
{
    std::cout << "Aprovado\n";
}
else
{
    std::cout << "Reprovado\n";
}
```

---

# 16. switch

```cpp
int opcao = 2;

switch (opcao)
{
    case 1:
        std::cout << "Cadastrar\n";
        break;

    case 2:
        std::cout << "Listar\n";
        break;

    case 3:
        std::cout << "Sair\n";
        break;

    default:
        std::cout << "Inválido\n";
}
```

---

# 17. Operador ternário

```cpp
std::string resultado =
    idade >= 18
        ? "Maior de idade"
        : "Menor de idade";
```

---

# 18. while

```cpp
int contador = 1;

while (contador <= 5)
{
    std::cout << contador << '\n';
    contador++;
}
```

---

# 19. do while

```cpp
int numero = 1;

do
{
    std::cout << numero << '\n';
    numero++;
}
while (numero <= 5);
```

---

# 20. for

```cpp
for (int i = 1; i <= 10; i++)
{
    std::cout << i << '\n';
}
```

---

# 21. range-based for

```cpp
int numeros[] = {10, 20, 30};

for (int numero : numeros)
{
    std::cout << numero << '\n';
}
```

---

# 22. break e continue

```cpp
for (int i = 1; i <= 10; i++)
{
    if (i == 5)
        break;

    std::cout << i << '\n';
}
```

```cpp
for (int i = 1; i <= 5; i++)
{
    if (i == 3)
        continue;

    std::cout << i << '\n';
}
```

---

# 23. Funções

```cpp
void saudacao()
{
    std::cout << "Olá!\n";
}
```

Uso:

```cpp
saudacao();
```

Com parâmetros:

```cpp
void saudacao(const std::string& nome)
{
    std::cout << "Olá, " << nome << "!\n";
}
```

Com retorno:

```cpp
int somar(int a, int b)
{
    return a + b;
}
```

---

# 24. Sobrecarga de funções

```cpp
int somar(int a, int b)
{
    return a + b;
}

double somar(double a, double b)
{
    return a + b;
}
```

---

# 25. Strings

```cpp
#include <string>

std::string nome = "Carlos";
```

Concatenação:

```cpp
std::string completo =
    nome + " Silva";
```

Tamanho:

```cpp
nome.length();
```

Buscar:

```cpp
nome.find("Car");
```

---

# 26. Arrays

```cpp
int numeros[] =
{
    10,
    20,
    30
};
```

Acessar:

```cpp
std::cout << numeros[0];
```

---

# 27. std::array

```cpp
#include <array>

std::array<int, 3> numeros =
{
    10,
    20,
    30
};
```

```cpp
numeros.size();
```

---

# 28. std::vector

Coleção dinâmica:

```cpp
#include <vector>

std::vector<int> numeros;
```

Adicionar:

```cpp
numeros.push_back(10);
numeros.push_back(20);
```

Remover último:

```cpp
numeros.pop_back();
```

Quantidade:

```cpp
numeros.size();
```

Iterar:

```cpp
for (int numero : numeros)
{
    std::cout << numero << '\n';
}
```

---

# 29. Referências

```cpp
int numero = 10;

int& referencia = numero;

referencia = 20;
```

Agora `numero` vale 20.

Parâmetro por referência:

```cpp
void dobrar(int& numero)
{
    numero *= 2;
}
```

Referência constante:

```cpp
void mostrar(const std::string& texto)
{
    std::cout << texto;
}
```

---

# 30. Ponteiros

Ponteiro guarda um endereço de memória.

```cpp
int numero = 10;

int* ponteiro = &numero;
```

Endereço:

```cpp
std::cout << ponteiro;
```

Valor apontado:

```cpp
std::cout << *ponteiro;
```

Alterar através do ponteiro:

```cpp
*ponteiro = 20;
```

---

# 31. nullptr

```cpp
int* ponteiro = nullptr;
```

Verifique antes de usar:

```cpp
if (ponteiro != nullptr)
{
    std::cout << *ponteiro;
}
```

---

# 32. Stack e Heap

## Stack

```cpp
int numero = 10;
```

Memória automática.

## Heap

```cpp
int* numero =
    new int(10);
```

Memória dinâmica.

Liberar:

```cpp
delete numero;
```

---

# 33. Memória dinâmica

Array:

```cpp
int* numeros =
    new int[5];
```

Liberar:

```cpp
delete[] numeros;
```

Em C++ moderno, prefira:

- `std::vector`;
- `std::unique_ptr`;
- `std::shared_ptr`.

---

# 34. Memory Leak

Isto:

```cpp
int* numero =
    new int(10);
```

sem:

```cpp
delete numero;
```

causa vazamento de memória.

---

# 35. Dangling Pointer

```cpp
int* p =
    new int(10);

delete p;
```

Depois disso, não use:

```cpp
*p
```

Uma boa prática:

```cpp
p = nullptr;
```

---

# 36. Classes e objetos

```cpp
class Pessoa
{
public:
    std::string nome;
    int idade;
};
```

Criar:

```cpp
Pessoa pessoa;

pessoa.nome = "Ana";
pessoa.idade = 25;
```

---

# 37. Encapsulamento

```cpp
class Conta
{
private:
    double saldo = 0;

public:
    void depositar(double valor)
    {
        if (valor > 0)
        {
            saldo += valor;
        }
    }

    double getSaldo() const
    {
        return saldo;
    }
};
```

---

# 38. Construtores

```cpp
class Pessoa
{
private:
    std::string nome;

public:
    Pessoa(std::string nome)
        : nome(nome)
    {
    }

    std::string getNome() const
    {
        return nome;
    }
};
```

Uso:

```cpp
Pessoa pessoa("Ana");
```

---

# 39. Destrutores

```cpp
class Recurso
{
public:
    ~Recurso()
    {
        std::cout
            << "Destruído\n";
    }
};
```

---

# 40. this

```cpp
class Pessoa
{
private:
    std::string nome;

public:
    void setNome(
        std::string nome)
    {
        this->nome = nome;
    }
};
```

---

# 41. Herança

```cpp
class Animal
{
public:
    std::string nome;
};
```

```cpp
class Cachorro : public Animal
{
public:
    void latir()
    {
        std::cout << "Au au!\n";
    }
};
```

---

# 42. Polimorfismo

```cpp
class Animal
{
public:
    virtual void emitirSom() const
    {
        std::cout << "Som\n";
    }

    virtual ~Animal() = default;
};
```

```cpp
class Cachorro : public Animal
{
public:
    void emitirSom() const override
    {
        std::cout << "Au au!\n";
    }
};
```

---

# 43. Classes abstratas

```cpp
class Pagamento
{
public:
    virtual void pagar(
        double valor
    ) = 0;

    virtual ~Pagamento() = default;
};
```

Implementação:

```cpp
class PagamentoPix : public Pagamento
{
public:
    void pagar(
        double valor
    ) override
    {
        std::cout
            << "PIX: "
            << valor
            << '\n';
    }
};
```

---

# 44. Composição

```cpp
class Motor
{
public:
    void ligar()
    {
        std::cout << "Motor ligado\n";
    }
};
```

```cpp
class Carro
{
private:
    Motor motor;

public:
    void ligar()
    {
        motor.ligar();
    }
};
```

---

# 45. Structs

```cpp
struct Produto
{
    int id;
    std::string nome;
    double preco;
};
```

Em `struct`, membros são públicos por padrão.

Em `class`, privados por padrão.

---

# 46. Enum class

```cpp
enum class StatusPedido
{
    Pendente,
    Pago,
    Enviado,
    Cancelado
};
```

Uso:

```cpp
StatusPedido status =
    StatusPedido::Pago;
```

---

# 47. Templates

```cpp
template <typename T>
T maior(T a, T b)
{
    return a > b ? a : b;
}
```

Uso:

```cpp
maior(10, 20);
maior(10.5, 9.8);
```

Template de classe:

```cpp
template <typename T>
class Caixa
{
private:
    T valor;

public:
    Caixa(T valor)
        : valor(valor)
    {
    }

    T getValor() const
    {
        return valor;
    }
};
```

---

# 48. STL

STL significa:

```text
Standard Template Library
```

Ela oferece containers, algoritmos e iteradores.

Principais containers:

- vector;
- array;
- list;
- deque;
- stack;
- queue;
- set;
- map;
- unordered_map.

---

# 49. list

```cpp
#include <list>

std::list<int> numeros =
{
    10,
    20,
    30
};

numeros.push_front(5);
numeros.push_back(40);
```

---

# 50. deque

```cpp
#include <deque>

std::deque<int> numeros;

numeros.push_front(5);
numeros.push_back(10);
```

---

# 51. stack

```cpp
#include <stack>

std::stack<int> pilha;

pilha.push(10);
pilha.push(20);

std::cout << pilha.top();

pilha.pop();
```

---

# 52. queue

```cpp
#include <queue>

std::queue<std::string> fila;

fila.push("Ana");
fila.push("Carlos");

std::cout << fila.front();

fila.pop();
```

---

# 53. set

Valores únicos:

```cpp
#include <set>

std::set<int> numeros =
{
    3,
    1,
    2,
    3
};
```

Resultado:

```text
1 2 3
```

---

# 54. map

```cpp
#include <map>

std::map<int, std::string>
    clientes;

clientes[1] = "Ana";
clientes[2] = "Carlos";
```

---

# 55. unordered_map

```cpp
#include <unordered_map>

std::unordered_map<int, std::string>
    clientes;

clientes[1] = "Ana";
```

---

# 56. Algoritmos da STL

```cpp
#include <algorithm>
```

Algoritmos úteis:

- sort;
- find;
- find_if;
- count;
- reverse;
- for_each;
- min_element;
- max_element.

---

# 57. sort

```cpp
std::sort(
    numeros.begin(),
    numeros.end()
);
```

Decrescente:

```cpp
std::sort(
    numeros.begin(),
    numeros.end(),
    std::greater<int>()
);
```

---

# 58. find

```cpp
auto it =
    std::find(
        numeros.begin(),
        numeros.end(),
        20
    );

if (it != numeros.end())
{
    std::cout << "Encontrado\n";
}
```

---

# 59. find_if

```cpp
auto it =
    std::find_if(
        produtos.begin(),
        produtos.end(),
        [](const Produto& p)
        {
            return p.id == 10;
        }
    );
```

---

# 60. Lambdas

```cpp
auto somar =
    [](int a, int b)
    {
        return a + b;
    };
```

Uso:

```cpp
std::cout << somar(10, 20);
```

Captura:

```cpp
int multiplicador = 2;

auto calcular =
    [multiplicador](int valor)
    {
        return valor * multiplicador;
    };
```

---

# 61. Iteradores

```cpp
for (
    auto it = numeros.begin();
    it != numeros.end();
    ++it
)
{
    std::cout << *it << '\n';
}
```

---

# 62. Arquivos

```cpp
#include <fstream>
```

Escrever:

```cpp
std::ofstream arquivo(
    "dados.txt"
);

arquivo
    << "Olá mundo\n";
```

Ler:

```cpp
std::ifstream arquivo(
    "dados.txt"
);

std::string linha;

while (
    std::getline(
        arquivo,
        linha
    )
)
{
    std::cout << linha << '\n';
}
```

---

# 63. Exceções

```cpp
#include <stdexcept>

throw std::runtime_error(
    "Algo deu errado"
);
```

Tratamento:

```cpp
try
{
    throw std::runtime_error(
        "Erro"
    );
}
catch (
    const std::exception& ex
)
{
    std::cout
        << ex.what()
        << '\n';
}
```

---

# 64. Smart Pointers

Inclua:

```cpp
#include <memory>
```

Tipos:

- unique_ptr;
- shared_ptr;
- weak_ptr.

---

# 65. unique_ptr

Um único dono:

```cpp
auto numero =
    std::make_unique<int>(10);

std::cout << *numero;
```

A memória é liberada automaticamente.

---

# 66. shared_ptr

Vários donos:

```cpp
auto cliente =
    std::make_shared<std::string>(
        "Ana"
    );

auto copia = cliente;
```

---

# 67. weak_ptr

Não aumenta o contador de referências:

```cpp
std::weak_ptr<int> fraco;
```

Ajuda a evitar ciclos de `shared_ptr`.

---

# 68. RAII

RAII:

```text
Resource Acquisition Is Initialization
```

Ideia:

> o tempo de vida de um recurso deve ser controlado pelo tempo de vida de um objeto.

Exemplos:

- memória;
- arquivo;
- mutex;
- conexão.

Smart pointers seguem esse princípio.

---

# 69. Copy Constructor

```cpp
class Pessoa
{
public:
    std::string nome;

    Pessoa(
        const Pessoa& outra)
        : nome(outra.nome)
    {
    }
};
```

---

# 70. Move Semantics

```cpp
#include <utility>

std::string origem =
    "Texto";

std::string destino =
    std::move(origem);
```

Evita cópias desnecessárias em alguns cenários.

---

# 71. Move Constructor

```cpp
class Pessoa
{
public:
    std::string nome;

    Pessoa(Pessoa&& outra) noexcept
        : nome(
            std::move(
                outra.nome
            )
        )
    {
    }
};
```

---

# 72. Rule of Zero

Em C++ moderno, prefira usar tipos que já gerenciam recursos:

```text
std::string
std::vector
std::unique_ptr
```

Assim você normalmente não precisa implementar manualmente:

- destrutor;
- cópia;
- movimento.

---

# 73. Rule of Five

Se uma classe gerencia recurso manualmente, pense em:

1. destrutor;
2. copy constructor;
3. copy assignment;
4. move constructor;
5. move assignment.

---

# 74. Operator Overloading

```cpp
class Vetor2
{
public:
    float x;
    float y;

    Vetor2(float x, float y)
        : x(x), y(y)
    {
    }

    Vetor2 operator+(
        const Vetor2& outro
    ) const
    {
        return {
            x + outro.x,
            y + outro.y
        };
    }
};
```

Uso:

```cpp
Vetor2 a(1, 2);
Vetor2 b(3, 4);

Vetor2 c = a + b;
```

---

# 75. const correctness

Método que não altera:

```cpp
double getSaldo() const
{
    return saldo;
}
```

Parâmetro que não deve ser modificado:

```cpp
void mostrar(
    const std::string& texto
)
{
    std::cout << texto;
}
```

---

# 76. Headers e arquivos separados

Estrutura:

```text
projeto/
├── main.cpp
├── Produto.h
└── Produto.cpp
```

`Produto.h`:

```cpp
#pragma once

#include <string>

class Produto
{
public:
    Produto(
        std::string nome,
        double preco
    );

    void mostrar() const;

private:
    std::string nome;
    double preco;
};
```

`Produto.cpp`:

```cpp
#include "Produto.h"
#include <iostream>

Produto::Produto(
    std::string nome,
    double preco
)
    : nome(nome),
      preco(preco)
{
}

void Produto::mostrar() const
{
    std::cout
        << nome
        << " - "
        << preco
        << '\n';
}
```

---

# 77. CMake

`CMakeLists.txt`:

```cmake
cmake_minimum_required(VERSION 3.20)

project(MeuProjeto)

set(CMAKE_CXX_STANDARD 20)

add_executable(
    MeuProjeto
    main.cpp
    Produto.cpp
)
```

Gerar:

```bash
cmake -S . -B build
```

Compilar:

```bash
cmake --build build
```

---

# 78. Debugging

Aprenda a usar:

- breakpoint;
- step over;
- step into;
- watch;
- call stack;
- inspeção de variáveis.

Evite depender apenas de:

```cpp
std::cout
```

---

# 79. Multithreading

```cpp
#include <thread>
```

```cpp
void tarefa()
{
    std::cout
        << "Executando\n";
}
```

```cpp
std::thread t(tarefa);

t.join();
```

---

# 80. mutex

```cpp
#include <mutex>

std::mutex mutex;
int contador = 0;
```

```cpp
void incrementar()
{
    std::lock_guard<std::mutex>
        lock(mutex);

    contador++;
}
```

---

# 81. atomic

```cpp
#include <atomic>

std::atomic<int>
    contador = 0;
```

Útil para operações concorrentes simples.

---

# 82. std::optional

```cpp
#include <optional>

std::optional<int>
buscar(bool encontrou)
{
    if (encontrou)
        return 10;

    return std::nullopt;
}
```

---

# 83. std::variant

```cpp
#include <variant>

std::variant<
    int,
    std::string
> valor;

valor = 10;

valor =
    std::string("Olá");
```

---

# 84. Structured Bindings

```cpp
std::pair<int, std::string>
    cliente =
    {
        1,
        "Ana"
    };

auto [id, nome] =
    cliente;
```

---

# 85. constexpr

```cpp
constexpr int quadrado(
    int n
)
{
    return n * n;
}
```

```cpp
constexpr int resultado =
    quadrado(5);
```

---

# 86. static_cast

```cpp
int a = 5;
int b = 2;

double resultado =
    static_cast<double>(a)
    / b;
```

Evite casts no estilo C quando existe uma alternativa C++ mais clara.

---

# 87. chrono

```cpp
#include <chrono>

auto inicio =
    std::chrono::
    high_resolution_clock::now();

// código

auto fim =
    std::chrono::
    high_resolution_clock::now();
```

Calcular:

```cpp
auto tempo =
    std::chrono::
    duration_cast<
        std::chrono::milliseconds
    >(
        fim - inicio
    );
```

---

# 88. random

```cpp
#include <random>

std::random_device rd;

std::mt19937 gerador(
    rd()
);

std::uniform_int_distribution<int>
    dist(1, 100);

int numero =
    dist(gerador);
```

---

# 89. filesystem

```cpp
#include <filesystem>

namespace fs =
    std::filesystem;
```

Verificar:

```cpp
if (
    fs::exists(
        "dados.txt"
    )
)
{
    std::cout
        << "Existe\n";
}
```

Criar pasta:

```cpp
fs::create_directory(
    "dados"
);
```

---

# 90. Boas práticas

## Prefira std::vector

Em vez de:

```cpp
int* numeros =
    new int[100];
```

prefira:

```cpp
std::vector<int>
    numeros(100);
```

## Prefira smart pointers

Em vez de:

```cpp
Pessoa* p =
    new Pessoa();
```

prefira:

```cpp
auto p =
    std::make_unique<Pessoa>();
```

## Use const

```cpp
void mostrar(
    const Produto& produto
);
```

## Evite using namespace std

Evite:

```cpp
using namespace std;
```

Prefira:

```cpp
std::cout
std::string
std::vector
```

---

# 91. Erros comuns

## Índice inválido

```cpp
std::vector<int> numeros =
{
    1,
    2,
    3
};

std::cout << numeros[10];
```

Use `at()` quando quiser verificação:

```cpp
std::cout
    << numeros.at(1);
```

## Ponteiro nulo

```cpp
int* p = nullptr;

std::cout << *p;
```

Não faça isso.

## Divisão inteira

```cpp
int a = 5;
int b = 2;

std::cout << a / b;
```

Resultado:

```text
2
```

Para decimal:

```cpp
double resultado =
    static_cast<double>(a)
    / b;
```

---

# 92. Projeto prático 1 — Calculadora

Menu:

```text
1 - Somar
2 - Subtrair
3 - Multiplicar
4 - Dividir
0 - Sair
```

Crie funções:

```cpp
double somar(
    double a,
    double b
)
{
    return a + b;
}
```

Requisitos:

- funções separadas;
- menu em loop;
- validação;
- divisão por zero;
- opção inválida.

---

# 93. Projeto prático 2 — Cadastro

Classe:

```cpp
class Cliente
{
private:
    int id;
    std::string nome;
    std::string email;

public:
    Cliente(
        int id,
        std::string nome,
        std::string email
    )
        : id(id),
          nome(nome),
          email(email)
    {
    }

    int getId() const
    {
        return id;
    }

    std::string getNome() const
    {
        return nome;
    }
};
```

Armazene em:

```cpp
std::vector<Cliente>
    clientes;
```

Implemente:

- cadastrar;
- listar;
- buscar;
- editar;
- excluir.

---

# 94. Projeto prático 3 — Estoque

Classe:

```cpp
class Produto
{
private:
    int id;
    std::string nome;
    double preco;
    int estoque;

public:
    Produto(
        int id,
        std::string nome,
        double preco,
        int estoque
    )
        : id(id),
          nome(nome),
          preco(preco),
          estoque(estoque)
    {
    }

    double valorEmEstoque() const
    {
        return preco * estoque;
    }
};
```

Funcionalidades:

```text
1 - Cadastrar
2 - Listar
3 - Buscar
4 - Entrada
5 - Saída
6 - Sem estoque
7 - Estoque baixo
8 - Valor total
0 - Sair
```

---

# 95. Exercícios básicos

1. Mostre `Olá, mundo!`.
2. Leia nome e idade.
3. Some dois números.
4. Calcule média.
5. Descubra se um número é par.
6. Descubra o maior entre três valores.
7. Faça uma tabuada.
8. Conte de 1 a 100.
9. Mostre somente números pares.
10. Calcule o fatorial de um número.
11. Faça uma calculadora.
12. Inverta uma string.
13. Conte vogais.
14. Descubra se uma palavra é palíndromo.
15. Gere números aleatórios.

---

# 96. Exercícios intermediários

1. Crie uma função de média.
2. Crie classe Produto.
3. Crie `vector<Produto>`.
4. Busque produto por ID.
5. Ordene por preço.
6. Ordene por nome.
7. Salve em arquivo.
8. Leia de arquivo.
9. Crie ContaBancaria.
10. Implemente depósito.
11. Implemente saque.
12. Crie classe abstrata Pagamento.
13. Crie PagamentoPix.
14. Crie PagamentoCartao.
15. Use smart pointers.

---

# 97. Exercícios avançados

1. Crie um template genérico.
2. Implemente operador `+`.
3. Implemente operador `<<`.
4. Use `find_if`.
5. Use lambda em `sort`.
6. Use `unique_ptr`.
7. Use `shared_ptr`.
8. Implemente copy constructor.
9. Implemente move constructor.
10. Crie projeto com `.h` e `.cpp`.
11. Configure CMake.
12. Crie duas threads.
13. Proteja contador com mutex.
14. Use atomic.
15. Faça profiling básico com chrono.

---

# 98. Projeto final

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
id
nome
email
telefone
cidade
```

## Produto

```text
id
categoriaId
nome
descricao
preco
estoque
ativo
```

## Pedido

```text
id
clienteId
data
status
total
```

## ItemPedido

```text
id
pedidoId
produtoId
quantidade
precoUnitario
```

## Pagamento

```text
id
pedidoId
forma
valor
status
```

Funcionalidades:

- CRUD de clientes;
- CRUD de produtos;
- categorias;
- estoque;
- pedidos;
- pagamentos;
- relatórios;
- persistência em arquivo.

Use obrigatoriamente:

- classes;
- encapsulamento;
- herança;
- polimorfismo;
- templates;
- STL;
- vector;
- map;
- algoritmos;
- lambdas;
- exceções;
- smart pointers;
- RAII;
- múltiplos arquivos;
- CMake.

Estrutura sugerida:

```text
SistemaVendas/
├── CMakeLists.txt
├── src/
│   ├── main.cpp
│   ├── Cliente.cpp
│   ├── Produto.cpp
│   └── Pedido.cpp
├── include/
│   ├── Cliente.h
│   ├── Produto.h
│   └── Pedido.h
└── data/
```

---

# 99. Cheat Sheet

Saída:

```cpp
std::cout << "Olá\n";
```

Entrada:

```cpp
std::cin >> idade;
```

String:

```cpp
std::string nome = "Ana";
```

IF:

```cpp
if (idade >= 18)
{
}
```

FOR:

```cpp
for (int i = 0; i < 10; i++)
{
}
```

Função:

```cpp
int somar(int a, int b)
{
    return a + b;
}
```

Vector:

```cpp
std::vector<int> numeros;
```

Adicionar:

```cpp
numeros.push_back(10);
```

Classe:

```cpp
class Cliente
{
public:
    std::string nome;
};
```

Ponteiro:

```cpp
int numero = 10;
int* p = &numero;
```

Referência:

```cpp
int& ref = numero;
```

Smart pointer:

```cpp
auto p =
    std::make_unique<int>(10);
```

Lambda:

```cpp
auto dobro =
    [](int n)
    {
        return n * 2;
    };
```

Arquivo:

```cpp
std::ofstream arquivo(
    "dados.txt"
);
```

Exceção:

```cpp
try
{
}
catch (
    const std::exception& ex
)
{
}
```

Thread:

```cpp
std::thread t(funcao);
t.join();
```

---

# 100. Checklist de domínio

## Básico

- [ ] Sei instalar compilador.
- [ ] Sei compilar `.cpp`.
- [ ] Sei usar `cout`.
- [ ] Sei usar `cin`.
- [ ] Sei criar variáveis.
- [ ] Conheço os tipos básicos.
- [ ] Sei usar `if`.
- [ ] Sei usar `switch`.
- [ ] Sei usar `for`.
- [ ] Sei usar `while`.
- [ ] Sei criar funções.
- [ ] Sei usar string.
- [ ] Sei usar arrays.
- [ ] Sei usar vector.

## Intermediário

- [ ] Entendo referências.
- [ ] Entendo ponteiros.
- [ ] Entendo Stack e Heap.
- [ ] Sei criar classes.
- [ ] Sei usar encapsulamento.
- [ ] Sei criar construtores.
- [ ] Sei usar herança.
- [ ] Sei usar polimorfismo.
- [ ] Sei usar enum class.
- [ ] Sei usar templates.
- [ ] Sei usar STL.
- [ ] Sei trabalhar com arquivos.

## Avançado

- [ ] Sei usar lambdas.
- [ ] Sei usar algoritmos STL.
- [ ] Sei usar smart pointers.
- [ ] Entendo RAII.
- [ ] Entendo Copy e Move.
- [ ] Sei sobrecarregar operadores.
- [ ] Entendo const correctness.
- [ ] Sei separar headers e fontes.
- [ ] Sei usar CMake.
- [ ] Sei criar threads.
- [ ] Sei usar mutex.
- [ ] Sei usar atomic.
- [ ] Sei evitar memory leaks.

---

# 101. Como estudar

## Etapa 1

Aprenda:

```text
variáveis
tipos
entrada
saída
condicionais
loops
funções
```

## Etapa 2

Aprenda:

```text
strings
arrays
vector
referências
ponteiros
```

## Etapa 3

Aprenda:

```text
classes
objetos
encapsulamento
herança
polimorfismo
```

## Etapa 4

Aprenda:

```text
STL
templates
algoritmos
lambdas
arquivos
```

## Etapa 5

Aprenda:

```text
smart pointers
RAII
move semantics
CMake
threads
```

---

# 102. Próximos passos

Depois deste curso, estude:

- C++ moderno;
- concepts;
- ranges;
- coroutines;
- modules;
- metaprogramação;
- memory model;
- lock-free programming;
- design patterns;
- Boost;
- Qt;
- SDL;
- OpenGL;
- Vulkan;
- Unreal Engine;
- sistemas embarcados;
- profiling;
- SIMD;
- CMake avançado;
- Conan;
- vcpkg;
- GoogleTest.

---

# Regra de ouro do C++

Ao escrever C++, faça estas perguntas:

```text
Quem é dono deste recurso?
Quanto tempo ele vive?
Quem pode alterar?
Está no Stack ou Heap?
Preciso copiar?
Posso passar por referência?
Posso mover?
Preciso mesmo de um ponteiro?
```

Entender isso vale mais do que decorar centenas de comandos.

---

# Desafio final

Crie um sistema para um destes temas:

- restaurante;
- estoque;
- biblioteca;
- escola;
- oficina;
- game;
- banco;
- agenda;
- e-commerce;
- gerenciamento de tarefas.

Requisitos mínimos:

- 8 classes;
- herança;
- polimorfismo;
- 2 classes abstratas;
- templates;
- vector;
- map;
- algorithms;
- lambdas;
- arquivos;
- exceptions;
- smart pointers;
- RAII;
- múltiplos arquivos;
- CMake;
- ao menos uma thread.

Se conseguir desenvolver isso sem depender de um tutorial passo a passo, você já terá uma base muito sólida em C++.

---

# Conclusão

Ao concluir e praticar este curso, você deve conseguir:

- criar e compilar programas C++;
- trabalhar com tipos e variáveis;
- usar condicionais e loops;
- criar funções;
- trabalhar com strings e coleções;
- compreender referências;
- compreender ponteiros;
- entender Stack e Heap;
- gerenciar memória;
- criar classes e objetos;
- aplicar orientação a objetos;
- usar templates;
- trabalhar com STL;
- usar algoritmos;
- trabalhar com arquivos;
- tratar exceções;
- usar smart pointers;
- entender RAII;
- entender copy e move semantics;
- estruturar projetos reais;
- utilizar CMake;
- trabalhar com concorrência básica.

> C++ se aprende entendendo código, memória e tempo de vida dos objetos — e depois praticando muito.

Crie projetos, use o debugger, leia os erros do compilador e refatore seu código várias vezes.
