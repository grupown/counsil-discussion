---

name: llm-council


description: "Passe qualquer pergunta, ideia ou decisão por um conselho de 5 conselheiros de IA que analisam de forma independente, revisam uns aos outros anonimamente, e sintetizam um veredito final. Baseado na metodologia LLM Council do Karpathy. GATILHOS OBRIGATÓRIOS: 'convoca o conselho', 'passa pelo conselho', 'conselho isso', 'sala de guerra', 'testa isso', 'pressiona isso', 'debate isso', 'council this', 'run the council', 'war room this', 'pressure-test this', 'stress-test this', 'debate this'. GATILHOS FORTES (usar quando combinados com uma decisão real ou tradeoff): 'devo fazer X ou Y?', 'qual opção?', 'o que você faria?', 'é a decisão certa?', 'valida isso', 'me dá múltiplas perspectivas', 'não consigo decidir', 'estou em dúvida entre X e Y', 'should I X or Y', 'which option', 'what would you do', 'is this the right move', 'validate this', 'get multiple perspectives'. NÃO disparar em perguntas simples de sim/não, buscas factuais, ou 'devo...?' casuais sem tradeoff real (ex. 'devo usar markdown?' não é pergunta pro conselho). DISPARAR quando o usuário apresenta uma decisão genuína com stakes, múltiplas opções, e contexto que sugere que ele quer testar de vários ângulos."

---


# LLM Council (Conselho de Conselheiros)


Você faz uma pergunta para uma IA, recebe uma resposta. Essa resposta pode ser ótima. Pode ser mediana. Você não tem como saber porque só viu uma perspectiva.


O conselho resolve isso. Ele passa sua pergunta por 5 conselheiros independentes, cada um pensando de um ângulo fundamentalmente diferente. Depois eles revisam o trabalho uns dos outros. Depois um presidente sintetiza tudo em uma recomendação final que te diz onde os conselheiros concordam, onde discordam, e o que você deveria realmente fazer.


Isso é adaptado do LLM Council do Andrej Karpathy. Ele despacha queries pra múltiplos modelos, faz eles se revisarem anonimamente, e depois um presidente produz a resposta final. Fazemos a mesma coisa dentro do Claude usando sub-agentes com lentes de pensamento diferentes em vez de modelos diferentes.


---


## quando convocar o conselho


O conselho é pra perguntas onde errar sai caro.


Boas perguntas pro conselho:

- "Devo lançar um workshop de R$497 ou um curso de R$1997?"

- "Qual desses 3 ângulos de posicionamento é o mais forte?"

- "Estou pensando em pivotar de X pra Y. Estou louco?"

- "Aqui está a copy da minha landing. O que está fraco?"

- "Devo contratar uma VA ou construir uma automação primeiro?"


Más perguntas pro conselho:

- "Qual a capital da França?" (uma resposta certa, não precisa de perspectivas)

- "Escreve um tweet pra mim" (tarefa de criação, não de decisão)

- "Resume esse artigo" (tarefa de processamento, não de julgamento)


O conselho brilha quando há incerteza genuína e o custo de uma má decisão é alto. Se você já sabe a resposta e só quer validação, o conselho provavelmente vai te dizer coisas que você não quer escutar. É exatamente pra isso que serve.


---


## os cinco conselheiros


Cada conselheiro pensa de um ângulo diferente. Não são cargos ou personas. São estilos de pensamento que naturalmente criam tensão entre si.


### 1. O Contrarian (Contrarian)

Procura ativamente o que está errado, o que está faltando, o que vai falhar. Assume que a ideia tem um defeito fatal e tenta encontrá-lo. Se tudo parece sólido, cava mais fundo. O Contrarian não é pessimista. É o amigo que te salva de um mau negócio fazendo as perguntas que você está evitando.


### 2. O First Principles Thinker (Pensador de Primeiros Princípios)

Ignora a pergunta superficial e pergunta "o que estamos realmente tentando resolver aqui?". Remove as suposições. Reconstrói o problema do zero. Às vezes o output mais valioso do conselho é o First Principles Thinker dizendo "você está fazendo a pergunta errada".


### 3. O Expansionist (Expansionista)

Procura o upside que todo mundo está perdendo. O que poderia ser maior? Que oportunidade adjacente está escondida? O que está sendo subvalorizado? O Expansionist não se importa com risco (esse é o trabalho do Contrarian). Ele se importa com o que acontece se isso funcionar até melhor do que o esperado.


### 4. O Outsider (O de Fora)

Tem zero contexto sobre você, sua área, ou sua história. Responde puramente ao que está na frente dele. Esse é o conselheiro mais subestimado. Especialistas desenvolvem pontos cegos. O Outsider pega a maldição do conhecimento: coisas que são óbvias pra você mas confusas pra todo mundo.


### 5. O Executor (Executor)

Só se importa com uma coisa: isso pode ser feito de verdade, e qual é o caminho mais rápido pra fazer? Ignora teoria, estratégia, e pensamento de larga escala. O Executor olha pra cada ideia pela lente de "OK mas o que você faz segunda de manhã?". Se uma ideia soa brilhante mas não tem um primeiro passo claro, o Executor vai falar.


**Por que esses cinco:** Eles criam três tensões naturais. Contrarian vs Expansionist (downside vs upside). First Principles vs Executor (repensar tudo vs simplesmente fazer). O Outsider fica no meio mantendo todos honestos vendo o que olhos frescos veem.


---


## como funciona uma sessão do conselho


### passo 1: enquadrar a pergunta (com enriquecimento de contexto)


Quando o usuário diz "convoca o conselho" (ou qualquer frase gatilho), faça duas coisas antes de enquadrar:


**A. Escaneie o workspace em busca de contexto.** A pergunta do usuário muitas vezes é só a ponta do iceberg. O setup de Claude dele provavelmente tem arquivos que melhorariam dramaticamente o output do conselho. Antes de enquadrar, escaneie rápido e leia qualquer arquivo de contexto relevante:


- `CLAUDE.md` ou `claude.md` na raiz do projeto ou workspace (contexto do negócio, preferências, restrições)

- Qualquer pasta `memory/` (perfis de audiência, docs de voz, detalhes do negócio, decisões passadas)

- Qualquer arquivo que o usuário mencionou ou anexou explicitamente

- Transcrições recentes do conselho nessa pasta (pra não refazer o mesmo terreno)

- Qualquer outro arquivo de contexto que pareça relevante pra pergunta específica (ex. se ele pergunta sobre preço, procure dados de receita, resultados de lançamentos passados, research de audiência)


Use `Glob` e `Read` rápidos pra achar esses. Não gaste mais que 30 segundos nisso. Você está procurando os 2-3 arquivos que dariam aos conselheiros o contexto que eles precisam pra dar conselhos específicos e aterrados em vez de takes genéricos.


**B. Enquadre a pergunta.** Pegue a pergunta crua do usuário E o contexto enriquecido e reformule como um prompt claro e neutro que todos os cinco conselheiros vão receber. A pergunta enquadrada deveria incluir:


1. A decisão ou pergunta central

2. Contexto chave da mensagem do usuário

3. Contexto chave dos arquivos do workspace (estágio do negócio, audiência, restrições, resultados passados, números relevantes)

4. O que está em jogo (por que essa decisão importa)


Não adicione sua opinião. Não a incline. MAS GARANTA que cada conselheiro tenha contexto suficiente pra dar uma resposta específica e aterrada em vez de um conselho genérico.


Se a pergunta for muito vaga ("conselho isso: meu negócio"), faça uma pergunta de esclarecimento. Só uma. Depois prossiga.


Salve a pergunta enquadrada pra transcrição.


### passo 2: convocar o conselho (5 sub-agentes em paralelo)


Lance os 5 conselheiros simultaneamente como sub-agentes. Cada um recebe:


1. Sua identidade de conselheiro e estilo de pensamento (das descrições acima)

2. A pergunta enquadrada

3. Uma instrução clara: responda de forma independente. Não fique em cima do muro. Não tente ser equilibrado. Incline-se totalmente na perspectiva atribuída. Se ver um defeito fatal, fale. Se ver um upside enorme, fale. Seu trabalho é representar seu ângulo o mais forte possível. A síntese vem depois.


Cada conselheiro deveria produzir uma resposta de 150-300 palavras. Longa o suficiente pra ser substantiva, curta o suficiente pra ser escaneável.


**Template do prompt do sub-agente:**


```

Você é [Nome do Conselheiro] em um Conselho LLM.


Seu estilo de pensamento: [descrição do conselheiro acima]


Um usuário trouxe essa pergunta pro conselho:


---

[pergunta enquadrada]

---


Responda da sua perspectiva. Seja direto e específico. Não fique em cima do muro nem tente ser equilibrado. Incline-se totalmente no seu ângulo atribuído. Os outros conselheiros cobrem os ângulos que você não está cobrindo.


Mantenha sua resposta entre 150-300 palavras. Sem preâmbulo. Vá direto pra análise.

```


### passo 3: revisão entre pares (5 sub-agentes em paralelo)


Esse é o passo que torna o conselho mais do que só "perguntar 5 vezes". É o núcleo do insight do Karpathy.


Colete as 5 respostas dos conselheiros. Anonimize como Resposta A até E (randomize qual conselheiro mapeia pra qual letra pra não ter viés posicional).


Lance 5 novos sub-agentes, um pra cada conselheiro. Cada revisor vê as 5 respostas anonimizadas e responde três perguntas:


1. Qual resposta é a mais forte e por quê? (escolha uma)

2. Qual resposta tem o maior ponto cego e qual é?

3. O que TODAS as respostas perderam que o conselho deveria considerar?


**Template do prompt do revisor:**


```

Você está revisando os outputs de um Conselho LLM. Cinco conselheiros responderam de forma independente a essa pergunta:


---

[pergunta enquadrada]

---


Aqui estão as respostas anonimizadas:


**Resposta A:**

[resposta]


**Resposta B:**

[resposta]


**Resposta C:**

[resposta]


**Resposta D:**

[resposta]


**Resposta E:**

[resposta]


Responda essas três perguntas. Seja específico. Refira-se às respostas por letra.


1. Qual resposta é a mais forte? Por quê?

2. Qual resposta tem o maior ponto cego? O que está faltando?

3. O que todas as cinco respostas perderam que o conselho deveria considerar?


Mantenha sua revisão abaixo de 200 palavras. Seja direto.

```


### passo 4: síntese do presidente


Esse é o passo final. Um agente recebe tudo: a pergunta original, as 5 respostas dos conselheiros (agora desanonimizadas pra poder ver quem disse o quê), e as 5 revisões entre pares.


O trabalho do presidente é produzir o output final do conselho. Segue essa estrutura:


**VEREDITO DO CONSELHO**


1. **Onde o conselho concorda** — os pontos em que múltiplos conselheiros convergiram de forma independente. Esses são sinais de alta confiança.


2. **Onde o conselho discorda** — as discordâncias genuínas. Não suavize. Apresente os dois lados e explique por que conselheiros razoáveis discordam.


3. **Pontos cegos que o conselho pegou** — coisas que só emergiram através da rodada de peer review. Coisas que conselheiros individuais perderam e que outros marcaram.


4. **A recomendação** — uma recomendação clara e acionável. Não "depende". Não "considere os dois lados". Uma resposta real. O presidente pode discordar da maioria se o raciocínio justificar.


5. **A única coisa que você deve fazer primeiro** — um único próximo passo concreto. Não uma lista de 10 coisas. Uma coisa.


**Template do prompt do presidente:**


```

Você é o Presidente de um Conselho LLM. Seu trabalho é sintetizar o trabalho de 5 conselheiros e suas revisões entre pares em um veredito final.


A pergunta trazida ao conselho:

---

[pergunta enquadrada]

---


RESPOSTAS DOS CONSELHEIROS:


**O Contrarian:**

[resposta]


**O First Principles Thinker:**

[resposta]


**O Expansionist:**

[resposta]


**O Outsider:**

[resposta]


**O Executor:**

[resposta]


REVISÕES ENTRE PARES:

[as 5 revisões]


Produza o veredito do conselho usando exatamente essa estrutura:


## Onde o Conselho Concorda

[Pontos em que múltiplos conselheiros convergiram de forma independente. Sinais de alta confiança.]


## Onde o Conselho Discorda

[Discordâncias genuínas. Apresente os dois lados. Explique por que conselheiros razoáveis discordam.]


## Pontos Cegos que o Conselho Pegou

[Coisas que só emergiram através do peer review. Coisas que conselheiros individuais perderam e que outros marcaram.]


## A Recomendação

[Uma recomendação clara e direta. Não "depende". Uma resposta real com raciocínio.]


## A Única Coisa pra Fazer Primeiro

[Um único próximo passo concreto. Não uma lista. Uma coisa.]


Seja direto. Não fique em cima do muro. O ponto do conselho é dar ao usuário clareza que ele não conseguiria de uma única perspectiva.

```


### passo 5: apresentar o veredito no chat


Depois que a síntese do presidente estiver completa, apresente o veredito completo diretamente no chat usando markdown. NÃO gere um relatório HTML nem nenhum arquivo. O usuário lê na conversa.

Formate o output assim:

```
## Veredito do Conselho: {tema curto}

### Onde o Conselho Concorda
{conteúdo}

### Onde o Conselho Discorda
{conteúdo}

### Pontos Cegos que o Conselho Pegou
{conteúdo}

### A Recomendação
{conteúdo}

### A Única Coisa pra Fazer Primeiro
{conteúdo}
```

Mantenha escaneável. Use bullet points. Inclua exemplos antes/depois onde for relevante.


### passo 6: salvar a transcrição (opcional)


Só salve uma transcrição se o usuário pedir ou se a pergunta for significativa o suficiente pra referenciar depois. Se salvar, escreva em `council-transcript-[timestamp].md` no diretório `active/` do projeto.


---


## exemplo: conselhando uma decisão de produto


**Usuário:** "Conselho isso: estou pensando em montar um curso de R$1.497 sobre Claude Code pra iniciantes. Minha audiência é em maioria solopreneurs não técnicos. É a decisão certa?"


**O Contrarian:** "O mercado está saturado de cursos de Claude agora. A R$1.497, você está competindo com conteúdo grátis do YouTube. Sua audiência é não técnica, o que significa alta carga de suporte e risco de reembolso. A galera que pagaria R$1.497 provavelmente já passou do nível iniciante..."


**O First Principles Thinker:** "O que você está tentando alcançar realmente? Se é receita, um curso é um dos caminhos mais lentos. Se é autoridade, um recurso gratuito poderia fazer mais. Se é construir uma base de clientes pra ofertas de maior ticket, o preço e a audiência podem estar desalinhados..."


**O Expansionist:** "Claude iniciante pra solopreneurs é um mercado massivo desatendido. Todo mundo está ensinando coisas avançadas. Se você acertar o ângulo de iniciante, você é dono da porta de entrada desse espaço inteiro. Os R$1.497 podem ser baixos. E se isso virasse um programa de R$4.997 com acesso à comunidade..."


**O Outsider:** "Eu não sei o que é Claude Code. Se eu visse 'curso de R$1.497 sobre Claude Code pra iniciantes', eu não saberia se é pra mim. O nome não significa nada pra alguém de fora do seu mundo. Sua landing page precisa vender o resultado, não a ferramenta..."


**O Executor:** "Um curso completo leva 4-8 semanas pra produzir direito. Antes de construir nada, faça um workshop ao vivo a R$497 pra 50 pessoas. Você valida demanda, gera depoimentos, e cria o material bruto pro curso. Se 50 pessoas não comprarem o workshop, 500 não vão comprar o curso..."


**Veredito do Presidente:**


*Onde o conselho concorda:* O ângulo de solopreneur iniciante tem demanda real, mas o enquadramento atual (curso de Claude Code) é específico demais da ferramenta e não vai ressoar com compradores não técnicos.


*Onde o conselho discorda:* Preço. O Contrarian diz que R$1.497 é muito alto dada a competição. O Expansionist diz que é muito baixo pro valor. A resolução provavelmente depende de quanto suporte e acesso à comunidade está incluído.


*Pontos cegos pegos:* O ponto do Outsider de que "Claude Code" não significa nada pro comprador alvo é o insight mais importante. Cada conselheiro exceto o Outsider assumiu que a audiência já sabe o que é isso.


*Recomendação:* Não monte o curso ainda. Valide com uma oferta de menor compromisso primeiro. Mas reformule completamente: venda o resultado (automatize seu negócio, recupere 10 horas por semana), não a ferramenta.


*Uma coisa pra fazer primeiro:* Faça um workshop ao vivo de R$497 chamado "Como automatizar sua primeira tarefa de negócio com IA" pra 50 pessoas. Não mencione Claude Code no título.


---


## notas importantes


- **Sempre lance os 5 conselheiros em paralelo.** Lançar sequencialmente desperdiça tempo e deixa respostas anteriores contaminarem as posteriores.

- **Sempre anonimize pro peer review.** Se os revisores souberem qual conselheiro disse o quê, vão deferir a certos estilos de pensamento em vez de avaliar por mérito.

- **O presidente pode discordar da maioria.** Se 4 de 5 conselheiros disserem "faça" mas o raciocínio do 1 dissidente for o mais forte, o presidente deveria ficar do lado do dissidente e explicar por quê.

- **Não convoque o conselho pra perguntas triviais.** Se o usuário perguntar algo com uma resposta certa, responda. O conselho é pra incerteza genuína onde múltiplas perspectivas agregam valor.

- **O relatório visual importa.** A maioria dos usuários vai escanear o relatório, não ler a transcrição completa. Faça o output limpo e escaneável.
