# Curso Completo de SQL — Do Absoluto Zero ao Uso Profissional

> Um curso prático para quem nunca trabalhou com banco de dados e quer sair do zero sabendo criar bancos, tabelas, inserir dados, consultar, filtrar, relacionar informações, fazer relatórios, atualizar registros, trabalhar com transações, índices, views e muito mais.

---

## 📚 Sumário

1. [O que é SQL?](#1-o-que-é-sql)
2. [O que é um banco de dados?](#2-o-que-é-um-banco-de-dados)
3. [Como preparar o ambiente](#3-como-preparar-o-ambiente)
4. [Como pensar em tabelas](#4-como-pensar-em-tabelas)
5. [Criando seu primeiro banco](#5-criando-seu-primeiro-banco)
6. [CREATE TABLE](#6-create-table)
7. [Tipos de dados](#7-tipos-de-dados)
8. [INSERT — Inserindo dados](#8-insert--inserindo-dados)
9. [SELECT — Consultando dados](#9-select--consultando-dados)
10. [WHERE — Filtrando resultados](#10-where--filtrando-resultados)
11. [Operadores de comparação](#11-operadores-de-comparação)
12. [AND, OR e NOT](#12-and-or-e-not)
13. [ORDER BY](#13-order-by)
14. [LIMIT](#14-limit)
15. [DISTINCT](#15-distinct)
16. [LIKE](#16-like)
17. [IN](#17-in)
18. [BETWEEN](#18-between)
19. [NULL](#19-null)
20. [UPDATE](#20-update)
21. [DELETE](#21-delete)
22. [ALTER TABLE](#22-alter-table)
23. [DROP e TRUNCATE](#23-drop-e-truncate)
24. [Chaves primárias e estrangeiras](#24-chaves-primárias-e-estrangeiras)
25. [Relacionamentos](#25-relacionamentos)
26. [JOIN](#26-join)
27. [INNER JOIN](#27-inner-join)
28. [LEFT JOIN](#28-left-join)
29. [RIGHT JOIN e FULL JOIN](#29-right-join-e-full-join)
30. [Funções de agregação](#30-funções-de-agregação)
31. [GROUP BY](#31-group-by)
32. [HAVING](#32-having)
33. [Aliases com AS](#33-aliases-com-as)
34. [CASE](#34-case)
35. [Funções de texto](#35-funções-de-texto)
36. [Funções matemáticas](#36-funções-matemáticas)
37. [Datas e horários](#37-datas-e-horários)
38. [Subqueries](#38-subqueries)
39. [EXISTS](#39-exists)
40. [CTEs com WITH](#40-ctes-com-with)
41. [UNION e UNION ALL](#41-union-e-union-all)
42. [Views](#42-views)
43. [Índices](#43-índices)
44. [Constraints](#44-constraints)
45. [Transações](#45-transações)
46. [Normalização](#46-normalização)
47. [Modelagem de banco](#47-modelagem-de-banco)
48. [Boas práticas](#48-boas-práticas)
49. [Segurança e SQL Injection](#49-segurança-e-sql-injection)
50. [Diferenças entre MySQL, PostgreSQL e SQLite](#50-diferenças-entre-mysql-postgresql-e-sqlite)
51. [Banco completo para praticar](#51-banco-completo-para-praticar)
52. [Consultas práticas](#52-consultas-práticas)
53. [Exercícios](#53-exercícios)
54. [Projeto final](#54-projeto-final)
55. [Cheat Sheet](#55-cheat-sheet)
56. [Próximos passos](#56-próximos-passos)

---

# 1. O que é SQL?

SQL significa:

**Structured Query Language**

Em português:

**Linguagem de Consulta Estruturada**

É uma linguagem usada para conversar com bancos de dados relacionais.

Com SQL você consegue:

- criar bancos;
- criar tabelas;
- cadastrar dados;
- buscar dados;
- filtrar resultados;
- atualizar informações;
- apagar registros;
- relacionar tabelas;
- gerar relatórios;
- fazer cálculos;
- controlar integridade;
- melhorar desempenho;
- trabalhar com transações.

Exemplo:

```sql
SELECT nome, email
FROM clientes;
```

Essa instrução significa:

> Busque as colunas `nome` e `email` da tabela `clientes`.

---

# 2. O que é um banco de dados?

Imagine uma planilha.

Ela possui:

- colunas;
- linhas;
- informações organizadas.

Um banco de dados funciona de maneira parecida, mas é muito mais poderoso.

Exemplo de tabela `clientes`:

| id | nome | email | cidade |
|---|---|---|---|
| 1 | Ana | ana@email.com | Caxias do Sul |
| 2 | João | joao@email.com | Porto Alegre |
| 3 | Maria | maria@email.com | Caxias do Sul |

Cada:

- **linha** representa um registro;
- **coluna** representa uma característica;
- **tabela** representa um tipo de entidade.

---

# 3. Como preparar o ambiente

Para aprender SQL você pode usar:

## Opção 1 — SQLite

É a opção mais simples para começar.

Não exige servidor.

Ferramentas:

- DB Browser for SQLite;
- SQLiteStudio;
- extensão SQLite no VS Code.

## Opção 2 — MySQL

Muito usado em:

- PHP;
- hospedagens;
- sistemas web;
- WordPress;
- aplicações empresariais.

Ferramentas:

- MySQL Server;
- MySQL Workbench;
- phpMyAdmin.

## Opção 3 — PostgreSQL

Muito usado em sistemas modernos e profissionais.

Ferramentas:

- PostgreSQL;
- pgAdmin;
- DBeaver.

## Recomendação para este curso

Você pode estudar usando qualquer um deles.

Os exemplos usam SQL bastante genérico. Quando houver diferença importante entre bancos, ela será mencionada.

---

# 4. Como pensar em tabelas

Antes de escrever SQL, pense:

> Que tipo de informação quero armazenar?

Exemplo: loja.

Podemos ter:

- clientes;
- produtos;
- pedidos;
- itens do pedido.

Um cliente pode fazer vários pedidos.

Um pedido pode ter vários produtos.

Essa forma de separar os dados evita repetição e facilita consultas.

---

# 5. Criando seu primeiro banco

No MySQL:

```sql
CREATE DATABASE loja;
```

Depois:

```sql
USE loja;
```

No PostgreSQL, normalmente o banco é criado fora da sessão atual e depois você se conecta a ele.

No SQLite, o próprio arquivo `.db` já representa o banco.

---

# 6. CREATE TABLE

Agora vamos criar uma tabela.

```sql
CREATE TABLE clientes (
    id INTEGER PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(150),
    cidade VARCHAR(100)
);
```

A tabela possui quatro colunas:

- `id`;
- `nome`;
- `email`;
- `cidade`.

---

# 7. Tipos de dados

Cada coluna deve possuir um tipo.

## INTEGER

Números inteiros.

```sql
idade INTEGER
```

Exemplos:

```text
10
25
100
```

## DECIMAL

Valores com casas decimais.

```sql
preco DECIMAL(10,2)
```

Exemplos:

```text
19.90
100.00
1499.99
```

## VARCHAR

Texto com limite de tamanho.

```sql
nome VARCHAR(100)
```

## TEXT

Texto maior.

```sql
descricao TEXT
```

## DATE

Data.

```sql
data_nascimento DATE
```

Exemplo:

```text
2026-09-05
```

## DATETIME / TIMESTAMP

Data e hora.

```sql
criado_em TIMESTAMP
```

## BOOLEAN

Verdadeiro ou falso.

```sql
ativo BOOLEAN
```

---

# 8. INSERT — Inserindo dados

Para cadastrar um registro:

```sql
INSERT INTO clientes (nome, email, cidade)
VALUES ('Ana', 'ana@email.com', 'Caxias do Sul');
```

Vários registros:

```sql
INSERT INTO clientes (nome, email, cidade)
VALUES
('João', 'joao@email.com', 'Porto Alegre'),
('Maria', 'maria@email.com', 'Caxias do Sul'),
('Carlos', 'carlos@email.com', 'Bento Gonçalves');
```

---

# 9. SELECT — Consultando dados

O comando mais usado do SQL é `SELECT`.

Todos os campos:

```sql
SELECT *
FROM clientes;
```

Campos específicos:

```sql
SELECT nome, email
FROM clientes;
```

---

# 10. WHERE — Filtrando resultados

Buscar somente clientes de Caxias do Sul:

```sql
SELECT *
FROM clientes
WHERE cidade = 'Caxias do Sul';
```

Buscar cliente de ID 2:

```sql
SELECT *
FROM clientes
WHERE id = 2;
```

---

# 11. Operadores de comparação

## Igual

```sql
=
```

Exemplo:

```sql
WHERE cidade = 'Caxias do Sul'
```

## Diferente

```sql
<>
```

ou, em muitos bancos:

```sql
!=
```

## Maior

```sql
>
```

## Menor

```sql
<
```

## Maior ou igual

```sql
>=
```

## Menor ou igual

```sql
<=
```

Exemplo:

```sql
SELECT *
FROM produtos
WHERE preco >= 100;
```

---

# 12. AND, OR e NOT

## AND

Todas as condições precisam ser verdadeiras.

```sql
SELECT *
FROM produtos
WHERE preco > 50
AND estoque > 0;
```

## OR

Pelo menos uma condição precisa ser verdadeira.

```sql
SELECT *
FROM clientes
WHERE cidade = 'Caxias do Sul'
OR cidade = 'Farroupilha';
```

## NOT

Inverte a condição.

```sql
SELECT *
FROM clientes
WHERE NOT cidade = 'Caxias do Sul';
```

---

# 13. ORDER BY

Ordenar resultados.

Do menor para o maior:

```sql
SELECT *
FROM produtos
ORDER BY preco ASC;
```

Do maior para o menor:

```sql
SELECT *
FROM produtos
ORDER BY preco DESC;
```

Também pode ordenar por texto:

```sql
SELECT *
FROM clientes
ORDER BY nome ASC;
```

---

# 14. LIMIT

Limitar resultados:

```sql
SELECT *
FROM produtos
LIMIT 5;
```

Os cinco produtos mais caros:

```sql
SELECT *
FROM produtos
ORDER BY preco DESC
LIMIT 5;
```

No SQL Server, a sintaxe costuma ser diferente, usando `TOP` ou `OFFSET/FETCH`.

---

# 15. DISTINCT

Remove resultados repetidos.

```sql
SELECT DISTINCT cidade
FROM clientes;
```

---

# 16. LIKE

Usado para buscas em texto.

Nomes que começam com A:

```sql
SELECT *
FROM clientes
WHERE nome LIKE 'A%';
```

Nomes que terminam com A:

```sql
WHERE nome LIKE '%a';
```

Nomes que contêm `mar`:

```sql
WHERE nome LIKE '%mar%';
```

O `%` significa:

> qualquer quantidade de caracteres.

---

# 17. IN

Evita vários `OR`.

Em vez de:

```sql
WHERE cidade = 'Caxias do Sul'
OR cidade = 'Farroupilha'
OR cidade = 'Flores da Cunha'
```

Use:

```sql
WHERE cidade IN (
    'Caxias do Sul',
    'Farroupilha',
    'Flores da Cunha'
);
```

---

# 18. BETWEEN

Buscar intervalo:

```sql
SELECT *
FROM produtos
WHERE preco BETWEEN 50 AND 200;
```

Datas:

```sql
SELECT *
FROM pedidos
WHERE data_pedido BETWEEN '2026-09-01' AND '2026-09-30';
```

---

# 19. NULL

`NULL` significa ausência de valor.

Não use:

```sql
email = NULL
```

Use:

```sql
email IS NULL
```

Ou:

```sql
email IS NOT NULL
```

---

# 20. UPDATE

Atualizar dados:

```sql
UPDATE clientes
SET cidade = 'Farroupilha'
WHERE id = 2;
```

Atualizar várias colunas:

```sql
UPDATE produtos
SET preco = 99.90,
    estoque = 20
WHERE id = 5;
```

## ⚠️ Cuidado

Isto:

```sql
UPDATE clientes
SET cidade = 'Caxias do Sul';
```

altera **todos os clientes**.

Antes de executar um `UPDATE`, é uma boa prática testar o `WHERE`:

```sql
SELECT *
FROM clientes
WHERE id = 2;
```

Se retornar exatamente o registro esperado, faça o update.

---

# 21. DELETE

Excluir um registro:

```sql
DELETE FROM clientes
WHERE id = 3;
```

## ⚠️ Muito cuidado

Isto:

```sql
DELETE FROM clientes;
```

apaga todos os registros da tabela.

Antes:

```sql
SELECT *
FROM clientes
WHERE id = 3;
```

Depois:

```sql
DELETE FROM clientes
WHERE id = 3;
```

---

# 22. ALTER TABLE

Modificar uma tabela existente.

Adicionar coluna:

```sql
ALTER TABLE clientes
ADD telefone VARCHAR(20);
```

Em alguns bancos, alterar tipo de coluna:

```sql
ALTER TABLE clientes
ALTER COLUMN nome TYPE VARCHAR(200);
```

A sintaxe pode variar entre MySQL, PostgreSQL e SQLite.

---

# 23. DROP e TRUNCATE

## DROP

Remove a tabela inteira:

```sql
DROP TABLE clientes;
```

A estrutura também desaparece.

## TRUNCATE

Apaga todos os registros rapidamente:

```sql
TRUNCATE TABLE clientes;
```

A tabela continua existindo.

SQLite não possui `TRUNCATE`; normalmente usa-se:

```sql
DELETE FROM clientes;
```

---

# 24. Chaves primárias e estrangeiras

## PRIMARY KEY

Identifica um registro de maneira única.

```sql
id INTEGER PRIMARY KEY
```

Não deve haver dois registros com o mesmo ID.

## FOREIGN KEY

Relaciona uma tabela com outra.

Exemplo:

```sql
CREATE TABLE pedidos (
    id INTEGER PRIMARY KEY,
    cliente_id INTEGER,
    data_pedido DATE,

    FOREIGN KEY (cliente_id)
        REFERENCES clientes(id)
);
```

`cliente_id` aponta para:

```text
clientes.id
```

---

# 25. Relacionamentos

Existem três relacionamentos principais.

## Um para um — 1:1

Um usuário possui um perfil.

```text
usuario -> perfil
```

## Um para muitos — 1:N

Um cliente pode possuir vários pedidos.

```text
cliente -> pedidos
```

## Muitos para muitos — N:N

Um pedido pode ter vários produtos.

Um produto pode aparecer em vários pedidos.

Para isso criamos uma tabela intermediária:

```text
pedidos
   |
itens_pedido
   |
produtos
```

---

# 26. JOIN

`JOIN` serve para combinar dados de tabelas diferentes.

Exemplo:

Tabela `clientes`:

| id | nome |
|---|---|
| 1 | Ana |
| 2 | João |

Tabela `pedidos`:

| id | cliente_id | total |
|---|---|---|
| 1 | 1 | 150 |
| 2 | 1 | 80 |
| 3 | 2 | 200 |

Queremos:

| cliente | pedido | total |
|---|---|---|
| Ana | 1 | 150 |
| Ana | 2 | 80 |
| João | 3 | 200 |

Isso é feito com `JOIN`.

---

# 27. INNER JOIN

Retorna somente registros que possuem correspondência.

```sql
SELECT
    clientes.nome,
    pedidos.id,
    pedidos.total
FROM pedidos
INNER JOIN clientes
    ON pedidos.cliente_id = clientes.id;
```

Com aliases:

```sql
SELECT
    c.nome,
    p.id,
    p.total
FROM pedidos AS p
INNER JOIN clientes AS c
    ON p.cliente_id = c.id;
```

---

# 28. LEFT JOIN

Retorna todos os registros da tabela da esquerda, mesmo quando não existe correspondência.

```sql
SELECT
    c.nome,
    p.id
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id;
```

Isso é ótimo para descobrir clientes que nunca fizeram pedidos.

```sql
SELECT
    c.*
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id
WHERE p.id IS NULL;
```

---

# 29. RIGHT JOIN e FULL JOIN

## RIGHT JOIN

Semelhante ao `LEFT JOIN`, mas prioriza a tabela da direita.

```sql
SELECT *
FROM clientes c
RIGHT JOIN pedidos p
    ON p.cliente_id = c.id;
```

SQLite não possui `RIGHT JOIN` em versões antigas.

## FULL JOIN

Retorna todos os registros dos dois lados.

```sql
SELECT *
FROM tabela_a a
FULL OUTER JOIN tabela_b b
    ON a.id = b.id;
```

MySQL não possui `FULL OUTER JOIN` diretamente.

---

# 30. Funções de agregação

Funções de agregação calculam valores sobre vários registros.

## COUNT

Quantidade:

```sql
SELECT COUNT(*)
FROM clientes;
```

## SUM

Soma:

```sql
SELECT SUM(total)
FROM pedidos;
```

## AVG

Média:

```sql
SELECT AVG(preco)
FROM produtos;
```

## MIN

Menor valor:

```sql
SELECT MIN(preco)
FROM produtos;
```

## MAX

Maior valor:

```sql
SELECT MAX(preco)
FROM produtos;
```

---

# 31. GROUP BY

Agrupa registros.

Quantidade de clientes por cidade:

```sql
SELECT
    cidade,
    COUNT(*) AS quantidade
FROM clientes
GROUP BY cidade;
```

Total vendido por cliente:

```sql
SELECT
    cliente_id,
    SUM(total) AS total_comprado
FROM pedidos
GROUP BY cliente_id;
```

Com `JOIN`:

```sql
SELECT
    c.nome,
    SUM(p.total) AS total_comprado
FROM clientes c
INNER JOIN pedidos p
    ON p.cliente_id = c.id
GROUP BY c.id, c.nome;
```

---

# 32. HAVING

`WHERE` filtra registros antes do agrupamento.

`HAVING` filtra grupos depois do `GROUP BY`.

Clientes que gastaram mais de R$ 500:

```sql
SELECT
    cliente_id,
    SUM(total) AS total_gasto
FROM pedidos
GROUP BY cliente_id
HAVING SUM(total) > 500;
```

---

# 33. Aliases com AS

Renomeiam colunas ou tabelas temporariamente.

```sql
SELECT
    nome AS cliente,
    cidade AS municipio
FROM clientes;
```

Tabela:

```sql
SELECT c.nome
FROM clientes AS c;
```

---

# 34. CASE

Funciona como `if/else`.

```sql
SELECT
    nome,
    preco,
    CASE
        WHEN preco < 50 THEN 'Barato'
        WHEN preco <= 200 THEN 'Intermediário'
        ELSE 'Caro'
    END AS faixa_preco
FROM produtos;
```

Outro exemplo:

```sql
SELECT
    nome,
    estoque,
    CASE
        WHEN estoque = 0 THEN 'Sem estoque'
        WHEN estoque <= 5 THEN 'Estoque baixo'
        ELSE 'Disponível'
    END AS situacao
FROM produtos;
```

---

# 35. Funções de texto

A disponibilidade pode variar entre bancos.

## UPPER

```sql
SELECT UPPER(nome)
FROM clientes;
```

## LOWER

```sql
SELECT LOWER(email)
FROM clientes;
```

## LENGTH

```sql
SELECT LENGTH(nome)
FROM clientes;
```

## CONCAT

MySQL/PostgreSQL:

```sql
SELECT CONCAT(nome, ' - ', cidade)
FROM clientes;
```

SQLite também permite:

```sql
SELECT nome || ' - ' || cidade
FROM clientes;
```

## TRIM

Remove espaços extras:

```sql
SELECT TRIM(nome)
FROM clientes;
```

---

# 36. Funções matemáticas

Exemplo:

```sql
SELECT
    preco,
    preco * 1.10 AS preco_com_reajuste
FROM produtos;
```

Desconto:

```sql
SELECT
    preco,
    preco * 0.90 AS preco_com_desconto
FROM produtos;
```

Arredondamento:

```sql
SELECT ROUND(19.987, 2);
```

Resultado:

```text
19.99
```

---

# 37. Datas e horários

Datas são uma das partes que mais variam entre bancos.

## Data atual

MySQL:

```sql
SELECT CURDATE();
```

PostgreSQL:

```sql
SELECT CURRENT_DATE;
```

SQLite:

```sql
SELECT DATE('now');
```

## Data e hora atual

Padrão comum:

```sql
SELECT CURRENT_TIMESTAMP;
```

## Filtrar por data

```sql
SELECT *
FROM pedidos
WHERE data_pedido >= '2026-09-01';
```

---

# 38. Subqueries

Uma subquery é uma consulta dentro de outra.

Produtos mais caros que a média:

```sql
SELECT *
FROM produtos
WHERE preco > (
    SELECT AVG(preco)
    FROM produtos
);
```

Clientes que fizeram pedidos:

```sql
SELECT *
FROM clientes
WHERE id IN (
    SELECT cliente_id
    FROM pedidos
);
```

---

# 39. EXISTS

Verifica se uma subquery retorna algum registro.

```sql
SELECT *
FROM clientes c
WHERE EXISTS (
    SELECT 1
    FROM pedidos p
    WHERE p.cliente_id = c.id
);
```

Clientes sem pedidos:

```sql
SELECT *
FROM clientes c
WHERE NOT EXISTS (
    SELECT 1
    FROM pedidos p
    WHERE p.cliente_id = c.id
);
```

---

# 40. CTEs com WITH

CTE significa:

**Common Table Expression**

Ajuda a deixar consultas complexas mais legíveis.

```sql
WITH vendas_por_cliente AS (
    SELECT
        cliente_id,
        SUM(total) AS total_gasto
    FROM pedidos
    GROUP BY cliente_id
)
SELECT *
FROM vendas_por_cliente
WHERE total_gasto > 500;
```

Com `JOIN`:

```sql
WITH vendas_por_cliente AS (
    SELECT
        cliente_id,
        SUM(total) AS total_gasto
    FROM pedidos
    GROUP BY cliente_id
)
SELECT
    c.nome,
    v.total_gasto
FROM vendas_por_cliente v
INNER JOIN clientes c
    ON c.id = v.cliente_id;
```

---

# 41. UNION e UNION ALL

Juntam resultados de duas consultas.

```sql
SELECT nome, email
FROM clientes

UNION

SELECT nome, email
FROM fornecedores;
```

`UNION` remove duplicados.

`UNION ALL` mantém duplicados.

```sql
SELECT nome
FROM clientes

UNION ALL

SELECT nome
FROM fornecedores;
```

---

# 42. Views

Uma `VIEW` é uma consulta salva.

```sql
CREATE VIEW vw_vendas_clientes AS
SELECT
    c.nome,
    p.id AS pedido,
    p.total
FROM pedidos p
INNER JOIN clientes c
    ON c.id = p.cliente_id;
```

Depois:

```sql
SELECT *
FROM vw_vendas_clientes;
```

Uma view não é simplesmente uma nova cópia dos dados. Em geral, ela representa uma consulta armazenada.

---

# 43. Índices

Índices ajudam o banco a encontrar dados mais rápido.

Exemplo:

```sql
CREATE INDEX idx_clientes_email
ON clientes(email);
```

Outro:

```sql
CREATE INDEX idx_pedidos_cliente
ON pedidos(cliente_id);
```

## Quando índices ajudam?

Principalmente em colunas usadas frequentemente em:

- `WHERE`;
- `JOIN`;
- `ORDER BY`;
- buscas por identificadores.

## Quando índices podem atrapalhar?

Cada índice ocupa espaço e precisa ser atualizado em operações de:

- `INSERT`;
- `UPDATE`;
- `DELETE`.

Não crie índice em tudo sem necessidade.

---

# 44. Constraints

Constraints são regras impostas pelo banco.

## NOT NULL

Campo obrigatório:

```sql
nome VARCHAR(100) NOT NULL
```

## UNIQUE

Valor não pode repetir:

```sql
email VARCHAR(150) UNIQUE
```

## CHECK

Cria uma regra:

```sql
preco DECIMAL(10,2) CHECK (preco >= 0)
```

## DEFAULT

Valor padrão:

```sql
ativo BOOLEAN DEFAULT TRUE
```

## PRIMARY KEY

```sql
id INTEGER PRIMARY KEY
```

## FOREIGN KEY

```sql
FOREIGN KEY (cliente_id)
REFERENCES clientes(id)
```

---

# 45. Transações

Transações permitem executar várias operações como uma unidade.

Exemplo:

```sql
BEGIN;
```

Atualização 1:

```sql
UPDATE contas
SET saldo = saldo - 100
WHERE id = 1;
```

Atualização 2:

```sql
UPDATE contas
SET saldo = saldo + 100
WHERE id = 2;
```

Se tudo der certo:

```sql
COMMIT;
```

Se algo der errado:

```sql
ROLLBACK;
```

Isso é essencial para operações financeiras e processos que não podem ficar pela metade.

## ACID

Transações são associadas a quatro propriedades:

### Atomicidade

Ou tudo acontece, ou nada acontece.

### Consistência

Os dados devem continuar válidos.

### Isolamento

Transações paralelas não devem causar resultados incorretos.

### Durabilidade

Depois do `COMMIT`, a alteração deve persistir.

---

# 46. Normalização

Normalização é uma forma de organizar dados para reduzir repetição.

## Exemplo ruim

```text
pedido_id
cliente_nome
cliente_email
produto_1
produto_2
produto_3
```

Problemas:

- quantidade fixa de produtos;
- repetição;
- atualização difícil;
- dados inconsistentes.

## Melhor

```text
clientes
produtos
pedidos
itens_pedido
```

Cada informação fica no local correto.

## 1ª Forma Normal

Evitar campos com múltiplos valores.

Ruim:

```text
telefones = "9999-1111,9999-2222"
```

Melhor:

Criar tabela de telefones.

## 2ª Forma Normal

Cada coluna deve depender da chave completa da tabela.

## 3ª Forma Normal

Evitar dependências indiretas entre colunas.

Na prática, para começar:

> Evite duplicar a mesma informação em várias tabelas sem necessidade.

---

# 47. Modelagem de banco

Antes de programar, desenhe as entidades.

Exemplo de loja:

```text
CLIENTES
- id
- nome
- email

PRODUTOS
- id
- nome
- preco
- estoque

PEDIDOS
- id
- cliente_id
- data_pedido
- status

ITENS_PEDIDO
- id
- pedido_id
- produto_id
- quantidade
- preco_unitario
```

Relacionamentos:

```text
CLIENTES
   |
   | 1:N
   |
PEDIDOS
   |
   | 1:N
   |
ITENS_PEDIDO
   |
   | N:1
   |
PRODUTOS
```

---

# 48. Boas práticas

## 1. Use nomes claros

Bom:

```text
cliente_id
data_pedido
preco_unitario
```

Ruim:

```text
cli
dt
x1
```

## 2. Seja consistente

Escolha um padrão:

```text
snake_case
```

Exemplo:

```text
data_criacao
cliente_id
valor_total
```

## 3. Use chaves primárias

Toda tabela principal deve ter uma forma clara de identificar seus registros.

## 4. Use foreign keys

Elas ajudam a impedir relacionamentos inválidos.

## 5. Não use `SELECT *` em tudo

Durante aprendizado é útil:

```sql
SELECT *
FROM clientes;
```

Em aplicações reais, prefira:

```sql
SELECT id, nome, email
FROM clientes;
```

## 6. Sempre revise UPDATE e DELETE

Antes:

```sql
SELECT *
FROM clientes
WHERE id = 10;
```

Depois:

```sql
DELETE FROM clientes
WHERE id = 10;
```

## 7. Use transações quando necessário

Principalmente quando várias alterações dependem umas das outras.

---

# 49. Segurança e SQL Injection

Nunca monte SQL diretamente usando valores enviados pelo usuário.

## Exemplo perigoso em PHP

```php
$sql = "SELECT * FROM usuarios
        WHERE email = '$email'
        AND senha = '$senha'";
```

Isso pode permitir SQL Injection.

## Use prepared statements

Exemplo com PDO:

```php
$stmt = $pdo->prepare(
    "SELECT * FROM usuarios
     WHERE email = :email"
);

$stmt->execute([
    ':email' => $email
]);
```

## Senhas

Nunca salve senha em texto puro.

Use:

```php
password_hash()
```

e:

```php
password_verify()
```

SQL armazena o hash.

A validação da senha normalmente acontece na aplicação.

---

# 50. Diferenças entre MySQL, PostgreSQL e SQLite

## MySQL

Muito comum com PHP.

Auto incremento:

```sql
id INT AUTO_INCREMENT PRIMARY KEY
```

## PostgreSQL

Exemplo moderno:

```sql
id INTEGER GENERATED ALWAYS AS IDENTITY PRIMARY KEY
```

Também é comum encontrar:

```sql
SERIAL
```

em projetos antigos.

## SQLite

```sql
id INTEGER PRIMARY KEY AUTOINCREMENT
```

## Concatenação

MySQL:

```sql
CONCAT(nome, ' ', sobrenome)
```

PostgreSQL/SQLite:

```sql
nome || ' ' || sobrenome
```

## Boolean

PostgreSQL:

```text
TRUE / FALSE
```

SQLite normalmente armazena como:

```text
1 / 0
```

## Datas

Funções de data variam bastante.

Sempre consulte a documentação do banco específico quando entrar em recursos de data mais avançados.

---

# 51. Banco completo para praticar

A partir daqui vamos montar um pequeno sistema de loja.

## Tabela clientes

```sql
CREATE TABLE clientes (
    id INTEGER PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(150) UNIQUE,
    cidade VARCHAR(100),
    criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Tabela produtos

```sql
CREATE TABLE produtos (
    id INTEGER PRIMARY KEY,
    nome VARCHAR(120) NOT NULL,
    preco DECIMAL(10,2) NOT NULL,
    estoque INTEGER NOT NULL DEFAULT 0
);
```

## Tabela pedidos

```sql
CREATE TABLE pedidos (
    id INTEGER PRIMARY KEY,
    cliente_id INTEGER NOT NULL,
    data_pedido DATE NOT NULL,
    status VARCHAR(30) DEFAULT 'pendente',

    FOREIGN KEY (cliente_id)
        REFERENCES clientes(id)
);
```

## Tabela itens_pedido

```sql
CREATE TABLE itens_pedido (
    id INTEGER PRIMARY KEY,
    pedido_id INTEGER NOT NULL,
    produto_id INTEGER NOT NULL,
    quantidade INTEGER NOT NULL,
    preco_unitario DECIMAL(10,2) NOT NULL,

    FOREIGN KEY (pedido_id)
        REFERENCES pedidos(id),

    FOREIGN KEY (produto_id)
        REFERENCES produtos(id)
);
```

---

## Inserindo clientes

```sql
INSERT INTO clientes (id, nome, email, cidade)
VALUES
(1, 'Ana Souza', 'ana@email.com', 'Caxias do Sul'),
(2, 'João Silva', 'joao@email.com', 'Porto Alegre'),
(3, 'Maria Lima', 'maria@email.com', 'Caxias do Sul'),
(4, 'Carlos Alves', 'carlos@email.com', 'Farroupilha');
```

## Inserindo produtos

```sql
INSERT INTO produtos (id, nome, preco, estoque)
VALUES
(1, 'Teclado', 120.00, 15),
(2, 'Mouse', 80.00, 30),
(3, 'Monitor', 899.90, 8),
(4, 'Headset', 250.00, 12),
(5, 'Webcam', 199.90, 0);
```

## Inserindo pedidos

```sql
INSERT INTO pedidos (id, cliente_id, data_pedido, status)
VALUES
(1, 1, '2026-09-01', 'pago'),
(2, 1, '2026-09-03', 'pendente'),
(3, 2, '2026-09-04', 'pago'),
(4, 3, '2026-09-05', 'enviado');
```

## Inserindo itens

```sql
INSERT INTO itens_pedido
(id, pedido_id, produto_id, quantidade, preco_unitario)
VALUES
(1, 1, 1, 1, 120.00),
(2, 1, 2, 2, 80.00),
(3, 2, 3, 1, 899.90),
(4, 3, 4, 1, 250.00),
(5, 4, 2, 1, 80.00),
(6, 4, 1, 1, 120.00);
```

---

# 52. Consultas práticas

## Listar clientes

```sql
SELECT *
FROM clientes;
```

## Listar produtos disponíveis

```sql
SELECT *
FROM produtos
WHERE estoque > 0;
```

## Produtos sem estoque

```sql
SELECT *
FROM produtos
WHERE estoque = 0;
```

## Produtos acima de R$ 200

```sql
SELECT nome, preco
FROM produtos
WHERE preco > 200
ORDER BY preco DESC;
```

## Buscar cliente por nome

```sql
SELECT *
FROM clientes
WHERE nome LIKE '%Ana%';
```

## Pedidos com nome do cliente

```sql
SELECT
    p.id AS pedido,
    c.nome AS cliente,
    p.data_pedido,
    p.status
FROM pedidos p
INNER JOIN clientes c
    ON c.id = p.cliente_id;
```

## Itens de cada pedido

```sql
SELECT
    ip.pedido_id,
    pr.nome AS produto,
    ip.quantidade,
    ip.preco_unitario
FROM itens_pedido ip
INNER JOIN produtos pr
    ON pr.id = ip.produto_id;
```

## Total por item

```sql
SELECT
    pedido_id,
    produto_id,
    quantidade,
    preco_unitario,
    quantidade * preco_unitario AS subtotal
FROM itens_pedido;
```

## Total de cada pedido

```sql
SELECT
    pedido_id,
    SUM(quantidade * preco_unitario) AS total
FROM itens_pedido
GROUP BY pedido_id;
```

## Total de pedidos por cliente

```sql
SELECT
    c.nome,
    COUNT(p.id) AS quantidade_pedidos
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id
GROUP BY c.id, c.nome;
```

## Total gasto por cliente

```sql
SELECT
    c.nome,
    SUM(ip.quantidade * ip.preco_unitario) AS total_gasto
FROM clientes c
INNER JOIN pedidos p
    ON p.cliente_id = c.id
INNER JOIN itens_pedido ip
    ON ip.pedido_id = p.id
GROUP BY c.id, c.nome
ORDER BY total_gasto DESC;
```

## Cliente que mais gastou

```sql
SELECT
    c.nome,
    SUM(ip.quantidade * ip.preco_unitario) AS total_gasto
FROM clientes c
INNER JOIN pedidos p
    ON p.cliente_id = c.id
INNER JOIN itens_pedido ip
    ON ip.pedido_id = p.id
GROUP BY c.id, c.nome
ORDER BY total_gasto DESC
LIMIT 1;
```

## Produto mais vendido

```sql
SELECT
    pr.nome,
    SUM(ip.quantidade) AS quantidade_vendida
FROM itens_pedido ip
INNER JOIN produtos pr
    ON pr.id = ip.produto_id
GROUP BY pr.id, pr.nome
ORDER BY quantidade_vendida DESC
LIMIT 1;
```

## Clientes que nunca compraram

```sql
SELECT
    c.*
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id
WHERE p.id IS NULL;
```

## Ticket médio

```sql
WITH totais AS (
    SELECT
        pedido_id,
        SUM(quantidade * preco_unitario) AS total
    FROM itens_pedido
    GROUP BY pedido_id
)
SELECT AVG(total) AS ticket_medio
FROM totais;
```

---

# 53. Exercícios

Tente resolver sem olhar a resposta.

---

## Nível 1 — Básico

### Exercício 1

Liste todos os produtos.

### Exercício 2

Liste somente:

- nome;
- preço.

### Exercício 3

Liste produtos com preço maior que R$ 100.

### Exercício 4

Liste clientes de Caxias do Sul.

### Exercício 5

Liste produtos do mais caro para o mais barato.

### Exercício 6

Liste apenas três produtos.

### Exercício 7

Liste as cidades sem repetir.

---

## Respostas — Nível 1

```sql
SELECT * FROM produtos;
```

```sql
SELECT nome, preco
FROM produtos;
```

```sql
SELECT *
FROM produtos
WHERE preco > 100;
```

```sql
SELECT *
FROM clientes
WHERE cidade = 'Caxias do Sul';
```

```sql
SELECT *
FROM produtos
ORDER BY preco DESC;
```

```sql
SELECT *
FROM produtos
LIMIT 3;
```

```sql
SELECT DISTINCT cidade
FROM clientes;
```

---

## Nível 2 — Intermediário

### Exercício 8

Liste todos os pedidos com o nome do cliente.

### Exercício 9

Mostre quantos pedidos cada cliente fez.

### Exercício 10

Mostre o total de cada pedido.

### Exercício 11

Mostre clientes sem pedido.

### Exercício 12

Mostre produtos com estoque entre 1 e 15.

### Exercício 13

Mostre produtos cujo nome contenha a letra `o`.

### Exercício 14

Crie uma coluna calculada chamada `situacao`:

- `Sem estoque` quando estoque for 0;
- `Estoque baixo` quando estoque for até 5;
- `Disponível` nos demais casos.

---

## Respostas — Nível 2

```sql
SELECT
    p.id,
    c.nome,
    p.data_pedido,
    p.status
FROM pedidos p
INNER JOIN clientes c
    ON c.id = p.cliente_id;
```

```sql
SELECT
    c.nome,
    COUNT(p.id) AS total_pedidos
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id
GROUP BY c.id, c.nome;
```

```sql
SELECT
    pedido_id,
    SUM(quantidade * preco_unitario) AS total
FROM itens_pedido
GROUP BY pedido_id;
```

```sql
SELECT c.*
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id
WHERE p.id IS NULL;
```

```sql
SELECT *
FROM produtos
WHERE estoque BETWEEN 1 AND 15;
```

```sql
SELECT *
FROM produtos
WHERE nome LIKE '%o%';
```

```sql
SELECT
    nome,
    estoque,
    CASE
        WHEN estoque = 0 THEN 'Sem estoque'
        WHEN estoque <= 5 THEN 'Estoque baixo'
        ELSE 'Disponível'
    END AS situacao
FROM produtos;
```

---

## Nível 3 — Avançado

### Exercício 15

Descubra o cliente que mais gastou.

### Exercício 16

Descubra o produto mais vendido em quantidade.

### Exercício 17

Calcule o ticket médio dos pedidos.

### Exercício 18

Liste clientes que já fizeram pelo menos um pedido.

### Exercício 19

Liste clientes que gastaram mais de R$ 300.

### Exercício 20

Crie uma view que mostre:

- ID do pedido;
- cliente;
- data;
- status;
- total.

---

## Respostas — Nível 3

```sql
SELECT
    c.nome,
    SUM(ip.quantidade * ip.preco_unitario) AS total_gasto
FROM clientes c
INNER JOIN pedidos p
    ON p.cliente_id = c.id
INNER JOIN itens_pedido ip
    ON ip.pedido_id = p.id
GROUP BY c.id, c.nome
ORDER BY total_gasto DESC
LIMIT 1;
```

```sql
SELECT
    pr.nome,
    SUM(ip.quantidade) AS quantidade_vendida
FROM produtos pr
INNER JOIN itens_pedido ip
    ON ip.produto_id = pr.id
GROUP BY pr.id, pr.nome
ORDER BY quantidade_vendida DESC
LIMIT 1;
```

```sql
WITH totais AS (
    SELECT
        pedido_id,
        SUM(quantidade * preco_unitario) AS total
    FROM itens_pedido
    GROUP BY pedido_id
)
SELECT AVG(total) AS ticket_medio
FROM totais;
```

```sql
SELECT *
FROM clientes c
WHERE EXISTS (
    SELECT 1
    FROM pedidos p
    WHERE p.cliente_id = c.id
);
```

```sql
SELECT
    c.nome,
    SUM(ip.quantidade * ip.preco_unitario) AS total_gasto
FROM clientes c
INNER JOIN pedidos p
    ON p.cliente_id = c.id
INNER JOIN itens_pedido ip
    ON ip.pedido_id = p.id
GROUP BY c.id, c.nome
HAVING SUM(ip.quantidade * ip.preco_unitario) > 300;
```

```sql
CREATE VIEW vw_resumo_pedidos AS
SELECT
    p.id AS pedido_id,
    c.nome AS cliente,
    p.data_pedido,
    p.status,
    SUM(ip.quantidade * ip.preco_unitario) AS total
FROM pedidos p
INNER JOIN clientes c
    ON c.id = p.cliente_id
INNER JOIN itens_pedido ip
    ON ip.pedido_id = p.id
GROUP BY
    p.id,
    c.nome,
    p.data_pedido,
    p.status;
```

---

# 54. Projeto final

Agora você vai montar um sistema simples de vendas.

## Requisitos

Crie as tabelas:

```text
usuarios
categorias
produtos
clientes
pedidos
itens_pedido
pagamentos
```

## Usuários

Campos:

```text
id
nome
email
senha_hash
ativo
criado_em
```

## Categorias

```text
id
nome
```

## Produtos

```text
id
categoria_id
nome
descricao
preco
estoque
ativo
```

## Clientes

```text
id
nome
email
telefone
cidade
```

## Pedidos

```text
id
cliente_id
data_pedido
status
```

## Itens do pedido

```text
id
pedido_id
produto_id
quantidade
preco_unitario
```

## Pagamentos

```text
id
pedido_id
forma_pagamento
valor
status
pago_em
```

---

## Consultas que o projeto deve responder

1. Quantos clientes existem?
2. Quantos produtos estão ativos?
3. Quais produtos estão sem estoque?
4. Qual produto é o mais caro?
5. Qual produto é o mais vendido?
6. Qual cliente fez mais pedidos?
7. Qual cliente mais gastou?
8. Quanto foi vendido em determinado mês?
9. Qual foi o ticket médio?
10. Quantos pedidos existem por status?
11. Quais clientes nunca compraram?
12. Quais categorias geraram mais faturamento?
13. Quais produtos possuem estoque baixo?
14. Quantos pedidos foram pagos?
15. Qual forma de pagamento é mais usada?

Se você conseguir montar o banco e responder essas perguntas sem copiar as consultas deste material, já terá uma base muito boa de SQL.

---

# 55. Cheat Sheet

## Criar tabela

```sql
CREATE TABLE tabela (
    id INTEGER PRIMARY KEY,
    nome VARCHAR(100)
);
```

## Inserir

```sql
INSERT INTO tabela (nome)
VALUES ('Valor');
```

## Consultar

```sql
SELECT *
FROM tabela;
```

## Filtrar

```sql
SELECT *
FROM tabela
WHERE id = 1;
```

## Ordenar

```sql
SELECT *
FROM tabela
ORDER BY nome ASC;
```

## Limitar

```sql
SELECT *
FROM tabela
LIMIT 10;
```

## Atualizar

```sql
UPDATE tabela
SET nome = 'Novo nome'
WHERE id = 1;
```

## Excluir

```sql
DELETE FROM tabela
WHERE id = 1;
```

## Contar

```sql
SELECT COUNT(*)
FROM tabela;
```

## Somar

```sql
SELECT SUM(valor)
FROM tabela;
```

## Média

```sql
SELECT AVG(valor)
FROM tabela;
```

## Agrupar

```sql
SELECT categoria_id, COUNT(*)
FROM produtos
GROUP BY categoria_id;
```

## JOIN

```sql
SELECT *
FROM pedidos p
INNER JOIN clientes c
    ON c.id = p.cliente_id;
```

## LEFT JOIN

```sql
SELECT *
FROM clientes c
LEFT JOIN pedidos p
    ON p.cliente_id = c.id;
```

## Subquery

```sql
SELECT *
FROM produtos
WHERE preco > (
    SELECT AVG(preco)
    FROM produtos
);
```

## CTE

```sql
WITH dados AS (
    SELECT *
    FROM tabela
)
SELECT *
FROM dados;
```

## Criar índice

```sql
CREATE INDEX idx_nome
ON tabela(nome);
```

## Criar view

```sql
CREATE VIEW minha_view AS
SELECT *
FROM tabela;
```

## Transação

```sql
BEGIN;

UPDATE tabela
SET valor = 100
WHERE id = 1;

COMMIT;
```

Ou:

```sql
ROLLBACK;
```

---

# 56. Próximos passos

Depois de dominar este conteúdo, estude:

- modelagem relacional avançada;
- PostgreSQL ou MySQL em profundidade;
- window functions;
- procedures;
- functions;
- triggers;
- recursive CTE;
- JSON dentro do banco;
- análise de plano de execução;
- otimização de queries;
- índices compostos;
- locks;
- níveis de isolamento;
- backup e restore;
- permissões de usuários;
- replicação;
- bancos distribuídos;
- ORMs;
- integração com PHP, Node.js, Python ou Java.

---

# Bônus — Window Functions

Este assunto já é mais avançado, mas vale conhecer.

## ROW_NUMBER

Numera registros:

```sql
SELECT
    nome,
    preco,
    ROW_NUMBER() OVER (
        ORDER BY preco DESC
    ) AS posicao
FROM produtos;
```

## RANK

Cria ranking:

```sql
SELECT
    nome,
    preco,
    RANK() OVER (
        ORDER BY preco DESC
    ) AS ranking
FROM produtos;
```

## SUM OVER

Total acumulado:

```sql
SELECT
    id,
    total,
    SUM(total) OVER (
        ORDER BY id
    ) AS acumulado
FROM pedidos;
```

Window functions são extremamente úteis em relatórios e análises.

---

# Bônus — Índices compostos

Um índice pode usar mais de uma coluna.

```sql
CREATE INDEX idx_pedidos_cliente_data
ON pedidos(cliente_id, data_pedido);
```

Pode ajudar consultas como:

```sql
SELECT *
FROM pedidos
WHERE cliente_id = 10
AND data_pedido >= '2026-01-01';
```

A ordem das colunas do índice importa.

---

# Bônus — EXPLAIN

Bancos profissionais permitem analisar como uma consulta será executada.

```sql
EXPLAIN
SELECT *
FROM pedidos
WHERE cliente_id = 10;
```

PostgreSQL também permite:

```sql
EXPLAIN ANALYZE
SELECT *
FROM pedidos
WHERE cliente_id = 10;
```

Isso ajuda a descobrir:

- scans completos;
- uso de índices;
- joins custosos;
- gargalos de performance.

---

# Bônus — Trigger

Um trigger executa automaticamente uma ação quando algo acontece.

Exemplo conceitual:

```sql
CREATE TRIGGER atualizar_estoque
AFTER INSERT ON itens_pedido
FOR EACH ROW
BEGIN
    UPDATE produtos
    SET estoque = estoque - NEW.quantidade
    WHERE id = NEW.produto_id;
END;
```

A sintaxe de triggers varia bastante entre bancos.

Use triggers com cuidado. Uma lógica automática escondida no banco pode tornar sistemas mais difíceis de entender se for usada em excesso.

---

# Bônus — Procedure

Procedures são rotinas armazenadas no banco.

Exemplo conceitual:

```sql
CALL fechar_pedido(10);
```

São úteis em alguns sistemas empresariais, mas a sintaxe e o uso variam bastante entre bancos.

---

# Bônus — Como ler uma consulta grande

Nunca tente entender tudo de uma vez.

Leia nesta ordem:

1. `FROM`
2. `JOIN`
3. `WHERE`
4. `GROUP BY`
5. `HAVING`
6. `SELECT`
7. `ORDER BY`
8. `LIMIT`

Exemplo:

```sql
SELECT
    c.nome,
    SUM(ip.quantidade * ip.preco_unitario) AS total
FROM clientes c
INNER JOIN pedidos p
    ON p.cliente_id = c.id
INNER JOIN itens_pedido ip
    ON ip.pedido_id = p.id
WHERE p.status = 'pago'
GROUP BY c.id, c.nome
HAVING SUM(ip.quantidade * ip.preco_unitario) > 500
ORDER BY total DESC
LIMIT 10;
```

Interpretação:

1. Pegue `clientes`;
2. relacione com `pedidos`;
3. relacione com `itens_pedido`;
4. mantenha apenas pedidos pagos;
5. agrupe por cliente;
6. calcule o total;
7. mantenha clientes com total acima de 500;
8. ordene do maior para o menor;
9. retorne os 10 primeiros.

---

# Bônus — Ordem lógica de execução do SELECT

Embora você escreva:

```sql
SELECT
FROM
WHERE
GROUP BY
HAVING
ORDER BY
LIMIT
```

conceitualmente o banco processa aproximadamente:

```text
FROM
JOIN
WHERE
GROUP BY
HAVING
SELECT
DISTINCT
ORDER BY
LIMIT
```

Entender isso ajuda muito quando as consultas ficam mais complexas.

---

# Erros comuns de quem está começando

## Esquecer aspas em texto

Errado:

```sql
WHERE cidade = Caxias do Sul
```

Certo:

```sql
WHERE cidade = 'Caxias do Sul'
```

## Usar `= NULL`

Errado:

```sql
WHERE email = NULL
```

Certo:

```sql
WHERE email IS NULL
```

## Esquecer o WHERE

Perigoso:

```sql
DELETE FROM clientes;
```

## Confundir WHERE e HAVING

`WHERE`:

```sql
WHERE preco > 100
```

`HAVING`:

```sql
HAVING COUNT(*) > 5
```

## Fazer JOIN sem condição correta

Errado:

```sql
SELECT *
FROM clientes
JOIN pedidos;
```

Isso pode gerar combinações indesejadas.

Certo:

```sql
SELECT *
FROM clientes c
JOIN pedidos p
    ON p.cliente_id = c.id;
```

## Guardar tudo em uma única tabela

É comum iniciantes criarem tabelas gigantes.

Aprenda a separar entidades.

---

# Checklist de domínio

Marque quando conseguir fazer sem consultar.

## Básico

- [ ] Sei explicar o que é banco de dados.
- [ ] Sei explicar o que é tabela.
- [ ] Sei criar uma tabela.
- [ ] Sei inserir dados.
- [ ] Sei usar SELECT.
- [ ] Sei usar WHERE.
- [ ] Sei usar ORDER BY.
- [ ] Sei usar LIMIT.
- [ ] Sei atualizar dados.
- [ ] Sei excluir dados.

## Intermediário

- [ ] Sei usar PRIMARY KEY.
- [ ] Sei usar FOREIGN KEY.
- [ ] Sei criar relacionamentos.
- [ ] Sei usar INNER JOIN.
- [ ] Sei usar LEFT JOIN.
- [ ] Sei usar COUNT.
- [ ] Sei usar SUM.
- [ ] Sei usar AVG.
- [ ] Sei usar GROUP BY.
- [ ] Sei usar HAVING.
- [ ] Sei usar CASE.
- [ ] Sei usar subquery.

## Avançado

- [ ] Sei usar CTE.
- [ ] Sei criar VIEW.
- [ ] Sei criar índices.
- [ ] Entendo transações.
- [ ] Entendo normalização.
- [ ] Sei modelar um banco simples.
- [ ] Entendo SQL Injection.
- [ ] Sei interpretar EXPLAIN.
- [ ] Conheço window functions.
- [ ] Consigo criar relatórios com várias tabelas.

---

# Como estudar este curso

A melhor forma de aprender SQL é escrevendo SQL.

Sugestão:

### Etapa 1

Estude do capítulo 1 ao 21.

Depois crie uma tabela sozinho e faça:

```text
INSERT
SELECT
WHERE
ORDER BY
UPDATE
DELETE
```

### Etapa 2

Estude relacionamentos e JOIN.

Crie pelo menos três tabelas relacionadas.

### Etapa 3

Estude:

```text
COUNT
SUM
AVG
GROUP BY
HAVING
```

Monte relatórios.

### Etapa 4

Estude:

```text
CASE
subqueries
CTEs
views
```

### Etapa 5

Faça o projeto final sem copiar.

---

# Regra de ouro

Quando você estiver diante de uma consulta difícil, transforme o problema em perguntas menores.

Em vez de pensar:

> "Como faço um relatório com os 10 clientes que mais gastaram em pedidos pagos no mês?"

Pense:

1. Como pego os pedidos pagos?
2. Como relaciono pedidos aos clientes?
3. Como relaciono pedidos aos itens?
4. Como calculo o total?
5. Como agrupo por cliente?
6. Como filtro o mês?
7. Como ordeno?
8. Como limito a 10?

SQL fica muito mais simples quando o problema é dividido em etapas.

---

# Conclusão

Se você chegou até aqui e praticou os exemplos, já conhece a base necessária para trabalhar com bancos relacionais em sistemas reais.

Você já deve conseguir:

- criar estruturas;
- cadastrar dados;
- consultar informações;
- filtrar resultados;
- atualizar registros;
- excluir dados;
- relacionar tabelas;
- criar relatórios;
- calcular totais;
- agrupar resultados;
- trabalhar com subqueries;
- usar CTEs;
- criar views;
- entender índices;
- usar transações;
- evitar SQL Injection;
- modelar bancos simples.

O próximo nível vem principalmente de prática.

Crie bancos.

Quebre consultas.

Corrija erros.

Refaça relatórios.

E, principalmente:

> não tente decorar SQL inteiro.

Aprenda a entender o problema e descobrir qual ferramenta SQL resolve cada parte.

---

## 🚀 Desafio final

Crie sozinho um banco para um dos sistemas abaixo:

- restaurante;
- delivery;
- estoque;
- agenda;
- rede social;
- e-commerce;
- CRM;
- biblioteca;
- escola;
- sistema financeiro.

Inclua no mínimo:

- 6 tabelas;
- chaves primárias;
- chaves estrangeiras;
- relacionamento 1:N;
- relacionamento N:N;
- 30 registros de teste;
- 10 consultas simples;
- 10 consultas com JOIN;
- 5 relatórios com GROUP BY;
- 3 subqueries;
- 2 CTEs;
- 1 view;
- 2 índices;
- 1 transação.

Se conseguir fazer isso sem depender de um tutorial passo a passo, você já deixou de ser iniciante em SQL.
