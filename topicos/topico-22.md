## [Tópico T22] - Modelo Entidade Relacionamento (MER) - Decisões de Projeto
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)* &#9728;

Ao abstrair potenciais elementos conceituais no projeto de banco de dados, a questão inicial é:

| **O *elemento conceitual* é um *tipo de entidade*, *um tipo de relacionamento* ou um *atributo*?** |
| -------------------------------------------------------------------------------------------------- |

```diff
- Há diretrizes para essa tomada de decisão?
+ É preciso estar atento ao significado de cada elemento conceitual ...
```

### Preâmbulo

>**Mudanças** são esperadas e típicas:
- Cada decisão durante o projeto conceitual está sujeita a alterações durante a modelagem.<br>
Por exemplo, um **elemento conceitual** inicialmente categorizado como ***atributo*** pode tornar-se um ***tipo de entidade*** no decorrer do processo, e vice-versa.

>Por se tratar de um **processo interativo, iterativo e evolutivo**, comumente **três aprendizados** são compartilhados:
- A **interação** entre os atores é parte integrante da **elaboração** e da **validação** de cada versão do esquema conceitual.
- Quaisquer **discussões excessivas** sobre *como modelar um elemento conceitual devem ser evitadas*: **iterações porvir** trarão maior clareza para as decisões.
- A sequência de versões em si do esquema conceitual resulta em aprendizado com efeitos positivos para a **evolução do próprio esquema conceitual**.

### Tipo de relacionamento **versus** Atributo ou Tipo de Entidade

> O elemento conceitual representa uma associação com significado entre dois (ou mais) elementos conceituais?
- se sim, é um candidato a TIPO DE RELACIONAMENTO, principalmente se os outros elementos conceituais são *tipos de entidade*:
  - por exemplo, o elemento conceitual cujo significado é **aluno se matricula em turma** é um tipo de relacionamento entre os tipos de entidade cujos significados são **conjunto de alunos** e **conjunto de turmas**, respectivamente.
- se não, é um candidato a ATRIBUTO ou TIPO DE ENTIDADE, conforme o seu significado:
  - por exemplo, o elemento conceitual cujo significado é **conjunto de alunos** é um tipo de entidade;
  - outro exemplo, o elemento conceitual que tem o significado **data de nascimento do aluno** é um atributo do tipo de entidade cujo significado é **conjunto de alunos**.

### Atributo *versus* Tipo de Entidade

> O domínio de valores do elemento conceitual é estável (ou mesmo fixo)?
- Se sim, é um candidato a ATRIBUTO, principalmente se o domínio for fixo:
  - por exemplo, o elemento conceitual cujo significado é **estado civil do funcionário** possui domínio fixo: *&#123; casado, solteiro, ... &#125;*.
- Se não, é um candidato a TIPO DE ENTIDADE, principalmente se for composto e houver pretendente(s) a atributo chave:
  - por exemplo, o elemento conceitual **produto** é composto por _código_, _descrição_ e _preço unitário_, em que _código_ é pretendente natural a atributo chave.

> O elemento conceitual possui vários (dois ou mais) significados, que mencionam outros elementos conceituais?
- Se sim, é um candidato a TIPO DE ENTIDADE, principalmente se os outros elementos conceituais são *tipos de entidade*:
  - os elementos conceituais **departamento do curso de graduação** e **departamento do professor** mencionam os tipos de entidade cujos significados são **conjunto de cursos de graduação** e **conjunto de professores**: neste caso o elemento conceitual em questão é um tipo de entidade cujo significado é **conjunto de departamentos**:
    - neste exemplo, há um tipo de relacionamento binário entre os elementos conceituais cujos significados são:
      - **conjunto de departamentos** e **conjunto de cursos de graduação**; e
      - **conjunto de departamentos** e **conjunto de professores**.
- Se não, é um candidato a ATRIBUTO, principalmente se seu significado menciona um único tipo de entidade:
  - por exemplo, o elemento conceitual cujo significado é **preço unitário do produto** é um atributo do tipo de entidade que tem o significado **conjunto de produtos**.

### Atributo de Tipo de Entidade *versus* Atributo de Tipo de Relacionamento

> O significado do elemento conceitual menciona outros (dois ou mais) elementos conceituais?
- Se sim, é um candidato a ATRIBUTO DE TIPO DE RELACIONAMENTO, principalmente se os outros elementos conceituais são *tipos de entidade*:
  - por exemplo, se o significado do elemento conceitual é a **quantidade de horas semanais que um *funcionário* trabalha em um *projeto***, então este é um atributo do tipo de relacionamento que tem o significado **funcionário trabalha em projeto**.
- Se não, é um candidato a ATRIBUTO DE TIPO DE ENTIDADE, principalmente se o significado menciona um único tipo de entidade:
  - por exemplo, se o significado do elemento conceitual é **a data de pagamento da *fatura***, então este é um atributo do tipo de entidade que tem o significado **conjunto de *faturas***.
- Em ambos os casos, o atributo contribui para o significado do tipo de entidade ou do tipo de relacionamento.

### Atributo Multivalorado *versus* Tipo de Entidade e Tipo de Relacionamento

> O significado do elemento conceitual menciona um outro elemento conceitual e atribui cardinalidade maior do que 1 (um)?
- Se sim, é um candidato a ATRIBUTO MULTIVALORADO, principalmente se for um atributo simples (não composto):
  - por exemplo, o elemento conceitual cujo significado é **telefones celulares do vendedor** é um atributo multivalorado do tipo de entidade que tem o significado **conjunto de vendedores**.
- Se não, é um candidato a TIPO DE ENTIDADE e TIPO DE RELACIONAMENTO, principalmente se for composto e houver pretendente(s) a atributo chave:
  - por exemplo, o elemento conceitual que tem o significado **autores do livro** é composto por _código_, _nome_ e _data de nascimento_, em que _código_ é candidato a atributo chave:
    - neste caso, o elemento conceitual representa:
      - um tipo de entidade (significado **conjunto de autores**); e 
      - um tipo de relacionamento binário (significado **autor do livro**).

## Atividade (data limite: **27/03/2022 23h59min59s**)

Observe que, para cada decisão de projeto ilustrada acima, há um exemplo que é apresentado.<br>
Tente desenhar um trecho de DER independente para cada exemplo apresentado, conforme a notação do DER apresentada no [Tópico 20](./topico-20.md). 

Criar uma _issue_ no projeto https://github.com/plinioleitao/bd-2021-2-bec, com o título "Tópico 22", para responder: 

1. _Você consegue **elaborar uma interpretação** (a sua interpretação) para as **decisões de projeto**, que foram apresentadas no presente tópico, quando se aplica o Modelo Entidade Relacionamento (MER) na fase de projeto conceitual?_ Favor selecionar uma das respostas a seguir:
   - "Sim, eu consigo ter a minha interpretação para as decisões de projeto, que foram apresentadas no presente tópico", ou
   - "Não, pois eu tenho dificuldade em interpretar as seguintes decisões de projeto: blá, blá, ...". Nesta resposta, você deve descrever as suas dificuldades, em vez de apenas listá-las.

## Artefatos

1. _Issue_ criada no projeto https://github.com/plinioleitao/bd-2021-2-bec, cujo título é "Tópico 22", para indicar suas reflexões iniciais sobre *decisões de projeto no Modelo Entidade Relacionamento (MER)*.
