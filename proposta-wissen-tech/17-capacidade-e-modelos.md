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

> **CORREÇÃO — rev. 24.** Este bloco foi escrito sob a premissa de que o
> desenvolvedor ainda não existia. **Ele existe: o Felipe é da Wissen Tech.** A
> conta de horas abaixo continua válida como dimensionamento de esforço, mas a
> alocação real é outra e está em `20-validacao-propostas.md`, seção 11 — as 168 h
> já estão comprometidas com quatro frentes, e sobram cerca de 38 h/mês para
> cliente externo. **A restrição da empresa não é orçamento; é prioridade.**

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
| Teórico, se o desenvolvedor estivesse livre | 128 h/mês |
| **Real, com as quatro frentes ativas** | **~78 h/mês — 40 h de CTO + 38 h do desenvolvedor** |

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

## 9. Acesso ao dado e ferramenta de IA — a sua sugestão, corrigida em dois pontos

Você propôs duas pré-condições novas: adquirir uma ferramenta de IA (Claude, Codex
ou equivalente) para construir os plugins e integrações, e exigir que o sistema da
clínica forneça os dados de alguma forma. **A segunda é mais importante do que
você apresentou. A primeira não é pré-condição.**

### 9.1 Acesso ao dado é critério de qualificação, não pré-condição interna

A camada de resultado (L5) **não existe sem leitura dos dados do sistema que a
clínica já usa.** Não é detalhe técnico, é o go/no-go do cliente. E não é sim ou
não — é uma escada, e cada degrau tem consequência de preço:

| Nível de acesso | Custo de integração | Consequência |
|---|---|---|
| API documentada do fornecedor | 4–8 h | preço de tabela |
| Exportação agendada configurada pelo cliente | 6–12 h | preço de tabela |
| Acesso direto ao banco, autorizado por escrito | 8–16 h | preço de tabela + contrato de operador |
| Exportação manual feita por pessoa | **2–4 h/mês permanentes** | sobretaxa ou recusa |
| Só a tela do sistema | quebra a cada atualização | **recusa** |

**O risco que você não citou, e é o seu:** se orçar uma L5 fechada em R$ 4.900 e o
fornecedor da clínica levar três meses para responder um e-mail sobre API, quem
come o prejuízo é você. Duas defesas, ambas incorporadas ao catálogo:

1. **A verificação de acesso acontece dentro da L2**, que já está paga. Nenhuma L5
   é orçada antes. A L2 vira portão além de diagnóstico — ganho, não custo.
2. **Quem pede a documentação ao fornecedor é o cliente**, por escrito e com prazo.
   Fornecedor de software não responde a terceiro; responde a quem paga a
   mensalidade.

**E um item de conformidade:** com acesso direto ao banco, a Wissen Tech passa a
tratar dado pessoal sensível em nome da clínica — posição de **operador** sob a
LGPD, com a clínica permanecendo controladora. Exige contrato específico, controle
de acesso por perfil e registro de tratamento. *Confirmar a redação com advogado
antes do primeiro contrato — não tenho certeza da forma exigida, só do
enquadramento.*

**Ativo comercial barato:** levantar uma vez o nível de acesso dos cinco sistemas
mais comuns na região. Feito, qualifica qualquer prospect em cinco minutos de
reunião em vez de duas semanas de investigação.

### 9.2 A ferramenta de IA não é pré-condição — e o motivo é de negociação

Claude Code ou Codex custam de US$ 20 a 200 por assento/mês. Somando ambiente e
nuvem, algo entre **R$ 600 e R$ 2.000/mês**.

**Colocar um item de mil reais numa lista ao lado de "licença de propriedade
intelectual" e "autorização para atender fora do grupo" dilui os dois bloqueantes
de verdade.** Uma lista de oito pré-condições onde uma custa mil reais lê como
lista de desejos, e a leitura contamina as outras sete. Vai para orçamento de
infraestrutura.

**O enquadramento que funciona a seu favor:** ferramenta de IA não é custo, é **o
que sustenta o número de 128 h**. Toda a conta de capacidade assume produtividade
por hora. É o que faz 168 h de um desenvolvedor renderem como 250 h — e é a razão
pela qual duas pessoas sustentam um catálogo deste tamanho. Isso é argumento seu na
conversa com o Leonardo, não pedido.

### 9.3 O ponto cego, e este é grave

Você vai usar a IA para construir integrações com o sistema da clínica. Vai colar
estrutura de tabela, e em algum momento vai colar dado real de exemplo.

**Verificado:** nos planos de consumidor da Anthropic (Free, Pro e Max), desde
agosto de 2025 o treinamento com as conversas vem **ligado por padrão**, com
retenção de até **cinco anos** para quem mantém ligado. Dá para desligar nas
configurações de privacidade, e há ressalva para conversas sinalizadas em revisão
de segurança. Planos comerciais e de API têm tratamento diferente — confirme os
termos vigentes do plano que for assinar, porque isso muda.

Dado de paciente é **dado pessoal sensível** (LGPD art. 11). Colar isso num plano
de consumidor com treinamento ligado é exportar dado sensível de terceiro.

**E o agravante é o que mata:** você vai estar vendendo a L1 — conformidade de IA
sob a Resolução CFM 2.454/2026 — enquanto viola exatamente o que a L1 vende. Um
cliente que descobre isso não cancela um contrato; cancela a empresa.

**Regra escrita antes do primeiro cliente externo, e ela é bloqueante:**

> Assinatura comercial ou de API, nunca plano de consumidor. A ferramenta toca
> estrutura de tabela, dado sintético e dado anonimizado. **Base de produção de
> cliente não entra em prompt, em nenhuma hipótese.**

Escrita, essa regra deixa de ser restrição e vira argumento de venda da L1: você
mostra a sua política antes de vender a dele.

---

## 10. Como o produto é entregue sem o cliente comprar licença de nada

Pergunta legítima e que eu tinha passado por cima: se os plugins e skills foram
construídos com Claude ou Codex, como entregar a uma clínica que não tem licença?

**A pergunta tem uma confusão embutida, e desfazê-la resolve quase tudo.** Há dois
usos de IA aqui:

| Uso | O que é entregue | Licença do cliente |
|---|---|---|
| **IA como ferramenta de construção** — o modelo escreve o código | software que roda sozinho | **nenhuma** |
| **IA como parte do produto em execução** — o modelo é chamado toda vez que roda | serviço | depende de onde roda |

**A maior parte das 29 rotinas não precisa de modelo em execução.** Alerta de
estoque abaixo do mínimo, régua de retorno de orçamento, conferência de divergência
de caixa — isso é lógica determinística. Foi construído com IA; não precisa de IA
para rodar. **Regra de arquitetura: toda rotina que puder ser determinística é
convertida para código convencional antes de ir a cliente.**

O que genuinamente exige modelo em execução é pouco: texto livre (anotação clínica,
mensagem de paciente), classificação, e o atendimento do MODELO 3.

### Para esses, três caminhos e só um presta

| Caminho | Quem paga a IA | Licença do cliente | Veredito |
|---|---|---|---|
| Cliente assina e roda os skills no ambiente dele | cliente | sim | **recusar** |
| **Roda no ambiente da Wissen Tech, com chave de API própria** | **nós, por consumo** | **nenhuma** | **este** |
| Cliente com TI interno usa a própria assinatura | cliente | sim | só no MODELO 1 |

**A API é cobrada por token, não por assento.** Não existe licença a comprar do lado
de quem executa — existe consumo, e o consumo é nosso, embutido na mensalidade. O
cliente compra resultado, não ferramenta.

### Por que "o cliente compra a licença" é ruim, e o motivo principal não é custo

**Skill é markdown.** Entregar os arquivos no ambiente do cliente é entregar o
produto inteiro na primeira mensalidade. Ele copia e cancela; não há o que renovar.
**Isso sozinho já derruba a opção.**

Somam-se: barreira de compra imposta a quem menos pode comprar; perda de controle de
versão, modelo e plano, o que torna o suporte impossível de diagnosticar; e
dependência de um terceiro que muda preço e estrutura de plano sem avisar — quebrando
um produto que leva o nosso nome.

**Exceção única:** cliente de MODELO 1 com equipe de TI própria, aprendendo a operar
as próprias ferramentas. Isso é consultoria, entra no plano de trabalho, nunca na
fatura de produto.

### O custo de token, e é uma boa notícia

Ordem de grandeza com premissas explícitas — **não é medição, é teste de sanidade;
o piloto tem que medir de verdade.** Um relatório mensal de resultado de uma clínica,
algo como 200 mil tokens de entrada e 20 mil de saída:

| Modelo | Custo por conta/mês |
|---|---|
| Haiku 4.5 (US$ 1 / US$ 5 por milhão) | ≈ US$ 0,30 |
| Opus 5 (US$ 5 / US$ 25 por milhão) | ≈ US$ 1,50 |

Contra uma mensalidade de R$ 490. **O token não é a restrição — a hora de suporte
é.** Automação é barata, gente é cara: é a justificativa econômica do MODELO 3, e
agora com número em vez de intuição.

---

## 11. O sistema de relatórios — a proposta, e o que corrigir nela

Você propôs três coisas numa frase: montar um sistema pequeno de relatórios que
converta os skills em software, dar acesso via web na nossa infraestrutura, e cobrar
por requisição. **Duas estão certas. A terceira eu recomendo abandonar.**

### 11.1 Converter em software na própria infraestrutura — sim, e é o MODELO 2

Isso não é projeto paralelo nem ferramenta de apoio. **É o produto.** Merece linha
própria no plano de capacidade e marco próprio na escada de participação — e é
provavelmente o marco mais forte que você tem para justificar os degraus acima da
base, porque é o que faz a Wissen Tech valer alguma coisa como empresa.

**"Sistema pequeno" é o adjetivo errado.** Um serviço web que segura dado de clínica
exige isolamento entre clientes, log de auditoria, criptografia em repouso e em
trânsito, backup com recuperação testada, monitoramento — e **guarda das credenciais
de acesso aos sistemas dos clientes.** Você vai armazenar token e senha de acesso ao
sistema de outra empresa. Isso te torna alvo, e é a parte que ninguém lembra de
orçar.

| Bloco da v1 | h |
|---|---:|
| Integração e leitura dos dados | 40 |
| Motor de cálculo dos indicadores | 60 |
| Camada web: autenticação, painel, relatório | 80 |
| Base de segurança: criptografia, auditoria, backup | 40 |
| Teste com dado real de uma clínica e correção | 40 |
| **Total** | **≈ 260** |

Contra as 80 h/mês de produtização do desenvolvedor: **3 a 4 meses.**

**A implicação que você ainda não precificou:** o MODELO 2 não abre no mês em que o
desenvolvedor chega. Abre um trimestre depois. A Fase 1 tem gestação, e ela precisa
estar no cronograma **antes** de você prometer qualquer coisa a um cliente.

### 11.2 Cobrar por requisição — recomendo abandonar

**Você mediria a coisa barata e deixaria a cara sem preço.** Token custa US$ 0,30 a
1,50 por conta/mês. A restrição é hora de suporte. Preço por requisição precifica o
insumo de centavos e não toca no custo que limita a operação.

**E taxa exatamente o comportamento que precisa acontecer.** A tese inteira é medir e
reportar o ganho. Clínica que pensa duas vezes antes de puxar um relatório porque
cada consulta custa é clínica que nunca vê o valor e cancela no terceiro mês.

| Problema | Consequência |
|---|---|
| Receita imprevisível | quebra o gatilho "contrata o dev no 2º contrato" — não dá para contratar em cima de faturamento que você não sabe qual é |
| Dono de clínica não orça por requisição | orça mensalidade; preço variável obriga a pensar em custo toda vez que usa |
| Ancora o valor no mecanismo | preço por chamada = custo de computação + margem = centavos; preço por resultado = R$ 890 a 1.490 |

**É trocar R$ 1.400 por R$ 50.**

**Estrutura correta:** mensalidade fixa por unidade, faixas por porte, uso justo
generoso. Se houver componente variável, que acompanhe **unidade atendida ou volume
de atendimentos da clínica** — proxy do valor recebido —, nunca chamada de sistema.

*Onde cobrança por uso funciona de verdade:* como teto interno de uso justo para
evitar abuso, e num produto de API vendido a outros desenvolvedores. Nenhum dos dois
é o seu mercado.

### 11.4 A direção da integração, e por que a v1 não tem painel

Duas correções que surgiram de uma leitura errada da estimativa de 260 h — a
conclusão delas melhora o produto.

**Primeiro, a estimativa nunca disse que o sistema web é inviável.** Ela disse que
"pequeno" é o adjetivo errado e que o MODELO 2 abre um trimestre depois da
contratação. É prazo e sequência, não viabilidade. O serviço hospedado por nós
continua sendo a recomendação.

**Segundo, "o cliente integra com a nossa IA via token" é pior, não melhor:**

| Problema | Por quê |
|---|---|
| Consultório não tem quem integre | vender API para quem compra software; o MODELO 2 existe para exigir zero trabalho técnico do cliente |
| Inverte quem faz o trabalho | o fornecedor de software do cliente teria que construir contra a nossa API, e não tem motivo nenhum para isso |
| Expõe a IA como se fosse o produto | acesso a modelo é commodity que o cliente compra mais barato na fonte; **o produto é a lógica** — quais indicadores, quais limites, como interpretar |
| Reintroduz cobrança por uso | pela porta dos fundos, depois de já descartada |

**Regra de direção, escrita no catálogo: nós puxamos, o cliente não empurra nada.**
O cliente faz duas coisas na vida: autoriza o acesso uma vez, e recebe.

**Onde a API cabe de verdade:** somente-leitura dos números já calculados, como
acessório da L3 e da L4, para cliente com TI interno que quer o indicador dentro do
painel dele. Quase de graça, porque o número já existe. Nunca como produto da L2.

### 11.5 O corte que reduz a v1 de 260 h para 190 h

O instinto de que o sistema web era pesado demais para clínica pequena estava certo.
A saída não é token — é **tirar a camada web da v1.**

**Painel de gestão em negócio pequeno não é usado.** O dono não lembra de entrar. O
valor está no alerta que chega, não na página que ele precisa visitar. Para um
consultório de um médico, relatório mensal em PDF por e-mail e alerta quando um
limite estoura é **produto melhor** que painel — não é só mais barato de construir.

| Bloco | Só relatório e alerta | Com painel web |
|---|---:|---:|
| Integração e leitura | 40 h | 40 h |
| Motor de cálculo | 60 h | 60 h |
| Entrega ao cliente | 30 h (PDF, e-mail, alerta) | 80 h (painel, login, usuários) |
| Base de segurança | 30 h (sem login público) | 40 h |
| Teste com dado real | 30 h | 40 h |
| **Total** | **≈ 190 h · 2,5 meses** | **≈ 260 h · 3,5 meses** |

**O painel vira incremento posterior de 80 a 100 h, construído quando um cliente
pedir.** E há um ganho colateral que vale mais que as 70 h: sem login público, a
superfície de ataque cai a quase nada — o que compõe com a decisão de não armazenar
dado de paciente.

### 11.3 A decisão de arquitetura mais importante, e é grátis agora

**Na v1, não armazenar dado de paciente.** Ler, calcular o indicador, guardar o
agregado, descartar o detalhe. Não é preciso o nome de ninguém para dizer que a
conversão de orçamento caiu 12 %.

| | Armazenando prontuário | Só agregado |
|---|---|---|
| O que um incidente expõe | dado sensível de paciente | números |
| Classificação de risco (CFM 2.454) | alta | baixa |
| O que provar em auditoria | cadeia inteira de tratamento | muito menos |
| Custo de conformidade | permanente | marginal |

**É aqui que você precisa sentir medo, porque é o seu nome, não o da empresa:**
vazamento de dado de paciente numa clínica não é um bug, é o fim da empresa — e você
é sócio, não fornecedor. Decidir isso hoje custa zero. Decidir depois de oito
clientes custa uma migração.

**Associado:** nos três primeiros clientes, **uma instância isolada por cliente.**
Multi-tenant é a produtização mais cara e a mais fácil de errar sem dados reais de
clínica de fora. Vem depois dos três, não antes — e casa com o teto de oito contas.

---

## 12. A única coisa a fazer primeiro

**Escolher, antes de qualquer proposta comercial, o que o MODELO 2 vende:** o
sistema de clínica, ou a camada de resultado sobre o sistema que a clínica já tem.

Todo o resto — preço, teto de contas, o que a IA automatiza, quanto vale a
produtização no acordo societário — depende dessa escolha. E a evidência aponta
para a segunda com folga.
