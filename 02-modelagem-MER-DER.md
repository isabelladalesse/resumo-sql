# Modelo Entidade x Relacionamento

O **Modelo Entidade–Relacionamento (MER)** é uma forma de representar a estrutura de um banco de dados antes de ele ser implementado em SQL. Ele descreve **quais dados serão armazenados, como eles se relacionam e quais regras esses dados seguem**, facilitando o planejamento e evitando erros na modelagem.

---

- **Entidade**
  
  É um grupo de informações relacionadas que são necessárias para as atividades do sistema. Geralmente representam um objeto do mundo real, como alunos, clientes, produtos... No banco de dados, geralmente são representados como tabelas.
  
- **Atributos**
  
  São as características de cada entidade. Por exemplo, a entidade aluno pode possuir os atributos matrícula, nome, idade, curso... Na tabela que representa as entidades, os atributos geralmente estão dispostos nas colunas.
  
- **Relacionamentos**

  Indica como duas ou mais entidades estão associadas entre si. Por exemplo, o aluno _cursa_ curso, o professor _leciona_ disciplina, e por aí vai.

- **Instância**

  São os registros individuais de uma entidade, também chamadas de **ocorrências**. Por exemplo, uma instância da entidade Aluno é um aluno específico com suas características. Na tabela das entidades, as instâncias são representadas pelas linhas; as **tuplas**.

  
