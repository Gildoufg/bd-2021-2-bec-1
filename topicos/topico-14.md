## [Tópico T14] - SQL - Introdução, DDL (_Data Definition Language_)
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

**SQL** (**_Structured Query Language_**) é a linguagem padrão para Sistemas Gerenciadores de Bancos de Dados Relacionais (SGBDR):
- Originalmente, chamava-se SEQUEL (_Structured English QUEry Language_) e foi projetada e implementada na IBM Research como a _interface_ para um sistema de banco de dados relacional experimental chamado SYSTEM R. 
- A padronização da SQL é uma iniciativa mútua do _American National Standards Institute_ (ANSI) e da _International Standards Organization_ (ISO):
  - o primeiro padrão SQL é chamado de SQL-86 ou SQL1;
  - a segunda versão do padrão é chamada SQL-92 ou SQL2;
  - a proxima revisão do padrão é chamada SQL:1999 ou SQL3;
  - revisões posteriores foram apresentadas em 2006, 2008 e 2011.

Apesar do nome **Linguagem Estruturada de Consulta**, os comandos da SQL não são restritos a consultas a bancos de dados. A SQL é uma linguagem de banco de dados abrangente, pois inclui comandos de:
- DDL (_Data Definition Languague_), tais como comandos para a criação de relações (tabelas) e restrições de integridade;
- DML (_Data Manipulation Language_), tais como comandos para consultas e atualizações de dados;
- DCL (_Data Control Language_), tais como comandos para a atribuição e a revogação de permissão de acesso a dados.

Para aderir à ementa da disciplina, essencialmente exploraremos os comandos SQL de DML. Outrossim, para a 'implementação' de bancos de dados durante o nosso curso, alguns dos comandos SQL de DDL serão introduzidos abaixo.

### Comandos DDL

Alguns dos comandos SQL de DDL (_Data Definition Languague_) são apresentados abaixo por meio de exemplos. Não há a intenção de ser exaustivo, nem genérico.

#### Comandos DDL Exemplo 1

CREATE TABLE FUNCIONARIO (<br>
&nbsp;&nbsp;&nbsp;&nbsp; Pnome VARCHAR(20) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Minicial CHAR(1) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Unome VARCHAR(20) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Cpf CHAR(9) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Datanasc DATE NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Endereco VARCHAR(40) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Sexo CHAR(1) NOT NULL CHECK Sexo IN ('M','F'), <br>
&nbsp;&nbsp;&nbsp;&nbsp; Salario NUMERIC(20,2) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Cpf_supervisor CHAR(9) NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Dnr INT NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; PRIMARY KEY (Cpf), <br>
&nbsp;&nbsp;&nbsp;&nbsp; FOREIGN KEY (Cpf_supervisor) REFERENCES FUNCIONARIO(Cpf) <br>
); <br>

#### Comandos DDL Exemplo 2

CREATE TABLE FUNCIONARIO (<br>
&nbsp;&nbsp;&nbsp;&nbsp; Pnome VARCHAR(20) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Minicial CHAR(1) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Unome VARCHAR(20) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Cpf CHAR(9) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Datanasc DATE NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Endereco VARCHAR(40) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Sexo CHAR(1) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Salario NUMERIC(20,2) NOT NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Cpf_supervisor CHAR(9) NULL, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Dnr INT NOT NULL, <br>
); <br>
ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; ADD CONSTRAINT FUNCIONARIO_PK <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; PRIMARY KEY (Cpf); <br>
ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; ADD CONSTRAINT FUNCIONARIO_FK_SUPERVISAO <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; FOREIGN KEY (Cpf_supervisor) REFERENCES FUNCIONARIO(Cpf); <br>
ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; ADD CONSTRAINT FUNCIONARIO_FK_TRABALHA_EM <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; FOREIGN KEY (Dnr) REFERENCES DEPARTAMENTO(Dnumero); <br>
ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; ADD CONSTRAINT FUNCIONARIO_CK_SEXO <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; CHECK Sexo IN ('M','F'); <br>

#### Comandos DDL Exemplo 3

ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; ADD CONSTRAINT FUNCIONARIO_PK <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; PRIMARY KEY (Cpf); <br>
ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; DROP CONSTRAINT FUNCIONARIO_PK; <br>
ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; ADD Email VARCHAR(255) NOT NULL; <br>
ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; ALTER COLUMN Email VARCHAR(255) NULL; <br>
ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; DROP COLUMN Email; <br>
ALTER TABLE FUNCIONARIO <br>
&nbsp;&nbsp;&nbsp;&nbsp; ADD CONSTRAINT FUNCIONARIO_CK_SEXO <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; CHECK (Sexo IN ('M','F')); <br>

### Exercício

Veja o conteúdo do arquivo [empresa.sql](../data/empresa.sql):
- O conteúdo do arquivo possui comandos para a **definição** (criação das estruturas de dados) e **construção** (carga inicial) do **BD Empresa**.
- Há comandos DDL da SQL: CREATE TABLE e ALTER TABLE.
- Há comandos DML da SQL: INSERT.

Vamos executar o conteúdo do arquivo [empresa.sql](../data/empresa.sql), tal que possamos ter um banco de dados em nosso estudo sobre a SQL. Os passos abaixo se referem à ferramenta _SQLiteOnline_, entretanto você pode usar outra ferramenta de sua preferência.

1. Iniciar a _interface_ em https://sqliteonline.com/.
1. Selecionar um SGBD: **MariaDB** ou **PostgreSQL**.
1. Conectar-se ao SGBD selecionado (clique em **_click to connect_**).
1. Copiar o conteúdo do arquivo [empresa.sql](../data/empresa.sql) e colar na área de comandos SQL (parte central da _interface_).
1. Clicar em **&#x27A4;Run** (no _menu_ superior), para executar o conteúdo do arquivo.
1. Checar no menu à esquerda (no SGBD selecionado) se as relações (tabelas) do **BD Empresa** foram criadas.
1. Limpar a área de comandos SQL (parte central da _interface_).

Pronto, o **BD Empresa** foi criado e está pronto para ser manipulado (usado).<br>
**Qual o conteúdo de cada relação (tabela)?**
- Para cada relação do **BD Empresa**, execute o comando SQL<br>&nbsp;&nbsp;&nbsp;&nbsp;**SELECT * FROM _<nome_relação>_;**
  - substitua _<nome_relação>_ por:
    - FUNCIONARIO, DEPARTAMENTO, LOCALIZACAO_DEP, PROJETO, TRABALHA_EM, DEPENDENTE.

## Atividade (data limite: **13/02/2022 23h59min59s**)

Criar uma _issue_ no projeto https://github.com/plinioleitao/bd-2021-2-bec, com o título "Tópico 14", para responder:  

Sistemas Gerenciadores de Banco de Dados (SGBDs) suportam uma variedade de tipos de dados para definir o dominio de atributos. 

1. São exemplos de tipos de dados numéricos: DECIMAL, TINYINT e FLOAT:
- Exemplifique um SGBD que implemente os três tipos de dados.
- Apresente a diferença entre tais tipos de dados.

2. São exemplos de tipos de dados para datas: DATE, DATETIME e SMALLDATETIME:
- Exemplifique um SGBD que implemente os três tipos de dados.
- Apresente a diferença entre tais tipos de dados.

## Artefatos

1. _Issue_ criada no projeto https://github.com/plinioleitao/bd-2021-2-bec, cujo título é "Tópico 14", para explorar os tipos de dados para definir o dominio de atributos.
