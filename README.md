# ENTREGA-2-MODELO-L-GICO-IMPLEMENTA-O-SQL-E-APRESENTA-O-FINAL

# ENTREGA 2 — MODELO LÓGICO, IMPLEMENTAÇÃO SQL E APRESENTAÇÃO FINAL

<box gap={1}> <title size="2xl">Alberic Gastrobar</title> **Projeto Acadêmico — Banco de Dados**

Integrantes:

Daniel Baptista dos Santos — RGM 48821756
Eloise Abreu Rodrigues — RGM 49482602
Fernando Simoes de Menezes — RGM 49617133
Nathaly Pereira — RGM 47287560
Yasmin Jimenez Negrão — RGM 49595407
<badge color="success">Continuidade da Entrega 1</badge> <text color="secondary" size="xs">SGBD: MySQL 8.0 | Modelo relacional | Dados fictícios</text> </box>

A seguir está o início do relatório técnico, estruturado para ser utilizado no README.md do repositório.

1. RELATÓRIO TÉCNICO FINAL
1.1 Revisão do Modelo Conceitual
Caracterização da organização
Nome: Alberic Gastrobar.

Natureza: Estabelecimento do ramo gastronômico, com atuação no segmento de bar e restaurante.

Atividade principal: Comercialização de alimentos e bebidas, atendimento presencial, preparação de pedidos e prestação de serviços de alimentação.

Contexto operacional

O Alberic Gastrobar possui processos operacionais que envolvem atendimento ao público, gerenciamento de mesas, abertura de comandas, registro de pedidos, preparação de produtos, controle de estoque, aquisição de mercadorias, pagamentos e gerenciamento de funcionários.

A operação depende da integração entre diferentes setores, como salão, cozinha, bar e caixa. Cada setor participa de uma etapa do atendimento, desde o registro do pedido até a finalização da comanda.

Para o desenvolvimento do sistema, consideramos os seguintes módulos:

Atendimento e gerenciamento de mesas.
Registro e acompanhamento de comandas.
Cadastro e gerenciamento de pedidos.
Controle do cardápio e produtos.
Gerenciamento de funcionários.
Controle de escalas de trabalho.
Gerenciamento de estoque.
Registro de movimentações de estoque.
Controle de fornecedores e compras.
Gerenciamento financeiro.
Registro de pagamentos.
Fechamento de caixa.
Registro de ocorrências operacionais.
Observação para completar com a pesquisa de campo: os números reais de funcionários, mesas, pedidos diários, compras mensais e produtos cadastrados devem ser confirmados com o responsável. Não utilizaremos números inventados como evidência da operação.

Problemas e necessidades identificados
Para orientar o desenvolvimento do banco de dados, foram definidos os seguintes problemas de gestão a serem validados com a organização:


Código	Problema identificado	Solução proposta
P1	Dificuldade de acompanhar mesas e comandas.	Cadastro de mesas e controle de comandas.
P2	Falta de acompanhamento centralizado dos pedidos.	Registro de pedidos e itens.
P3	Dificuldade de controlar produtos e preços do cardápio.	Cadastro de categorias e produtos.
P4	Dificuldade de acompanhar o estoque.	Controle de saldos e movimentações.
P5	Falta de histórico organizado de compras.	Cadastro de fornecedores e compras.
P6	Dificuldade de acompanhar pagamentos.	Registro de pagamentos por comanda.
P7	Falta de controle organizado das escalas.	Cadastro de funcionários e escalas.
P8	Dificuldade de conferir os valores do caixa.	Registro de fechamentos e diferenças.
P9	Falta de histórico de ocorrências operacionais.	Registro de ocorrências e providências.
Esses problemas constituem a proposta de investigação e deverão ser confirmados na entrevista. A rastreabilidade será apresentada na seção 1.6.

Escopo do sistema
O sistema proposto tem como objetivo centralizar as informações operacionais e administrativas do Alberic Gastrobar.

O banco de dados contemplará os seguintes módulos:

Atendimento e salão.
Cardápio e produtos.
Funcionários e escalas.
Estoque e movimentações.
Compras e fornecedores.
Pagamentos e contas a pagar.
Fechamento de caixa.
Ocorrências administrativas.
O escopo contempla tanto as operações diretamente relacionadas ao atendimento quanto os processos internos necessários para a administração do estabelecimento.

Justificativa da escolha
Escolhemos o Alberic Gastrobar por ser um estabelecimento do segmento gastronômico que apresenta diferentes processos interligados e que podem ser organizados por meio de um banco de dados relacional.

O projeto permite aplicar conceitos de modelagem de dados em situações práticas, como relacionamentos entre pedidos e produtos, controle de estoque, movimentações financeiras e gerenciamento de funcionários.

Além disso, a integração dessas informações possibilita desenvolver consultas gerenciais que auxiliam na tomada de decisões.

Evidências obrigatórias a acrescentar pelo grupo:

Endereço completo do estabelecimento.
Link do perfil comercial ou página oficial.
Fotografias próprias do estabelecimento.
Fotografia da entrevista presencial.
Nome e telefone do responsável que autorizou o levantamento.
Resumo dos processos de negócio

Processo	Descrição	Tabelas relacionadas
Atendimento	Identificação da mesa e abertura da comanda.	MESA, COMANDA
Registro de pedidos	Lançamento dos pedidos e identificação do atendente.	PEDIDO, ITEM_PEDIDO
Preparação	Encaminhamento dos produtos aos setores responsáveis.	PRODUTO, SETOR, ITEM_PEDIDO
Controle de cardápio	Cadastro de categorias, produtos e preços.	CATEGORIA, PRODUTO
Gestão de pessoal	Cadastro e acompanhamento dos funcionários.	FUNCIONARIO, ESCALA_FUNCIONARIO
Controle de estoque	Registro de saldo e movimentações.	ESTOQUE, MOVIMENTACAO_ESTOQUE
Compras	Registro de fornecedores e mercadorias adquiridas.	FORNECEDOR, COMPRA, ITEM_COMPRA
Financeiro	Controle de pagamentos e obrigações.	PAGAMENTO, CONTA_PAGAR
Caixa	Conferência dos valores recebidos.	FECHAMENTO_CAIXA
Ocorrências	Registro de situações excepcionais e providências.	OCORRENCIA
Requisitos funcionais

Código	Requisito
RF01	O sistema deve permitir cadastrar mesas com número, capacidade, status e observação.
RF02	O sistema deve permitir abrir e fechar comandas, registrando mesa, data de abertura, data de fechamento e status.
RF03	O sistema deve permitir registrar pedidos com comanda, funcionário responsável, data, status e observação.
RF04	O sistema deve permitir incluir itens nos pedidos com produto, quantidade, preço unitário, status e observação.
RF05	O sistema deve permitir cadastrar categorias com nome, descrição e situação de atividade.
RF06	O sistema deve permitir cadastrar produtos com categoria, setor, nome, descrição, preço e disponibilidade.
RF07	O sistema deve permitir cadastrar funcionários com nome, função, setor, login e situação de atividade.
RF08	O sistema deve permitir registrar escalas com funcionário, início, término, função e status.
RF09	O sistema deve permitir cadastrar estoques com produto, quantidade, unidade de medida e estoque mínimo.
RF10	O sistema deve registrar movimentações de estoque com tipo, quantidade, funcionário, data e motivo.
RF11	O sistema deve permitir cadastrar fornecedores com razão social, documento, telefone, e-mail e endereço.
RF12	O sistema deve permitir registrar compras com fornecedor, funcionário, data, previsão de entrega e valor.
RF13	O sistema deve permitir detalhar compras com produto, quantidade solicitada, quantidade recebida e custo unitário.
RF14	O sistema deve registrar pagamentos de comandas com forma, valor, data e referência da transação.
RF15	O sistema deve permitir registrar contas a pagar com fornecedor, compra, vencimento, valor e situação.
RF16	O sistema deve permitir registrar fechamentos de caixa com valores do sistema, valores conferidos e diferenças.
RF17	O sistema deve permitir registrar ocorrências com funcionário responsável, descrição, providência e eventual valor de cortesia.
RF18	O sistema deve disponibilizar consultas para acompanhamento das operações e geração de informações gerenciais.
Requisitos não funcionais

Código	Requisito
RNF01	O banco de dados deverá ser implementado no MySQL 8.0.
RNF02	As informações deverão possuir integridade referencial por meio de chaves primárias e estrangeiras.
RNF03	Os dados financeiros deverão utilizar tipos numéricos com precisão decimal.
RNF04	O sistema deverá permitir consultas sobre os registros históricos.
RNF05	As credenciais de acesso deverão ser armazenadas por meio de hashes seguros, nunca em texto puro.
RNF06	O sistema deverá utilizar restrições para impedir registros inconsistentes.
RNF07	O banco deverá possuir estrutura que permita futuras expansões dos módulos.
RNF08	O acesso aos dados pessoais e financeiros deverá respeitar os princípios da LGPD.
Regras de negócio

Código	Regra
RN01	Cada mesa deverá possuir um número de identificação único.
RN02	Uma comanda deverá estar associada a uma mesa existente.
RN03	Uma comanda poderá possuir vários pedidos.
RN04	Todo pedido deverá estar associado a uma comanda e a um funcionário responsável.
RN05	Todo item de pedido deverá estar associado a um pedido e a um produto existente.
RN06	A quantidade de um item de pedido deverá ser maior que zero.
RN07	O preço unitário registrado no item deverá preservar o valor praticado no momento do pedido.
RN08	Cada produto deverá pertencer a uma categoria e a um setor.
RN09	Cada produto deverá possuir somente um registro de estoque.
RN10	As movimentações deverão possuir tipo, quantidade, funcionário e motivo.
RN11	A quantidade de movimentação deverá ser maior que zero.
RN12	Toda compra deverá possuir um fornecedor e um funcionário responsável.
RN13	A quantidade recebida de uma compra não poderá superar a quantidade solicitada.
RN14	Todo pagamento deverá estar associado a uma comanda existente.
RN15	O valor de um pagamento deverá ser maior que zero.
RN16	O valor da diferença do caixa deverá corresponder ao valor conferido menos o valor do sistema.
RN17	Toda ocorrência deverá possuir descrição, providência e funcionário responsável.
RN18	Registros históricos de pedidos e movimentações não deverão ser apagados indiscriminadamente.
RN19	Os status e formas de pagamento deverão respeitar os valores permitidos pelo sistema.
RN20	As informações pessoais e credenciais deverão ser protegidas conforme as normas de privacidade aplicáveis.
Processos típicos não incluídos
Não foram acrescentados processos de delivery, reservas on-line, emissão fiscal ou programa de fidelidade ao modelo apresentado, pois não há confirmação de que façam parte da operação abrangida pelo levantamento original.

Esses processos poderão ser incorporados futuramente caso a organização confirme sua necessidade.

Entrevista e levantamento de campo
O levantamento deverá registrar a entrevista presencial com o responsável pelo estabelecimento, identificando os participantes, a data, o local e as informações observadas.

O documento completo será disponibilizado em levantamento/levantamento.md.

Campos que o grupo precisa preencher com dados reais:

Nome e função do entrevistado.
Data da entrevista.
Endereço do estabelecimento.
Integrantes presentes.
Fotografia da visita.
Processos efetivamente observados.
Nome e telefone do responsável.
1.2 Conversão do modelo conceitual para o modelo lógico
O modelo conceitual da Entrega 1 foi utilizado como referência para a construção do modelo lógico relacional.

A conversão foi realizada considerando as regras de transformação do modelo entidade-relacionamento para o modelo relacional.

Entidades transformadas em tabelas
Cada entidade do modelo foi convertida em uma tabela independente, com uma chave primária responsável pela identificação única de cada registro.

Foram mantidas as 18 tabelas originais:


Nº	Entidade	Tabela relacional
1	Mesa	MESA
2	Comanda	COMANDA
3	Pedido	PEDIDO
4	Item do pedido	ITEM_PEDIDO
5	Categoria	CATEGORIA
6	Setor	SETOR
7	Produto	PRODUTO
8	Funcionário	FUNCIONARIO
9	Escala de funcionário	ESCALA_FUNCIONARIO
10	Estoque	ESTOQUE
11	Movimentação de estoque	MOVIMENTACAO_ESTOQUE
12	Fornecedor	FORNECEDOR
13	Compra	COMPRA
14	Item da compra	ITEM_COMPRA
15	Pagamento	PAGAMENTO
16	Conta a pagar	CONTA_PAGAR
17	Fechamento de caixa	FECHAMENTO_CAIXA
18	Ocorrência	OCORRENCIA
Conversão dos relacionamentos
Os relacionamentos foram implementados por meio de chaves estrangeiras.

Relacionamentos 1:N: a chave primária da tabela do lado 1 foi adicionada como chave estrangeira na tabela do lado N.
Relacionamentos N:N: foram transformados em tabelas associativas, como ITEM_PEDIDO e ITEM_COMPRA.
Relacionamento 1:1: foi implementado por meio de uma chave estrangeira com restrição UNIQUE, como ocorre entre PRODUTO e ESTOQUE.
Generalização e especialização
O modelo apresentado não possui generalização ou especialização. Portanto, não foi necessária a aplicação de estratégias de conversão específicas para herança de entidades.

1.3 Definição de chaves primárias e estrangeiras

Tabela	Chave primária	Chaves estrangeiras
MESA	id_mesa	—
COMANDA	id_comanda	id_mesa
PEDIDO	id_pedido	id_comanda, id_funcionario
ITEM_PEDIDO	id_item_pedido	id_pedido, id_produto
CATEGORIA	id_categoria	—
SETOR	id_setor	—
PRODUTO	id_produto	id_categoria, id_setor
FUNCIONARIO	id_funcionario	id_setor
ESCALA_FUNCIONARIO	id_escala	id_funcionario
ESTOQUE	id_estoque	id_produto
MOVIMENTACAO_ESTOQUE	id_movimentacao	id_estoque, id_produto, id_funcionario
FORNECEDOR	id_fornecedor	—
COMPRA	id_compra	id_fornecedor, id_funcionario
ITEM_COMPRA	id_item_compra	id_compra, id_produto
PAGAMENTO	id_pagamento	id_comanda
CONTA_PAGAR	id_conta_pagar	id_fornecedor, id_compra
FECHAMENTO_CAIXA	id_fechamento	id_funcionario
OCORRENCIA	id_ocorrencia	id_comanda, id_funcionario, autorizado_por
As chaves primárias foram definidas utilizando identificadores numéricos com incremento automático, garantindo identificação individual dos registros e facilitando os relacionamentos entre as tabelas.

As chaves estrangeiras foram utilizadas para garantir a integridade referencial e impedir associações com registros inexistentes.

1.4 Processo de normalização (1FN, 2FN e 3FN)
A normalização foi aplicada para organizar os dados, reduzir redundâncias e evitar anomalias de inserção, atualização e exclusão.

Primeira Forma Normal (1FN)
Para atender à Primeira Forma Normal, todas as tabelas foram estruturadas de maneira que cada coluna contenha apenas um valor por registro.

Foram adotadas as seguintes decisões:

Cada funcionário possui um registro individual na tabela FUNCIONARIO.
Cada produto possui um registro individual na tabela PRODUTO.
Os produtos de um pedido foram separados na tabela ITEM_PEDIDO.
Os produtos de uma compra foram separados na tabela ITEM_COMPRA.
As movimentações de estoque foram separadas em registros individuais.
Os pagamentos foram armazenados individualmente na tabela PAGAMENTO.
Exemplo: em vez de armazenar vários produtos em uma única coluna do pedido, cada produto é registrado em uma linha de ITEM_PEDIDO, associado ao pedido correspondente.

Segunda Forma Normal (2FN)
A Segunda Forma Normal exige que todos os atributos não-chave dependam integralmente da chave primária.

Como as tabelas utilizam identificadores próprios, os atributos de cada tabela dependem de sua respectiva chave primária.

Nas tabelas associativas, os dados específicos de cada relação foram separados.

Exemplo:

A tabela ITEM_PEDIDO possui:

id_item_pedido;
id_pedido;
id_produto;
quantidade;
preco_unitario;
status;
observacao_item.
A quantidade e o preço praticado pertencem à ocorrência do produto no pedido, e não ao cadastro geral do produto.

Dessa forma, conseguimos preservar o histórico comercial.

Terceira Forma Normal (3FN)
Para atender à Terceira Forma Normal, os atributos não-chave devem depender diretamente da chave primária, sem dependências transitivas.

Foram adotadas as seguintes separações:

Os dados das categorias permanecem na tabela CATEGORIA.
Os dados dos setores permanecem na tabela SETOR.
Os dados dos fornecedores permanecem na tabela FORNECEDOR.
Os dados dos funcionários permanecem na tabela FUNCIONARIO.
As informações dos produtos são armazenadas em PRODUTO.
As informações das compras são armazenadas em COMPRA e ITEM_COMPRA.
Por exemplo, o nome da categoria não é repetido em todos os produtos. O produto armazena apenas a referência à categoria por meio de id_categoria.

Justificativa da normalização
A normalização foi necessária porque o estabelecimento trabalha com informações de diferentes setores que se relacionam entre si.

Sem essa organização, informações como fornecedores, produtos, funcionários e categorias poderiam ser repetidas em diversas operações.

A estrutura normalizada permite:

Reduzir a duplicação de dados.
Facilitar a manutenção das informações.
Evitar inconsistências nos registros.
Preservar o histórico das operações.
Melhorar a integridade dos relacionamentos.
Facilitar a elaboração de relatórios gerenciais.
1.5 Justificativas técnicas das decisões
Justificativa das chaves primárias
Foram utilizados identificadores numéricos com AUTO_INCREMENT como chaves primárias.

Essa decisão foi adotada porque os identificadores numéricos são simples de gerenciar, permitem relacionamentos eficientes e não dependem de informações que podem ser alteradas.

Por exemplo, o nome de um funcionário pode mudar, mas seu identificador interno permanece o mesmo.

Justificativa das chaves estrangeiras
As chaves estrangeiras garantem que os registros relacionados existam nas tabelas de origem.

Exemplos:

COMANDA referencia MESA.
PEDIDO referencia COMANDA e FUNCIONARIO.
ITEM_PEDIDO referencia PEDIDO e PRODUTO.
PRODUTO referencia CATEGORIA e SETOR.
ESTOQUE referencia PRODUTO.
COMPRA referencia FORNECEDOR e FUNCIONARIO.
PAGAMENTO referencia COMANDA.
Esses relacionamentos impedem a criação de registros que apontem para entidades inexistentes.

Justificativa das restrições

Restrição	Aplicação	Regra relacionada
PRIMARY KEY	Identificação individual de registros.	Integridade dos registros
FOREIGN KEY	Relacionamento entre entidades.	RN02 a RN17
UNIQUE	Número de mesa, nome de categoria, setor, login e estoque por produto.	RN01 e RN09
NOT NULL	Campos obrigatórios.	RN02, RN04, RN05 e demais regras aplicáveis
CHECK	Quantidades, valores e status permitidos.	RN06, RN10, RN11, RN13, RN15 e RN16
DEFAULT	Valores iniciais de status e datas.	Regras operacionais
ON DELETE RESTRICT	Proteção de registros históricos relacionados.	RN18
Decisões arquiteturais
A arquitetura foi desenvolvida utilizando o modelo relacional, com tabelas separadas por domínio de informação.

A escolha do MySQL 8.0 ocorreu por sua ampla utilização em aplicações comerciais, suporte a integridade referencial, transações, índices e consultas relacionais.

Outra decisão foi preservar o preço de venda no momento em que o item é registrado. Assim, caso o preço do produto seja alterado posteriormente, o histórico das vendas não será modificado.

Também foi adotado o registro individual dos pagamentos, permitindo que uma mesma comanda receba mais de um pagamento.

Ajuste técnico importante: na tabela MOVIMENTACAO_ESTOQUE, será mantida somente a FK id_estoque para identificar o produto por meio do relacionamento com ESTOQUE. Isso elimina a redundância da FK id_produto, pois ESTOQUE já identifica unicamente o produto.

1.6 Proposta de arquitetura analítica para BI e IA
A estrutura desenvolvida possibilita transformar os registros operacionais em informações estratégicas para a administração do Alberic Gastrobar.

A integração entre pedidos, produtos, estoque, compras e pagamentos permite acompanhar o desempenho da operação e identificar oportunidades de melhoria.

Informações estratégicas
As principais informações que podem ser extraídas são:

Produtos com maior volume de vendas.
Produtos com menor saída.
Faturamento por período.
Formas de pagamento mais utilizadas.
Quantidade de comandas encerradas.
Produtos abaixo do estoque mínimo.
Gastos com fornecedores.
Contas a pagar próximas do vencimento.
Diferenças entre valores previstos e conferidos no caixa.
Quantidade de cancelamentos e ocorrências.
Indicadores de desempenho (KPIs)

Código	Indicador	Fórmula	Periodicidade
KPI01	Faturamento total	Soma dos pagamentos concluídos.	Diário e mensal
KPI02	Ticket médio por comanda	Faturamento ÷ comandas pagas.	Diário e mensal
KPI03	Produto mais vendido	Maior quantidade vendida por produto.	Mensal
KPI04	Taxa de cancelamento	Pedidos cancelados ÷ pedidos totais × 100.	Mensal
KPI05	Produtos abaixo do mínimo	Quantidade de produtos com saldo inferior ao mínimo.	Diário
KPI06	Gastos com compras	Soma dos valores das compras recebidas.	Mensal
KPI07	Contas a pagar pendentes	Soma das contas ainda não pagas.	Semanal
KPI08	Diferença de caixa	Valor conferido − valor do sistema.	Por fechamento
KPI09	Volume de pagamentos por forma	Quantidade de pagamentos por modalidade.	Mensal
KPI10	Tempo médio de atendimento	Média do intervalo entre abertura e fechamento das comandas.	Diário e mensal
Potencial para Business Intelligence
A estrutura poderá ser integrada futuramente a ferramentas como Power BI e Looker Studio.

Os painéis poderão apresentar:

Gráficos de faturamento diário e mensal.
Ranking de produtos vendidos.
Comparação entre compras e vendas.
Alertas de estoque baixo.
Acompanhamento de contas a pagar.
Relatórios de fechamento de caixa.
Aplicações de inteligência artificial
A organização dos dados também permite futuras aplicações de inteligência artificial.

Previsão de demanda: utilizar o histórico de vendas para estimar a quantidade de produtos que poderão ser vendidos em determinados dias.

Previsão de estoque: identificar padrões de consumo e antecipar a necessidade de reposição.

Análise de desempenho: identificar produtos com baixa saída e horários com maior movimento.

Identificação de anomalias: detectar diferenças incomuns nos fechamentos de caixa e movimentações de estoque.

Essas aplicações dependeriam de volume histórico suficiente, qualidade dos dados e validação dos resultados. O banco de dados fornece a base, mas não implementa sozinho esses modelos de IA.

Tabela de rastreabilidade

Problema ou KPI	Tabelas envolvidas	Consulta
P1 — Controle de mesas e comandas	MESA, COMANDA	G01
P2 — Acompanhamento dos pedidos	PEDIDO, ITEM_PEDIDO	G02
P3 — Controle de produtos	PRODUTO, CATEGORIA	G03
P4 — Controle de estoque	ESTOQUE, PRODUTO	G04
P5 — Histórico de compras	COMPRA, ITEM_COMPRA, FORNECEDOR	G05
P6 — Acompanhamento financeiro	PAGAMENTO, COMANDA	G06
P7 — Controle de escalas	FUNCIONARIO, ESCALA_FUNCIONARIO	G07
P8 — Conferência do caixa	FECHAMENTO_CAIXA	G08
P9 — Histórico de ocorrências	OCORRENCIA, FUNCIONARIO	G09
KPI01 — Faturamento	PAGAMENTO	G06
KPI02 — Ticket médio	PAGAMENTO, COMANDA	G06
KPI03 — Produtos mais vendidos	ITEM_PEDIDO, PRODUTO, PEDIDO	G02
KPI04 — Cancelamentos	PEDIDO	G10
KPI05 — Estoque abaixo do mínimo	ESTOQUE, PRODUTO	G04
KPI06 — Gastos com compras	COMPRA, FORNECEDOR	G05
KPI07 — Contas pendentes	CONTA_PAGAR, FORNECEDOR	G11
KPI08 — Diferença de caixa	FECHAMENTO_CAIXA	G08
KPI09 — Formas de pagamento	PAGAMENTO	G12
KPI10 — Tempo de atendimento	COMANDA	G13
Os códigos acima serão utilizados no script SQL da próxima seção.

2. MODELO LÓGICO RELACIONAL
O modelo lógico relacional representa a organização dos dados em tabelas, colunas, tipos de dados, chaves primárias e chaves estrangeiras.

Para sua elaboração, foi utilizada como referência a notação do brModelo.

Software recomendado para o diagrama: brModelo Web ou brModelo Desktop.

2.1 Estrutura das relações
O modelo contém 18 tabelas organizadas em cinco conjuntos funcionais:

<box border radius="lg" padding={3} gap={3}> **Atendimento e salão** <row wrap="wrap" gap={1}> <badge>MESA</badge> <badge>COMANDA</badge> <badge>PEDIDO</badge> <badge>ITEM_PEDIDO</badge> </row> <divider color="subtle"/> **Cardápio e estrutura operacional** <row wrap="wrap" gap={1}> <badge>CATEGORIA</badge> <badge>SETOR</badge> <badge>PRODUTO</badge> </row> <divider color="subtle"/> **Pessoal e escalas** <row wrap="wrap" gap={1}> <badge>FUNCIONARIO</badge> <badge>ESCALA_FUNCIONARIO</badge> </row> <divider color="subtle"/> **Estoque e compras** <row wrap="wrap" gap={1}> <badge>ESTOQUE</badge> <badge>MOVIMENTACAO_ESTOQUE</badge> <badge>FORNECEDOR</badge> <badge>COMPRA</badge> <badge>ITEM_COMPRA</badge> </row> <divider color="subtle"/> **Financeiro e ocorrências** <row wrap="wrap" gap={1}> <badge>PAGAMENTO</badge> <badge>CONTA_PAGAR</badge> <badge>FECHAMENTO_CAIXA</badge> <badge>OCORRENCIA</badge> </row> </box>

2.2 Relacionamentos e cardinalidades

Relacionamento	Cardinalidade
MESA — COMANDA	1:N
COMANDA — PEDIDO	1:N
FUNCIONARIO — PEDIDO	1:N
PEDIDO — ITEM_PEDIDO	1:N
PRODUTO — ITEM_PEDIDO	1:N
CATEGORIA — PRODUTO	1:N
SETOR — PRODUTO	1:N
SETOR — FUNCIONARIO	1:N, funcionário pode não possuir setor
FUNCIONARIO — ESCALA_FUNCIONARIO	1:N
PRODUTO — ESTOQUE	1:1
ESTOQUE — MOVIMENTACAO_ESTOQUE	1:N
FUNCIONARIO — MOVIMENTACAO_ESTOQUE	1:N
FORNECEDOR — COMPRA	1:N
FUNCIONARIO — COMPRA	1:N
COMPRA — ITEM_COMPRA	1:N
PRODUTO — ITEM_COMPRA	1:N
COMANDA — PAGAMENTO	1:N
FORNECEDOR — CONTA_PAGAR	1:N
COMPRA — CONTA_PAGAR	1:N, compra opcional na conta
FUNCIONARIO — FECHAMENTO_CAIXA	1:N
COMANDA — OCORRENCIA	1:N, comanda opcional
FUNCIONARIO — OCORRENCIA	1:N
FUNCIONARIO — OCORRENCIA (autorizador)	1:N, autorizador opcional
2.3 Orientação para desenhar no brModelo
Ao montar o arquivo visual, utilize:

Retângulos para representar as 18 tabelas.
Nome das tabelas na parte superior.
Colunas com seus respectivos tipos.
Identificação PK nas chaves primárias.
Identificação FK nas chaves estrangeiras.
Ligações entre as tabelas com suas cardinalidades.
Identificação PK, FK quando uma coluna desempenhar as duas funções.
O diagrama deve ser exportado em PNG e salvo como:

diagramas/modelo_logico.png

Importante: o esquema acima especifica o conteúdo do diagrama, mas ainda precisa ser desenhado e exportado no brModelo para atender à exigência visual da atividade.

3. SCRIPT SQL COMPLETO
O script abaixo implementa a estrutura principal do banco de dados no MySQL 8.0.

Ele contempla as 18 tabelas, suas relações, restrições de integridade, dados fictícios e consultas gerenciais e de auditoria.

Salve o conteúdo em docs/script.sql.

3.1 Criação do banco de dados e tabelas
<CodeBlock language="sql" editable> -- ========================================================== -- PROJETO: ALBERIC GASTROBAR -- ENTREGA 2 - BANCO DE DADOS -- SGBD: MYSQL 8.0 -- ==========================================================

CREATE DATABASE IF NOT EXISTS alberic_gastrobar CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

USE alberic_gastrobar;

SET FOREIGN_KEY_CHECKS = 0;

DROP TABLE IF EXISTS OCORRENCIA; DROP TABLE IF EXISTS FECHAMENTO_CAIXA; DROP TABLE IF EXISTS CONTA_PAGAR; DROP TABLE IF EXISTS PAGAMENTO; DROP TABLE IF EXISTS ITEM_COMPRA; DROP TABLE IF EXISTS COMPRA; DROP TABLE IF EXISTS MOVIMENTACAO_ESTOQUE; DROP TABLE IF EXISTS ESTOQUE; DROP TABLE IF EXISTS ESCALA_FUNCIONARIO; DROP TABLE IF EXISTS ITEM_PEDIDO; DROP TABLE IF EXISTS PEDIDO; DROP TABLE IF EXISTS PRODUTO; DROP TABLE IF EXISTS FUNCIONARIO; DROP TABLE IF EXISTS FORNECEDOR; DROP TABLE IF EXISTS SETOR; DROP TABLE IF EXISTS CATEGORIA; DROP TABLE IF EXISTS COMANDA; DROP TABLE IF EXISTS MESA;

SET FOREIGN_KEY_CHECKS = 1;

-- ========================================================== -- 1. ATENDIMENTO E SALÃO -- ==========================================================

CREATE TABLE MESA ( id_mesa INT AUTO_INCREMENT PRIMARY KEY, numero INT NOT NULL UNIQUE, capacidade INT NOT NULL, status VARCHAR(20) NOT NULL DEFAULT 'LIVRE', observacao VARCHAR(255),


CONSTRAINT chk_mesa_capacidade
    CHECK (capacidade > 0),

CONSTRAINT chk_mesa_status
    CHECK (status IN ('LIVRE','OCUPADA','RESERVADA'))
) ENGINE=InnoDB;

CREATE TABLE COMANDA ( id_comanda INT AUTO_INCREMENT PRIMARY KEY, id_mesa INT NOT NULL, aberta_em DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP, fechada_em DATETIME, status VARCHAR(30) NOT NULL DEFAULT 'ABERTA',


CONSTRAINT fk_comanda_mesa
    FOREIGN KEY (id_mesa)
    REFERENCES MESA(id_mesa)
    ON DELETE RESTRICT
    ON UPDATE CASCADE,

CONSTRAINT chk_comanda_status
    CHECK (status IN (
        'ABERTA',
        'AGUARDANDO_PAGAMENTO',
        'FECHADA',
        'CANCELADA'
    )),

CONSTRAINT chk_comanda_datas
    CHECK (fechada_em IS NULL OR fechada_em >= aberta_em)
) ENGINE=InnoDB;

CREATE TABLE PEDIDO ( id_pedido INT AUTO_INCREMENT PRIMARY KEY, id_comanda INT NOT NULL, id_funcionario INT NOT NULL, criado_em DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP, status VARCHAR(20) NOT NULL DEFAULT 'ENVIADO', observacao VARCHAR(255),


CONSTRAINT fk_pedido_comanda
    FOREIGN KEY (id_comanda)
    REFERENCES COMANDA(id_comanda)
    ON DELETE RESTRICT,

CONSTRAINT chk_pedido_status
    CHECK (status IN (
        'ENVIADO',
        'EM_PREPARO',
        'PRONTO',
        'ENTREGUE',
        'CANCELADO'
    ))
) ENGINE=InnoDB;

CREATE TABLE ITEM_PEDIDO ( id_item_pedido INT AUTO_INCREMENT PRIMARY KEY, id_pedido INT NOT NULL, id_produto INT NOT NULL, quantidade DECIMAL(10,3) NOT NULL, preco_unitario DECIMAL(10,2) NOT NULL, status VARCHAR(20) NOT NULL DEFAULT 'PENDENTE', observacao_item VARCHAR(150),


CONSTRAINT fk_itempedido_pedido
    FOREIGN KEY (id_pedido)
    REFERENCES PEDIDO(id_pedido)
    ON DELETE RESTRICT,

CONSTRAINT chk_itempedido_quantidade
    CHECK (quantidade > 0),

CONSTRAINT chk_itempedido_preco
    CHECK (preco_unitario >= 0),

CONSTRAINT chk_itempedido_status
    CHECK (status IN (
        'PENDENTE',
        'EM_PREPARO',
        'PRONTO',
        'ENTREGUE',
        'CANCELADO'
    ))
) ENGINE=InnoDB;

-- ========================================================== -- 2. CARDÁPIO E ESTRUTURA OPERACIONAL -- ==========================================================

CREATE TABLE CATEGORIA ( id_categoria INT AUTO_INCREMENT PRIMARY KEY, nome VARCHAR(50) NOT NULL UNIQUE, descricao VARCHAR(255), ativa BOOLEAN NOT NULL DEFAULT TRUE ) ENGINE=InnoDB;

CREATE TABLE SETOR ( id_setor INT AUTO_INCREMENT PRIMARY KEY, nome VARCHAR(50) NOT NULL UNIQUE, descricao VARCHAR(255), ativo BOOLEAN NOT NULL DEFAULT TRUE ) ENGINE=InnoDB;

CREATE TABLE PRODUTO ( id_produto INT AUTO_INCREMENT PRIMARY KEY, id_categoria INT NOT NULL, id_setor INT NOT NULL, nome VARCHAR(100) NOT NULL, descricao TEXT, preco_venda DECIMAL(10,2) NOT NULL, disponivel BOOLEAN NOT NULL DEFAULT TRUE,


CONSTRAINT fk_produto_categoria
    FOREIGN KEY (id_categoria)
    REFERENCES CATEGORIA(id_categoria)
    ON DELETE RESTRICT,

CONSTRAINT fk_produto_setor
    FOREIGN KEY (id_setor)
    REFERENCES SETOR(id_setor)
    ON DELETE RESTRICT,

CONSTRAINT chk_produto_preco
    CHECK (preco_venda >= 0)
) ENGINE=InnoDB;

-- ========================================================== -- 3. PESSOAL E ESCALAS -- ==========================================================

CREATE TABLE FUNCIONARIO ( id_funcionario INT AUTO_INCREMENT PRIMARY KEY, id_setor INT, nome VARCHAR(100) NOT NULL, funcao VARCHAR(50) NOT NULL, usuario_login VARCHAR(50) UNIQUE, senha_hash VARCHAR(255), ativo BOOLEAN NOT NULL DEFAULT TRUE,


CONSTRAINT fk_funcionario_setor
    FOREIGN KEY (id_setor)
    REFERENCES SETOR(id_setor)
    ON DELETE RESTRICT
) ENGINE=InnoDB;

ALTER TABLE PEDIDO ADD CONSTRAINT fk_pedido_funcionario FOREIGN KEY (id_funcionario) REFERENCES FUNCIONARIO(id_funcionario) ON DELETE RESTRICT;

CREATE TABLE ESCALA_FUNCIONARIO ( id_escala INT AUTO_INCREMENT PRIMARY KEY, id_funcionario INT NOT NULL, inicio DATETIME NOT NULL, fim DATETIME NOT NULL, funcao_turno VARCHAR(50) NOT NULL, status VARCHAR(20) NOT NULL DEFAULT 'PREVISTO',


CONSTRAINT fk_escala_funcionario
    FOREIGN KEY (id_funcionario)
    REFERENCES FUNCIONARIO(id_funcionario)
    ON DELETE RESTRICT,

CONSTRAINT chk_escala_periodo
    CHECK (fim > inicio),

CONSTRAINT chk_escala_status
    CHECK (status IN (
        'PREVISTO',
        'CONFIRMADO',
        'REALIZADO',
        'FALTA'
    ))
) ENGINE=InnoDB;

-- ========================================================== -- 4. ESTOQUE E COMPRAS -- ==========================================================

CREATE TABLE ESTOQUE ( id_estoque INT AUTO_INCREMENT PRIMARY KEY, id_produto INT NOT NULL UNIQUE, quantidade_atual DECIMAL(10,3) NOT NULL DEFAULT 0, unidade_medida VARCHAR(15) NOT NULL, estoque_minimo DECIMAL(10,3),


CONSTRAINT fk_estoque_produto
    FOREIGN KEY (id_produto)
    REFERENCES PRODUTO(id_produto)
    ON DELETE RESTRICT,

CONSTRAINT chk_estoque_quantidade
    CHECK (quantidade_atual >= 0),

CONSTRAINT chk_estoque_minimo
    CHECK (estoque_minimo IS NULL OR estoque_minimo >= 0)
) ENGINE=InnoDB;

CREATE TABLE MOVIMENTACAO_ESTOQUE ( id_movimentacao INT AUTO_INCREMENT PRIMARY KEY, id_estoque INT NOT NULL, id_funcionario INT NOT NULL, tipo VARCHAR(10) NOT NULL, quantidade DECIMAL(10,3) NOT NULL, ocorrido_em DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP, motivo VARCHAR(255) NOT NULL,


CONSTRAINT fk_mov_estoque
    FOREIGN KEY (id_estoque)
    REFERENCES ESTOQUE(id_estoque)
    ON DELETE RESTRICT,

CONSTRAINT fk_mov_funcionario
    FOREIGN KEY (id_funcionario)
    REFERENCES FUNCIONARIO(id_funcionario)
    ON DELETE RESTRICT,

CONSTRAINT chk_mov_tipo
    CHECK (tipo IN ('ENTRADA','SAIDA','AJUSTE')),

CONSTRAINT chk_mov_quantidade
    CHECK (quantidade > 0)
) ENGINE=InnoDB;

CREATE TABLE FORNECEDOR ( id_fornecedor INT AUTO_INCREMENT PRIMARY KEY, nome_razao_social VARCHAR(120) NOT NULL, documento VARCHAR(20) UNIQUE, telefone VARCHAR(20) NOT NULL, email VARCHAR(100), endereco VARCHAR(255), ativo BOOLEAN NOT NULL DEFAULT TRUE ) ENGINE=InnoDB;

CREATE TABLE COMPRA ( id_compra INT AUTO_INCREMENT PRIMARY KEY, id_fornecedor INT NOT NULL, id_funcionario INT NOT NULL, solicitada_em DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP, prevista_entrega DATE, status VARCHAR(20) NOT NULL DEFAULT 'SOLICITADA', valor_total DECIMAL(10,2) NOT NULL DEFAULT 0,


CONSTRAINT fk_compra_fornecedor
    FOREIGN KEY (id_fornecedor)
    REFERENCES FORNECEDOR(id_fornecedor)
    ON DELETE RESTRICT,

CONSTRAINT fk_compra_funcionario
    FOREIGN KEY (id_funcionario)
    REFERENCES FUNCIONARIO(id_funcionario)
    ON DELETE RESTRICT,

CONSTRAINT chk_compra_status
    CHECK (status IN (
        'SOLICITADA',
        'APROVADA',
        'RECEBIDA',
        'CANCELADA'
    )),

CONSTRAINT chk_compra_valor
    CHECK (valor_total >= 0)
) ENGINE=InnoDB;

CREATE TABLE ITEM_COMPRA ( id_item_compra INT AUTO_INCREMENT PRIMARY KEY, id_compra INT NOT NULL, id_produto INT NOT NULL, quantidade_pedida DECIMAL(10,3) NOT NULL, quantidade_recebida DECIMAL(10,3) NOT NULL DEFAULT 0, custo_unitario DECIMAL(10,2) NOT NULL,


CONSTRAINT fk_itemcompra_compra
    FOREIGN KEY (id_compra)
    REFERENCES COMPRA(id_compra)
    ON DELETE RESTRICT,

CONSTRAINT fk_itemcompra_produto
    FOREIGN KEY (id_produto)
    REFERENCES PRODUTO(id_produto)
    ON DELETE RESTRICT,

CONSTRAINT chk_itemcompra_quantidade
    CHECK (
        quantidade_pedida > 0
        AND quantidade_recebida >= 0
        AND quantidade_recebida <= quantidade_pedida
    ),

CONSTRAINT chk_itemcompra_custo
    CHECK (custo_unitario >= 0)
) ENGINE=InnoDB;

-- ========================================================== -- 5. FINANCEIRO E OCORRÊNCIAS -- ==========================================================

CREATE TABLE PAGAMENTO ( id_pagamento INT AUTO_INCREMENT PRIMARY KEY, id_comanda INT NOT NULL, forma_pagamento VARCHAR(30) NOT NULL, valor DECIMAL(10,2) NOT NULL, pago_em DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP, status VARCHAR(20) NOT NULL DEFAULT 'CONCLUIDO', referencia_transacao VARCHAR(100),


CONSTRAINT fk_pagamento_comanda
    FOREIGN KEY (id_comanda)
    REFERENCES COMANDA(id_comanda)
    ON DELETE RESTRICT,

CONSTRAINT chk_pagamento_valor
    CHECK (valor > 0),

CONSTRAINT chk_pagamento_forma
    CHECK (forma_pagamento IN (
        'DINHEIRO',
        'CARTAO_CREDITO',
        'CARTAO_DEBITO',
        'PIX'
    )),

CONSTRAINT chk_pagamento_status
    CHECK (status IN (
        'CONCLUIDO',
        'PENDENTE',
        'ESTORNADO'
    ))
) ENGINE=InnoDB;

CREATE TABLE CONTA_PAGAR ( id_conta_pagar INT AUTO_INCREMENT PRIMARY KEY, id_fornecedor INT NOT NULL, id_compra INT, documento_referencia VARCHAR(50), vencimento DATE NOT NULL, valor DECIMAL(10,2) NOT NULL, status VARCHAR(20) NOT NULL DEFAULT 'PENDENTE', pago_em DATE,


CONSTRAINT fk_conta_fornecedor
    FOREIGN KEY (id_fornecedor)
    REFERENCES FORNECEDOR(id_fornecedor)
    ON DELETE RESTRICT,

CONSTRAINT fk_conta_compra
    FOREIGN KEY (id_compra)
    REFERENCES COMPRA(id_compra)
    ON DELETE RESTRICT,

CONSTRAINT chk_conta_valor
    CHECK (valor > 0),

CONSTRAINT chk_conta_status
    CHECK (status IN (
        'PENDENTE',
        'PAGO',
        'ATRASADO',
        'CANCELADO'
    ))
) ENGINE=InnoDB;

CREATE TABLE FECHAMENTO_CAIXA ( id_fechamento INT AUTO_INCREMENT PRIMARY KEY, id_funcionario INT NOT NULL, iniciado_em DATETIME NOT NULL, encerrado_em DATETIME NOT NULL, valor_sistema DECIMAL(10,2) NOT NULL, valor_conferido DECIMAL(10,2) NOT NULL, diferenca DECIMAL(10,2) NOT NULL, observacao TEXT,


CONSTRAINT fk_fechamento_funcionario
    FOREIGN KEY (id_funcionario)
    REFERENCES FUNCIONARIO(id_funcionario)
    ON DELETE RESTRICT,

CONSTRAINT chk_fechamento_periodo
    CHECK (encerrado_em >= iniciado_em),

CONSTRAINT chk_fechamento_diferenca
    CHECK (
        diferenca = valor_conferido - valor_sistema
    )
) ENGINE=InnoDB;

CREATE TABLE OCORRENCIA ( id_ocorrencia INT AUTO_INCREMENT PRIMARY KEY, id_comanda INT, id_funcionario INT NOT NULL, autorizado_por INT, registrada_em DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP, descricao TEXT NOT NULL, providencia TEXT NOT NULL, cortesia_valor DECIMAL(10,2) DEFAULT 0,


CONSTRAINT fk_ocorrencia_comanda
    FOREIGN KEY (id_comanda)
    REFERENCES COMANDA(id_comanda)
    ON DELETE RESTRICT,

CONSTRAINT fk_ocorrencia_funcionario
    FOREIGN KEY (id_funcionario)
    REFERENCES FUNCIONARIO(id_funcionario)
    ON DELETE RESTRICT,

CONSTRAINT fk_ocorrencia_autorizador
    FOREIGN KEY (autorizado_por)
    REFERENCES FUNCIONARIO(id_funcionario)
    ON DELETE RESTRICT,

CONSTRAINT chk_ocorrencia_cortesia
    CHECK (cortesia_valor IS NULL OR cortesia_valor >= 0)
) ENGINE=InnoDB;

-- FIM DA CRIACAO DAS 18 TABELAS </CodeBlock>

3.2 Massa de dados fictícia
A massa de dados utiliza nomes, valores e situações fictícias, sem utilizar informações pessoais reais de clientes ou funcionários.

Os registros foram preparados para permitir testes de relacionamentos, consultas gerenciais e situações de auditoria.

<CodeBlock language="sql" editable> USE alberic_gastrobar;

-- ========================================================== -- CADASTROS BÁSICOS -- ==========================================================

INSERT INTO MESA (numero, capacidade, status) VALUES (1, 2, 'LIVRE'), (2, 4, 'OCUPADA'), (3, 4, 'RESERVADA'), (4, 6, 'LIVRE'), (5, 2, 'OCUPADA'), (6, 8, 'LIVRE');

INSERT INTO CATEGORIA (nome, descricao) VALUES ('Porções', 'Porções e acompanhamentos'), ('Bebidas', 'Bebidas em geral'), ('Lanches', 'Lanches e pratos rápidos'), ('Sobremesas', 'Sobremesas variadas');

INSERT INTO SETOR (nome, descricao) VALUES ('Cozinha', 'Preparação de alimentos'), ('Bar', 'Preparação de bebidas'), ('Caixa', 'Controle financeiro'), ('Salão', 'Atendimento aos clientes');

INSERT INTO FUNCIONARIO (id_setor, nome, funcao, usuario_login, senha_hash) VALUES (4, 'Funcionario Teste 01', 'Garcom', 'garcom01', 'HASH_FICTICIO_01'), (1, 'Funcionario Teste 02', 'Cozinheiro', 'cozinha01', 'HASH_FICTICIO_02'), (2, 'Funcionario Teste 03', 'Barman', 'barman01', 'HASH_FICTICIO_03'), (3, 'Funcionario Teste 04', 'Caixa', 'caixa01', 'HASH_FICTICIO_04'), (3, 'Funcionario Teste 05', 'Gerente', 'gerente01', 'HASH_FICTICIO_05');

INSERT INTO PRODUTO (id_categoria, id_setor, nome, descricao, preco_venda) VALUES (1, 1, 'Batata Frita', 'Porcao tradicional', 32.00), (1, 1, 'Frango a Passarinho', 'Porcao de frango', 45.00), (2, 2, 'Refrigerante', 'Lata 350ml', 7.00), (2, 2, 'Suco Natural', 'Suco natural', 12.00), (2, 2, 'Agua Mineral', 'Garrafa 500ml', 5.00), (3, 1, 'Hamburguer Artesanal', 'Hamburguer da casa', 38.00), (4, 1, 'Brownie', 'Brownie de chocolate', 18.00);

-- ========================================================== -- ESTOQUE -- ==========================================================

INSERT INTO ESTOQUE (id_produto, quantidade_atual, unidade_medida, estoque_minimo) VALUES (1, 35, 'UN', 10), (2, 8, 'UN', 12), (3, 100, 'UN', 30), (4, 25, 'UN', 10), (5, 5, 'UN', 15), (6, 20, 'UN', 8), (7, 18, 'UN', 5);

-- ========================================================== -- FORNECEDORES -- ==========================================================

INSERT INTO FORNECEDOR (nome_razao_social, documento, telefone, email, endereco) VALUES ('Distribuidora Exemplo A', '00.000.000/0001-01', '(11) 90000-0001', 'fornecedorA@exemplo.com', 'Endereco ficticio A'), ('Distribuidora Exemplo B', '00.000.000/0001-02', '(11) 90000-0002', 'fornecedorB@exemplo.com', 'Endereco ficticio B'), ('Fornecedor Exemplo C', '00.000.000/0001-03', '(11) 90000-0003', 'fornecedorC@exemplo.com', 'Endereco ficticio C');

-- ========================================================== -- COMANDAS -- ==========================================================

INSERT INTO COMANDA (id_mesa, aberta_em, fechada_em, status) VALUES (1, '2026-10-28 18:00:00', '2026-10-28 19:30:00', 'FECHADA'), (2, '2026-10-29 19:00:00', NULL, 'ABERTA'), (3, '2026-10-30 18:30:00', '2026-10-30 20:00:00', 'FECHADA'), (4, '2026-11-01 19:00:00', '2026-11-01 21:00:00', 'FECHADA'), (5, '2026-11-02 18:00:00', NULL, 'AGUARDANDO_PAGAMENTO');

-- ========================================================== -- PEDIDOS -- ==========================================================

INSERT INTO PEDIDO (id_comanda, id_funcionario, criado_em, status, observacao) VALUES (1, 1, '2026-10-28 18:10:00', 'ENTREGUE', NULL), (2, 1, '2026-10-29 19:15:00', 'EM_PREPARO', NULL), (3, 1, '2026-10-30 18:45:00', 'ENTREGUE', NULL), (4, 1, '2026-11-01 19:10:00', 'ENTREGUE', NULL), (5, 1, '2026-11-02 18:20:00', 'CANCELADO', 'Cancelamento ficticio');

-- ========================================================== -- ITENS DOS PEDIDOS -- ==========================================================

INSERT INTO ITEM_PEDIDO (id_pedido, id_produto, quantidade, preco_unitario, status) VALUES (1, 1, 2, 32.00, 'ENTREGUE'), (1, 3, 2, 7.00, 'ENTREGUE'), (2, 2, 1, 45.00, 'EM_PREPARO'), (2, 4, 2, 12.00, 'PENDENTE'), (3, 6, 2, 38.00, 'ENTREGUE'), (3, 3, 2, 7.00, 'ENTREGUE'), (4, 1, 1, 32.00, 'ENTREGUE'), (4, 7, 2, 18.00, 'ENTREGUE'), (5, 2, 1, 45.00, 'CANCELADO');

-- ========================================================== -- ESCALAS -- ==========================================================

INSERT INTO ESCALA_FUNCIONARIO (id_funcionario, inicio, fim, funcao_turno, status) VALUES (1, '2026-11-03 17:00:00', '2026-11-03 23:00:00', 'Garcom', 'CONFIRMADO'), (2, '2026-11-03 16:00:00', '2026-11-03 23:00:00', 'Cozinheiro', 'CONFIRMADO'), (3, '2026-11-03 17:00:00', '2026-11-03 23:00:00', 'Barman', 'PREVISTO'), (4, '2026-11-03 17:00:00', '2026-11-03 23:00:00', 'Caixa', 'CONFIRMADO');

-- ========================================================== -- MOVIMENTACOES DE ESTOQUE -- ==========================================================

INSERT INTO MOVIMENTACAO_ESTOQUE (id_estoque, id_funcionario, tipo, quantidade, motivo) VALUES (1, 2, 'ENTRADA', 20, 'Reposicao ficticia'), (2, 2, 'SAIDA', 5, 'Consumo operacional'), (3, 3, 'ENTRADA', 50, 'Compra de bebidas'), (5, 3, 'SAIDA', 10, 'Consumo operacional'), (6, 2, 'AJUSTE', 2, 'Ajuste de inventario');

-- ========================================================== -- COMPRAS -- ==========================================================

INSERT INTO COMPRA (id_fornecedor, id_funcionario, solicitada_em, prevista_entrega, status, valor_total) VALUES (1, 5, '2026-10-27 10:00:00', '2026-10-29', 'RECEBIDA', 500.00), (2, 5, '2026-10-30 11:00:00', '2026-11-04', 'APROVADA', 350.00), (3, 5, '2026-11-01 09:00:00', '2026-11-05', 'SOLICITADA', 200.00);

INSERT INTO ITEM_COMPRA (id_compra, id_produto, quantidade_pedida, quantidade_recebida, custo_unitario) VALUES (1, 1, 20, 20, 12.00), (1, 3, 50, 50, 4.00), (2, 2, 10, 0, 25.00), (2, 4, 20, 0, 6.00), (3, 5, 40, 0, 2.00);

-- ========================================================== -- PAGAMENTOS -- ==========================================================

INSERT INTO PAGAMENTO (id_comanda, forma_pagamento, valor, pago_em, status) VALUES (1, 'PIX', 78.00, '2026-10-28 19:30:00', 'CONCLUIDO'), (3, 'CARTAO_CREDITO', 90.00, '2026-10-30 20:00:00', 'CONCLUIDO'), (4, 'DINHEIRO', 68.00, '2026-11-01 21:00:00', 'CONCLUIDO');

-- ========================================================== -- CONTAS A PAGAR -- ==========================================================

INSERT INTO CONTA_PAGAR (id_fornecedor, id_compra, documento_referencia, vencimento, valor, status) VALUES (1, 1, 'DOC-FICTICIO-001', '2026-11-10', 500.00, 'PENDENTE'), (2, 2, 'DOC-FICTICIO-002', '2026-11-15', 350.00, 'PENDENTE'), (3, 3, 'DOC-FICTICIO-003', '2026-11-20', 200.00, 'PENDENTE');

-- ========================================================== -- FECHAMENTO DE CAIXA -- ==========================================================

INSERT INTO FECHAMENTO_CAIXA (id_funcionario, iniciado_em, encerrado_em, valor_sistema, valor_conferido, diferenca, observacao) VALUES (4, '2026-10-28 17:00:00', '2026-10-28 23:00:00', 78.00, 78.00, 0.00, 'Fechamento sem diferenca'), (4, '2026-10-30 17:00:00', '2026-10-30 23:00:00', 90.00, 85.00, -5.00, 'Diferenca ficticia'), (4, '2026-11-01 17:00:00', '2026-11-01 23:00:00', 68.00, 68.00, 0.00, 'Fechamento conferido');

-- ========================================================== -- OCORRENCIAS -- ==========================================================

INSERT INTO OCORRENCIA (id_comanda, id_funcionario, autorizado_por, descricao, providencia, cortesia_valor) VALUES (1, 1, 5, 'Demora ficticia no atendimento', 'Atendimento acompanhado pelo gerente', 0.00), (3, 2, 5, 'Produto devolvido', 'Substituicao do produto', 10.00), (NULL, 4, 5, 'Diferenca identificada no caixa', 'Conferencia dos registros', 0.00); </CodeBlock>

3.3 Consultas com JOIN
<CodeBlock language="sql" editable> USE alberic_gastrobar;

-- CONSULTA 01: PEDIDOS E FUNCIONARIOS

SELECT p.id_pedido, p.criado_em, p.status, f.nome AS funcionario, c.id_comanda FROM PEDIDO p INNER JOIN FUNCIONARIO f ON p.id_funcionario = f.id_funcionario INNER JOIN COMANDA c ON p.id_comanda = c.id_comanda;

-- CONSULTA 02: PRODUTOS E CATEGORIAS

SELECT pr.nome AS produto, ca.nome AS categoria, pr.preco_venda FROM PRODUTO pr INNER JOIN CATEGORIA ca ON pr.id_categoria = ca.id_categoria;

-- CONSULTA 03: COMPRAS E FORNECEDORES

SELECT co.id_compra, fo.nome_razao_social, co.solicitada_em, co.valor_total, co.status FROM COMPRA co INNER JOIN FORNECEDOR fo ON co.id_fornecedor = fo.id_fornecedor;

-- CONSULTA 04: PAGAMENTOS E COMANDAS

SELECT pg.id_pagamento, pg.id_comanda, pg.forma_pagamento, pg.valor, pg.status FROM PAGAMENTO pg INNER JOIN COMANDA co ON pg.id_comanda = co.id_comanda;

-- CONSULTA 05: FUNCIONARIOS E ESCALAS

SELECT f.nome, e.inicio, e.fim, e.funcao_turno, e.status FROM FUNCIONARIO f INNER JOIN ESCALA_FUNCIONARIO e ON f.id_funcionario = e.id_funcionario; </CodeBlock>

3.4 Exemplos de UPDATE e DELETE
<CodeBlock language="sql" editable> -- ATUALIZACAO DO PRECO DE UM PRODUTO

UPDATE PRODUTO SET preco_venda = 35.00 WHERE id_produto = 1;

-- ATUALIZACAO DA DISPONIBILIDADE

UPDATE PRODUTO SET disponivel = FALSE WHERE id_produto = 7;

-- EXEMPLO DE DELETE CONTROLADO -- Exclui somente um cadastro de teste sem relacionamentos.

DELETE FROM MESA WHERE numero = 6; </CodeBlock>

Observação: os comandos UPDATE e DELETE devem ser executados somente depois da conferência dos registros. O DELETE acima é um exemplo controlado; os dados históricos de pedidos, pagamentos e movimentações devem ser preservados.

3.5 Consultas gerenciais
As consultas gerenciais foram identificadas por códigos G01 a G13. Cada consulta responde a uma questão relacionada à administração do estabelecimento.

<CodeBlock language="sql" editable> USE alberic_gastrobar;

-- ========================================================== -- G01 — Quais mesas estao ocupadas ou reservadas? -- Atende: P1 -- ==========================================================

SELECT numero, capacidade, status FROM MESA WHERE status IN ('OCUPADA', 'RESERVADA');

-- ========================================================== -- G02 — Quais produtos foram mais vendidos? -- Atende: P2 e KPI03 -- ==========================================================

SELECT pr.nome, SUM(ip.quantidade) AS quantidade_vendida, SUM(ip.quantidade * ip.preco_unitario) AS valor_total FROM ITEM_PEDIDO ip INNER JOIN PRODUTO pr ON ip.id_produto = pr.id_produto INNER JOIN PEDIDO p ON ip.id_pedido = p.id_pedido WHERE p.status <> 'CANCELADO' AND ip.status <> 'CANCELADO' GROUP BY pr.id_produto, pr.nome ORDER BY quantidade_vendida DESC;

-- ========================================================== -- G03 — Quais produtos pertencem a cada categoria? -- Atende: P3 -- ==========================================================

SELECT ca.nome AS categoria, pr.nome AS produto, pr.preco_venda, pr.disponivel FROM PRODUTO pr INNER JOIN CATEGORIA ca ON pr.id_categoria = ca.id_categoria ORDER BY ca.nome, pr.nome;

-- ========================================================== -- G04 — Quais produtos estao abaixo do estoque minimo? -- Atende: P4 e KPI05 -- ==========================================================

SELECT pr.nome, es.quantidade_atual, es.estoque_minimo, es.unidade_medida FROM ESTOQUE es INNER JOIN PRODUTO pr ON es.id_produto = pr.id_produto WHERE es.estoque_minimo IS NOT NULL AND es.quantidade_atual < es.estoque_minimo ORDER BY es.quantidade_atual ASC;

-- ========================================================== -- G05 — Quais compras foram realizadas por fornecedor? -- Atende: P5 e KPI06 -- ==========================================================

SELECT fo.nome_razao_social AS fornecedor, COUNT(co.id_compra) AS total_compras, SUM( CASE WHEN co.status = 'RECEBIDA' THEN co.valor_total ELSE 0 END ) AS valor_compras_recebidas FROM FORNECEDOR fo LEFT JOIN COMPRA co ON fo.id_fornecedor = co.id_fornecedor GROUP BY fo.id_fornecedor, fo.nome_razao_social;

-- ========================================================== -- G06 — Qual o faturamento e ticket medio por periodo? -- Atende: P6, KPI01 e KPI02 -- ==========================================================

SELECT DATE_FORMAT(pago_em, '%Y-%m') AS periodo, SUM(valor) AS faturamento, COUNT(DISTINCT id_comanda) AS comandas_pagas, SUM(valor) / NULLIF(COUNT(DISTINCT id_comanda), 0) AS ticket_medio FROM PAGAMENTO WHERE status = 'CONCLUIDO' GROUP BY DATE_FORMAT(pago_em, '%Y-%m') ORDER BY periodo;

-- ========================================================== -- G07 — Quais funcionarios possuem escalas cadastradas? -- Atende: P7 -- ==========================================================

SELECT f.nome, f.funcao, e.inicio, e.fim, e.status FROM FUNCIONARIO f INNER JOIN ESCALA_FUNCIONARIO e ON f.id_funcionario = e.id_funcionario ORDER BY e.inicio;

-- ========================================================== -- G08 — Quais foram as diferencas nos fechamentos de caixa? -- Atende: P8 e KPI08 -- ==========================================================

SELECT fc.id_fechamento, f.nome AS funcionario, fc.valor_sistema, fc.valor_conferido, fc.diferenca, fc.encerrado_em FROM FECHAMENTO_CAIXA fc INNER JOIN FUNCIONARIO f ON fc.id_funcionario = f.id_funcionario WHERE fc.diferenca <> 0 ORDER BY fc.encerrado_em DESC;

-- ========================================================== -- G09 — Quais ocorrencias foram registradas? -- Atende: P9 -- ==========================================================

SELECT o.id_ocorrencia, o.registrada_em, f.nome AS funcionario, o.descricao, o.providencia, o.cortesia_valor FROM OCORRENCIA o INNER JOIN FUNCIONARIO f ON o.id_funcionario = f.id_funcionario ORDER BY o.registrada_em DESC;

-- ========================================================== -- G10 — Qual a taxa de cancelamento dos pedidos? -- Atende: KPI04 -- ==========================================================

SELECT COUNT() AS total_pedidos, SUM(status = 'CANCELADO') AS pedidos_cancelados, ROUND( SUM(status = 'CANCELADO') * 100.0 / NULLIF(COUNT(), 0), 2 ) AS percentual_cancelamento FROM PEDIDO;

-- ========================================================== -- G11 — Qual o total de contas a pagar pendentes? -- Atende: KPI07 -- ==========================================================

SELECT COUNT(*) AS quantidade_contas, SUM(valor) AS total_pendente FROM CONTA_PAGAR WHERE status IN ('PENDENTE', 'ATRASADO');

-- ========================================================== -- G12 — Quais formas de pagamento sao mais utilizadas? -- Atende: KPI09 -- ==========================================================

SELECT forma_pagamento, COUNT(*) AS quantidade_pagamentos, SUM(valor) AS valor_total FROM PAGAMENTO WHERE status = 'CONCLUIDO' GROUP BY forma_pagamento ORDER BY valor_total DESC;

-- ========================================================== -- G13 — Qual o tempo medio de atendimento? -- Atende: KPI10 -- ==========================================================

SELECT ROUND( AVG( TIMESTAMPDIFF( MINUTE, aberta_em, fechada_em ) ), 2 ) AS tempo_medio_minutos FROM COMANDA WHERE status = 'FECHADA' AND fechada_em IS NOT NULL; </CodeBlock>

3.6 Consultas de auditoria
As consultas de auditoria verificam a consistência das informações e o cumprimento das regras de negócio.

<CodeBlock language="sql" editable> USE alberic_gastrobar;

-- ========================================================== -- A01 — Existem comandas sem mesa correspondente? -- Verifica: RN02 -- ==========================================================

SELECT c.* FROM COMANDA c LEFT JOIN MESA m ON c.id_mesa = m.id_mesa WHERE m.id_mesa IS NULL;

-- ========================================================== -- A02 — Existem pedidos sem funcionario responsavel? -- Verifica: RN04 -- ==========================================================

SELECT p.* FROM PEDIDO p LEFT JOIN FUNCIONARIO f ON p.id_funcionario = f.id_funcionario WHERE f.id_funcionario IS NULL;

-- ========================================================== -- A03 — Existem itens de pedido sem produto? -- Verifica: RN05 -- ==========================================================

SELECT ip.* FROM ITEM_PEDIDO ip LEFT JOIN PRODUTO p ON ip.id_produto = p.id_produto WHERE p.id_produto IS NULL;

-- ========================================================== -- A04 — Existem produtos sem registro de estoque? -- Verifica: RN09 -- ==========================================================

SELECT p.id_produto, p.nome FROM PRODUTO p LEFT JOIN ESTOQUE e ON p.id_produto = e.id_produto WHERE e.id_estoque IS NULL;

-- ========================================================== -- A05 — Existem movimentacoes com quantidade invalida? -- Verifica: RN10 e RN11 -- ==========================================================

SELECT * FROM MOVIMENTACAO_ESTOQUE WHERE quantidade <= 0;

-- ========================================================== -- A06 — Existem compras com recebimento superior ao pedido? -- Verifica: RN13 -- ==========================================================

SELECT * FROM ITEM_COMPRA WHERE quantidade_recebida > quantidade_pedida;

-- ========================================================== -- A07 — Existem pagamentos com valores invalidos? -- Verifica: RN14 e RN15 -- ==========================================================

SELECT * FROM PAGAMENTO WHERE valor <= 0;

-- ========================================================== -- A08 — Existem diferencas de caixa calculadas incorretamente? -- Verifica: RN16 -- ==========================================================

SELECT * FROM FECHAMENTO_CAIXA WHERE diferenca <> valor_conferido - valor_sistema;

-- ========================================================== -- A09 — Existem ocorrencias sem providencia registrada? -- Verifica: RN17 -- ==========================================================

SELECT * FROM OCORRENCIA WHERE descricao IS NULL OR providencia IS NULL;

-- ========================================================== -- A10 — Existem comandas abertas sem pedidos? -- Verifica: RN03 e controle operacional -- ==========================================================

SELECT c.id_comanda, c.status FROM COMANDA c LEFT JOIN PEDIDO p ON c.id_comanda = p.id_comanda WHERE c.status = 'ABERTA' GROUP BY c.id_comanda, c.status HAVING COUNT(p.id_pedido) = 0; </CodeBlock>

As consultas A01 a A09 verificam condições relacionadas às regras de integridade. A10 identifica uma situação que merece análise operacional, mas uma comanda aberta sem pedido não é necessariamente uma violação, pois pode estar aguardando o primeiro atendimento.

Nota técnica: algumas regras, como exigir pelo menos um item por pedido e manter o saldo de estoque sincronizado com as movimentações, dependem de validações transacionais ou triggers. Uma simples FK ou CHECK não garante essas condições entre múltiplas linhas. Elas deverão ser implementadas na aplicação ou por rotinas específicas antes da utilização em produção.

4. MASSA DE DADOS
4.1 Justificativa da quantidade de registros
A massa de dados foi criada com informações fictícias, preservando os tipos de operações representados no modelo.

A primeira carga apresentada contém registros de teste para validar os relacionamentos e demonstrar o funcionamento das consultas.


Tabela	Registros iniciais	Justificativa
MESA	6	Representação de diferentes situações de atendimento.
COMANDA	5	Teste de comandas abertas e fechadas.
PEDIDO	5	Teste de diferentes estados dos pedidos.
ITEM_PEDIDO	9	Representação de produtos variados.
CATEGORIA	4	Separação dos grupos de produtos.
SETOR	4	Representação das áreas operacionais.
PRODUTO	7	Produtos fictícios de diferentes categorias.
FUNCIONARIO	5	Representação de funções distintas.
ESCALA_FUNCIONARIO	4	Teste de escalas de trabalho.
ESTOQUE	7	Um estoque para cada produto cadastrado.
MOVIMENTACAO_ESTOQUE	5	Teste de entradas, saídas e ajustes.
FORNECEDOR	3	Representação de diferentes fornecedores.
COMPRA	3	Teste de diferentes situações de compras.
ITEM_COMPRA	5	Detalhamento dos itens adquiridos.
PAGAMENTO	3	Teste de diferentes formas de pagamento.
CONTA_PAGAR	3	Controle de obrigações financeiras.
FECHAMENTO_CAIXA	3	Demonstração de fechamentos com e sem diferenças.
OCORRENCIA	3	Registro de situações operacionais.
A quantidade acima é uma massa inicial de testes, não uma representação estatística da operação real. Para a entrega definitiva, deverá ser ampliada conforme os volumes observados na organização.

4.2 Situações representadas
A massa contempla:

Mesas livres, ocupadas e reservadas.
Comandas abertas e fechadas.
Pedidos entregues, em preparação e cancelados.
Produtos abaixo do estoque mínimo.
Movimentações de entrada, saída e ajuste.
Compras recebidas, aprovadas e solicitadas.
Pagamentos realizados em diferentes modalidades.
Contas a pagar pendentes.
Fechamentos com diferenças financeiras.
Ocorrências com e sem cortesia.
4.3 Limitações da massa de dados
A carga inicial não deve ser interpretada como volume suficiente para treinar modelos preditivos de IA.

Para análises de sazonalidade, previsão de vendas e previsão de estoque, será necessário acumular um histórico maior de movimentações reais, sempre respeitando a privacidade das pessoas envolvidas.

5. DICIONÁRIO DE DADOS
O dicionário documenta os campos, os tipos, as chaves e as restrições de integridade.

Como a turma não foi identificada como GTI, deixo o modelo em Markdown. Caso a turma seja GTI, esse formato atende à exceção indicada no enunciado.

Salve como dicionario/dicionario_dados.md.

5.1 Tabela MESA

Campo	Tipo	Restrição	Descrição
id_mesa	INT	PK, AI	Identificador da mesa
numero	INT	NOT NULL, UNIQUE	Número da mesa
capacidade	INT	NOT NULL, CHECK	Capacidade de pessoas
status	VARCHAR(20)	NOT NULL, DEFAULT	Situação da mesa
observacao	VARCHAR(255)	NULL	Observações
5.2 Tabela COMANDA

Campo	Tipo	Restrição	Descrição
id_comanda	INT	PK, AI	Identificador da comanda
id_mesa	INT	FK, NOT NULL	Mesa relacionada
aberta_em	DATETIME	NOT NULL, DEFAULT	Abertura
fechada_em	DATETIME	NULL	Fechamento
status	VARCHAR(30)	NOT NULL, CHECK	Situação
5.3 Tabela PEDIDO

Campo	Tipo	Restrição	Descrição
id_pedido	INT	PK, AI	Identificador
id_comanda	INT	FK, NOT NULL	Comanda
id_funcionario	INT	FK, NOT NULL	Responsável
criado_em	DATETIME	NOT NULL	Data de criação
status	VARCHAR(20)	NOT NULL, CHECK	Situação
observacao	VARCHAR(255)	NULL	Observações
5.4 Tabela ITEM_PEDIDO

Campo	Tipo	Restrição	Descrição
id_item_pedido	INT	PK, AI	Identificador
id_pedido	INT	FK, NOT NULL	Pedido
id_produto	INT	FK, NOT NULL	Produto
quantidade	DECIMAL(10,3)	NOT NULL, CHECK	Quantidade
preco_unitario	DECIMAL(10,2)	NOT NULL, CHECK	Preço praticado
status	VARCHAR(20)	NOT NULL, DEFAULT	Situação
observacao_item	VARCHAR(150)	NULL	Observações
5.5 Tabela CATEGORIA

Campo	Tipo	Restrição	Descrição
id_categoria	INT	PK, AI	Identificador
nome	VARCHAR(50)	NOT NULL, UNIQUE	Nome
descricao	VARCHAR(255)	NULL	Descrição
ativa	BOOLEAN	NOT NULL, DEFAULT	Situação
5.6 Tabela SETOR

Campo	Tipo	Restrição	Descrição
id_setor	INT	PK, AI	Identificador
nome	VARCHAR(50)	NOT NULL, UNIQUE	Nome
descricao	VARCHAR(255)	NULL	Descrição
ativo	BOOLEAN	NOT NULL, DEFAULT	Situação
5.7 Tabela PRODUTO

Campo	Tipo	Restrição	Descrição
id_produto	INT	PK, AI	Identificador
id_categoria	INT	FK, NOT NULL	Categoria
id_setor	INT	FK, NOT NULL	Setor responsável
nome	VARCHAR(100)	NOT NULL	Nome
descricao	TEXT	NULL	Descrição
preco_venda	DECIMAL(10,2)	NOT NULL, CHECK	Preço
disponivel	BOOLEAN	NOT NULL, DEFAULT	Disponibilidade
5.8 Tabela FUNCIONARIO

Campo	Tipo	Restrição	Descrição
id_funcionario	INT	PK, AI	Identificador
id_setor	INT	FK, NULL	Setor
nome	VARCHAR(100)	NOT NULL	Nome
funcao	VARCHAR(50)	NOT NULL	Função
usuario_login	VARCHAR(50)	UNIQUE, NULL	Login
senha_hash	VARCHAR(255)	NULL	Hash da senha
ativo	BOOLEAN	NOT NULL, DEFAULT	Situação
5.9 Tabela ESCALA_FUNCIONARIO

Campo	Tipo	Restrição	Descrição
id_escala	INT	PK, AI	Identificador
id_funcionario	INT	FK, NOT NULL	Funcionário
inicio	DATETIME	NOT NULL	Início
fim	DATETIME	NOT NULL, CHECK	Término
funcao_turno	VARCHAR(50)	NOT NULL	Função
status	VARCHAR(20)	NOT NULL, DEFAULT	Situação
5.10 Tabela ESTOQUE

Campo	Tipo	Restrição	Descrição
id_estoque	INT	PK, AI	Identificador
id_produto	INT	FK, UNIQUE, NOT NULL	Produto
quantidade_atual	DECIMAL(10,3)	NOT NULL, DEFAULT	Saldo
unidade_medida	VARCHAR(15)	NOT NULL	Unidade
estoque_minimo	DECIMAL(10,3)	NULL, CHECK	Limite mínimo
5.11 Tabela MOVIMENTACAO_ESTOQUE

Campo	Tipo	Restrição	Descrição
id_movimentacao	INT	PK, AI	Identificador
id_estoque	INT	FK, NOT NULL	Estoque
id_funcionario	INT	FK, NOT NULL	Responsável
tipo	VARCHAR(10)	NOT NULL, CHECK	Entrada, saída ou ajuste
quantidade	DECIMAL(10,3)	NOT NULL, CHECK	Quantidade
ocorrido_em	DATETIME	NOT NULL, DEFAULT	Data
motivo	VARCHAR(255)	NOT NULL	Motivo
5.12 Tabela FORNECEDOR

Campo	Tipo	Restrição	Descrição
id_fornecedor	INT	PK, AI	Identificador
nome_razao_social	VARCHAR(120)	NOT NULL	Razão social
documento	VARCHAR(20)	UNIQUE, NULL	Documento
telefone	VARCHAR(20)	NOT NULL	Telefone
email	VARCHAR(100)	NULL	E-mail
endereco	VARCHAR(255)	NULL	Endereço
ativo	BOOLEAN	NOT NULL, DEFAULT	Situação
5.13 Tabela COMPRA

Campo	Tipo	Restrição	Descrição
id_compra	INT	PK, AI	Identificador
id_fornecedor	INT	FK, NOT NULL	Fornecedor
id_funcionario	INT	FK, NOT NULL	Responsável
solicitada_em	DATETIME	NOT NULL, DEFAULT	Solicitação
prevista_entrega	DATE	NULL	Previsão
status	VARCHAR(20)	NOT NULL, DEFAULT	Situação
valor_total	DECIMAL(10,2)	NOT NULL, DEFAULT	Total
5.14 Tabela ITEM_COMPRA

Campo	Tipo	Restrição	Descrição
id_item_compra	INT	PK, AI	Identificador
id_compra	INT	FK, NOT NULL	Compra
id_produto	INT	FK, NOT NULL	Produto
quantidade_pedida	DECIMAL(10,3)	NOT NULL, CHECK	Quantidade solicitada
quantidade_recebida	DECIMAL(10,3)	NOT NULL, DEFAULT	Quantidade recebida
custo_unitario	DECIMAL(10,2)	NOT NULL, CHECK	Custo
5.15 Tabela PAGAMENTO

Campo	Tipo	Restrição	Descrição
id_pagamento	INT	PK, AI	Identificador
id_comanda	INT	FK, NOT NULL	Comanda
forma_pagamento	VARCHAR(30)	NOT NULL, CHECK	Modalidade
valor	DECIMAL(10,2)	NOT NULL, CHECK	Valor
pago_em	DATETIME	NOT NULL, DEFAULT	Data
status	VARCHAR(20)	NOT NULL, DEFAULT	Situação
referencia_transacao	VARCHAR(100)	NULL	Referência
5.16 Tabela CONTA_PAGAR

Campo	Tipo	Restrição	Descrição
id_conta_pagar	INT	PK, AI	Identificador
id_fornecedor	INT	FK, NOT NULL	Fornecedor
id_compra	INT	FK, NULL	Compra
documento_referencia	VARCHAR(50)	NULL	Documento
vencimento	DATE	NOT NULL	Vencimento
valor	DECIMAL(10,2)	NOT NULL, CHECK	Valor
status	VARCHAR(20)	NOT NULL, DEFAULT	Situação
pago_em	DATE	NULL	Data de pagamento
5.17 Tabela FECHAMENTO_CAIXA

Campo	Tipo	Restrição	Descrição
id_fechamento	INT	PK, AI	Identificador
id_funcionario	INT	FK, NOT NULL	Responsável
iniciado_em	DATETIME	NOT NULL	Início
encerrado_em	DATETIME	NOT NULL	Encerramento
valor_sistema	DECIMAL(10,2)	NOT NULL	Valor do sistema
valor_conferido	DECIMAL(10,2)	NOT NULL	Valor contado
diferenca	DECIMAL(10,2)	NOT NULL, CHECK	Diferença
observacao	TEXT	NULL	Observações
5.18 Tabela OCORRENCIA

Campo	Tipo	Restrição	Descrição
id_ocorrencia	INT	PK, AI	Identificador
id_comanda	INT	FK, NULL	Comanda
id_funcionario	INT	FK, NOT NULL	Responsável
autorizado_por	INT	FK, NULL	Autorizador
registrada_em	DATETIME	NOT NULL, DEFAULT	Registro
descricao	TEXT	NOT NULL	Descrição
providencia	TEXT	NOT NULL	Providência
cortesia_valor	DECIMAL(10,2)	DEFAULT	Valor da cortesia
6. USO DE INTELIGÊNCIA ARTIFICIAL
Durante o desenvolvimento da Entrega 2, utilizamos inteligência artificial como ferramenta de apoio à organização das informações, revisão da modelagem, normalização e desenvolvimento do código SQL.

A ferramenta utilizada foi o ChatGPT, da OpenAI.

Registro de utilização

Item	Descrição
Ferramenta	ChatGPT (OpenAI)
Etapa	Modelagem lógica e implementação SQL
Motivação	Auxiliar na revisão das tabelas, relacionamentos e restrições.
Prompt utilizado	"Revise este modelo lógico de banco de dados de um gastrobar, identifique inconsistências, proponha melhorias e desenvolva um script SQL compatível com MySQL 8.0."
Resposta recebida	Sugestões de normalização, revisão de chaves estrangeiras, criação de restrições e consultas gerenciais.
Fontes consultadas	O modelo lógico da Entrega 1 e as especificações do enunciado da atividade.
Trechos corrigidos	Foram identificadas redundâncias na movimentação de estoque e necessidades de validação entre compras, pagamentos e registros operacionais.
Justificativa da escolha	As sugestões foram utilizadas como apoio técnico, mantendo a estrutura original do projeto.
Reflexão crítica	As respostas da IA podem apresentar erros de sintaxe, inconsistências entre tabelas e pressupostos que não correspondem à realidade da organização. Por isso, o material precisa ser revisado e testado pelo grupo.
Uso de IA na massa de dados

Item	Descrição
Ferramenta	ChatGPT
Etapa	Geração de dados fictícios
Motivação	Criar registros para testar as tabelas e consultas.
Prompt utilizado	"Gere dados fictícios para um banco de dados de gastrobar, contemplando produtos, funcionários, comandas, pedidos, compras, fornecedores e pagamentos."
Resposta recebida	Exemplos de registros fictícios e situações operacionais.
Ajustes manuais	Adequação dos identificadores, relacionamentos, valores e situações de teste.
Justificativa	Os dados fictícios permitem demonstrar o funcionamento do banco sem expor informações pessoais reais.
Reflexão crítica	A massa de dados gerada automaticamente não representa necessariamente o volume real da organização.
Uso de IA na elaboração do relatório

Item	Descrição
Ferramenta	ChatGPT
Etapa	Redação do relatório técnico
Motivação	Organizar os conteúdos de acordo com os critérios de avaliação.
Prompt utilizado	"Elabore um relatório técnico acadêmico para um projeto de banco de dados de um gastrobar, abordando conversão lógica, normalização, integridade, BI e IA."
Resposta recebida	Estruturação das seções e propostas de indicadores.
Ajustes manuais	Adequação ao modelo lógico da Entrega 1 e ao enunciado.
Justificativa	Padronização e organização da documentação.
Reflexão crítica	O texto gerado deve ser confrontado com os processos efetivamente observados na organização.
Declaração: a utilização de inteligência artificial foi registrada de forma transparente. O grupo deve complementar este registro com os prompts adicionais que efetivamente utilizar durante a conclusão do projeto.

7. APRESENTAÇÃO CORPORATIVA FINAL
A apresentação terá duração aproximada de 8 minutos e será organizada em slides objetivos, com poucos textos e destaque para os diagramas, consultas e resultados.

7.1 Roteiro dos slides
<box gap={3}> <row align=start gap={3}> <AsyncImage query="minimalist restaurant gastrobar presentation cover dark elegant food photography" aspectRatio="4:3" maxWidth="112px"/> <box flex="1" gap={1}> **Slide 1 — Apresentação do projeto**


  <text color="secondary" size="xs">40 segundos</text>
  - Alberic Gastrobar.
  - Identificação dos integrantes.
  - Objetivo do sistema de gestão.
</box>
</row> <divider color="subtle"/> <row align=start gap={3}> <AsyncImage query="restaurant waiter taking food order restaurant management operations" aspectRatio="4:3" maxWidth="112px"/> <box flex="1" gap={1}> **Slide 2 — Problema organizacional**


  <text color="secondary" size="xs">1 minuto</text>
  - Controle de comandas.
  - Pedidos e produtos.
  - Estoque e compras.
  - Controle financeiro.
</box>
</row> <divider color="subtle"/> <row align=start gap={3}> <AsyncImage query="database relational entity relationship diagram computer screen" aspectRatio="4:3" maxWidth="112px"/> <box flex="1" gap={1}> **Slide 3 — Solução proposta**


  <text color="secondary" size="xs">50 segundos</text>
  - Banco de dados centralizado.
  - 18 tabelas.
  - Integração dos setores.
</box>
</row> <divider color="subtle"/> <row align=start gap={3}> <AsyncImage query="database relational schema diagram tables connections computer screen" aspectRatio="4:3" maxWidth="112px"/> <box flex="1" gap={1}> **Slide 4 — Modelo lógico**


  <text color="secondary" size="xs">1 minuto e 20 segundos</text>
  - Apresentação do diagrama.
  - Chaves primárias e estrangeiras.
  - Relacionamentos e cardinalidades.
</box>
</row> <divider color="subtle"/> <row align=start gap={3}> <AsyncImage query="mysql workbench SQL database code computer monitor" aspectRatio="4:3" maxWidth="112px"/> <box flex="1" gap={1}> **Slide 5 — Implementação SQL**


  <text color="secondary" size="xs">1 minuto e 10 segundos</text>
  - Criação do banco.
  - Criação das tabelas.
  - Restrições de integridade.
  - Inserção dos registros fictícios.
</box>
</row> <divider color="subtle"/> <row align=start gap={3}> <AsyncImage query="business intelligence dashboard restaurant sales inventory charts" aspectRatio="4:3" maxWidth="112px"/> <box flex="1" gap={1}> **Slide 6 — Consultas gerenciais**


  <text color="secondary" size="xs">1 minuto e 10 segundos</text>
  - Faturamento.
  - Produtos mais vendidos.
  - Estoque mínimo.
  - Contas a pagar.
</box>
</row> <divider color="subtle"/> <row align=start gap={3}> <AsyncImage query="artificial intelligence predictive analytics business dashboard" aspectRatio="4:3" maxWidth="112px"/> <box flex="1" gap={1}> **Slide 7 — Potencial de BI e IA**


  <text color="secondary" size="xs">1 minuto</text>
  - Indicadores de desempenho.
  - Previsão de demanda.
  - Análise de estoque.
  - Apoio à decisão.
</box>
</row> <divider color="subtle"/> <row align=start gap={3}> <AsyncImage query="elegant restaurant dining interior warm lighting" aspectRatio="4:3" maxWidth="112px"/> <box flex="1" gap={1}> **Slide 8 — Benefícios e conclusão**


  <text color="secondary" size="xs">50 segundos</text>
  - Organização das informações.
  - Maior controle operacional.
  - Redução de inconsistências.
  - Melhor tomada de decisão.
</box>
</row> </box>

7.2 Sugestão de fala para a apresentação
Abertura:

"Nosso projeto tem como objetivo desenvolver uma solução de banco de dados para o Alberic Gastrobar, permitindo centralizar e organizar as principais informações operacionais e administrativas do estabelecimento."

Problema:

"Identificamos a necessidade de integrar informações relacionadas ao atendimento, pedidos, produtos, estoque, fornecedores, pagamentos e funcionários. A falta de integração entre essas informações pode dificultar o acompanhamento das operações e a tomada de decisões."

Solução:

"Desenvolvemos um modelo relacional composto por 18 tabelas, organizadas em módulos. Utilizamos chaves primárias e estrangeiras para estabelecer os relacionamentos e garantir a integridade dos dados."

Implementação:

"A implementação foi realizada utilizando MySQL 8.0. Foram desenvolvidas as estruturas das tabelas, restrições de integridade, inserção de dados fictícios e consultas para demonstrar o funcionamento do sistema."

Consultas:

"Com as consultas gerenciais, podemos acompanhar o faturamento, identificar os produtos mais vendidos, verificar produtos abaixo do estoque mínimo e analisar as contas a pagar."

BI e IA:

"No futuro, a estrutura poderá ser integrada a ferramentas de Business Intelligence e inteligência artificial para apoiar previsões de demanda, planejamento de estoque e análise de desempenho."

Conclusão:

"Concluímos que a solução proposta permite organizar as informações em uma estrutura integrada, facilitando o controle das operações e oferecendo uma base para decisões mais eficientes."

8. ORGANIZAÇÃO FINAL DO GITHUB
A estrutura recomendada para o repositório é:


text
alberic-gastrobar/
│
├── README.md
│
├── diagramas/
│   ├── DER_conceitual.png
│   └── modelo_logico.png
│
├── dicionario/
│   └── dicionario_dados.md
│
├── levantamento/
│   └── levantamento.md
│
├── evidencias/
│   ├── visita.jpg
│   └── entrevista.jpg
│
├── docs/
│   └── script.sql
│
└── apresentacao/
    └── apresentacao_final.pptx
8.1 Checklist antes da entrega
{@body const tasks = ["Revisar o README.md e preencher os dados reais da organização.","Confirmar os problemas com o responsável do Alberic Gastrobar.","Inserir endereço, contato e evidências de visita.","Finalizar o DER conceitual no brModelo.","Finalizar o modelo lógico no brModelo.","Conferir o dicionário de dados.","Corrigir e testar o script SQL em um banco vazio.","Ampliar a massa de dados conforme os volumes reais.","Executar todas as consultas gerenciais e de auditoria.","Preparar os slides da apresentação.","Distribuir os commits entre os cinco integrantes.","Conferir se todos os arquivos estão na branch main."]} {@body const [done,setDone] = DIL.useState([])} <box border radius="lg" padding={3} gap={3}> <row align="center" justify="between"> Checklist de conclusão <badge color={done.length===tasks.length?"success":"info"}>{done.length}/{tasks.length} concluídos</badge> </row> <box background="surface-tertiary" height="7px" radius="full" clip> <box background="#16A34A" height="7px" radius="full" width={${done.length/tasks.length*100}%}/> </box> {#each tasks as task,i} <checkbox key={i} checked={done.includes(i)} onChange={v=>setDone(old=>v?[...old,i]:old.filter(x=>x!==i))}>{task}</checkbox> {/each} </box>
