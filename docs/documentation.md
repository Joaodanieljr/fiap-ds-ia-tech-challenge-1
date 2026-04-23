# Tech Challenge — Fase 1 | Case NPS Preditivo
## Notebook de Análise Exploratória (EDA) — Estrutura CRISP-DM

**Pós Tech em Data Science (AI Scientist) — FIAP**  
**Grupo:** _(61)_  
**Data:** _(10/04/2026)_

# 1	Introdução
Trabalho apresentado à FIAP como requisito para conclusão da Fase 1 do curso POS TECH AI Scientist.
Este material é uma leitura complementar com detalhamento adicional em relação a conceitos e definições, sendo que a apresentação se encontra em:
•	Material disponibilizado no repositório `GitHub`, com códigos, comentários e estrutura de pastas (incluído arquivo README);
•	Vídeo com apresentação executiva (storytelling gerencial)

# 2	Objetivo
Elaboração de projeto denominado **Tech Challenge com tema proposto Case NPS Preditivo.** 
O Net Promoter Score (NPS) é uma metodologia utilizada para mensurar o nível de lealdade dos clientes, fundamentada na probabilidade de recomendação de uma empresa, produto ou serviço a terceiros. A denominação “Case NPS Preditivo” refere-se a um estudo de caso orientado à análise de dados históricos, com o objetivo de gerar percepções analíticas e apoiar a formulação de recomendações estratégicas.
O escopo consiste na aplicação do conteúdo apresentado na Fase 1, por meio do conhecimento adquirido em relação a metodologias, entendimento de negócio e definição de objetivo (target), análise exploratória de dados (EDA), elaboração de modelo estatístico (modelagem preditiva), elaboração de material gerencial com linguagem não técnica de análises e resultados (storytelling e slides gerencias), divulgação do material  em repositório público, apresentação de vídeo com as análises, técnicas e resultados obtidos.

# 3	Conteúdo do Curso Utilizados na Análise
Os conceitos e metodologias utilizados tem como base o material apresentado na Fase 1 do curso POS TECH AI SCIENTIST conforme abaixo:
•	Metodologia `CRISP-DM` para projetos de ciência de dados
•	Análise exploratória de dados
•	Estatística essencial para cientistas de dados
•	Ambientes de trabalho para cientistas de dados

# 4	Metodologia CRISP-DM
A padronização para análise apresentada no curso e utilizada neste trabalho é o `CRISP-DM (Cross-Industry Standard Process for Data Mining)`, que foi criado com o objetivo de estabelecer uma metodologia padrão para mineração de dados.
O método é composto por seis fases, sendo que este trabalho contempla apenas parte delas. Ainda assim, todas as fases são apresentadas a seguir, visando à compreensão integral do processo.
1. Compreensão do negócio
2. Compreensão dos dados
3. Preparação dos dados.
4. Modelagem
5. Avaliação
6. Implantação

# 5	Entendimento do negócio (Compreensão do negócio)

## 5.1	Conceito
A atividade de entendimento do negócio está inserida na fase de Compreensão do Negócio do `CRISP-DM`.
No entendimento do negócio, busca-se compreender o problema de negócio, sendo que os objetivos estratégicos e gerenciais devem ser traduzidos em perguntas analíticas claras e mensuráveis. Em outras palavras, trata-se de traduzir o problema de negócio (frequentemente referido como “dor do negócio”) em uma questão analítica, que servirá de base para as etapas posteriores de definição da variável alvo (target).

## 5.2	Cenário atual (coletado do documento TECH CHALLENGE FASE 1)
Com o crescimento acelerado do e-commerce nacional, temos o cenário de uma empresa que passou a lidar com um volume cada vez maior de pedidos, entregas e interações com clientes. Esse crescimento trouxe ganhos importantes de escala, mas também revelou desafios relevantes na experiência do cliente, especialmente refletidos na alta variabilidade do Net Promoter Score (NPS) entre diferentes perfis de consumidores. A área de Experiência do Cliente percebeu que, mesmo com indicadores operacionais aparentemente semelhantes, alguns clientes se tornam promotores da marca, enquanto outros se tornam detratores.
Atualmente, o NPS é coletado apenas após o encerramento da jornada de compra, o que limita a capacidade da empresa de antecipar problemas, priorizar ações corretivas e atuar de forma preventiva. Nesse contexto, surge a necessidade de transformar dados operacionais, como informações de pedidos, logística e atendimento, em insights acionáveis, capazes de orientar decisões estratégicas e operacionais.

## 5.3	Perguntas de negócio

### 5.3.1	Qual problema de negócio está sendo resolvido?
O problema de negócio consiste na limitação da empresa em antecipar a insatisfação dos clientes, priorizar ações corretivas e atuar de forma preventiva. Essa limitação decorre do fato de o NPS ser coletado apenas ao final da jornada de compra, caracterizando um indicador essencialmente reativo.

Adicionalmente, observa-se alta variabilidade no NPS entre diferentes perfis de clientes, mesmo diante de indicadores operacionais semelhantes, o que dificulta a identificação dos fatores que impactam a experiência do cliente. Nesse contexto, o problema de negócio consiste em transformar o NPS de um indicador reativo em um indicador preditivo, possibilitando a identificação antecipada de clientes com maior probabilidade de se tornarem detratores e permitindo a atuação preventiva sobre os fatores que influenciam sua satisfação.

### 5.3.2	Por que o NPS é importante para um e-commerce?
O Net Promoter Score (NPS) é uma metodologia utilizada para mensurar o nível de lealdade dos clientes, com base na probabilidade de recomendação de uma empresa, produto ou serviço a terceiros. O NPS é mensurado a partir de uma escala padrão de 0 a 10, na qual os respondentes indicam a probabilidade de recomendação, sendo posteriormente classificados em promotores (9 e 10), neutros (7 e 8) e detratores (0 a 6), a partir dos quais se realiza o cálculo do indicador.

Sua importância para o e-commerce reside no fato de atuar como um indicador direto da lealdade do cliente, estando frequentemente associado ao crescimento orgânico do negócio. Em ambientes digitais, caracterizados por elevado custo de aquisição de clientes e alta concorrência, a retenção de clientes e sua conversão em promotores tendem a ser mais rentáveis do que a aquisição de novos clientes.

Adicionalmente, o NPS permite consolidar, em uma única métrica, percepções relacionadas a diferentes dimensões da experiência do cliente, como logística, atendimento, produto e preço, facilitando o alinhamento entre áreas e apoiando a tomada de decisão estratégica.

O NPS também possibilita a análise da relação entre satisfação do cliente e indicadores financeiros, como o valor do tempo de vida do cliente (Lifetime Value – LTV) e o custo de aquisição de clientes (Customer Acquisition Cost – CAC), contribuindo para a avaliação da eficiência das estratégias de retenção. Além disso, permite a identificação de riscos de churn, a priorização de melhorias operacionais e a segmentação de clientes com base em seus níveis de satisfação.


### 5.3.3	Quais áreas poderiam se beneficiar desses insights? Exemplos: logística, atendimento, pricing, produto etc. 
Os insights gerados por uma análise preditiva do NPS têm aplicação transversal na operação:
Logística: priorizar rotas e transportadoras com maior impacto em atrasos, reduzir tentativas de entrega frustradas e otimizar SLAs (Service Level Agreement, que define níveis de desempenho esperados, prazos e responsabilidades entre as partes).
Atendimento (CX): antecipar contatos recorrentes, dimensionar equipe por perfil de risco e reduzir tempo de resolução em casos críticos.
Produto: identificar categorias com maior taxa de reclamação e revisar descrições, fotos ou curadoria de fornecedores.
Pricing e Promoções: entender se faixas de desconto ou parcelamento afetam a percepção de valor e a satisfação final.
Estratégia e CRM: segmentar clientes por probabilidade de virarem promotores/detratores e direcionar campanhas de retenção.

### 5.3.4	Reflexão sobre o impacto do NPS em características adicionais
- Recompra
Promotores (avaliações elevadas) apresentam taxa de recompra significativamente maior do que detratores (avaliações baixas). Um cliente que teve experiência positiva não apenas volta, mas também tende a aumentar o ticket médio ao longo do tempo. Detratores, por outro lado, frequentemente abandonam a base após o primeiro problema não resolvido, comprometendo o lifetime value.
- Boca a boca
O NPS foi desenhado justamente para medir a propensão de recomendação. Em e-commerce, avaliações em marketplaces, redes sociais e grupos de consumo funcionam como vetores de boca a boca digital. Um detrator vocal pode impactar dezenas de potenciais compradores, enquanto um promotor atua como canal de aquisição orgânico e barato.
- Market share em e-commerce
Em mercados maduros e competitivos, a diferença entre líder e seguidores raramente está no produto ou no preço, mas na experiência. Empresas com NPS consistentemente acima da média do setor tendem a ganhar participação de mercado por retenção e aquisição orgânica, enquanto concorrentes gastam mais em mídia paga para compensar a evasão.
- Indicadores de mercado que complementariam a análise
Benchmarks de NPS por setor (varejo online brasileiro como referência competitiva).
SLA logístico da concorrência: tempo médio de entrega e taxa de cumprimento de prazo.
Churn rate e taxa de recompra do mercado.
CSAT de atendimento e tempo médio de resolução de chamados (TMR).
Reclamações públicas em plataformas como Reclame Aqui e análise de sentimento em reviews.

# 6	Definição da Target
6.1	Variável target baseada no problema de negócio
Após a etapa inicial do Entendimento do Negócio, onde traduzimos o problema de negócio em questão analítica, temos a base para a definição da variável target. O objetivo é definirmos exatamente o que o Modelo irá prever.
Problema de negócio identificado na etapa anterior: O problema de negócio consiste na limitação da empresa em antecipar a insatisfação dos clientes, priorizar ações corretivas e atuar de forma preventiva. Essa limitação decorre do fato de o NPS ser coletado apenas ao final da jornada de compra, caracterizando um indicador essencialmente reativo.

## 6.2	Definição da variável target

### 6.2.1	Qual variável representa a satisfação do cliente?
A variável que representa diretamente a satisfação do cliente no dataset é o campo nps_score, uma nota de 0 a 10 atribuída pelo próprio cliente após a experiência de compra. Seguindo a metodologia clássica do Net Promoter Score, essa nota pode ser traduzida em três segmentos: detratores (0 a 6), neutros (7 ou 8) e promotores (9 ou 10).
Tipo da **variável Target nps_score**.
- Quantitativa (Numérica) Discreta, no formato que assume notas de 0 a 10 (contagem que assume valor inteiro).
- Qualitativa (Categórica) Ordinal, no formato de ordenadas Detratores, Neutros e Promotores Representam uma hierarquia de satisfação.
A partir da variável target no formato original da base de dados (quantitativa discreta, notas de 0 a 10), foi criada uma variável qualitativa ordinal, classificando os clientes em detratores, neutros e promotores, conforme a metodologia NPS

Existe também o campo csat_internal_score, que mede satisfação interna, porém reflete a percepção operacional da empresa sobre o atendimento, não a avaliação espontânea do cliente. Por isso, a target de negócio é a variável nps_score.

A definição formal obtida no Dicionário de Dados da Base de dados NPS da variável nps_score  é a seguinte : 
nps_score: Nota de satisfação do cliente (NPS), variando de 0 a 10, coletada após a experiência de compra.

### 6.2.2	Por que ela foi escolhida?
O nps_score é a métrica que o próprio enunciado do case indica como alvo de predição e é a única variável do dataset que captura a voz direta do cliente. Além disso, é um indicador amplamente reconhecido no mercado, o que facilita a comunicação dos resultados para stakeholders não técnicos e permite comparação com benchmarks externos.

### 6.2.3	Em que momento da jornada essa informação é coletada?
O NPS é coletado após o encerramento da jornada de compra, tipicamente alguns dias depois da entrega, via pesquisa por e-mail, SMS ou dentro do aplicativo. Esse momento é importante porque significa que todas as variáveis operacionais do pedido (valor, logística, atendimento, etc.) já aconteceram quando a nota é dada — ou seja, elas são candidatas legítimas a features preditivas sem risco de data leakage temporal.

### 6.2.4	Existe algum risco de usar essa variável de forma inadequada?
Sim. Alguns riscos relevantes que o grupo precisa ter em mente:
•	Viés de resposta: nem todos os clientes respondem à pesquisa. Quem responde costuma estar nos extremos (muito satisfeito ou muito insatisfeito), gerando amostra não representativa da base total.
•	Data leakage: variáveis como complaints_count e csat_internal_score podem ser parcialmente construídas após a coleta do NPS ou estar fortemente correlacionadas a ele. É preciso validar a ordem temporal antes de usá-las como features.
•	Subjetividade da nota: o NPS mede percepção, não fato. Dois clientes com exatamente a mesma experiência podem dar notas diferentes por fatores externos (humor, expectativa prévia, ancoragem).
•	Risco ético e de ação automatizada: usar a predição de NPS para discriminar atendimento (por exemplo, priorizar apenas quem será promotor) pode criar desigualdade de tratamento e danos reputacionais. A predição deve apoiar decisões, não substituir julgamento humano.
•	Interpretação como escala contínua: tratar o NPS como variável contínua em regressão é válido, mas ignora a natureza discreta das faixas (detrator/neutro/promotor), que é o que o negócio efetivamente utiliza

# 7	Análise Exploratória de Dados (EDA)
Após e entendimento do negócio e a definição da variável target (que neste caso representa a satisfação do cliente), vamos entender e tratar os dados da base de dados e obter insights para as etapas posteriores. 
A Análise Exploratória de Dados (EDA – Exploratory Data Analysis) tem como objetivo investigar a estrutura, a distribuição e a qualidade dos dados por meio de técnicas estatísticas descritivas e visualizações, visando identificar padrões, relações e possíveis anomalias, de forma a orientar as etapas subsequentes de modelagem e análise.
Neste trabalho utilizamos a Base de Dados fornecida desafio_nps_fase_1, com 2500 linhas e 19 colunas.
A avaliação teve como objetivo o entendimento dos dados, identificação de eventuais ajustes na base, distribuição e relação entre as variáveis, interpretação do comportamento dos dados e entendimento de seus resultados para a continuidade do processo.

# 8	Modelagem
A partir da Análise Exploratória dos Dados, vamos partir para a elaboração de modelo que tenha como objetivo a utilização pela empresa nas análises e ações futuras.

# 9	Resultados



# 10 Considerações Finais



