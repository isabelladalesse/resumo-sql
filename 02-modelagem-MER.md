# Modelo Entidade x Relacionamento

O **Modelo Entidade–Relacionamento (MER)** é uma forma de representar a estrutura de um banco de dados antes de ele ser implementado em SQL. Ele descreve **quais dados serão armazenados, como eles se relacionam e quais regras esses dados seguem**, facilitando o planejamento e evitando erros na modelagem.

---

- **Entidade**: É um grupo de informações relacionadas que são necessárias para as atividades do sistema. Geralmente representam um objeto do mundo real, como alunos, clientes, produtos... No banco de dados, geralmente são representados como tabelas.
  
- **Atributos**: São as características de cada entidade. Por exemplo, a entidade aluno pode possuir os atributos matrícula, nome, idade, curso... Na tabela que representa as entidades, os atributos geralmente estão dispostos nas colunas.
  
- **Relacionamentos**: Indica como duas ou mais entidades estão associadas entre si. Por exemplo, o aluno _cursa_ curso, o professor _leciona_ disciplina, e por aí vai.

- **Instância**: São os registros individuais de uma entidade, também chamadas de **ocorrências**. Por exemplo, uma instância da entidade Aluno é um aluno específico com suas características. Na tabela das entidades, as instâncias são representadas pelas linhas; as **tuplas**.
  
- **Chaves**: Atributo utilizado para indexar dados. Há 3 tipos:

  - **Primária (Primary Key - PK):** É o atributo que identifica de forma única cada instância dentro de uma entidade. Não podem existir dois registros com a mesma chave primária, e ela nunca pode ser nula.
  - **Estrangeira (Foreign Key - FK):** É um atributo que aponta para a chave primária de outra entidade, formalizando um vínculo entre essas duas entidades.
  - **Secundária:** Atributo usado para indexar dados que também é único, mas não foi escolhido como a chave principal.

- **Cardinalidade**: A cardinalidade define quantas instâncias de uma entidade que podem estar associadas a instâncias de outra entidade por meio de um relacionamento.

  - **1:1 (Um para Um):** Cada instância de uma entidade associa-se a apenas uma instância da outra.
  - **1:N (Um para Muitos):** Uma instância da entidade A pode se relacionar com várias de B, mas a instância de B só se relaciona com uma de A.
  - **N:N (Muitos para Muitos):** As instâncias podem se relacionar com múltiplas instâncias do lado oposto.
 
## Exemplo de Entidade

### Alunos
| Código | Matrícula | Nome | Idade | Curso |
| --- | :--- | :--- | :--- | :--- |
| 194 | 202301 | Ana Souza | 20 | Matemática |
| 195 | 202302 | João Lima | 22 | Engenharia |
| 196 | 202303 | Maria Alves | 19 | Ciência da Computação |
