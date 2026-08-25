# 11 · A escada até 40 % e quanto cada percentual vale

> **rev. 8.** Você pediu o caminho até 40 % e a participação nos lucros. Os dois
> estão aqui — e o segundo é mais importante que o primeiro.

## O dinheiro primeiro, porque ele reordena tudo

Base de custo mensal assumida para a Wissen Tech:

| Item | R$ / mês |
|---|---|
| Seu retainer | 30.000 |
| 1 desenvolvedor pleno, PJ | 12.000 |
| 1 analista de suporte, PJ | 5.000 |
| Infra, ferramentas, contabilidade, licenças | 4.000 |
| **Total** | **51.000** |

Carga tributária efetiva assumida em **~11 % da receita** (Simples Anexo III com
fator R atendido — item de contador). Serviço no Brasil é tributado sobre
**receita**, não sobre lucro: por isso margem baixa em prestação de serviços
praticamente desaparece.

| Cenário | Receita/ano | Lucro/ano | 12 % | 28 % | 40 % |
|---|---|---|---|---|---|
| **A · rateio puro, sem margem** — o mais provável | 612.000 | **0** | R$ 0 | R$ 0 | **R$ 0** |
| **B · interno, margem contratada 20 %** | 734.400 | 41.600 | 416/mês | 971/mês | **1.387/mês** |
| **C · interno + 60 clientes externos a R$ 900** | 1.382.400 | 414.300 | 4.143/mês | 9.668/mês | **13.811/mês** |

**No cenário mais provável, 40 % vale zero reais — para sempre, por desenho
fiscal.** E no cenário B, 40 % da empresa vale R$ 1.387/mês contra um retainer de
R$ 30.000: 4,6 % da sua remuneração.

**Regra prática: nunca troque R$ 2.000 de retainer por pontos percentuais.** A
matemática não fecha em nenhum cenário interno.

### Onde o percentual vale algo: valor patrimonial

Múltiplos verificados para SaaS B2B brasileiro: **2x a 4x ARR** para crescimento
moderado; 4x a 8x para crescimento acima de 40 % com boa retenção.

| Múltiplo sobre o ARR do cenário C | Valor da empresa | 28 % | 40 % |
|---|---|---|---|
| 2x — conservador | R$ 2,76 mi | R$ 774 mil | R$ 1,10 mi |
| **3x — base** | **R$ 4,15 mi** | R$ 1,16 mi | **R$ 1,66 mi** |
| 4x — otimista | R$ 5,53 mi | R$ 1,55 mi | R$ 2,21 mi |

**A resposta em uma frase:** seus 40 % valem R$ 1.400/mês se a empresa ficar
interna, ou R$ 14 mil/mês mais R$ 1,7 milhão de valor patrimonial se houver
negócio externo real. **A escada não é sobre percentual — é sobre criar a receita
externa que dá valor ao percentual.**

## O número que derruba uma premissa do plano

Preços verificados de software de gestão para clínica no Brasil, 2026:

| Fornecedor / faixa | Mensalidade |
|---|---|
| Amplimed (entrada) | R$ 89 / mês por profissional |
| Feegow | R$ 129 / mês |
| Clinicorp | R$ 159,90 / mês |
| Clínica nas Nuvens Essencial | R$ 499 / mês |
| Faixa intermediária de mercado | R$ 400 – 800 / mês |

**Pequeno consultório paga R$ 89 a R$ 499 por mês.** O cenário C precisa de R$ 900
de ticket — quase o dobro do topo do segmento. Só fecha vendendo **serviço**, não
software. E se o alvo for consultório pequeno a R$ 300/mês, **você precisa de 180
clientes** para chegar ao cenário C.

Não existe operação comercial no plano para vender 180 contratos, e **você não vai
construí-la em meio período.** Pergunte ao Leonardo qual é o segmento real e qual é
o ticket. Se a resposta for "consultório pequeno", os degraus de cima não disparam
nunca e os 40 % são conversa.

## A escada, com marco mensurável em cada degrau

| Degrau | Marco | Como se mede | Prazo | % |
|---|---|---|---|---|
| **Base** | Assinatura | PI licenciada + contrato com o grupo + natureza do faturamento definida | — | **12 %** |
| **T1** interno | Marco da Etapa 2 — a matriz roda sem o dono | 5 dias úteis consecutivos em Jundiaí com zero alerta órfão e zero SLA estourado. Fonte: log do motor + trilha de fechamento | 6 meses, **suspenso enquanto a alçada estiver em branco** | 15 % |
| **T2** interno | Produto legalmente vendível fora | (a) zero IDs de clínica no código, comprovado provisionando unidade de teste em < 1 dia; (b) inventário LGPD cobrindo 100 % dos skills que tocam dado pessoal; (c) responsável técnico nomeado por unidade | 12 meses | 18 % |
| **T3** o moat | Camada 3 entregue | Certificação por pessoa em operação, ≥ 80 % do quadro das 3 unidades certificado, e 1 ciclo de auditoria de aderência concluído com nota por área | 18 meses | 21 % |
| **T4** externo | 1º cliente externo pagante | Contrato com PJ sem relação com o grupo, ≥ 12 meses, primeira fatura paga | sem prazo | 24 % |
| **★ Porta** | Dedicação integral | Notificação formal de saída do Mercado Livre. Gatilho unilateral seu. Retainer vira pró-labore de R$ 36.000, step-up a R$ 42.000 | 5 anos | **28 %** |
| **T5** externo | Receita externa material | R$ 50.000/mês recorrente de fora do grupo, 3 meses consecutivos. Fonte: faturamento auditado | — | 34 % |
| **T6** externo | Independência econômica | Receita externa ≥ 50 % do custo fixo, EBITDA positivo em 2 trimestres consecutivos | — | **40 %** |

**Nota de honestidade:** a faixa de mercado para primeiro sócio técnico é 5–15 % e
aplica-se **à base** (os 12 %). O resto é conquistado contra entrega verificável.
E note: **28 dos 40 pontos dependem de receita externa.** Se ela não vier, sua
escada termina em 24 %.

## As seis regras que impedem a escada de virar decoração

1. **Suspensão por bloqueio de sócio.** Marco que depende de decisão sob controle
   do grupo, não entregue em N dias após pedido formal registrado → prazo suspende
   e o degrau não caduca. Sem isso, T1 morre esperando as 3 horas do Leonardo.
2. **Marco atingido é irreversível.** Conquistou, é seu. Indicador piorar depois
   não devolve pontos percentuais.
3. **Orçamento comercial no contrato.** T4, T5 e T6 valem 16 dos 40 pontos e
   **nenhum depende de você.** Sem verba de vendas e pessoa de comercial
   contratada, não disparam — e isso não pode ser registrado como falha sua.
4. **Verificação por terceiro.** Discordância sobre marco → auditor independente,
   custo dividido. Evita que "atingiu ou não" vire discussão de vontade.
5. **Percentual sobre capital totalmente diluído**, com direito de preferência
   exercível em aumento de capital.
6. **Janela de 5 anos.** O que não foi atingido caduca; o conquistado é permanente.
   Prazo protege os dois lados e torna o pedido negociável.

## Participação nos lucros: como o dinheiro chega até você

| Mecanismo | Quando paga | Exigível? | Depende de lucro? | Prioridade |
|---|---|---|---|---|
| **Retainer** | mensal | **sim, contratual** | não | **1ª — é a negociação** |
| **Taxa de sucesso sobre economia comprovada** | anual | **sim, contratual** | não — incide sobre a economia nas clínicas | **2ª — é o upside real** |
| Dividendos | anual | só com política de distribuição obrigatória no contrato social | **sim** | 3ª |
| Valorização patrimonial | só na saída | não | depende de receita | 4ª — prêmio grande e incerto |

### Três armadilhas

1. **PLR não se aplica a você.** A Participação nos Lucros e Resultados da Lei
   10.101/2000 é instrumento para **empregados**. Como quotista você recebe
   **dividendos**, que é outra coisa com outra tributação. Se alguém te oferecer
   "PLR", entenda o que está sendo oferecido.
2. **Dividendo sem política obrigatória é promessa.** Sem cláusula de distribuição
   mínima no contrato social, o lucro fica retido. E lembre da tributação de 2026:
   retenção de 10 % acima de R$ 50 mil/mês da mesma empresa, mais IRPF mínimo de
   até 10 % para renda global acima de R$ 600 mil/ano — e a sua renda global soma
   Mercado Livre, restaurante, retainer e dividendos.
3. **Em rateio não existe lucro para participar.** Cenário A. Se a resposta for
   "rateio", a linha de dividendos é zero e a negociação se resume às duas
   primeiras.

## O que fazer com isso na reunião

**Leve a escada e leve o modelo.** Mostrar ao Leonardo que você calculou que 40 %
vale R$ 1.400/mês no cenário interno faz duas coisas: prova que você não pede
percentual por vaidade, e move a conversa para onde ela deveria estar — **margem
contratada, orçamento comercial e política de dividendos.** Um sócio que entende
que a própria fatia vale pouco é muito mais convincente que um que acha que vale
muito.
