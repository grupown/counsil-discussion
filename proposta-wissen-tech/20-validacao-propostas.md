# 20 · Validação do catálogo contra duas propostas reais

> **rev. 23.** Duas peças reais entraram na mesa: a proposta à **Clínica Dr. M.
> Batista** (27/08/2026) e o **plano comercial do CRM** discutido na reunião com o
> Felipe (26/08/2026). O catálogo foi conferido contra as duas.
>
> **Veredito: reprovou em quatro pontos, um deles urgente.**

---

## 1. O achado urgente — e ele tem data

O catálogo rev. 3 dizia, como política:

> Fase 0, hoje: **1 cliente piloto de Modelo 1. Modelo 2 fechado.**

O plano do CRM prevê **Leonardo apresentando e vendendo licenças em 5 de setembro**,
com go-live em 21 de setembro, e a reunião trabalhou com a hipótese de **cinco
licenças**.

**São a mesma empresa, na mesma semana, com duas políticas incompatíveis.** Uma das
duas está errada, e não é uma questão de redação:

| Se o certo for o catálogo | Se o certo for o CRM |
|---|---|
| A venda de 5 de setembro viola a política de capacidade que se pediu à diretoria para aprovar. | A capacidade declarada no memorando à diretoria está errada, e o memorando precisa ser corrigido **antes** de ser enviado. |

**Isto precisa ser resolvido antes do dia 5, e a decisão não é minha.** O catálogo
rev. 4 já não fala em "Fase 0 com um piloto" como regra universal — passou a falar em
**teto e fila por linha**, que é a formulação que acomoda as duas realidades sem
mentir para nenhuma delas. Mas a incoerência com o memorando permanece e é sua para
resolver.

---

## 2. O que a proposta Batista revelou — preço inventado

O catálogo tinha números que **eu construí por analogia**, e a proposta real mostra
que estavam altos demais.

| | Catálogo rev. 3 | Proposta real | Diferença |
|---|---|---|---|
| Diagnóstico multi-local | R$ 24.800 / 48 h = **R$ 517/h** | R$ 19.600 / 56 h = **R$ 350/h** | catálogo 48 % mais caro |
| Diagnóstico 1 local | R$ 16.800 / 32 h = **R$ 525/h** | — | sem referência real |
| Acompanhamento | R$ 5.900 a 11.800 · R$ 369/h fixo | R$ 7.600 / 11.200 / 15.600 · **R$ 380 → 350 → 325/h** | catálogo perdeu o desconto por volume |

**Corrigido na rev. 4 para os valores praticados.** A estrutura real é melhor do que
a que eu tinha desenhado: três planos com desconto por volume dão ao cliente uma
escolha e ancoram o plano do meio, que é o que se quer vender.

**E a proposta real vai a 48 h/mês; o catálogo parava em 32 h.** Havia um plano de
maior ticket que o catálogo simplesmente não oferecia.

## 3. Três linhas que existiam na prática e não existiam no catálogo

| Linha ausente | Onde estava | Por que importa |
|---|---|---|
| **Assessoria continuada** — 8 h/mês, R$ 3.600, R$ 450/h, vigência de 12 meses | Fase 2 da proposta Batista | É a linha de retenção. Sem ela, todo cliente que termina a Fase 1 vira zero. |
| **CRM Aurora** — três planos de R$ 890 a R$ 2.690 mais implantação | Plano comercial do CRM | É a linha de maior ticket recorrente da empresa, e a única que vende sistema próprio. |
| **Serviços avulsos** — hora técnica, fluxo de robô, treinamento, número adicional, recuperação de banimento | Tabela do CRM | Sem tabela de avulso, toda demanda pequena vira favor — e favor pequeno repetido consome capacidade sem aparecer. |

Todas as três entraram na rev. 4 como L7, L8 e L9.

## 4. O erro de arquitetura que a validação expôs

O catálogo rev. 3 afirmava, como tese central do MODELO 2:

> *"Não vendemos sistema de clínica. Vendemos a camada que faz o sistema render."*

**O CRM Aurora é exatamente um sistema, e está a seis dias de ser vendido.**

A tese não estava errada — estava **incompleta**. As duas coisas convivem porque
atacam camadas diferentes:

| | L5 e L6 · camada de resultado | L8 · CRM Aurora |
|---|---|---|
| Relação com o sistema do cliente | lê o que existe, não substitui | é o sistema, no que toca relacionamento |
| Concorre com | ninguém diretamente | ferramenta de multiatendimento WhatsApp |
| Depende de acesso ao dado do cliente | **sim, é condição** | não |
| Existe hoje | não — 190 h de distância | **sim, com go-live marcado** |

A rev. 4 declara isso abertamente: a L8 é **a única linha em que a Wissen Tech
entrega o próprio sistema.** Não é contradição, é escopo diferente — mas precisava
estar escrito, porque um vendedor lendo a rev. 3 concluiria que não pode vender o CRM.

## 5. O erro de preço que teria dado prejuízo

O catálogo oferecia a **L6 a R$ 490/mês**. A reunião do CRM mediu o custo real de
entrega: **R$ 660/mês nos seis primeiros meses**, e concluiu que *"mensalidade abaixo
de R$ 700 dá prejuízo no primeiro semestre de qualquer cliente"*.

Se alguém vendesse a L6 acreditando estar entregando o CRM, **estaria vendendo
R$ 170 abaixo do custo, todo mês, por seis meses.**

**Corrigido:** a rev. 4 diz explicitamente o que a L6 **não** tem — sem WhatsApp
oficial, sem robô, sem gestão de conta na Meta — e que qualquer uma das três muda a
linha para L8 e o patamar de preço.

## 6. O teto da L3 estava errado, e é aritmética

O catálogo dizia teto de 3 clientes simultâneos. Com o plano Condução de 32 h/mês, e
considerando que cerca de 60 % dessas horas são de CTO — reunião, plano, especificação
e revisão, que não se delegam:

| Plano | h/mês | h de CTO | Cabem em 40 h |
|---|---:|---:|---:|
| Essencial | 20 | 12 | 3,3 |
| **Condução** | **32** | **19** | **2,1** |
| Intensivo | 48 | 29 | 1,4 |

**Teto corrigido para 2.** E a Fase 0, com 56 h para multi-local, consome mais de um
mês inteiro da capacidade externa do CTO — **uma Fase 0 por vez**, o que o catálogo
não dizia.

## 7. Quatro cláusulas que a proposta real tinha e o catálogo não

Estas são as melhores da proposta Batista, e nenhuma estava no catálogo:

1. **Declaração de interesse no Aurora.** A proposta declara, por escrito, que a
   Wissen Tech tem interesse comercial no próprio sistema que poderia recomendar — e
   se compromete a apresentar duas alternativas de mercado avaliadas nos mesmos
   critérios. **Declarar o conflito é o que torna o parecer confiável.**
2. **Cláusula de não uso da informação.** O grupo também opera clínicas. Sem essa
   cláusula, ser do mesmo setor que o cliente é motivo para não fechar.
3. **D-0 com checklist de partida e suspensão dia a dia.** O prazo não conta da
   assinatura, conta de quando o cliente cumpriu a parte dele.
4. **Regras do banco de horas** — acúmulo de até 25 %, não reembolsável, hora extra
   autorizada por escrito a R$ 450, e a carga real do responsável do cliente
   apontada no relatório mensal, sem absorção silenciosa.

Todas entraram na rev. 4 como seção própria.

---

## 8. Duas coisas que eu não sei, e que mudam o plano

**Primeira: o Felipe é da Wissen Tech?**

O modelo de capacidade do memorando à diretoria diz *"1 desenvolvedor de 168 h que
ainda não existe e não tem orçamento aprovado"*. Mas a reunião de 26/08 mostra o
Felipe construindo o multi-tenant, fazendo todos os deploys e sendo o único que sobe
release.

Ou o desenvolvedor existe e **o memorando está errado**, ou ele não é da Wissen Tech
e **o plano do CRM não tem quem entregue**. A ata registra que ele está dividido entre
CRM, Aurora e ValorMed, com nenhum despriorizado — o que aponta para o segundo caso.
**Preciso da sua resposta antes que o memorando seja enviado.**

**Segunda: as faixas de mercado do CRM.**

A própria ata registra que não foi possível conferir preço de concorrente, e que *"se
as faixas ainda valerem, o plano Clínica está 3× acima do mercado de software"*. O
catálogo herdou os preços sem essa validação. **Estão marcados como a confirmar na
objeção da L8**, e não devem ser usados como argumento de venda antes de conferidos
contra iClinic, Ninsaúde, Feegow, Kommo, RD Station e Huggy.

## 11. Resposta confirmada: o Felipe é da Wissen Tech

Isso resolve a dúvida da seção 8, e a resposta **piora o plano em vez de melhorá-lo.**

### O que estava errado

O memorando à diretoria pedia, na decisão D5, **"orçamento condicional do primeiro
desenvolvedor"**, e a tabela de capacidade dizia *"Fase 0: só o CTO · Fase 1: mais um
desenvolvedor"*. **Isso é falso, e teria ido para a diretoria assim.** Pedir orçamento
para contratar quem já está na folha é o tipo de erro que custa a credibilidade do
documento inteiro, não só do item.

### Por que a boa notícia é a má notícia

O problema não desapareceu — **mudou de natureza, e para pior:**

| | Antes, com o dev inexistente | Agora, com o dev real |
|---|---|---|
| Natureza da restrição | orçamento | **prioridade** |
| Como se resolve | com dinheiro | **matando ou adiando alguma coisa** |
| Quando aparece | no futuro | **agora** |
| Quem decide | a diretoria, aprovando um valor | a diretoria, escolhendo entre quatro frentes |

Restrição de orçamento é confortável: pede-se, aprova-se ou não, e a vida segue.
**Restrição de prioridade obriga alguém a dizer que uma coisa vai esperar** — e a ata
de 26/08 registra explicitamente que *"nenhum foi despriorizado."*

### A alocação real das 168 horas

Reconstruída a partir do que a própria ata descreve:

| Onde as horas já estão | h/mês |
|---|---:|
| Limpeza manual de conversas — "mais de uma hora por dia", à mão | 22 |
| Operação e manutenção do CRM nas três unidades | 18 |
| Publicação e infraestrutura — sem automação, único habilitado | 15 |
| Construção do multi-tenant e das telas de gestão | 25 |
| Aurora — feira de setembro | 30 |
| ValorMed — integração pendente, declarada postergada | 20 |
| **Sobra para implantar cliente externo** | **38** |

**Trinta e oito horas contra 36 h por implantação de CRM: pouco mais de uma por mês.**
Confere com a conta que a própria equipe fez por outro caminho — duas em paralelo por
janela de 45 dias. Duas rotas independentes, mesmo resultado.

**E isso confirma a incoerência da seção 1 pela aritmética, não pela política:** se o
Leonardo vender cinco licenças em 5 de setembro, os dois primeiros clientes começam em
21/09, o terceiro e o quarto em 05/11, e o quinto em 20/12.

### O item de melhor retorno que existe hoje

**As 22 horas por mês de limpeza manual de conversas são 13 % da capacidade do único
desenvolvedor da empresa.** Automatizar isso devolve mais de meia implantação de CRM
por mês, todos os meses, para sempre.

Não há nada no roadmap com esse retorno. E é exatamente a tese do MODELO 3 aplicada
para dentro antes de ser vendida para fora — o que também a torna um caso demonstrável
na venda.

### O que a D5 virou

De *"aprove orçamento para o primeiro desenvolvedor"* para:

> **Definir a ordem de prioridade entre CRM, Aurora e ValorMed para o próximo
> trimestre; e aprovar a faixa orçamentária de uma segunda pessoa técnica, liberada
> pelo segundo contrato externo assinado.**

Com recomendação anexa, como a própria ata mandou: concentrar o trimestre no CRM,
adiar formalmente a ValorMed, manter o Aurora só no que a feira exigir. **Levar
recomendação, não pergunta aberta.**

### E o bus factor deixou de ser tolerável

A ata descreve uma pessoa que constrói, publica, é a única habilitada a publicar, não
tem automação de publicação, e evita horário comercial para não derrubar a operação.

**Enquanto o cliente era o próprio grupo, isso era um risco interno tolerável.** No dia
em que houver cliente externo pagando, deixa de ser — e o risco passa a ser do grupo,
não da Wissen Tech. **Automação de publicação sai de melhoria e vira pré-condição
antes do primeiro cliente externo.**

### O que foi corrigido

| Documento | Correção |
|---|---|
| Memorando à diretoria | D5 reescrita; D4 abandona o gating por fase e fixa teto e fila por linha; sequência e continuidade atualizadas |
| Catálogo | acaba o gating Fase 0/Fase 1; L5 e L6 passam a "Não lançadas" com o motivo declarado e entram nas recusas; alocação real do desenvolvedor no bloco de capacidade |
| Memorando 17 | bloco de capacidade marcado com a correção e o cenário real de ~78 h/mês |

---

## 12. O que o catálogo cobriu bem

Para ser justo com ele, três coisas passaram no teste:

- **A recusa de banco de horas** era condicional, não absoluta — "para cliente sem
  responsável nomeado". A proposta Batista vende banco de horas **com** responsável
  nomeado (Douglas, 30 h/semana). A regra estava certa.
- **Os três papéis** — quem define, quem executa, quem patrocina — já estavam na
  definição do MODELO 1 e apareceram idênticos na proposta real.
- **A exigência de linha de base assinada antes** estava nos dois documentos.

## 13. A única coisa a fazer primeiro

**Resolver a incoerência entre a política de capacidade e a venda de 5 de setembro,
antes do dia 5.** Não é escolher qual documento reescrever: é decidir quantas
licenças a fila realmente comporta, com data por cliente, e comunicar isso ao
Leonardo antes da apresentação.

A ata já dá a recomendação, e ela é boa: **teto de 2, no máximo 3, para a primeira
safra.** Vender sem teto é vender atraso.
