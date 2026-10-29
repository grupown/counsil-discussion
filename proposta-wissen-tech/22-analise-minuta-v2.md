# 22 · Análise da Minuta v2 — Contrato de Outorga com Vesting

> **rev. 29 · 29/10/2026.** Dois meses depois do Term Sheet v3, chegou a minuta
> contratual. Lida na íntegra pelo conector do Claude Docs — o documento está
> compartilhado com o autor **como writer**, ou seja, ele pode comentar e editar
> dentro dele.
>
> Doc: "Minuta v2 — Vesting WissenTech × Gustavo Polar", rascunho do controlador
> para análise interna.

---

## 1. Eles se moveram em quase tudo

Comparando com o que eu tinha apontado em agosto:

| | Term Sheet v3 (ago) | Minuta v2 (out) |
|---|---|---|
| Na assinatura | **0 %** | **5 %, liberadas, sem meta e sem prazo** |
| Carência | 12 meses | **nenhuma** |
| Remuneração | R$ 20.000 | **R$ 25.000**, com revisão para até R$ 40.000 no mês 6 |
| Aceleração em venda | não existia | **existe, proporcional ao % vendido** |
| Critério de aceite | "critério único do grupo" | **plano assinado pelas duas partes + avaliador independente** |
| Métricas | uso ativo de 70 %, SLA de 48 h — fora do controle dele | **entregas dele, com peso e critério de aceite** |
| PI | "retroativa, inclusive a consultoria anterior" | **só o criado na prestação; a retroação sumiu** |
| Proteção do valuation | não havia | **9.3 — a tabela intragrupo não pode cair sem a anuência dele** |
| Contrato intragrupo | mencionado | **condição para assinar (6.5)** |

**Dos itens que eu listei como "não ceder", praticamente todos foram atendidos.**
A estrutura também ficou mais inteligente: a participação deixou de depender de
receita que ele não vende e passou a depender de entregas que ele controla — que era
exatamente a crítica da análise anterior. O considerando (iii) explica o raciocínio e
ele está correto.

É um documento sério, com notas de fundamentação legal corretas (art. 122 do Código
Civil sobre condição puramente potestativa, arts. 1.031 e 1.085 sobre haveres, art.
413 sobre redução de penalidade, Tema 1.389 do STF, Lei 15.270/2025). Quem escreveu
sabe o que está fazendo.

## 2. O fato novo que muda o cálculo de risco

Considerando (ii): *"O Beneficiário deixou seu vínculo anterior em [data] e passou a
dedicar-se integralmente à Sociedade."* E nas decisões pendentes: *"data de saída do
Beneficiário do Mercado Livre."*

**Tudo o que eu escrevi sobre 70 horas semanais virou passado.** Em compensação,
nasce um risco novo e maior: **não há mais renda alternativa.** Isso eleva
enormemente o peso das cláusulas de desligamento — que antes eram hipótese e agora
são o que separa uma carreira de uma ruína.

É por isso que os três pontos abaixo são de outra natureza que os da rodada passada.

## 3. Não assinar sem resolver — os três

### 3.1 · O Valor Justo está em branco · Cláusula 9.1

> *"Até a Sociedade registrar EBITDA positivo em [2] exercícios consecutivos, o Valor
> Justo de cada quota é **R$ [●]**."*

**Este é o campo mais importante do documento inteiro e está vazio.** Ele determina:

- quanto ele recebe se sair como good leaver e a Cedente exercer a opção de compra;
- o piso do valor na Fase 2 (9.2 diz que o resultado nunca pode ser inferior ao da
  Fase 1);
- e, por consequência, quanto valem os 25 % em qualquer cenário que não seja venda a
  terceiro.

Se esse número for preenchido como R$ 1,00 — o preço da outorga —, **os 25 % valem
R$ 25.000 na saída.** O múltiplo de EBITDA da Fase 2 (9.2) também está em branco.

**Não é detalhe de advogado. É o preço.**

### 3.2 · "Culpa grave" em incidente de dados é bad leaver · Cláusula 8.1(a)

> *"vazamento, cópia não autorizada ou uso indevido de dados... inclusive incidente
> de dados pessoais causado por dolo ou **culpa grave** (LGPD)"*

Consequência: perda de tudo o que não venceu **mais** recompra do que venceu pelo
preço pago — perto de R$ 1 por quota.

**Por que isto é perigoso especificamente para ele**, e não em tese: o material da
reunião de 26/08 documenta uma operação com **uma única pessoa que publica, sem
automação de publicação, sem CI/CD, com deploys fora de horário comercial.** Nesse
ambiente, um incidente de dados é uma questão de tempo, e caracterizá-lo como culpa
grave é trivial para quem quiser.

**Uma falha operacional previsível converte-se em perda total da participação.**

Pedir: ou a hipótese exige **dolo**, ou a caracterização de culpa grave passa pelo
avaliador independente da Cláusula 4.6 — não pela decisão unilateral da Cedente.

### 3.3 · A combinação que produz ruína

Três cláusulas que, isoladas, são razoáveis:

| | |
|---|---|
| 8.2(b) | bad leaver recompra as quotas **pelo preço pago**, sem atualização |
| 11.4 | não concorrência de **24 meses** em sistemas de gestão e IA para clínicas no Brasil |
| considerando (ii) | ele **não tem mais o emprego anterior** |

Somadas: num cenário de bad leaver, ele sai com cerca de R$ 25 mil pelas quotas, sem
emprego, e proibido de trabalhar no próprio setor por dois anos.

A nota do documento reconhece o problema — *"os advogados devem avaliar se a não
concorrência precisa de compensação financeira para ser válida. A recompra pelo Valor
Justo em parcelas pode servir como essa compensação"* — **mas no bad leaver não há
recompra pelo Valor Justo.** Há recompra pelo preço pago. Logo, no cenário em que a
não concorrência mais dói, a compensação que a justificaria não existe.

Pedir: a não concorrência não se aplica, ou é remunerada, quando a recompra se der
pelo preço da outorga.

## 4. Pedir — os quatro

**4.1 · Cláusula 4.5, a alternativa já está escrita.** Quotas não liberadas voltam à
Cedente e não acumulam. O próprio texto traz entre colchetes a alternativa de
recuperar até 50 % no ano seguinte com índice de 100 %. **Diga sim a ela** — sem isso,
um ano ruim é perda permanente de 5 % da empresa.

**4.2 · Cláusula 4.4, o degrau de 70 % é brusco demais.**

| Índice | Quotas | Da empresa |
|---:|---:|---:|
| 69 % | 0 | 0,00 % |
| **70 %** | **3.500** | **3,50 %** |
| 85 % | 4.250 | 4,25 % |
| 100 % | 5.000 | 5,00 % |

**Um ponto percentual de índice, entre 69 e 70, vale 3,5 % da empresa.** Pedir piso
mais baixo com proporcionalidade desde, por exemplo, 50 %.

**4.3 · Cláusula 8.1(h) — abandono por 30 dias é bad leaver.** Trinta dias é pouco
para doença séria, acidente ou emergência familiar. Pedir prazo maior e exclusão
expressa de afastamento por saúde.

**4.4 · Anexo I — "implantação em cada cliente em até 30 dias", peso 15 %.** A ata de
26/08, com os números da própria equipe, mediu **15 a 45 dias, duas implantações em
paralelo**. É a única métrica do anexo que ainda contradiz a capacidade medida.

## 5. Confirmar — os dois

**5.1 · Franqueado não conta como Receita Externa.** As cláusulas 1.7 e 7.2(a)
excluem "licenciada da rede". Mas o canal de franquia foi identificado em todo o
trabalho anterior como **o melhor canal da empresa** — cliente pré-qualificado, custo
de aquisição próximo de zero.

Ou seja: **a receita mais fácil de trazer é justamente a que não gera bônus.** Pode ser
intencional, porque franqueado já é do grupo; mas vale perguntar, porque a cláusula
6.4 coloca "prospecção de novos negócios" no escopo dele.

Para dimensionar o teto do bônus:

| Remuneração | Teto do bônus | O teto só morde acima de |
|---|---:|---|
| R$ 25.000 | R$ 125.000/ano | R$ 625 mil/ano de receita externa |
| R$ 40.000 | R$ 200.000/ano | R$ 1 milhão/ano |

Abaixo desses volumes ele recebe os 20 % cheios. O teto é generoso no começo.

**5.2 · Cláusula 12.1 substitui tudo o que veio antes.** Confirmar explicitamente que
isso inclui a carta de termos de agosto — **em especial a cessão de PI irrevogável e
retroativa que valia desde a rubrica.** Se aquela carta chegou a ser rubricada, esta
cláusula é o que a mata, e isso precisa estar claro.

## 6. O que ficou bom e merece ser dito

- **A parcela inicial de 5 % não depende de nada** além de não ser bad leaver (3.2).
  É o oposto do cliff de 12 meses da versão anterior.
- **A aceleração proporcional da 10.1** é um desenho elegante: ele nunca bloqueia uma
  venda, e recebe na proporção do que foi vendido.
- **A 9.3** é a melhor cláusula do documento para ele. A tabela do contrato intragrupo
  não pode ser reduzida sem a anuência dele enquanto for sócio ou credor — fecha
  exatamente o buraco de parte relacionada que eu vinha apontando desde o começo.
- **A 4.6 e a 9.4** tiram da Cedente a palavra final sobre metas e valor.
- **A 12.2** separa expressamente a relação societária da de serviços.

## 7. O que fazer

Ele é **writer** no documento — pode comentar dentro dele, ancorado em cada cláusula,
em vez de mandar uma lista por fora. É o melhor caminho: comentário em cláusula fica
preso ao texto e entra na próxima versão.

Ordem sugerida: os três do item 3 como comentários marcados, os quatro do item 4 como
comentários normais, e os dois do item 5 como perguntas.

**E uma consulta de advogado antes de assinar**, com três perguntas que o próprio
documento já lista mas que são dele, não do controlador: o risco de vínculo de emprego
no modelo PJ com metas e dedicação integral (Tema 1.389); a validade da recompra pelo
preço pago; e a validade da não concorrência de 24 meses sem compensação no cenário
de bad leaver.


---

## 8. O valor do salário faz sentido?

**R$ 25.000 está baixo. R$ 40.000 está certo. E a cláusula que leva de um ao outro é
a única do contrato que não tem gatilho.**

### 8.1 · PJ não é CLT, e a diferença é grande

A cláusula 6.1 paga por pessoa jurídica. Sem 13º, sem férias com um terço, sem FGTS,
sem multa rescisória, sem seguro-desemprego — e com o imposto por conta dele. O
multiplicador de mercado para manter o mesmo padrão fica entre **1,4 e 1,65**:

| | Equivalente CLT |
|---|---|
| **R$ 25.000 PJ** | **R$ 15.000 a 18.000** |
| **R$ 40.000 PJ** | **R$ 24.000 a 29.000** |

### 8.2 · Contra o mercado de 2026

| Fonte | Faixa |
|---|---|
| Glassdoor · CTO | R$ 11 a 30 mil · mediana ~R$ 20 mil |
| Glassdoor · Head de Tecnologia | R$ 15 a 25 mil · mediana ~R$ 20 mil |
| CTO de startup em estágio inicial | R$ 15 a 25 mil, com participação |
| Robert Half · CTO (empresa média e grande) | mediana ~R$ 38 mil, topo R$ 49,5 mil |

**R$ 25.000 PJ equivale a um CLT abaixo da faixa de CTO em todas as fontes** — abaixo,
inclusive, da mediana de Head de Tecnologia. **R$ 40.000 PJ cai dentro da faixa**: topo
da banda de startup, média do Glassdoor, bem abaixo da Robert Half.

*Os números do Glassdoor vêm de amostras pequenas e autodeclaradas; a Robert Half mira
empresa média e grande. Trate como ordem de grandeza.*

A banda de R$ 15 a 25 mil para CTO de estágio inicial pressupõe **participação
relevante em troca** — e ele tem 5 % na assinatura. Então R$ 25.000 como ponto de
partida não é absurdo. **O problema não é o valor inicial: é não haver nada que
garanta a saída dele.**

### 8.3 · O achado — a cláusula 6.2 é a única discricionária do contrato

> **6.2.** A remuneração mensal é de R$ 25.000. Após 6 meses da Data de Assinatura,
> haverá uma revisão única, vinculada à avaliação dos dois primeiros trimestres, que
> **poderá** elevar a remuneração para **até** R$ 40.000.

*Poderá. Até.* Sem gatilho, sem fórmula, sem árbitro.

Compare com o resto do documento, que é obsessivamente objetivo:

| Cláusula | Mecanismo |
|---|---|
| 4.4 | escala numérica pelo Índice de Atingimento |
| 4.6 | avaliador técnico independente em divergência |
| 7.1 | fórmula fechada — o menor entre dois valores |
| 9.1 e 9.2 | revisão anual com piso, e múltiplo de EBITDA |
| 9.4 | avaliador independente, com custo para quem errar mais |
| 10.1 | aceleração proporcional, calculada |
| 8.1 | lista fechada de hipóteses |
| **6.2** | **"poderá… até"** |

**E há uma ironia que é o melhor argumento dele.** A nota da cláusula 4.2 diz:

> *"as metas não podem depender só da vontade de uma das partes. Uma condição desse
> tipo é nula pelo art. 122 do Código Civil."*

**O documento conhece o princípio, aplica-o à participação, e não o aplica ao caixa
dele.** Não é preciso inventar argumento: basta pedir coerência com a própria nota.

### 8.4 · A correção usa a máquina que já existe

A cláusula 4.3 já prevê avaliação trimestral registrada em ata. A 4.4 já tem a escala.
Basta amarrar uma na outra:

| Índice dos dois primeiros trimestres | Remuneração a partir do mês 7 |
|---|---|
| 90 % ou mais | **R$ 40.000** |
| 70 % a 89 % | proporcional entre R$ 30.000 e R$ 40.000 |
| abaixo de 70 % | mantém R$ 25.000, com nova revisão em 6 meses |

Zero mecanismo novo. Mesma lógica da 4.4. **E transforma "poderá" em "será".**

### 8.5 · Por que eles escreveram assim — e a conexão que isso revela

O salto custa caro, e é honesto reconhecer:

| | Custo mensal | Equilíbrio em receita externa |
|---|---:|---:|
| Ele a R$ 25 mil | R$ 49 mil | R$ 37 mil/mês |
| Ele a R$ 40 mil | R$ 64 mil | **R$ 52 mil/mês** |

**O salto eleva em 41 % a receita externa necessária para a empresa se pagar.** Quase
certamente é por isso que a cláusula ficou discricionária.

**Mas isso revela algo maior.** A cláusula 6.5 diz que é o Contrato de Serviços
Intragrupo que dá receita para pagar a remuneração. E a 9.3 diz que o EBITDA — que
define o Valor Justo das quotas — é calculado com a receita desse mesmo contrato.

Logo: **se a tabela intragrupo não sustenta R$ 40 mil, ela também não sustenta um
EBITDA que faça as quotas dele valerem alguma coisa.** Salário, valor da participação
e preço do intragrupo são o mesmo problema, e a 9.3 só protege um número que precisa
ser alto o bastante para valer a pena proteger.

**A pergunta certa não é "por que não R$ 40 mil".** É *"qual é a tabela do intragrupo,
e ela sustenta a empresa?"* — que, não por acaso, é a condição de assinatura da
cláusula 6.5 e ainda não foi apresentada.

### 8.6 · A conta que só ele pode fazer

Tudo acima é mercado. **O número que decide é outro: o que ele deixou para trás.**

Antes havia R$ 13 mil da Wissence, cerca de R$ 10 mil de freelance, o emprego integral
e o restaurante. O considerando (ii) diz que o emprego acabou.

**R$ 25.000 pode ser uma queda de renda total**, e isso não aparece em nenhum guia
salarial. A comparação que importa não é com a mediana do Glassdoor — é com o que ele
ganhava somando tudo em julho.

Se R$ 25.000 for abaixo disso, **o degrau não é uma melhoria de carreira: é um
empréstimo que ele está fazendo à empresa**, e que só se paga pela participação. O que
devolve a conversa, de novo, para o campo em branco da cláusula 9.1.


---

## 9. Como entrar na negociação, e a contraproposta

### 9.1 · A postura, e por que ela é esta

Três fatos definem o jeito certo de entrar:

**Eles já se moveram em nove pontos.** Do term sheet de agosto para esta minuta,
praticamente tudo o que a análise anterior apontou foi atendido. Isso é evidência de
boa-fé, e muda a postura: **não é contraproposta, é fechamento.**

**Ele não tem mais BATNA.** Deixou o vínculo anterior. Não pode levantar da mesa, e
blefar de posição fraca é a pior coisa que se faz numa negociação. A boa notícia é que
a postura que funciona aqui — colaborativa — é a mesma que a posição fraca exige.
**Não há conflito entre o que convém e o que dá para sustentar.**

**O documento é um rascunho que pediram para ele analisar**, e ele é *writer* nele.
Comentário ancorado em cláusula entra na próxima versão; lista por e-mail vira resumo
e perde precisão.

### 9.2 · A regra de ouro desta rodada

**Não negociar os números de manchete.** Os 25 % e os R$ 25 mil não são o problema — a
estrutura está boa. **O valor está nos campos em branco e nas assimetrias.** Pedir 30 %
ou R$ 30 mil de partida gasta boa-fé no lugar errado e sinaliza que ele não leu o
documento com atenção.

### 9.3 · A contraproposta, em quatro blocos

Organizada por quanto custa a eles — do que não custa nada ao que custa.

#### Bloco 1 · Completar o documento — três campos em branco

**Não são pedidos.** São o que falta para o contrato poder ser avaliado.

| Onde | O que falta |
|---|---|
| 9.1 | O Valor Justo da Fase 1 — `R$ [●]` |
| 9.2 | O múltiplo de EBITDA da Fase 2 — `[●] vezes` |
| 6.5 | A tabela de preços do Contrato de Serviços Intragrupo |

#### Bloco 2 · Três cláusulas — o que ele precisa ajustar

São as únicas marcadas como bloqueantes. **Marcar só três é o que faz as três serem
levadas a sério.**

| Cláusula | Pedido |
|---|---|
| **6.2** | Amarrar a revisão ao Índice de Atingimento, com a escala da 4.4 |
| **8.1(a)** | Retirar "culpa grave", ou caracterização pelo avaliador da 4.6 |
| **11.4** | Não concorrência não se aplica quando a recompra for pelo preço da outorga |

#### Bloco 3 · Quatro ajustes de redação — num comentário só

| Cláusula | Ajuste |
|---|---|
| 4.5 | Adotar a alternativa que já está entre colchetes (recuperar 50 %) |
| 4.4 | Piso em 50 % em vez de 70 % — hoje, um ponto de índice vale 3,5 % da empresa |
| 8.1(h) | 60 dias em vez de 30, com exclusão de afastamento por saúde |
| Anexo I | Implantação em 45 dias, alinhada à capacidade medida em 26/08 |

#### Bloco 4 · Uma pergunta

**7.2(a)** — franqueado está fora da Receita Externa. É intencional? É o canal de menor
custo de aquisição do catálogo, e a 6.4 coloca prospecção no escopo dele.

### 9.4 · Os textos, prontos para colar

**Mensagem de abertura, antes dos comentários:**

> Leonardo, li a minuta inteira. Comparando com o term sheet de agosto, vocês mudaram
> quase tudo o que eu tinha levantado — os 5 % na assinatura sem carência, a aceleração
> em venda, o critério de aceite bilateral com avaliador independente, as métricas
> trocadas por entregas que eu controlo, e a proteção da 9.3 sobre a tabela intragrupo.
> É um documento melhor do que eu esperava, e dá para fechar.
>
> Comentei dentro do documento, em três blocos: três campos em branco que dependem de
> vocês, três cláusulas que eu preciso ajustar, e quatro ajustes de redação. **As três
> do segundo bloco são as que eu não consigo assinar como estão.** O resto é conversa
> rápida.

**Comentário na 9.1:**

> Este campo define quanto valem as quotas em qualquer saída que não seja venda a
> terceiro, e é o piso da Fase 2 pela 9.2. Não consigo avaliar o contrato sem ele
> preenchido — mesma coisa para o múltiplo da 9.2.

**Comentário na 6.5:**

> A tabela do intragrupo é condição de assinatura por esta cláusula, e é também a base
> do EBITDA da 9.2. Conseguimos fechar essa tabela antes de assinar?

**Comentário na 6.2:**

> Esta é a única cláusula do contrato sem gatilho objetivo: "poderá… até". A nota da
> 4.2 diz, corretamente, que condição que dependa só da vontade de uma das partes é
> nula pelo art. 122 do Código Civil — o mesmo raciocínio vale aqui.
>
> Proponho usar a máquina que já existe. A 4.3 apura o índice trimestralmente, e a
> escala segue a lógica da 4.4: índice dos dois primeiros trimestres igual ou acima de
> 90 % leva a R$ 40 mil; entre 70 e 89 %, proporcional entre R$ 30 e R$ 40 mil; abaixo
> de 70 %, mantém R$ 25 mil com nova revisão em seis meses.

**Comentário na 8.1(a):**

> Peço retirar "culpa grave" e deixar apenas dolo — ou, se preferirem manter, que a
> caracterização passe pelo avaliador independente da 4.6.
>
> A razão é factual, não teórica: hoje a operação tem uma única pessoa publicando, sem
> automação de publicação. Nesse ambiente um incidente é risco operacional conhecido, e
> esta cláusula transforma uma falha previsível em perda total da participação mais
> recompra pelo preço pago.
>
> **E a resposta certa para esse risco não é contratual, é técnica:** quero colocar a
> automação de publicação e o plano de resposta a incidente no Plano de Metas do Ano 1,
> com peso. Resolvido isso, a cláusula fica proporcional.

**Comentário na 11.4:**

> A nota desta cláusula diz que a recompra pelo Valor Justo em parcelas pode servir de
> compensação à não concorrência. Concordo com o raciocínio — mas no bad leaver a
> recompra é pelo preço pago (8.2b), e não pelo Valor Justo. No cenário em que a não
> concorrência mais pesa, a compensação que a validaria não existe.
>
> Proponho: a não concorrência não se aplica quando a recompra se der pelo preço da
> outorga, ou é remunerada nesse caso. Como deixei meu vínculo anterior, é o cenário em
> que eu ficaria sem participação, sem remuneração e impedido de trabalhar no setor.

**Comentário na 4.5:**

> Sim à alternativa entre colchetes: recuperar até 50 % do que faltou, no ano seguinte,
> com índice de 100 %.

### 9.5 · O que NÃO fazer

| | Por quê |
|---|---|
| Pedir mais que 25 % ou mais que R$ 25 mil de partida | A estrutura está boa; o valor está nos brancos. Gasta boa-fé no lugar errado. |
| Mandar os dez pontos com peso igual | Eles tratam tudo como negociável e dividem a diferença nos errados. **Marcar três é o que faz três serem levadas a sério.** |
| Blefar com saída | Ele não tem para onde ir, e os dois sabem disso. |
| Discutir a referência de hora | Continua valendo o de sempre: quanto maior, mais caro ele paga pela mesma fatia. |

### 9.6 · A sequência

1. **Hoje:** mensagem de abertura e os comentários no documento. Os do Bloco 1 primeiro
   — pedir que preencham o próprio documento é o jeito mais barato de abrir.
2. **Quando a v3 voltar:** conferir se os três do Bloco 2 entraram. Se dois dos três
   entrarem, está fechado.
3. **Antes de assinar, não antes de conversar:** uma hora de advogado, com três
   perguntas que são dele e não do controlador — risco de vínculo de emprego no modelo
   PJ com metas e dedicação integral (Tema 1.389 do STF), validade da recompra pelo
   preço pago, e validade da não concorrência de 24 meses sem compensação.

**O ponto de corte:** se o Valor Justo da 9.1 vier preenchido com o preço da outorga —
R$ 1 por quota —, os 25 % valem R$ 25 mil em qualquer saída que não seja venda a
terceiro, e a conversa toda sobre participação era decorativa. **Esse número é o que
decide se vale a pena, e tudo o mais é secundário a ele.**

---

## 10. Os seis meses já trabalhados, e o escopo que cresceu

Dois fatos novos entram na negociação: ele opera desde maio, e hoje apoia também
financeiro, marketing e comercial. Mudam o pedido — mas não na direção que parece.

### 10.1 · O ponto cego: o escopo extra está custando quotas a ele

A 4.4 define as parcelas anuais de 5 % pelo Índice de Atingimento. O índice é apurado
contra o **Anexo I**, e o Anexo I só tem métrica de tecnologia — implantação em 30 dias,
disponibilidade, entregas.

**Financeiro, marketing e comercial não estão no Anexo I.** Então cada hora gasta neles
não gera índice, e o que não gera índice não gera quota. Ele está fazendo trabalho extra
que **reduz** a participação que vai receber, porque consome a capacidade que produziria
as entregas medidas.

Três saídas, e ele precisa escolher uma antes de assinar:

1. O escopo extra entra no Anexo I com peso próprio;
2. Fica fora, e o índice é ajustado proporcionalmente à capacidade que ele consome;
3. É explicitamente temporário, com data para passar adiante.

**O que não pode é continuar como está**, que é a única configuração em que ele paga
pelo próprio esforço.

### 10.2 · O segundo ponto cego: "faço mais" é um argumento contra ele

Dizer "estou apoiando no financeiro, marketing e comercial" sem enquadrar machuca de
duas formas:

- **Lê-se como capacidade sobrando.** Todo o diagnóstico deste projeto é que a
  capacidade é a restrição — 38 h/mês livres, 22 h/mês perdidas em limpeza manual, um
  único desenvolvedor. Se sobra tempo para marketing, o argumento da capacidade cai.
- **Já está sendo entregue de graça.** Demonstrar que faz sem cobrar estabelece o preço
  em zero. Pedir depois é pedir para reprecificar o que já é gratuito.

O enquadramento que funciona não é "faço mais, pague mais". É **"o risco que a carência
existe para cobrir já foi corrido"**.

### 10.3 · O que os seis meses realmente compram

A 3.1 dá 5 % na assinatura sem carência. Essa parcela existe para remunerar a entrada e
o risco de encaixe — risco que **já foi corrido, de maio a outubro, e deu certo**.

Mas o relógio do vesting começa na assinatura. Os seis meses não contam para nada.

**O pedido mais barato do documento inteiro:** antecipar a primeira parcela anual de 5 %
para o mês 6, em reconhecimento ao período já cumprido. Custa zero em caixa, continua
condicionada ao índice (se ele não entregar, não recebe), usa a máquina que já existe, e
é justificada por um fato que os dois lados conhecem.

### 10.4 · Os valores

| # | Pedido | Vale | Argumento |
|---|---|---|---|
| 1 | Primeira parcela de 5 % antecipada para o mês 6 | 5 % seis meses antes, e o teto de 25 % no mês 42 em vez do 48 | Maio a outubro já cumpriu a carência |
| 2 | 6.2 automática pelo índice | até R$ 180 mil/ano | A nota da 4.2 deles diz que condição potestativa é nula |
| 3 | Piso de R$ 28.000 em vez de R$ 25.000 | R$ 36 mil/ano | Escopo real já inclui comercial e financeiro |
| 4 | Escopo extra no Anexo I, ou índice ajustado | as parcelas anuais inteiras | Hoje o trabalho extra reduz a participação |
| 5 | 8.1(a) sem "culpa grave" | os 25 % | Operação sem automação de publicação |
| 6 | 11.4 afastada na recompra ao preço da outorga | liberdade de trabalhar | Sem compensação não há validade |

Mais os três brancos: Valor Justo (9.1), múltiplo (9.2), tabela do intragrupo (6.5).

**A hierarquia importa mais que os números.** O item 2 vale cinco vezes o item 3. Se ele
gastar capital no piso e perder o mecanismo, perde a negociação ganhando a discussão.

### 10.5 · A frase que abre

> **Não estou entrando. Estou formalizando o que já existe desde maio.**

A minuta está escrita como se ele chegasse agora. Não chega — opera há seis meses, com
resultado conhecido pelos dois lados. É disso que decorrem os pedidos 1 e 3, e é o único
argumento da mesa que não depende de projeção nenhuma.
