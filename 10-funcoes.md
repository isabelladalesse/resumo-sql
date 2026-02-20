# Funções comuns para consultas

## Funções de Agregação

### COUNT()

A função `COUNT()` é usada para contar registros em uma tabela. Um exemplo de uso é o cálculo da quantidade de registros totais, quantidade de registros repetidos, quantidade de registros distintos...

```sql
SELECT COUNT(coluna1) - COUNT(DISTINCT coluna1)
FROM tabela;
```

### AVG()

A função `AVG()` calcula a média dos valores numéricos de uma coluna.

```sql
SELECT AVG(coluna1)
FROM tabela;
```

## Funções Matemáticas

### MOD()

A função `MOD()` retorna o resto de uma divisão e é muito usada para verificar se um número é divisível por outro. No exemplo, cunsulta-se IDs pares.

```sql
SELECT DISTINCT coluna
FROM tabela
WHERE MOD(ID, 2) = 0;
```

### CEIL()

A função `CEIL()` arredonda um número para cima, retornando o menor inteiro maior ou igual ao valor.

```sql
SELECT CEIL(AVG(coluna1))
FROM tabela;
```

## Funções de String

### LENGTH()

A função `LENGTH()` retorna o tamanho de uma string (número de caracteres). Um uso comum é para verificar o resultado mais longo ou mais curto.

```sql
SELECT coluna
FROM tabela
ORDER BY LENGTH(coluna) ASC
LIMIT 1;
```

### RIGHT()

A função `RIGHT()` serve para extrair uma parte da string, começando pela direita, com o número de caracteres que for especificado. Se o número de caracteres solicitado for maior que o tamanho da string, o SQL retorna a string inteira. Muito útil para sufixos de termos os números.

```sql
SELECT RIGHT(coluna, 3)
FROM tabela;
-- Retorna os 3 últimos caracteres de cada valor da coluna
```

