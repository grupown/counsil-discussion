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
