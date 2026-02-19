# Estruturando o Banco de Dados

Para começar a escrever código SQL de forma correta, existem algumas regras básicas. Tenha em mente que a sintaxe exata pode variar levemente dependendo do SGBD utilizado. 

## Tipos de Dados

- **Números inteiros**
    - `INT`: Inteiro padrão (4 bytes).
    - `SMALLINT`: Inteiro curto, ocupa menos espaço.
- **Números racionais (exatos)**
    - `NUMERIC`: Valor exato com precisão definida.
    - `DECIMAL`: Sinônimo de NUMERIC.
- **Números Reais (Aproximados)**
    - `REAL`: Ponto flutuante de precisão simples.
    - `FLOAT`: Ponto flutuante de precisão dupla.
- **Data**
    - `DATE`: Armazena apenas a data (AAAA-MM-DD).
    - `TIME`: Armazena apenas a hora (HH:MM:SS).
- **Texto**
    - `CHAR`: Texto de tamanho fixo (preenche com espaços).
    - `VARCHAR`: Texto de tamanho variável (também deve ser especificado).
- **Boolean**
    - `BOOLEAN`: Armazena valores Verdadeiro ou Falso.
 
## Integridade Referencial

As operações **CRUD (Create, Read, Update e Delete)** representam opções básicas de manipulação de dados em um sistema. Para que essas operações ocorram de forma segura, o banco de dados impõe a integridade referencial, um conjunto de regras que garante a consistência entre tabelas relacionadas. No contexto da integridade, não é permitida a entrada de valores duplicados em campos de identificação única (como chaves primárias), assegurando que cada registro seja exclusivo. Além disso, o sistema impede a existência de uma chave estrangeira sem uma instância de referência correspondente na chave primária, bem como proíbe a exclusão de um registro na tabela primária caso existam registros dependentes na tabela estrangeira, mantendo a confiabilidade das informações.

## O comando inicial: CREATE TABLE

O comando `CREATE TABLE`, da **Linguagem de Definição de Dados (DDL)**, é utilizado para definir a estrutura de uma nova tabela, permitindo a aplicação de diversas opções e restrições que garantem a integridade dos dados. Entre as **restrições de valor (constraints)**, temos o `NOT NULL`, que impede que uma coluna aceite valores nulos, o `UNIQUE`, que garante que todos os valores em uma coluna sejam distintos, e o `DEFAULT`, que define um valor padrão caso nenhum seja informado. Outra constraint muito interessante é o `CHECK`, que define opções de valores que podem ser utilizados na coluna ou, de forma mais geral, uma condição específica para os valores da coluna.

A sintaxe básica do comando `CREATE TABLE` é a seguinte:

```sql
CREATE TABLE nome_tabela (
    nome_coluna1  tipo_de_dado_coluna1  constraints_coluna1,
    nome_coluna2  tipo_de_dado_coluna2  constraints_coluna2,
    nome_coluna3  tipo_de_dado_coluna3  constraints_coluna3,
    constraints_tabela)
```

O comando também permite a configuração de **chaves primárias e estrangeiras** a partir das palavras chaves  `PRIMARY KEY`  e `FOREIGN KEY`. Alguns bancos de dados permitem a utilização delas como constraints de colunas, mas como todos as reconhecem como constraints de tabela, essa prática é mais indicada. Configurar chaves estrangeiras usa a seguinte sintaxe:

```sql
FOREIGN KEY (nome_coluna_chave_estrangeira)
    REFERENCES nome_tabela_chave_primaria (nome_coluna_chave_primaria)
    ON UPDATE ação
    ON DELETE ação
```

Nesse código ficam definidas as ações que devem ser tomadas quando uma linha da tabela de referência é alterada (`ON UPDATE`) ou excluída (`ON DELETE`). São comuns:

- `CASCADE`: Se um registro na tabela primária for excluído ou atualizado, todos os registros dependentes na tabela estrangeira serão removidos ou modificados da mesma forma.
- `SET NULL`: Quando um registro na tabela primária sofre uma ação, os valores correspondentes na tabela estrangeira são definidos automaticamente como nulos, desde que a coluna não possua a restrição `NOT NULL`.
- `SET DEFAULT`: Semelhante ao anterior, esta opção redefine os valores da chave estrangeira para o valor padrão (`DEFAULT`) configurado na criação da tabela caso o registro pai seja alterado ou removido.
- `RESTRICT, NO ACTION`: Impedem operações de atualização ou exclusão na tabela primária se houver algum registro vinculado na tabela estrangeira, lançando um erro.

Por fim, existe a opção de Auto Incremento (`AUTOINCREMENT`), que automatiza a geração de valores numéricos sequenciais para uma coluna, facilitando a criação de identificadores únicos sem a necessidade de intervenção manual.

### Exemplo de código

```sql
CREATE TABLE aluno (
    codigo int,
    matricula int UNIQUE,
    nome varchar(300) NOT NULL UNIQUE,
    idade int NOT NULL,
    curso varchar(70) DEFAULT 'pendente',
    PRIMARY KEY (codigo),
    CHECK (idade>=15)
);

CREATE TABLE professor (
    codigo int,
    departamento varchar(70) DEFAULT 'pendente',
    nome varchar (300) NOT NULL,
    PRIMARY KEY (codigo)
);

CREATE TABLE disciplina (
    codigo int,
    codigo_prof int,
    nome varchar(300) NOT NULL UNIQUE,
    carga_horaria int NOT NULL,
    PRIMARY KEY (codigo),
    FOREIGN KEY (codigo_prof)
  	REFERENCES professor (codigo)
  	ON UPDATE CASCADE
  	ON DELETE SET DEFAULT
);
```

Note que nesse código o relacionamento professor leciona disciplina está definido pela chave estrangeira codigo_prof, enquanto o relacionamento aluno cursa disciplina ainda não foi configurado.
