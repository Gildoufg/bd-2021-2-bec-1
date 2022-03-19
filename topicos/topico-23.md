## [Tópico T23] - Modelo Entidade Relacionamento (MER) - Exercício
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

Considere que a universidade precisa de um banco de dados, no contexto de um software de controle acadêmico. Três projetistas foram convidados para o desenvolvimento do esquema conceitual de banco do dados. Como resultado, cada projetista produziu um diagrama (DER) particular, conforme ilustrado a seguir.

<img src="../media/fig-der-universidade.jpg" width="650">

Sobre os diagramas, vale esclarecer:
- O tipo de entidade _Disciplina_ descreve o conjunto das disciplinas a serem ofertadas aos alunos:
  - O tipo de entidade _Turma_ denota a oferta de uma disciplina em semestre e ano específicos.
- O atributo _sem_ refere-se ao semestre e ao ano em que uma turma é ofertada.
- O atributo _se_lab_ indica se uma turma ofertada possui aulas de laboratório.
- Os atributos _data_ingr_ e _data_egre_ referem-se à data de ingresso e de egresso do aluno na instituição, respectivamente.
- O atributo _freq_ refere-se à frequência de um aluno em uma turma.
- O tipo de entidade _Título_ refere-se às titulações de cada professor; por exemplo, nível mestrado.
- O atributo _horário_ determina o dia da semana e a hora para a turma (multivalorado?).
- O atributo _créditos_ refere-se à carga horária (CH):
  - semanal para uma disciplina; ou
  - total de um curso.
- Para ser aprovado, um aluno deve ser aprovado por frequência e por média:
  - um aluno é reprovado por média, se a média aritmética de notas for inferior a 7.0;
  - um aluno é reprovado por frequência, se a frequência for inferior a 75 %.

Para responder as perguntas abaixo, considere o somatório das seguintes opções:<br>
(01) Quando o Diagrama 1 atende ao solicitado.<br>
(02) Quando o Diagrama 2 atende ao solicitado.<br>
(04) Quando o Diagrama 3 atende ao solicitado.<br>

### Exercício 01. Que diagrama(s) cobre(m) às demandas informacionais abaixo?

1. Relação de professores que possuem mestrado ou doutorado
1. Os professores que possuem turma com aulas de laboratório em um semestre.
1. A quantidade de turmas oferecidas em um semestre.
1. O código e ementa das disciplinas com turma oferecida em um semestre.
1. A carga horária de cada professor em um semestre.
1. As turmas oferecidas em um determinado semestre, apresentando horário e sala.
1. A quantidade de créditos das aprovações de cada aluno.
1. A idade que os alunos tinham quando ingressaram na instituição.
1. A idade que os professores tinham quando ingressaram na instituição.
1. A quantidade de reprovações por média de cada aluno.
1. A quantidade de reprovações por frequência de cada aluno.
1. A relação de professores que obtiveram doutorado em 2002.
1. Para cada professor, a quantidade de turmas oferecidas em laboratório.
1. A ementa das disciplinas com turmas oferecidas em um semestre para um certo professor.
1. Para cada aluno, os professores de suas turmas em um semestre.
1. O nome e matrícula dos alunos das turmas oferecidas em um semestre.
1. O nome e matrícula dos alunos das turmas oferecidas em um bloco de um campus.
1. A matrícula e nome de um professor, e o diretor do curso em o professor está associado.
1. A data de aniversário de cada professor.
1. A data de aniversário de cada diretor de curso.

### Exercício 02. Que diagrama(s) possui(em) as restrições abaixo?

1. Uma turma pode existir sem alunos, mas não pode existir sem professor.
1. Toda turma possui no máximo um professor, não existindo turma sem professor.
1. O atributo cod do tipo de entidade Turma possui restrição unicidade de dados.
1. Duas turmas podem ser oferecidas de uma mesma disciplina, em um mesmo semestre e em um  mesmo horário.
1. Um mesmo aluno pode possuir diversas turmas de um mesmo professor em um mesmo semestre.
1. Um mesmo professor pode possuir vários telefones.
1. Um aluno pode não estar matriculado em que qualquer turma em um determinado semestre.
1. Turma é um tipo entidade fraca que depende do professor para sua identificação.
1. Não existe professor sem qualquer turma associada.
1. Uma turma pode existir mesmo sem nenhum aluno associado.

## Atividade (data limite: **28/03/2022 23h59min59s**)

Criar uma _issue_ no projeto https://github.com/plinioleitao/bd-2021-2-bec, com o título "Tópico 23", para responder a atividade abaixo.

Seja um banco de dados referente a Viagens de Avião, conforme a figura abaixo.

<img src="../media/fig-der-aeroporto.jpg" width="650">

Considere os seguintes esclarecimentos: 
- Um voo pode ser composto por vários trechos:
  - Por exemplo, o voo **Goiânia-Manaus** é composto pelos trechos **Goiânia-Brasília**, **Brasília-Belém** e **Belém-Manaus**.
- Uma instância de trecho refere-se aos dados do trecho em determinada data:
  Por exemplo, na data 09/05/2021, a aeronave do trecho **Brasília-Belém** partiu às 14h e chegou às 16h.
- Em uma única viagem, o passageiro poderá viajar por um trajeto que envolve vários trechos de voos distintos:
  - O valor a ser pago na viagem refere-se à soma dos preços de cada trecho.
  - Noutras palavras, ao viajar, o passajeiro (cliente) fará um trajeto, que é uma sequência de trechos que ele adquiriu para sua viagem.
- Toda reserva de assentos refere-se a assentos confirmados pelos clientes para uma instância de trecho de voo:
  - Uma reserva significa um assento ocupado em uma passagem confirmada.

Para responder as questões abaixo:
- Some as alternativas verdadeiras.
- Acrescente ao somátório a quantidade de letras do seu primeiro nome.
- Por exemplo, se a soma for 05 e o seu primeiro nome for 'Ana', então a resposta para a questão é 08.

**Questão 01)** Que consultas PODEM ser atendidas pelo esquema conceitual?<br>
(01) Em que dias da semana houve algum voo que não foi realizado, mesmo que previsto?<br>
(02) Quais os voos que possuem atraso na partida de algum dos seus trechos?<br>
(04) Quais os voos que possuem mais de meia-hora de atraso na partida de algum dos seus trechos?

**Questão 02)** Que consultas NÃO PODEM ser atendidas pelo esquema conceitual?<br>
(01) Qual voo teve designação de aeronave para alguma instância de seus trechos de voo que é distinta da aeronave prevista para o trecho?<br>
(02) Qual aeronave foi prevista para um trecho de voo?<br>
(04) Qual aeronave foi designada para uma instância de trecho de voo?

**Questão 03)** Que consultas PODEM ser atendidas pelo esquema conceitual?<br>
(01) Que aeroporto teve voos com partida ou chegada atrasada em dias com chuva?<br>
(02) Que aeroporto teve voos com partida atrasada em 09/05/2019?<br>
(04) Que aeroporto teve voos com chegada atrasada em 09/05/2019?

**Questão 04)** Que consultas NÃO PODEM ser atendidas pelo esquema conceitual?<br>
(01) Em qual companhia aérea mais passageiros voaram no último mês?<br>
(02) Que dia da semana possui mais voos com ocupação inferior a 15% dos assentos disponíveis?<br>
(04) Que aeronave possui mais reservas na janela para crianças?

Responda conforme o padrão abaixo (apenas para exemplificar):<br>
Questão 01) 11<br>
Questão 02) 08<br>
Questão 03) 09<br>
Questão 04) 09<br>

RESPOSTAS:<br>
Questão 01) 07<br>
Questão 02) 03<br>
Questão 03) 06<br>
Questão 04) 04<br>

## Artefatos

1. _Issue_ criada no projeto https://github.com/plinioleitao/bd-2021-2-bec, cujo título é "Tópico 23", para exercitar a interpŕetação de Diagrama Entidade Relacionamento.
