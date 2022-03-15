## [Tópico T21a] - Modelo Entidade Relacionamento (MER) - Tipo de entidade fraca
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

Vimos que todo tipo de entidade possui **atributo chave**, o qual é um dos atributos do tipo de entidade, ou uma composição de dois os mais atributos do tipo de entidade. Dois exemplos, respectivamente, são: *(i)* o atributo chave do tipo de entidade VEICULO é o atributo *Placa*; e *(ii)* o atributo chave de MUNICIPIO é composto pelos atributos *Nome da Cidade* e *Estado*.

Entretanto, pode ocorrer que *um tipo de entidade não possua atributo chave próprio*; noutras palavras, dentre os atributos do tipo de entidade, *não há candidatos para ser o atributo chave* (atributo isolado, ou composição de atributos). Nesse caso o tipo de entidade é denominado **Tipo de Entidade Fraca**.<br>
*Obs.:* Chamamos os *tipos de entidade que possuem atributo chave próprio* de **Tipo de Entidade Regular**.

Para ilustrar, considere os dois diagramas (DERs) mostrados a seguir.

<img src="../media/fig-der-entidade-fraca-1.jpg" width="650">

Sobre o DER na Figura (a):
- FUNCIONARIO é um tipo de entidade regular, pois possui atributo chave dentre os seus atributos (no caso, o atributo *CPF*).
- **DEPENDENTE é um tipo de entidade fraca**, pois não possui atributo chave próprio: o atributo *Nome* (sublinhado com linha tracejada) não identifica um dependente, pois os requisitos de dados afirmam que:
  - pode haver dois dependentes com mesmo nome e data de nascimento;
  - um mesmo funcionário não pode ter dois dependentes com o mesmo nome.
-	DEPENDENTE tem **dependência de existência** com o tipo de relacionamento DEPENDENTES_DE (linha dupla entre ambos, pois há **restrição de participação total**), pois qualquer dependente deve estar associado a funcionário.
-	DEPENDENTES_DE é um **Tipo de Relacionamento de Identificação** (um losango com linha dupla), ou seja, é um tipo de relacionamento de identificação para DEPENDENTE.
- Dessa forma, **DEPENDENTE é identificado por: FUNCIONARIO (a partir de DEPENDENTES_DE) em conjunto com o atributo *Nome* em DEPENDENTE**.

Sobre o DER na Figura (b):
- Nem toda dependência de existência resulta em um tipo de entidade fraca. 
- DEPARTAMENTO tem restrição de participação total (dependência de existência) com respeito ao tipo de relacionamento GERENCIA, pois todo departamento deve ter gerente.
- Contudo, DEPARTAMENTO não é um tipo de entidade fraca, pois possui um atributo chave dentre os seus atributos (no caso, o atributo *Numero*).

**Outro exemplo.** Considere uma aplicação simples em que um usuário faz chamadas (ligações) para apresentar algum comentário ou reclamação. Cada chamada possui um registro de tempo (data e horário da ligação, com precisão de milissegundos), um motivo (comentário ou reclamação) e uma descrição. Se houver duas chamadas com o mesmo registro de tempo, tais chamadas devem ser de usuários distintos, ou seja, um mesmo usuário não pode fazer duas chamadas no mesmo registro de tempo (mas pode haver duas chamadas com mesmo registro de tempo). Dois projetistas distintos elaboraram duas soluções diferentes (dois esquemas conceituais), exibidos a seguir.

<img src="../media/fig-der-entidade-fraca-2.jpg" width="700">

Sobre o DER na Figura (a):
- O atributo *DataHora* não é atributo chave de LIGACAO, pois duas ligações podem ter o mesmo registro de tempo se forem de usuários distintos.
- O tipo de entidade LIGACAO não possui um candidato a atributo chave, mesmo com a combinação de atributos (exemplos: *DataHora* e *Motivo*; *DataHora* e *Descricao*, etc.).
- Dessa forma, **LIGACAO é um tipo de entidade fraca** e **FAZ_CHAMADA é um tipo de relacionamento de identificação**: uma ligação é identificada pelo usuário em conjunto com o registro de tempo. 

Sobre o DER na Figura (b):
- O outro projetista criou um **atributo artificial** (um atributo ausente dos requisitos de dados), denominado *Ident*. 
- Dessa forma, LIGACAO não é um tipo de entidade fraca, pois cada entidade desse tipo é identificada pelo valor do atributo *Ident*.
- Atributos artificiais não fazem parte do domínio da aplicação.
- Apesar da decisão do projetista, vale ressaltar que, nesse caso, não há a necessidade de criar um atributo artifical para ser o atributo chave de LIGACAO, pois há alternativa posta no Diagrama (a).

Em ambas as soluções, LIGACAO possui dependência de existência com FAZ_CHAMADA:
- LIGACAO possui restricao de participação total com respeito ao tipo de relacionamento FAZ_CHAMADA (linha dupla entre ambos).
- Contudo, somente na primeira solução - Diagrama (a) - o tipo de entidade LIGACAO é um tipo de entidade fraca.
- Logo, dependência de existência não determina se uma entidade é fraca.

Outro assunto, você consegue interpretar o diagrama abaixo?

<img src="../media/fig-der-entidade-fraca-3.jpg" width="400">

### Exercício

Construa um esquema conceitual, segundo o Modelo Entidade-Relacionamento, para os seguintes requsitos de dados:
- trata-se de um banco de dados simples para um aplicativo de transporte (tipo *Uber*), denominado **BD Transporte Simples**;
- basicamente, o banco de dados possui **percursos**, e cada percurso envolve um motorista, um cliente, data/hora de início, local de origem, local de destino, valor referente ao serviço prestado e data/hora do pagamento;
- dois ou mais percursos podem ter a mesma data/hora de início, desde que sejam de clientes diferentes;
- um cliente pode ter vários percursos;
- um motorista tem um ou mais percursos;
- o esquema do banco de dados deve ter pelo menos um tipo de entidade fraca;
- cliente e motorista têm os mesmos atributos: RG, CPF, nome, data de nascimento, cor preferida;
- algumas consultas típicas são:
  - quais os percursos que ainda não foram pagos?
  - qual a média diária de percursos por cliente?
  - qual a média diária de percursos por motorista?
  - qual o faturamento diário da empresa?

Favor estar atento às diretrizes abaixo:
- Empregue a notação para o DER paraque foi apresentada no [Tópico 20](./topico-20.md).
- Use a ferramenta que desejar, desde que a especificação do DER tenha precisamente a notação solicitada.
- Sugestão: use a ferramenta [Dia](http://dia-installer.de/), que é uma ferramenta de desenho:
  - para especificar o DER, selecione a *Folha* **ER** (em vez da *Folha* **Banco de Dados**);
  - ao final, exporte o desenho para um arquivo JPG, para ter a imagem do DER.

## Não há atividade para este tópico, excepcionalmente.
