# Manipulando Dados nas Tabelas

## Inserindo Dados

Para manipular registros em uma tabela já criada, utilizamos a **Linguagem de Manipulação de Dados (DML)**. O comando `INSERT INTO` é a instrução SQL utilizada para inserir um ou mais registros em uma tabela específica, colocando valores fornecidos nas colunas correspondentes.

```sql
INSERT INTO nome_tabela (nome_coluna1, nome_coluna2)
VALUES (registro1_coluna1, registro1_coluna2),
       (registro2_coluna1, registro2_coluna2),
       (registro3_coluna1, registro3_coluna2);
```

Na hora de realizar a inserção de dados, o SQL exige separadores específicos dependendo do tipo de dado para que o interpretador não confunda valores com comandos.

- Alfanuméricos: Devem obrigatoriamente estar envolvidos por aspas simples (ex: 'João Silva').
- Numéricos: São inseridos sem aspas, utilizando o ponto `.` como separador decimal, caso necessário (ex: 15 ou 1250.50).
- Datas: São tratadas como strings, devendo estar entre aspas simples no formato padrão `'AAAA-MM-DD'` (ex: '2026-02-05').
- Conteúdo Nulo (NULL): Deve ser escrito como a palavra-chave `NULL`, sem aspas, indicando a ausência de valor.

## Atualizando Dados

Para modificar registros já existentes em uma tabela, utilizamos a operação `UPDATE`, comando que permite alterar o valor de uma ou mais colunas em registros específicos. A estrutura básica do comando é:

```sql
UPDATE nome_tabela
SET nome_coluna1 = novo_valor1,
    nome_coluna2 = novo_valor2
WHERE condicao;
```

A cláusula `WHERE` é utilizada para **filtrar registros** nas operações de `UPDATE`, `DELETE` e `SELECT`, garantindo que apenas os dados que atendem a determinadas condições sejam afetados. Para alterar a coluna de um registro específico, basta especificar sua chave primária no `WHERE`. Se os comandos forem executados sem a cláusula `WHERE`, **todos os registros da tabela serão afetados**, o que geralmente não é desejado, principalmente com a exclusão. 

- **= (igualdade):** Seleciona registros cujo valor é igual ao valor informado.

  Exemplo: `WHERE idade = 18`.
  
- **<> ou != (desigualdade):** Seleciona registros cujo valor é diferente do valor informado.

  Exemplo: `WHERE status <> 'inativo'`.
  
- **>, <, >= e <= (comparação numérica):** Retorna registros de acordo com a comparação dada.

  Exemplos: `WHERE salario > 3000`, `WHERE nota < 6`, `WHERE idade >= 18` e `WHERE quantidade <= 10`.
  
- **LIKE (comparação de padrões):** Utilizado para buscar valores iguais a um padrão em campos de texto. O caractere % representa sequência de caracteres.
  
  Exemplo: `WHERE nome LIKE 'Ana%'`.
  
- **IN (pertence a uma lista de valores):** Verifica se o valor da coluna pertence a um conjunto pré-definido.

  Exemplo: `WHERE estado IN ('SP', 'RJ', 'MG')`.
  
- **BETWEEN (intervalo de valores):** Seleciona valores dentro de um intervalo definido (inclusive os limites).

  Exemplo: `WHERE data_nascimento BETWEEN '2000-01-01' AND '2005-12-31'`.
  
- **AND (operador lógico E):** Exige que todas as condições sejam verdadeiras ao mesmo tempo.

  Exemplo: `WHERE idade >= 18 AND status = 'ativo'`.
  
- **OR (operador lógico OU):** Exige que pelo menos uma das condições seja verdadeira.

  Exemplo: `WHERE cidade = 'São Paulo' OR cidade = 'Rio de Janeiro'`.

## Removendo Dados

Para excluir permanentemente registros de uma tabela, utilizamos o comando `DELETE`. Sua estrutura é:

```sql
DELETE FROM nome_tabela
WHERE condicao;
```

Se o DELETE for executado sem a cláusula `WHERE`, todos os registros da tabela serão apagados, mantendo apenas a estrutura da tabela.















