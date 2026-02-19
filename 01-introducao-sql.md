# SQL: Structured Query Language

**SQL (Structured Query Language)** é um conjunto de comando de manipulação de bancos de dados utilizados para criar, estruturar e modificar as informações das tabelas dele.

- **SQL**: Foca em tabelas e esquemas rígidos (relacional).
- **NoSQL**: Oferece flexibilidade para dados não estruturados.

## Introdução à Linguagem SQL

O SQL é dividido em sublinguagens, cada uma com um propósito específico no gerenciamento dos dados.

| Sigla | Significado              | Função                       | Exemplos                       |
|------:|--------------------------|------------------------------|--------------------------------|
| DDL   | Data Definition Language | Definição da estrutura       | 'CREATE', 'DROP', 'ALTER'      |
| DML   | Data Manipulation Language | Manipulação de registros   | 'INSERT', 'DELETE', 'UPDATE'   |
| DQL   | Data Query Language      | Consulta de dados            | 'SELECT'                       |
| DCL   | Data Control Language    | Controle de acessos          | 'GRANT', 'REVOKE'              |
| DTL   | Data Transaction Language | Gerenciamento de transações | 'COMMIT', 'ROLLBACK'           |


### Bancos de dados

Os bancos de dados estão em **SGBDs (Sistemas de Gerenciamento de Banco de Dados)** , que são softwares responsáveis por gerenciar o acesso, a manipulação e a organização dos dados. Um exemplo popular é o MongoDB, que é NoSQL. Os tipos mais comuns de bancos de dados são:

- **Rede**  
  Os dados são registros vinculados uns aos outros.

- **Hierárquico**  
  Dados em estrutura de árvore, com uma hierarquia de categorias. Caso especial do modelo de rede.

- **Relacional**  
  Formato padrão de linhas e colunas em tabelas.

- **Objeto**  
  Os dados e processos são representados como uma união de propriedades e métodos.

- **Objeto-relacional**  
  Combina o modelo orientado a objetos e o modelo relacional.

Para a criação de um banco de dados, é essencial um planejamento prévio. No geral, o processo segue a seguinte ordem:

1. **Modelo Conceitual**  
   O foco é a lógica, identificando as entidades e como elas se relacionam sem se preocupar com detalhes técnicos.  
   Geralmente é usado o **MER – Modelo Entidade x Relacionamento**, que possui diversas vantagens.

2. **Desenho de Banco de Dados (DER)**  
   A estrutura ganha corpo com a definição de tabelas, chaves e a aplicação de regras de normalização para evitar redundâncias.  
   Essa estrutura gráfica que identifica e relaciona entidades de um sistema é chamada de **Modelo de Dados**.

3. **Criação do Banco de Dados**  
   Modelo físico, onde o projeto é traduzido em scripts SQL e efetivamente implementado em um SGBD.
