# Curso SQL Completo 2020 + Desafios + Muita Prática

## Aula 01 - `SELECT`

O comando `SELECT` no **SQL** é utilizado para recuperar dados de uma ou mais tabelas em um banco de dados. Ele é fundamental para consultas, pois permite a seleção de colunas específicas, a aplicação de condições, a ordenação e a agrupamento dos resultados.

```sql
SELECT 
-- SQL Server, Postgres, MariaDB, Oracle, mySQL...
---------------------------------------------

SELECT coluna1, coluna2, ...
FROM tabela
WHERE condição;

---------------------------------------------
SELECT coluna1, coluna2
FROM tabela;

---------------------------------------------

SELECT * 
FROM tabela;
```

## Aula 02 - `DISTINCT`

O comando no **SQL** é utilizado para retornar valores únicos de uma coluna em uma consulta. Ele elimina duplicatas, exibindo apenas valores distintos. Isso é útil quando você deseja identificar os diferentes valores presentes em uma determinada coluna de uma tabela. A sintaxe básica é a seguinte:

```sql
SELECT DISTINCT
FROM tabela;

```

Exemplo:

Suponha que você tenha uma tabela chamada cores com uma coluna chamada cor que armazena diferentes cores, incluindo duplicatas. Se você quiser obter uma lista de cores distintas, você usaria o DISTINCT da seguinte maneira:

```sql
SELECT DISTINCT cor
FROM cores;
```

Isso retornaria uma lista de cores únicas presentes na coluna cor da tabela cores, eliminando duplicatas.

Em resumo, o DISTINCT é útil sempre que você precisa de uma lista única de valores de uma determinada coluna em uma consulta SQL.

## Aula 03 - `WHERE`

```sql
OPERADOR    -    DESCRIÇÃO
=                IGUAL
>                MAIOR QUER
<                MENOR QUE
>=               MAIOR QUE OU IGUAL
<=               MENOR QUE OU IGUAL
<>               DIFERENTE DE
AND              OPERADOR LÓGICO E
OR               OPERADOR LÓGICO OU
```

O comando `WHERE` é usado em consultas **SQL** para filtrar os resultados de uma consulta, permitindo que você especifique uma condição que os dados devem atender para serem incluídos no resultado. A estrutura básica de uma consulta com WHERE é a seguinte:

```sql
SELECT coluna1, coluna2,
FROM tabela
WHERE condição;
```

- `SELECT`: Especifica as colunas a serem recuperadas.
- `FROM`: Indica a tabela da qual os dados serão obtidos.
- `WHERE`: Define condições para filtrar os resultados.

Exemplo:

Suponha que você tenha uma tabela chamada clientes e deseje recuperar apenas os clientes que têm mais de 25 anos. Você usaria o comando WHERE da seguinte maneira:

```sql
SELECT nome, idade
FROM clientes
WHERE idade > 25;
```

Exemplo com `AND`:

```sql
SELECT nome, idade
FROM clientes
WHERE idade > 25 AND cidade = "São Paulo";
```

## Aula 04 - `COUNT`

A função `COUNT` no **SQL** é usada para contar o número de linhas em um conjunto de resultados ou o número de linhas que atendem a uma determinada condição. A sintaxe básica é:

```sql
SELECT COUNT(coluna)
FROM tabela
WHERE condição;
```

1. Contar o número total de registros em uma tabela:

    ```sql
    SELECT COUNT(*)
    FROM clientes;
    ```

2. Contar o número de clientes com idade maior que 30:

    ```sql
    SELECT COUNT(*)
    FROM clientes
    WHERE idade > 30;
    ```

3. Contar o número de pedidos concluídos:

     ```sql
    SELECT COUNT(*)
    FROM pedidos
    WHERE status = 'Concluído';
    ```

A função `COUNT` é útil para obter estatísticas sobre conjuntos de dados, contando o número de registros ou o número de registros que atendem a determinadas condições. Lembre-se de que a função `COUNT` sempre retorna um valor numérico, mesmo que não haja correspondências, retornando 0 nesses casos.

## Aula 05 - `TOP`

O uso do `TOP` no **SQL** depende do sistema de gerenciamento de banco de dados (**SGBD**) que você está usando, pois a sintaxe pode variar um pouco entre os diferentes sistemas. Vou fornecer exemplos para os sistemas mais comuns: **Microsoft SQL Server, MySQL e PostgreSQL**.

### Microsoft SQL Server

O `TOP` no **SQL** Server é usado para limitar o número de linhas retornadas em uma consulta. Aqui está um exemplo:

```sql
-- Retorna os 5 primeiros registros da tabela
SELECT TOP 5 coluna1, coluna2
FROM tabela
ORDER BY alguma_coluna;
```

### MySQL

O **MySQL** usa a cláusula `LIMIT` para alcançar um resultado semelhante ao `TOP`. Aqui está um exemplo:

```sql
-- Retorna os 5 primeiros registros da tabela
SELECT coluna1, coluna2
FROM tabela
ORDER BY alguma_coluna
LIMIT 5;
```

Em resumo, o `TOP` é utilizado para limitar o número de resultados retornados em uma consulta.

## Aula - 06 `ORDER BY`

- Consulta 1:

    ```sql
    SELECT FirstName, LastName, MiddleName
    FROM Person.Person
    ORDER BY FirstName ASC, LastName DESC;
    ```

    Esta consulta seleciona as colunas `FirstName`, `LastName` e `MiddleName` da tabela `Person.Person` e ordena os resultados primeiro pelo `FirstName` em ordem ascendente (`ASC`) e, em seguida, pelo LastName em ordem descendente (`DESC`).

- Consulta 2:

    ```sql
    SELECT *
    FROM Person.Person;
    ```

    Essa consulta seleciona todas as colunas da tabela `Person.Person` sem nenhuma ordenação específica. Ela retornará todas as linhas e colunas da tabela.

- Consulta 3:

    ```sql
    SELECT FirstName, LastName
    FROM Person.Person
    ORDER BY MiddleName ASC;
    ```

    Esta consulta seleciona as colunas  `FirstName` e `LastName` da tabela `Person.Person` e ordena os resultados pelo `MiddleName` em ordem ascendente (`ASC`). No entanto, vale mencionar que, na consulta original, a tabela `Person.Person` não possui uma coluna chamada `MiddleName`, o que pode resultar em um erro.

    Se a tabela tiver uma coluna `MiddleName`, a consulta será bem-sucedida. Caso contrário, é necessário ajustar a consulta para refletir as colunas existentes na tabela.

## Aula 07 - `BETWEEN`

- Consulta 1:

    ```sql
    SELECT *
    FROM Production.Product
    WHERE ListPrice BETWEEN 1000 AND 1500;
    ```

    Esta consulta seleciona todas as colunas da tabela `Production.Product` onde o valor da coluna `ListPrice` está entre $1000 e $1500, inclusive.

- Consulta 2:

    ```sql
    SELECT *
    FROM Production.Product
    WHERE ListPrice NOT BETWEEN 1000 AND 1500;
    ```

    Nesta consulta, são selecionadas todas as colunas da tabela `Production.Product` onde o valor da coluna `ListPrice` não está no intervalo de $1000 a $1500.

- Consulta 3:

    ```sql
    SELECT *
    FROM HumanResources.Employee
    WHERE HireDate BETWEEN '2009/01/01' AND '2010/01/01'
    ORDER BY HireDate;
    ```

    Esta consulta seleciona todas as colunas da tabela `HumanResources.Employee` onde a data de contratação (`HireDate`) está entre 1º de janeiro de 2009 e 1º de janeiro de 2010, inclusive. A consulta então ordena os resultados com base na data de contratação.

Em resumo, o uso do `BETWEEN` é útil para filtrar resultados com base em intervalos específicos, e as consultas que você forneceu ilustram isso bem, considerando preços de produtos e datas de contratação de funcionários.

## Aula 08 - `IN`

O operador `IN` frequentemente é usado junto com o `WHERE`, para verificar se um valor correspondem com qualquer valor passado na lista de valores.

A cláusula `IN` no **SQL** é utilizada para filtrar os resultados de uma consulta com base em uma lista de valores. Essa cláusula permite que você especifique várias opções para uma condição, tornando a consulta mais concisa e legível. A sintaxe básica é a seguinte:

```sql
SELECT coluna1, coluna2, ...
FROM tabela
WHERE coluna IN (valor1, valor2, ...);
```

Exemplo:

Suponha que você tenha uma tabela Produtos e deseje recuperar os produtos cujas categorias estão entre 'Eletrônicos' e 'Roupas':

```sql
SELECT *
FROM person.Person
WHERE BusinessEntityID IN (2, 7, 13);
```

Esta consulta **SQL** seleciona todas as colunas da tabela Person.Person onde o valor da coluna BusinessEntityID não está na lista de valores especificada **(2, 7, 13)**. Em outras palavras, ela retorna todas as linhas onde o `BusinessEntityID` não é **2, 7 ou 13**.

A cláusula `NOT IN` é útil quando você deseja excluir resultados que correspondem a valores específicos. Neste caso, a consulta está excluindo linhas em que o `BusinessEntityID` é **2, 7 ou 13** da tabela `Person.Person`.

O uso de `IN` é conveniente quando você precisa verificar se uma coluna está em uma lista específica de valores, evitando a repetição de cláusulas `OR` para cada valor individual. A lista pode conter valores literais, expressões ou subconsultas.

## Aula 09 - `LIKE`

### Consulta 1

```sql
SELECT *
FROM Person.Person
WHERE FirstName LIKE '%kenne%';
```

**Explicação:**

- Esta consulta seleciona todos os campos `*` da tabela `Person.Person`.

- Ela filtra os resultados para incluir apenas registros onde o valor da coluna FirstName contém a sequência de caracteres "kenne" em qualquer lugar do nome.

- Por exemplo, esta consulta retornaria registros para nomes como Kenneth, Mackenzie, e Ken.

### Consulta 2

```sql
SELECT *
FROM Person.Person
WHERE FirstName LIKE '%ro_'
```

**Explicação:**

- Esta consulta também seleciona todos os campos `*` da tabela `Person.Person`.

- No entanto, ela filtra os resultados para incluir apenas registros onde o valor da coluna `FirstName` começa com a sequência de caracteres `ro_` e tem um caractere desconhecido no final.

- Por exemplo, esta consulta retornaria registros para nomes como Robert, Rodrigo, e Roger.
Comparação:

Ambas as consultas utilizam o operador `LIKE` para buscar por padrões de texto na coluna `FirstName`. A diferença está no padrão de texto utilizado:

- A consulta 1 usa o padrão `%kenne%`, que permite que a sequência de caracteres "kenne" apareça em qualquer lugar do nome.

- A consulta 2 usa o padrão `%ro_`, que exige que a sequência de caracteres "ro_" apareça no início do nome e que o caractere final seja desconhecido.

**Resultados:**

Os resultados das duas consultas dependerão dos dados reais presentes na tabela Person.Person.

- A primeira consulta provavelmente retornará um conjunto mais amplo de resultados, pois o padrão de texto é mais flexível.

- A segunda consulta provavelmente retornará um conjunto de resultados mais específico, pois o padrão de texto tem requisitos mais rigorosos.

## Aula 09 - `MIN`, `MAX` e `AVG`

 