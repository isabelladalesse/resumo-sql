# Consultas a um Banco de Dados
## Comandos básicos

O comando `SELECT` é utilizado para **consultar dados** armazenados em uma tabela, permitindo escolher quais colunas serão retornadas no resultado da consulta.

```sql
SELECT coluna1, coluna2
FROM nome_tabela;
```

Caso seja necessário consultar todas as colunas da tabela, utiliza-se o caractere `*`.

```sql
SELECT *
FROM nome_tabela;
```

O comando `WHERE` é utilizada para **filtrar os registros** retornados por uma consulta, aplicando uma condição que deve ser satisfeita pelos dados.

```sql
SELECT colunas
FROM nome_tabela
WHERE condição;
```

O comando `ORDER BY` é utilizado para **ordenar os resultados** de uma consulta com base em uma ou mais colunas. Por padrão, a ordenação é crescente (`ASC`), mas também pode ser definida como decrescente (`DESC`).

```sql
SELECT colunas
FROM nome_tabela
ORDER BY coluna DESC;
```

Após a ordenação dos dados, é possível **restringir a quantidade de registros** retornados pela consulta com o comando `LIMIT`.

```sql
SELECT colunas
FROM nome_tabela
ORDER BY coluna
LIMIT numero;
```
