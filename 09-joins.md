## Consultas a diferentes tabelas

Os **JOINs** são usados para combinar dados de duas ou mais tabelas com base em uma condição de relacionamento, geralmente envolvendo **chaves primárias e estrangeiras**.

### INNER JOIN
Retorna apenas os **registros que possuem correspondência em ambas as tabelas**. Se não houver correspondência, o registro não aparece no resultado. É o tipo de JOIN mais utilizado.

```sql
SELECT colunas
FROM tabela1
INNER JOIN tabela2
ON condição_de_relacionamento;
```

### LEFT JOIN

Retorna **todos os registros da primeira tabela**. Os registros da segunda tabela aparecem apenas quando há correspondência. Quando não há correspondência, os campos da segunda tabela retornam NULL.

```sql
SELECT colunas
FROM tabela1
LEFT JOIN tabela2
ON condição_de_relacionamento;
```

### RIGHT JOIN

Retorna **todos os registros da segunda tabela**. Os registros da primeira tabela aparecem somente quando há correspondência. Quando não há correspondência, os campos da primeira tabela retornam NULL. Em muitos casos, `RIGHT JOIN` pode ser evitado invertendo a ordem das tabelas e usando `LEFT JOIN`, que melhora a legibilidade.

``` sql
SELECT colunas
FROM tabela1
RIGHT JOIN tabela2
ON condição_de_relacionamento;
```

### FULL JOIN

Retorna **todos os registros da primeira e da segunda tabela**. Quando não há correspondência em uma das tabelas, os campos da tabela sem correspondência retornam NULL. Nem todos os bancos de dados suportam `FULL JOIN` diretamente (ex.: MySQL). Nesses casos, ele pode ser simulado com `LEFT JOIN` + `RIGHT JOIN` usando `UNION`.

```sql
SELECT colunas
FROM tabela1
FULL JOIN tabela2
ON condição_de_relacionamento;
```

É possível realizar **vários JOINs em uma mesma consulta SQL**, permitindo relacionar mais de duas tabelas desde que exista uma condição de relacionamento clara entre elas. Uma **boa prática** nesse processo é o uso de **apelidos (aliases)** para as tabelas, definidos logo após o nome da tabela, pois eles deixam a escrita mais limpa, reduzem a repetição de nomes longos e evitam ambiguidades quando diferentes tabelas possuem colunas com o mesmo nome.

```sql
SELECT colunas
FROM tabela1 t1
INNER JOIN tabela2 t2
    ON t1.id = t2.id_tabela1
LEFT JOIN tabela3 t3
    ON t2.id = t3.id_tabela2;
```

