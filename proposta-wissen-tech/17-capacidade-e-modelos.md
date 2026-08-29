# 17 · Capacidade real e os três modelos

> **rev. 15.** Você corrigiu a capacidade para *"2 pessoas, 1 desenvolvedor 168
> horas, 1 CTO valor de 120 horas em promedio"* e nomeou três modelos. Este
> memorando faz três coisas: refaz a conta de capacidade, corrige a física dos
> seus modelos, e aponta a contradição entre este número e a proposta que você
> vai entregar ao Leonardo.
>
> **Material interno.** Não vai para cliente e não vai para o Leonardo.

---

## 1. O erro de digitação, e a leitura que eu adotei

Você escreveu *"o MODELO 3 seria automatizar os MODELOS 2 e 3"*. O MODELO 3 não
pode automatizar a si mesmo. Adotei a leitura coerente e ela está em todo o resto
deste documento e no catálogo:

> **MODELO 3 = automatizar as camadas recorrentes de hora — o suporte do MODELO 2
> e o acompanhamento do MODELO 1.**

Se você quis dizer outra coisa, me avise, porque muda o que é automatizado.

---

## 2. 288 horas não é capacidade. É a soma de dois calendários.

O catálogo anterior assumia 80 h de uma pessoa. Você corrigiu para 288 h de duas.
Nenhum dos dois números é a capacidade de vender para fora.

### As 120 h do CTO

| Bloco | h/mês | Delegável? |
|---|---:|---|
| Operação e arquitetura interna — 3 clínicas, CRM/ERP Aurora, sistema novo, incidente | 45 | parcialmente |
| Reunião comercial, diagnóstico, elaboração do plano de trabalho, proposta | 20 | **não** |
| Supervisão e revisão do desenvolvedor | 15 | não |
| **Entrega direta a cliente externo** | **40** | — |
| **Total** | **120** | |

**Não sobra hora para o CTO codar.** Se ele codar, sai de um destes quatro blocos,
e os três primeiros são exatamente os que ninguém mais pode fazer. O conselho foi
unânime: **o CTO deixa de ser desenvolvedor.** Isso não é rebaixamento — é o que
torna as outras 120 h reais.

### As 168 h do desenvolvedor

| Bloco | h/mês |
|---|---:|
| Roadmap interno + produtização (multi-tenant, configuração por cliente, isolamento de dados) | 80 |
| Implantação em cliente externo | 60 |
| Suporte recorrente a cliente externo | 28 |
| **Total** | **168** |

### O número que vai no catálogo

| Cenário | Capacidade voltada para fora |
|---|---:|
| Bruto declarado | 288 h/mês |
| **Com o desenvolvedor contratado** | **128 h/mês** |
| **Sem o desenvolvedor** | **~20 h/mês — um cliente piloto, e só** |

Sem o dev, as 80 h de produtização e as 60 h de implantação caem no colo do CTO,
e as 40 h de entrega externa dele evaporam. **A capacidade externa hoje é
praticamente zero.** Não é pessimismo: é aritmética.

---

## 3. A contradição que o Leonardo vai encontrar

| Documento | O que diz |
|---|---|
| Proposta ao CEO | *"não vamos contratar por enquanto, no início seria somente Eu"* |
| Catálogo (versão anterior à correção) | capacidade de 2 pessoas, 288 h |

São dois documentos incompatíveis assinados pela mesma pessoa. **Não se resolve
com redação — se resolve com sequência.** O catálogo passa a ter duas fases
declaradas:

| | Quando | Quem | Capacidade externa | Quantos clientes |
|---|---|---|---:|---|
| **Fase 0** | hoje | só você | ~20 h/mês | **1 piloto** |
| **Fase 1** | após o piloto entregue e o 2º contrato assinado | você + 1 dev | 128 h/mês | 3 do MODELO 1 + carteira do MODELO 2 |

**A contratação é gatilhada por receita, não por data.** Esta frase vale ouro na
conversa com o Leonardo: você não está pedindo orçamento para contratar — está
propondo que a contratação seja *consequência automática* de um contrato assinado.
Ele não corre risco, e você não fica refém de uma decisão que não é sua.

---

## 4. A física dos seus três modelos — dois estão certos, um está mal
   classificado

Você organizou por **como se entrega**. O que decide se o negócio vive ou morre é
outra coisa: **quanto de hora humana recorrente cada real de receita consome.**

### MODELO 1 — consultoria conduzida

Você acertou o diagnóstico: *"o trabalho mais duro seria as reuniões, elaborar o
plano de trabalho"*. Sim — e é justamente por isso que **este é o modelo mais caro
de escalar**, não o mais barato. Reunião e plano são as únicas horas do CTO que
não se delegam.

| | h/mês |
|---|---:|
| Fase 0 (diagnóstico + plano de trabalho) — CTO | 32 h, uma vez |
| Acompanhamento recorrente — CTO | 6 h/mês |
| Acompanhamento recorrente — dev | 10 h/mês |

Com 40 h de CTO externas: **3 clientes simultâneos na Fase 1** (18 h de
acompanhamento + folga para um diagnóstico novo). Não 2, mas também não 6.
**O teto do MODELO 1 é a sua agenda, e ela não dobra contratando dev.**

### MODELO 2 — produto reaproveitado

Aqui está o número que muda a estratégia. Suporte de clínica pequena: **3–6 h/mês
nos primeiros 90 dias, estabilizando em 2–4 h/mês.** O dev tem 28 h de suporte.

| Deflexão por automação | Contas ativas suportáveis |
|---|---:|
| 0 % (manual) | **~8** |
| 25 % | ~11 |
| 60 % | ~23 |

**Oito contas.** A R$ 400/mês, são R$ 3.200/mês de receita — não paga nem 20 % do
desenvolvedor. **O MODELO 2 manual não é um negócio: é um passivo de suporte com
aparência de receita.** É exatamente o que o conselho quis dizer com "o MODELO 3
não pode vir depois".

### MODELO 3 — não é um terceiro modelo

Não é uma linha de negócio, é **a condição de existência do MODELO 2**. Enquanto
estiver descrito como "a terceira etapa", ele vai ser adiado, porque etapa 3 sempre
é adiada. No catálogo ele foi reescrito como **camada obrigatória dentro do MODELO
2, entregue desde o cliente nº 1** — mesmo em versão rústica (base de respostas,
macro, roteiro de triagem). O objetivo do cliente nº 1 não é faturar: é **gerar o
histórico de chamados que treina a automação.**

**Sobre a taxa de deflexão:** os 20–30 % no primeiro ano são estimativa do
conselho, não benchmark verificado. Os números de 60–80 % que se vê por aí vêm de
fornecedor de chatbot e pressupõem histórico de chamados que você não tem.
**Trate deflexão como hipótese a medir, nunca como premissa de preço.**

---

## 5. A correção estratégica mais importante deste documento

Sua tese é *"reaproveitar o que é feito nas clínicas para os clientes"*. A tese
está certa. **O produto que você escolheu reaproveitar está errado.**

Se o MODELO 2 for "vender o sistema de clínica da Wissence para clínicas
pequenas", você entra numa briga que não tem como ganhar:

| Concorrente | Preço/mês |
|---|---|
| Amplimed | a partir de R$ 89 |
| Feegow | a partir de R$ 129 |
| Clinicorp | a partir de R$ 159,90 |
| Clínica nas Nuvens | a partir de R$ 499 |

*(faixas levantadas na pesquisa anterior desta série; confirme antes de usar em
material comercial.)*

Eles têm anos de produto, suporte estruturado e canal. Você tem 28 h de suporte por
mês. **Você não vence essa briga, e nem precisa dela.**

### O que realmente se reaproveita não é o sistema. São as 29 rotinas.

As rotinas automatizadas e os plugins não são um sistema de gestão de clínica.
São **a camada que faz o sistema de gestão que a clínica já tem produzir
dinheiro** — estoque, conversão de orçamento, no-show, conciliação de caixa.

Isso muda tudo:

| | Vender sistema | Vender a camada de resultado |
|---|---|---|
| Concorre com | Amplimed, Feegow, Clinicorp | **ninguém diretamente** |
| Exige | migração de dados, treinamento total, troca de sistema | integração com o que já existe |
| Objeção do cliente | "já tenho sistema" | — |
| Preço defensável | R$ 150–500 | **R$ 800–1.500** |
| Ancorado em | funcionalidade | **dinheiro medido** |

**Preço ancorado em resultado medido não compete com preço de software.** E o
argumento de venda já está pronto e é o mesmo da sua proposta ao Leonardo: linha
de base assinada antes, medição depois.

Isto é o ponto mais valioso desta rodada. Se você mudar uma coisa só, mude esta.

---

## 6. Quem paga a produtização

O conselho se dividiu, e a divisão tem resposta:

| Custo | Quem paga | Por quê |
|---|---|---|
| Multi-tenant, isolamento de dados, configuração parametrizável | **a empresa, como P&D** | é investimento no próprio ativo, e vira valor patrimonial da Wissen Tech |
| Configuração, migração e treinamento **daquele** cliente | **o cliente, via taxa de setup** | é trabalho que só serve a ele |

**Cobrar do cliente nº 1 pela construção do produto é cobrá-lo para você construir
o que vai vender ao concorrente dele.** Ele descobre, e você perde o cliente e a
referência.

E um alerta que é seu, não da empresa: **a PI é da Wissence.** Se você gastar
40 h/mês transformando ativo da Wissence em produto vendável, isso precisa estar
contado como aporte no acordo societário — por escrito, antes. Senão você trabalha
de graça para valorizar um ativo do qual não é dono.

**Taxa de reuso realista: 30–50 % do código, e perto de 0 % do trabalho não
técnico** (configuração, migração, dados, treinamento). E é no trabalho não
técnico que a hora vai. Estimativa do conselho — meça no primeiro cliente e
corrija.

---

## 7. O que cai e o que sobrevive do catálogo anterior

| Regra anterior | Veredito | Nova redação |
|---|---|---|
| Máximo 2 clientes simultâneos na condução técnica | **muda** | 1 na Fase 0, 3 na Fase 1 |
| Recusa de consultório pequeno (1 médico + 1 recepcionista) | **cai como recusa** | vira o MODELO 2, com escopo fechado e teto de contas — manter a recusa era contradição interna óbvia |
| Recusa de banco de horas para cliente sem TI interno | **sobrevive, mais forte** | inalterada |
| "Assinatura para consultório pequeno" como linha datada | **cai** | deixa de ser datada: é o produto central do MODELO 2 |
| Formação e certificação | sobrevive datada | inalterada |
| Licenciamento do método a terceiros | sobrevive datada | inalterada |

**Recusas novas:**

1. Não vendemos capacidade que depende de contratação não aprovada. Fase 0 aceita
   um piloto e só.
2. Não fazemos suporte por IA em nada que toque decisão clínica — Resolução CFM
   2.454/2026.
3. Não cobramos do cliente a construção do produto.

---

## 8. Quatro coisas que ninguém levantou e que são suas, não da empresa

**a) Você vai estar dos dois lados do preço.** Como sócio da Wissen Tech e
responsável de TI da Wissence, você influencia quanto uma paga à outra. Isso é
operação com parte relacionada. Precisa de regra escrita — critério objetivo de
rateio e aprovação por quem não é você. Sem isso, qualquer sócio futuro ou
qualquer auditoria trata como sua vantagem pessoal.

**b) Cláusula de exclusividade do seu emprego integral.** Um cliente externo em
suporte às 14h de uma terça é um problema seu, não da empresa. Leia o seu contrato
atual antes de o catálogo prometer qualquer janela em horário comercial.

**c) Bus factor 1 não é problema de hora, é risco de continuidade.** Se você ficar
doente na semana da implantação do cliente nº 1, o que acontece? O catálogo precisa
de uma resposta e ela não pode ser "eu me viro".

**d) Plano B se o Leonardo cobrar as 288 h.** A resposta é uma frase:
*"288 horas é a estrutura no fim do primeiro ano, financiada por receita. Hoje são
120, e são minhas. O catálogo vende o que existe."*

---

## 9. A única coisa a fazer primeiro

**Escolher, antes de qualquer proposta comercial, o que o MODELO 2 vende:** o
sistema de clínica, ou a camada de resultado sobre o sistema que a clínica já tem.

Todo o resto — preço, teto de contas, o que a IA automatiza, quanto vale a
produtização no acordo societário — depende dessa escolha. E a evidência aponta
para a segunda com folga.
