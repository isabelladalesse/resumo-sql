# Normalização de dados

A normalização de dados é um processo que busca **organizar as informações** da forma mais eficiente, contribuindo para **redução de dados duplicados, maior integridade** das informações e **facilidade de manutenção** do banco de dados. Esse processo consiste em estruturar as tabelas de forma que cada informação seja armazenada uma única vez, no local mais adequado, estabelecendo relações entre elas quando necessário.

## Formas Normais

A normalização é organizada em formas normais, que estabelecem regras progressivas para a estruturação correta das tabelas. Cada forma normal depende do cumprimento da anterior.

### Primeira Forma Normal (1FN)

Uma tabela está na Primeira Forma Normal (1FN) quando:

- Todos os campos armazenam **valores indivisíveis** em grupos menores  
- Não existem **grupos repetitivos** de informações  
- Cada registro pode ser identificado por uma **chave primária**

### Segunda Forma Normal (2FN)

Uma tabela está na Segunda Forma Normal (2FN) quando:

- Já atende aos critérios da Primeira Forma Normal  
- Todos os atributos não-chave dependem da **chave primária como todo**  
- Não existem **dependências parciais**, ou seja, um atributo depende apenas de **parte da chave composta**, e não da chave completa  

### Terceira Forma Normal (3FN)

Uma tabela está na Terceira Forma Normal (3FN) quando:

- Já atende aos critérios da Segunda Forma Normal  
- Não existem **dependências transitivas**  
- Atributos não-chave não podem depender de outros atributos não-chave, ou seja, não há dependências indiretas
