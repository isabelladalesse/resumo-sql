## Alterando a Estrutura de Tabelas

Para adicionar uma nova coluna a uma tabela existente, utiliza-se o comando `ADD COLUMN`.

```sql
ALTER TABLE nome_tabela
ADD COLUMN nome_coluna  tipo_de_dados  constraints;
```

Para modificar colunas, há várias possibilidades, como tipo de dado, tamanho e constraints de uma coluna.

```sql
ALTER TABLE nome_tabela
MODIFY COLUMN nome_coluna novo_tipo novos_constraints;
```

Pode-se especificar apenas o que está sendo alterado (tipo, tamanho, constraints) sem precisar repetir o resto. Para deletar uma coluna da tabela, utiliza-se o comando `DROP COLUMN`. Também é possível renomear uma coluna com o comando `RENAME`:

```sql
ALTER TABLE nome_tabela
RENAME nome_coluna to novo_nome_coluna
```

Se o desejado é alterar o nome da tabela:

```sql
ALTER TABLE nome_tabela
RENAME novo_nome_tabela
```

E, por fim, para adicionar constraints de tabela, usa a seguinte sintaxe:

```sql
ALTER TABLE nome_tabela
ADD CONSTRAINT constraint;
```

## Excluindo uma Tabela

Para excluir permanentemente uma tabela, o comando usado é o `DROP TABLE`:

```sql
DROP TABLE nome_tabela
```

