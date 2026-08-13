# Plano de Férias com Operação Autônoma — Clínica Wissence

**Objetivo do documento:** viabilizar 15 dias de férias de Leonardo (dono) e Adriana
(Diretora de Qualidade) em **fevereiro/2027**, provando que a clínica fatura e opera
sem eles — e só então transformar isso em produto vendável.

**Data-base:** agosto/2026 · **Janela-alvo:** fevereiro/2027 (~6 meses de preparação)

---

## 0. O problema real (leia antes de tudo)

O risco central **não é falta de monitoramento**. É **concentração de receita**:
Leonardo responde por **~60% do faturamento**. Câmera, dashboard e software não
faturam — o Leonardo fatura. A pergunta que decide se as férias são possíveis é:

> **Quando Leonardo sai 15 dias, quem produz esses 60%?**

Todo o resto do plano existe para responder a isso. Monitorar a operação é
secundário; **substituir a capacidade produtiva do Leonardo e reter os pacientes
dele é o item nº 1.**

### Regra de ouro do piloto
Fevereiro tem **um único objetivo**: *provar que a operação roda sem os donos.*
Vender consultoria, absorver outras clínicas e montar franquia são **Fases 2 e 3** —
não entram em fevereiro. Não se vende um modelo de autonomia que nunca sobreviveu a
uma única quinzena real.

---

## 1. Suposições a validar (🔴 = confirmar com Leonardo)

Estas premissas foram assumidas para não travar o plano. **Se qualquer 🔴 mudar, o
plano muda.**

| # | Suposição assumida | Impacto se falsa |
|---|---|---|
| 🔴 S1 | Médicos de referência cobrem **≥70%** da agenda/faturamento do Leonardo | Se cobrem menos, férias viram **escalonadas** (Leonardo primeiro, Adriana depois) ou vão para **baixa temporada** |
| 🔴 S2 | A clínica **já tem** sistema de gestão + prontuário eletrônico | Se não tem, "operação na palma da mão" em 6 meses é inviável do zero |
| 🔴 S3 | Existe **1 pessoa de confiança** que fica (gerente/coordenador) | Sem um responsável presente com alçada, nenhum app substitui decisão humana |
| 🔴 S4 | Fevereiro é aceitável como **baixa temporada** da clínica | Se fevereiro for pico, escolher outro mês reduz o risco de receita |

---

## 2. Princípios inegociáveis

1. **Legalidade primeiro.** Nada de câmera dentro de consultório (ver §6). Isso é
   veto do CFM, não preferência.
2. **Receita no centro.** Toda frente serve à meta de faturamento mínimo tolerável.
3. **Autonomia real = não precisar olhar.** O painel é de **exceção** (alarme só
   quando foge do padrão), não de vigilância contínua. Se Leonardo checa dashboard de
   hora em hora da praia, o piloto falhou.
4. **Sequência, não paralelo.** Validar (Fase 1) → produtizar (Fase 2) → franquear
   (Fase 3). Uma de cada vez.
5. **Gatilho de abortar definido.** Existe um número abaixo do qual as férias são
   encurtadas/interrompidas (ver §7).

---

## 3. As 4 frentes (reestruturadas)

### Frente A — RECEITA E BLINDAGEM (a que decide tudo)
- Mapear a agenda do Leonardo: quais pacientes são **fidelizados a ele** vs. quais
  aceitam outro médico.
- **Plano de cobertura:**
  - Remarcar procedimentos de alto valor/eletivos para **antes ou depois** de fevereiro.
  - Alocar médicos de referência para o que pode ser coberto — com **nome, agenda e
    combinado financeiro definidos** (não "cobririam", mas "cobrem, tais dias, tais
    pacientes").
  - Comunicar aos pacientes com antecedência (recado ativo, não passivo).
- **Blindagem contra "roubar o cliente" (aliciamento):**
  - **Cláusula de não-aliciamento / não-concorrência** no contrato dos médicos, com
    multa — é o que dissuade, não a gravação.
  - **Fidelizar o paciente à marca Wissence, não ao médico individual** —
    agendamento e pagamento sempre pela clínica.
  - Sinal de aliciamento vem do **CRM/agenda**: paciente que some ou para de remarcar
    após passar pelo Dr. X — não do áudio da consulta.
  - Distribuir a carteira entre **vários médicos** para não migrar a concentração do
    Leonardo para um único substituto.
- **Meta de faturamento mínimo tolerável** para os 15 dias + gatilho de abortar (§7).

### Frente B — QUALIDADE (legal, sem gravar a consulta)
Auditar a **prescrição registrada**, não o áudio da consulta — o dado que importa já
está no prontuário, e gravar para auditar conduta conflita com a autonomia médica
(Res. CFM 2.314/2022):
- **Auditoria de prescrição por amostragem** de prontuários + **alerta automático**
  de item fora do protocolo.
- **Checklist de atendimento** e protocolos padronizados assinados.
- **NPS/pesquisa de satisfação** do paciente pós-consulta (sinal de qualidade sem
  violar sigilo).
- **Gravação só para mentoria consentida** (médico e paciente de acordo, finalidade de
  treinamento) — nunca auditoria encoberta.
- Adriana define os **indicadores de qualidade** e **quem os acompanha na ausência
  dela** (a Diretora de Qualidade também sai — precisa de substituto nomeado).

### Frente C — OPERAÇÃO
- **Pontos focais** por área (recepção, enfermagem, faturamento, farmácia) com
  responsável nomeado.
- **Árvore de decisão** "se acontecer X → aciona Y" (intercorrência clínica,
  falta de insumo, paciente insatisfeito, problema de sistema).
- **Medicamentos:** processo de pedido e controle de estoque com responsável e
  **alçada de compra** definida (até R$ X sem aprovar; acima, aciona contato de crise).
- **Faturamento:** fechamento diário automatizado no sistema de gestão.

### Frente D — GOVERNANÇA REMOTA ("palma da mão", legal)
- Painel de **exceção**: KPIs (faturamento do dia, nº de atendimentos, cancelamentos,
  estoque crítico, reclamações) com **alarme só quando sai da faixa**.
- **Contato de crise:** 1 pessoa com autoridade que resolve; Leonardo só é acionado
  em nível "vermelho".
- Monitoramento de funcionário (computador/câmera de área comum) **somente** com a
  política legal do §6 assinada.

---

## 3.1 Monitoramento de cada frente e skills de IA

**Verdade antes da lista:** o Claude/IA é a **camada de inteligência e interface**, não
o sistema que roda a clínica. O dado mora no **sistema de gestão** (prontuário, estoque,
agenda, financeiro). O Claude lê esse dado (via API/conector/MCP), analisa, **rascunha
ações e sobe exceções** — mas **decisão clínica e de compra é humana**. Três
consequências:

- **O gargalo é a fonte de dados.** Sem sistema com API, o passo zero é integrar/trocar
  — sem isso não há o que a IA leia (Suposição S2).
- **Piloto ≠ monitorar tudo.** Em fevereiro, monitore só o que **explode em 15 dias**:
  faturamento, estoque crítico (controlados), agenda/no-show e alerta de prescrição.
  O resto é o produto (Fase 2).
- **Sempre "humano aprova".** A IA propõe o pedido, a resposta, o flag; uma pessoa
  confirma. É qualidade e é blindagem legal.

| Frente | Medir | Alerta | Skill/Agente Claude | Prioridade |
|---|---|---|---|---|
| **Estoque & Farmácia** | Nível vs. reposição, validade, entrada/saída de controlados, divergência físico × sistema | Item < mínimo · validade < 30d · divergência de controlado | **Agente de Reposição** (rascunha pedido) + **Auditor de Controlados** | Piloto |
| **Comercial** | Leads, conversão, orçamentos parados, follow-up, ticket médio, motivo de perda | Lead sem resposta > 2h · orçamento parado · queda de conversão | **Agente Comercial** — resume funil, rascunha follow-up/proposta (humano envia) | Piloto parcial |
| **Consultas** | Volume por médico, aderência ao protocolo, NPS, retorno | Prescrição fora do protocolo · NPS baixo · queda de volume | **Auditor Clínico** — amostra prontuários, sobe exceções p/ revisão humana | Piloto |
| **Agendamento** | Ocupação, no-show, cancelamento, buraco de agenda, tempo de espera | No-show acima da média · janela ociosa · fila > X min | **Agente de Agenda** — confirma/lembra, preenche buraco com lista de espera | Piloto |
| **Faturamento** | Faturamento diário vs. meta, recebíveis, glosas, mix de pagamento | Faturamento < piso (gatilho de abortar) · glosa acima de X | **Agente de Faturamento** — fecha o dia, resumo diário por exceção | Piloto (termômetro) |
| **Publicações & Reputação** | Posts, engajamento, avaliações novas, reputação | Avaliação negativa nova · calendário de posts atrasado | **Agente de Reputação** — monitora reviews, rascunha resposta (humano aprova) | Produto (reviews no piloto) |
| **Consolidação** | Estado geral da operação | Só empurra alerta nível vermelho | **Orquestrador** — responde em linguagem natural, chama só na exceção | Piloto |

**Cadeia de dependência (o que precisa existir):** sistema de gestão com API →
integração/MCP → agente Claude por frente → painel de exceção + **aprovação humana**. O
elo fraco é sempre a fonte de dados — comece por aí. Essa camada, bem-feita para a
Wissence, **é o próprio produto de consultoria** que se quer vender nas Fases 2 e 3.

---

## 4. Fases (sequenciais)

### Fase 0 — Preparação (ago/2026 → jan/2027)
Montar as 4 frentes, formalizar juridicamente, treinar equipe e substitutos.

### Fase 1 — Piloto: as férias (fevereiro/2027) 🎯
15 dias reais como **teste de estresse**. Sucesso = faturamento acima do mínimo +
zero incidente crítico não resolvido pela equipe + donos não precisaram operar.

### Fase 2 — Produtização (após fev, só se Fase 1 passar)
Transformar o que funcionou em **playbook de consultoria de IT/IA**. Documentar,
padronizar, precificar.

### Fase 3 — Escala (franquia / absorção de operações)
Modelo de adoção para franqueados e absorção de operações de outras clínicas.
**Só com Fase 1 e 2 validadas.**

---

## 5. Cronograma retroativo (de fevereiro para trás)

| Prazo | Marco |
|---|---|
| **Ago/2026** | Validar as 🔴 (S1–S4). Definir médicos de referência e combinado financeiro. Consultar advogado (CFM + LGPD + CLT). |
| **Set/2026** | Fechar plano de cobertura da agenda. Definir pontos focais e árvore de decisão. Escolher/ajustar sistema de gestão e painel. |
| **Out/2026** | Formalizar política de monitoramento (ciência assinada). Implantar painel de exceção. Treinar substitutos (inclusive da Adriana). |
| **Nov/2026** | **Ensaio 1:** Leonardo se ausenta **3 dias** e mede o que quebra. |
| **Dez/2026** | Corrigir falhas do Ensaio 1. Remarcar procedimentos de alto valor para fora de fevereiro. |
| **Jan/2027** | **Ensaio 2:** ausência de **5–7 dias** dos dois. Ajuste final. |
| **Fev/2027** | **Piloto: 15 dias.** Monitorar por exceção. |

> **Por que ensaios?** Você nunca deve descobrir o que quebra estando na praia.
> Os ensaios de novembro e janeiro revelam as falhas com você ainda por perto.

---

## 6. Checklist legal (não pule)

**Câmeras / atendimento médico — CFM:**
- ❌ **Proibido** câmera com áudio/vídeo dentro do consultório durante o ato médico —
  **inclusive com consentimento do paciente** (Parecer CFM). Viola sigilo médico.
- ✅ Permitido câmera **apenas em áreas de livre circulação** (recepção, corredores).
- ✅ Qualidade do atendimento se afere por **prontuário, prescrição, protocolo e NPS** —
  não por vídeo.

**Monitoramento de funcionários — CLT + LGPD:**
- ✅ Permitido (poder diretivo, art. 2º CLT) com **finalidade legítima**.
- ⚠️ Exige **aviso prévio inequívoco e por escrito** ao funcionário (ciência assinada).
- ⚠️ **Proporcionalidade** — nada de vigilância excessiva; nada em banheiro/copa/descanso.
- ⚠️ Descumprimento: dano moral trabalhista + multa ANPD (até 2% do faturamento,
  limitado a R$ 50 mi por infração).

**Ação obrigatória:** validar tudo com **advogado especializado em direito médico +
trabalhista/LGPD** antes de instalar qualquer equipamento.

---

## 7. Métricas de sucesso e gatilho de abortar

**Piloto é sucesso se, nos 15 dias:**
- Faturamento ≥ **[definir: X% da média mensal proporcional]** 🔴
- **Zero** incidente crítico não resolvido pela equipe
- Nenhuma decisão exigiu Leonardo (só acionamentos nível vermelho)
- Satisfação do paciente (NPS) não cai além de **[definir faixa]** 🔴

**Gatilho de abortar/encurtar:** se o faturamento acumulado cair abaixo de
**[definir piso]** 🔴 nos primeiros 5 dias, ou houver incidente crítico recorrente,
Leonardo retorna/assume remotamente. Definir isso **antes** de viajar.

---

## 8. Riscos principais

| Risco | Mitigação |
|---|---|
| Pacientes do Leonardo cancelam em vez de aceitar substituto | Comunicação ativa antecipada; remarcar alto valor para fora de fev; medir no Ensaio 1 |
| Médico de referência alicia o paciente (rouba o cliente) | Cláusula de não-aliciamento com multa; paciente fiel à marca; sinal de queda de remarcação pelo CRM |
| Concentração migra do Leonardo para o Dr. X | Distribuir carteira entre vários médicos; marca Wissence como âncora do paciente |
| Diretora de Qualidade ausente sem substituto | Nomear e treinar substituto de qualidade na Fase 0 |
| Câmera/monitoramento gera passivo jurídico | Checklist §6 + advogado antes de instalar |
| Escopo explode (produto/franquia antes de validar) | Sequência rígida das Fases; fev só valida |
| "Controle na palma" vira microgestão remota (não é férias) | Painel de exceção + contato de crise; Leonardo só em nível vermelho |

---

## 9. Próximos passos imediatos (agosto)

1. **Validar as 🔴 S1–S4** com Leonardo (principalmente % de cobertura dos médicos de
   referência).
2. **Reunião com advogado** (direito médico + trabalhista/LGPD).
3. **Levantar o sistema de gestão atual** e o que falta para o painel de exceção.
4. **Nomear** contato de crise, pontos focais e substituto de qualidade.
5. **Agendar Ensaio 1** (3 dias) para novembro.

---

*Documento vivo. As marcações 🔴 são premissas que precisam ser confirmadas antes de
executar. A Fase 2 (produto/consultoria) e a Fase 3 (franquia) só ganham detalhamento
depois que a Fase 1 for validada em fevereiro.*
