# Diagrama Entidade x Relacionamento

Tradicionalmente, utilizamos formas geométricas específicas para cada elemento:
* **Entidades:** Retângulos.
* **Atributos:** Elipses.
* **Relacionamentos:** Losangos.
* **Chaves Primárias:** Devem ser sublinhadas.

> **Nota:** É preferível organizar os atributos verticalmente dentro de retângulos logo abaixo do nome da entidade para evitar poluição visual.
## Exemplo de Diagrama Entidade x Relacionamento

<img width="693" height="548" alt="image" src="https://github.com/user-attachments/assets/949f98f4-f160-47f2-a383-224df761913f" />
<img width="693" height="548" alt="image" src="https://github.com/user-attachments/assets/949f98f4-f160-47f2-a383-224df761913f" />

Neste modelo com as entidades **Professor**, **Aluno** e **Disciplina**:

1.  **Relacionamento "leciona" (1:N):**
    - O **Professor** tem cardinalidade (0,n): pode não lecionar nada ou várias disciplinas.
    - A **Disciplina** tem cardinalidade (0,1): pode existir sem professor ou ter no máximo um responsável.
    - Vínculo: O atributo `codigo_prof` na entidade Disciplina é uma **chave estrangeira** que conecta à chave primária de Professor.
2.  **Relacionamento "cursa" (N:N):**
    - O **Aluno** tem cardinalidade (1,n): deve estar cursando pelo menos uma disciplina.
    - A **Disciplina** tem cardinalidade (0,n): pode ter nenhum ou muitos alunos.

### Identificadores no Exemplo:
- **Chaves Primárias (PK):** Atributo `código` nas entidades Professor, Aluno e Disciplina.
- **Chave Secundária:** Atributo `Matrícula` na entidade Aluno.

---

## 🛠️ Ferramentas Úteis
- **Automáticas (IA):** [QuickDBD](https://www.quickdatabasediagrams.com/) e [DbDiagram.io](https://dbdiagram.io/).
- **Manual:** [Creately](https://creately.com/).
