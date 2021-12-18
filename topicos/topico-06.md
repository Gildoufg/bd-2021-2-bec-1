## [Tópico T06] - Requisitos de Dados
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

Há problemas no mundo real cuja solução pode ser alcançada por meio de **software**. As necessidades e restrições colocadas em um produto de software são representadas pela especificação de **requisitos de software**. Então, a análise, elicitação e especificação de requisitos são etapas do **processo de software**. Requisitos de Software podem ser expressos em **artefatos**, cuja construção em geral aplica **modelos** e emprega **notações** tal como a UML, com o apoio de **ferramentas** na escrita desses artefatos.

> O banco de dados é parte integrante de um produto de software.<br>
> Questão 01:  Qual o banco de dados que atende aos **requisitos de software**?<br>
> Questão 01a: Sendo mais preciso, que **esquema de banco de dados** atende aos **requisitos de software**?

Independente da classificação de requisitos – se o requisito é funcional ou não-funcional, a prioridade do requisito, etc. – há os **requisitos de dados**, que é uma das partes de todo o conjunto de requisitos de software. Então, os requisitos de dados são os requisitos considerados para o projeto de banco de dados. Veja a Figura 7.1 no Capítulo 7 da 6a. edição do livro [1], para uma ilustração de contexto dos requisitos de dados.

> O projeto de banco de dados deve ser tal que contribua para a efetividade do produto de software.<br>
> Questão 02: O que é **projeto de banco de dados**?

**Por que coletar requisitos de dados?**<br>
Nostras palavras, como saber qual o [projeto de] banco de dados *certo* para o software?<br>
Uma resposta simples é que **bancos de dados são projetados** a partir dos requisitos de dados, pois tais requisitos retratam as necessidades e restrições próprias para o banco de dados do software. Nesse sentido, bancos de dados são usualmente projetados com o uso de **modelos de dados**, os quais apoiam a **representação** da estrutura e restrições da base de dados em algum **nível de abstração** - desde a visão conceitual dos dados (alto-nível) até a percepção dos dados armazenados (baixo-nível).

> Questão 03:  Que **esquema de banco de dados** atende aos **requisitos de dados**?<br>
> Questão 03a: Pode haver **mais de um** esquema de banco de dados que atende aos requisitos de dados?

### Requisitos de Dados - BD Empresa

O livro sugerido [1] para a disciplina inclui requisitos de dados para o **Banco de Dados Empresa** (*Company Database*). Este banco de dados é explorado em quase todo o livro. Os requisitos são apresentados abaixo, na forma de ***descrição textual***, conforme posto no livro.

>***A empresa é organizada em departamentos. Cada departamento tem um nome exclusivo, um número exclusivo e um funcionário em particular que o gerencia. Registramos a data inicial em que esse funcionário começou a gerenciar o departamento. Um departamento pode ter vários locais.<br>
Um departamento controla uma série de projetos, cada um deles com um nome exclusivo, um número exclusivo e um local exclusivo.<br>
Armazenamos o nome, número de Cadastro de Pessoa Física, endereço, salário, sexo (gênero) e data de nascimento de cada funcionário. Um funcionário é designado para um departamento, mas pode trabalhar em vários projetos, que não necessariamente são controlados pelo mesmo departamento. Registramos o número atual de horas por semana que um funcionário trabalha em cada projeto. Também registramos o supervisor direto de cada funcionário (que é outro funcionário).<br>
Queremos registrar os dependentes de cada funcionário para fins de seguro. Para cada dependente, mantemos o nome, sexo, data de nascimento e o parentesco com o funcionário.***

Em nossa disciplina, o **BD Empresa** será utilizado para ilustrar conceitos e apresentar exemplos pertinentes a banco de dados. Outrossim, outros bancos de dados, contextos e aplicações serão explorados, para enriquecer as discussões e ampliar os esforços de compreensão e a escala de aprendizagem.

>*Usaremos o **BD Empresa** em vários dos exemplos apresentados, além de outros bancos de dados, contextos e aplicações.*

Então, vamos nos apropriar (memorizar?) dos requisitos de dados do BD Empresa.

### Requisitos de Dados - BD Locadora de Veículos

Outro exemplo de requisitos de dados é apresentado [aqui](../media/bd-01-locadora.pdf). Trata-se de uma **Locadora de Veículos**, cujo tema é brevemente introduzido abaixo:

> O tema refere-se a uma locadora de veículos, cujo negócio é o empréstimo de veículos para clientes. Veículos são locados a partir do contato entre clientes e atendentes da locadora, que fazem as buscas no banco de dados para apoiar os clientes em suas decisões. O administrador da locadora toma decisões táticas, visando a conhecer os perfis de locação e clientes, para atuar na gestão operacional e campanhas de divulgação. O gerente financeiro da locadora lida essencialmente com aspectos monetários do negócio. Os mecânicos atuam conforme uma agenda diária de trabalho, que visa a reduzir o tempo dos veículos em estado de manutenção.

Observe que esses requisitos de dados incluem um conjunto de demandas informacionais, que são apresentadas na forma de **consultas** e são organizadas pelo **perfil do usuário**.

## Atividade (data limite: **26/12/2021 23h59min59s**)

Criar uma _issue_ no projeto https://github.com/plinioleitao/bd-2021-2-bec, com o título "Tópico 06", para responder conforme a seguir:  
1. Leia e releia os requisitos de dados pertinentes ao **BD Empresa**. Identifique 05 (cinco) pontos de imprecisão nos requisitos, conforme o exemplo abaixo.<br>
**Ponto 1:** Não está claro se um dependente é obrigatoriamente um parente do seu empregado responsável.<br>
**Ponto 2:** ...<br>
**Ponto 3:** ...<br>
**Ponto 4:** ...<br>
**Ponto 5:** ...

## Artefatos

1. _Issue_ criada no projeto https://github.com/plinioleitao/bd-2021-2-bec, cujo título é "Tópico 06", para indicar suas reflexões sobre os *requisitos de dados* para o **BD Empresa**.

### Bibliografia

[1] ELMASRI, R.; NAVATHE, S. B. Sistemas de Banco de Dados. 6. ed. Pearson, 2011.
