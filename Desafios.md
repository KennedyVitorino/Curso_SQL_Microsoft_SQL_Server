# Curso SQL Completo 2020 + Desafios + Muita Prática

## Desafio 01 - `SELECT`

Usar o `SELECT` para buscar o primeiro e segundo nome da pessoa na base.

![Prática Desafio 1](/imgs_do_desafio/Desafio01.png)

## Desafio 02 - `DISTINCT`

Buscar sobrenomes únicos temos na tabela person.person?

![Prática Desafio 2](/imgs_do_desafio/Desafio02.png)

## Desafio 03 - `WHERE`

1. A equipe de produção de produtos precisa do nome de todas as peças que pesam mais que **500kg** mas não mais que **700kg** para inspeção.
    ![Prática Desafio 3.1](/imgs_do_desafio/Desafio03_1.png)

2. Foi pedido marketing uma relação de todos os empregados(**employees**) que são casados (**single = solteiro, married = casado**) e são asalariados (**salaried**).
    ![Prática Desafio 3.2](/imgs_do_desafio/Desafio03_2.png)

3. Um usuário chamado **Peter Krebs** está devendo um pagamento, consiga o e-mail dele para que possamos enviar uma cobrança! (você vai ter que usara a tabela `person.person` e depois a tabela `person.emailaddress`).
    ![Prática do Desafio 3.3](/imgs_do_desafio/Desafio03_3.png)

## Desafio 04 - `COUNT`

1. Quantos produtos temos cadastrados em nossa tabela de produtos. (production.product)
    ![Desafio 4.1](/imgs_do_desafio/Desafio04_1.png)

1. Quantos tamanhos de produtos temos cadastrados em nossa tabela. (production.product)
    ![Desafio 4.2](/imgs_do_desafio/Desafio04_2.png)

## Desafio - 05 `TOP`

Usar o comando `TOP` buscar os 10 primeiros elementos do banco. (production.product)
    ![Desafio 5](/imgs_do_desafio/Desafio05.png)

## Desafio - 06 `ORDER BY`

1. Obter o `ProductID` dos 10 produtos cadastrados no sistema, listando do mais caro para o mais barato.
    Dicas:

    - Você terá que usar a tabela `Prodcution.product`.
    - Você terár que usar o `ORDER BY` e `TOP`.
    - E para ordenar você terá que usar o `ORDER BY AS` ou `DESC` dependenvo do resultado que está buscando
![Desafio 6.1](/imgs_do_desafio/Desafio06_1.png)

2. Obter o nome e número do produto dos produtos que tem o `ProductID` entre **1~4**.
    Dicas:

    - Você terá que usar a tabela `Prodcution.product`.
    - Você terár que usar o `ORDER BY` e `TOP`.
    - E para ordenar você terá que usar o `ORDER BY AS` ou `DESC` dependenvo do resultado que está buscando.
![Desafio 6.2](/imgs_do_desafio/Desafio06_2.png)

## Desafio: Fundamentos SQL

1. Quantos produtos temos cadastrado no sistema que custam mais que **1500** dólares?

    **Dicas:**

    > Você terá que usar a tabela `Production.Product`;
    >
    > Você tera que usar `COUNT` e `WHERE` e mais algum operador de **comparação**;

    **Resposta:**

    ![Fundamentos SQL: Desafio 1](/imgs_do_desafio/Desafio07_1.png)

2. Quantas pessoas temos com o sobrenome de inicia com a Letra P?

    **Dicas:**

    > Você terá que usar a tabela `Person.Person`;
    >
    > Você terá que usar o `COUNT`, `HWERE` e `LIKE`;

    **Resposta:**

    ![Fundamentos SQL: Desafio 2](/imgs_do_desafio/Desafio07_2.png)

3. Em quantas cidades unicas estão cadastrados nossos clientes?

    **Dicas:**

    > Você terá que usar a tabela `Person.Address`;
    >
    > Você terá que usar `COUNT`, `DISTINCT`;

    **Resposta:**

    ![Fundamentos SQL: Desafio 3](/imgs_do_desafio/Desafio07_3.png)

4. Quais são as cidades únicas que temos cadastrados em nosso sistema?

    **Dicas:**

    > Você terá que usar a tabela `Person.Address`;
    >
    > Resposta bem similiar a resposta anterior;

    **Resposta:**

    ![Fundamentos SQL: Desafio 4](/imgs_do_desafio/Desafio07_4.png)

5. Quantos produtos vermelhos tem preço entre **500** e **1000** dólares?

    **Dicas:**

    > Você terá que usar a tabela `Production.Product`;
    >
    > Você terá que usar `HWERE` e `BETWEEN`;

    **Resposta:**

    ![Fundamentos SQL: Desafio 5](/imgs_do_desafio/Desafio07_5.png)

6. Quantos produtos cadastrados tem a palavra road no nome deles?

    **Dicas:**

    > Você terá que usar a tabela `Production.Product`;
    >
    > Você terá que usar `COUNT` e `LIKE`;

    **Resposta:**

    ![Fundamentos SQL: Desafio 6](/imgs_do_desafio/Desafio07_6.png)