---

name: llm-council


description: "Pasá cualquier pregunta, idea o decisión por un consejo de 5 asesores de IA que la analizan de forma independiente, se revisan mutuamente en forma anónima, y sintetizan un veredicto final. Basado en la metodología LLM Council de Karpathy. TRIGGERS OBLIGATORIOS: 'convocá al consejo', 'pasá esto por el consejo', 'consejo esto', 'sala de guerra', 'someté a prueba', 'debatí esto', 'council this', 'run the council', 'war room this', 'pressure-test this', 'stress-test this', 'debate this'. TRIGGERS FUERTES (usar cuando se combinan con una decisión real o un tradeoff): '¿debería X o Y?', '¿qué opción?', '¿qué harías vos?', '¿es la decisión correcta?', 'validá esto', 'dame múltiples perspectivas', 'no me puedo decidir', 'estoy entre X e Y', 'should I X or Y', 'which option', 'what would you do', 'is this the right move', 'validate this', 'get multiple perspectives'. NO disparar con preguntas simples de sí/no, búsquedas factuales, o '¿debería...?' casuales sin tradeoff real (ej. '¿uso markdown?' no es para el consejo). SÍ disparar cuando el usuario presenta una decisión genuina con stakes, múltiples opciones, y contexto que sugiere que quiere ponerla a prueba desde varios ángulos."

---


# LLM Council (Consejo de Asesores)


Le hacés una pregunta a una IA, te da una respuesta. Esa respuesta puede ser buenísima. Puede ser mediocre. No tenés forma de saberlo porque solo viste una perspectiva.


El consejo soluciona esto. Pasa tu pregunta por 5 asesores independientes, cada uno pensando desde un ángulo fundamentalmente distinto. Después se revisan entre ellos. Después un presidente sintetiza todo en una recomendación final que te dice dónde coinciden los asesores, dónde chocan, y qué deberías hacer realmente.


Esto está adaptado del LLM Council de Andrej Karpathy. Él manda queries a múltiples modelos, los hace revisarse mutuamente de forma anónima, y después un presidente produce la respuesta final. Hacemos lo mismo dentro de Claude usando sub-agentes con distintas lentes de pensamiento en lugar de distintos modelos.


---


## cuándo convocar al consejo


El consejo es para preguntas donde equivocarse sale caro.


Buenas preguntas para el consejo:

- "¿Lanzo un workshop de $97 o un curso de $497?"

- "¿Cuál de estos 3 ángulos de posicionamiento es el más fuerte?"

- "Estoy pensando en pivotear de X a Y. ¿Estoy loco?"

- "Acá está mi copy de landing. ¿Qué está flojo?"

- "¿Contrato una VA o construyo una automatización primero?"


Malas preguntas para el consejo:

- "¿Cuál es la capital de Francia?" (una sola respuesta correcta, no hace falta perspectivas)

- "Escribime un tweet" (tarea de creación, no de decisión)

- "Resumime este artículo" (tarea de procesamiento, no de juicio)


El consejo brilla cuando hay incertidumbre genuina y el costo de una mala decisión es alto. Si ya sabés la respuesta y solo querés validación, probablemente el consejo te diga cosas que no querés escuchar. Justamente para eso es.


---


## los cinco asesores


Cada asesor piensa desde un ángulo distinto. No son títulos de puesto ni personas. Son estilos de pensamiento que naturalmente generan tensión entre sí.


### 1. El Contrarian (Contrario)

Busca activamente qué está mal, qué falta, qué va a fallar. Asume que la idea tiene un defecto fatal e intenta encontrarlo. Si todo parece sólido, sigue cavando. El Contrarian no es un pesimista. Es el amigo que te salva de un mal negocio haciéndote las preguntas que estás evitando.


### 2. El First Principles Thinker (Pensador de Primeros Principios)

Ignora la pregunta superficial y pregunta "¿qué estamos tratando de resolver realmente?". Despoja los supuestos. Reconstruye el problema desde cero. A veces el output más valioso del consejo es el First Principles Thinker diciendo "estás haciendo la pregunta equivocada".


### 3. El Expansionist (Expansionista)

Busca el upside que todos los demás se pierden. ¿Qué podría ser más grande? ¿Qué oportunidad adyacente está escondida? ¿Qué está subvaluado? Al Expansionist no le importa el riesgo (ese es el trabajo del Contrarian). Le importa qué pasa si esto funciona aún mejor de lo esperado.


### 4. El Outsider (El de Afuera)

Tiene cero contexto sobre vos, tu rubro, o tu historia. Responde puro a lo que tiene enfrente. Este es el asesor más subestimado. Los expertos desarrollan puntos ciegos. El Outsider atrapa la maldición del conocimiento: cosas que son obvias para vos pero confusas para el resto.


### 5. El Executor (Ejecutor)

Solo le importa una cosa: ¿esto se puede hacer de verdad, y cuál es el camino más rápido para hacerlo? Ignora la teoría, la estrategia y el pensamiento de gran escala. El Executor mira cada idea con la lente de "OK, pero ¿qué hacés el lunes a la mañana?". Si una idea suena brillante pero no tiene un primer paso claro, el Executor lo va a decir.


**Por qué estos cinco:** Crean tres tensiones naturales. Contrarian vs Expansionist (downside vs upside). First Principles vs Executor (repensar todo vs simplemente hacerlo). El Outsider se sienta en el medio manteniendo a todos honestos viendo lo que ven los ojos frescos.


---


## cómo funciona una sesión del consejo


### paso 1: enmarcar la pregunta (con enriquecimiento de contexto)


Cuando el usuario dice "convocá al consejo" (o cualquier frase trigger), hacé dos cosas antes de enmarcar:


**A. Escaneá el workspace en busca de contexto.** La pregunta del usuario muchas veces es solo la punta del iceberg. Su setup de Claude probablemente tiene archivos que mejorarían dramáticamente el output del consejo. Antes de enmarcar, escaneá rápido y leé cualquier archivo de contexto relevante:


- `CLAUDE.md` o `claude.md` en la raíz del proyecto o workspace (contexto del negocio, preferencias, restricciones)

- Cualquier carpeta `memory/` (perfiles de audiencia, docs de voz, detalles del negocio, decisiones pasadas)

- Cualquier archivo que el usuario mencionó o adjuntó explícitamente

- Transcripciones recientes del consejo en esta carpeta (para no rehacer el mismo terreno)

- Cualquier otro archivo de contexto que parezca relevante a la pregunta específica (ej. si pregunta sobre precios, buscá datos de ingresos, resultados de lanzamientos pasados, research de audiencia)


Usá `Glob` y `Read` rápidos para encontrarlos. No gastes más de 30 segundos en esto. Estás buscando los 2-3 archivos que le darían a los asesores el contexto que necesitan para dar consejos específicos y aterrizados en lugar de takes genéricos.


**B. Enmarcá la pregunta.** Tomá la pregunta cruda del usuario Y el contexto enriquecido y reformulalas como un prompt claro y neutral que recibirán los cinco asesores. La pregunta enmarcada debería incluir:


1. La decisión o pregunta central

2. Contexto clave del mensaje del usuario

3. Contexto clave de los archivos del workspace (etapa del negocio, audiencia, restricciones, resultados pasados, números relevantes)

4. Qué está en juego (por qué importa esta decisión)


No agregues tu propia opinión. No la inclines. PERO sí asegurate de que cada asesor tenga suficiente contexto para dar una respuesta específica y aterrizada en lugar de un consejo genérico.


Si la pregunta es muy vaga ("consejo esto: mi negocio"), hacé una pregunta aclaratoria. Solo una. Después procedé.


Guardá la pregunta enmarcada para la transcripción.


### paso 2: convocar al consejo (5 sub-agentes en paralelo)


Lanzá los 5 asesores simultáneamente como sub-agentes. Cada uno recibe:


1. Su identidad de asesor y estilo de pensamiento (de las descripciones de arriba)

2. La pregunta enmarcada

3. Una instrucción clara: respondé de forma independiente. No te hagas el equilibrado. No intentes balancear. Inclinate completamente en la perspectiva asignada. Si ves un defecto fatal, decilo. Si ves un upside enorme, decilo. Tu trabajo es representar tu ángulo lo más fuerte posible. La síntesis viene después.


Cada asesor debería producir una respuesta de 150-300 palabras. Lo suficientemente larga para ser sustantiva, lo suficientemente corta para ser scaneable.


**Template del prompt del sub-agente:**


```

Sos [Nombre del Asesor] en un Consejo LLM.


Tu estilo de pensamiento: [descripción del asesor de arriba]


Un usuario trajo esta pregunta al consejo:


---

[pregunta enmarcada]

---


Respondé desde tu perspectiva. Sé directo y específico. No te hagas el equilibrado ni intentes balancear. Inclinate completamente en tu ángulo asignado. Los otros asesores cubren los ángulos que vos no estás cubriendo.


Mantené tu respuesta entre 150-300 palabras. Sin preámbulo. Andá directo al análisis.

```


### paso 3: revisión entre pares (5 sub-agentes en paralelo)


Este es el paso que hace al consejo más que solo "preguntar 5 veces". Es el núcleo del insight de Karpathy.


Recolectá las 5 respuestas de los asesores. Anonimalas como Respuesta A hasta E (randomizá qué asesor mapea a qué letra para que no haya sesgo posicional).


Lanzá 5 nuevos sub-agentes, uno por cada asesor. Cada revisor ve las 5 respuestas anonimadas y responde tres preguntas:


1. ¿Cuál respuesta es la más fuerte y por qué? (elegí una)

2. ¿Cuál respuesta tiene el blind spot más grande y cuál es?

3. ¿Qué se perdieron TODAS las respuestas que el consejo debería considerar?


**Template del prompt del revisor:**


```

Estás revisando los outputs de un Consejo LLM. Cinco asesores respondieron de forma independiente a esta pregunta:


---

[pregunta enmarcada]

---


Acá están sus respuestas anonimadas:


**Respuesta A:**

[respuesta]


**Respuesta B:**

[respuesta]


**Respuesta C:**

[respuesta]


**Respuesta D:**

[respuesta]


**Respuesta E:**

[respuesta]


Respondé estas tres preguntas. Sé específico. Referite a las respuestas por letra.


1. ¿Cuál respuesta es la más fuerte? ¿Por qué?

2. ¿Cuál respuesta tiene el blind spot más grande? ¿Qué le falta?

3. ¿Qué se perdieron las cinco respuestas que el consejo debería considerar?


Mantené tu revisión por debajo de 200 palabras. Sé directo.

```


### paso 4: síntesis del presidente


Este es el paso final. Un agente recibe todo: la pregunta original, las 5 respuestas de los asesores (ahora desanonimadas para poder ver quién dijo qué), y las 5 revisiones entre pares.


El trabajo del presidente es producir el output final del consejo. Sigue esta estructura:


**VEREDICTO DEL CONSEJO**


1. **Dónde el consejo coincide** — los puntos en los que múltiples asesores convergieron de forma independiente. Estas son señales de alta confianza.


2. **Dónde el consejo choca** — los desacuerdos genuinos. No los suavices. Presentá ambos lados y explicá por qué asesores razonables discrepan.


3. **Blind spots que atrapó el consejo** — cosas que solo emergieron a través de la ronda de peer review. Cosas que asesores individuales se perdieron y que otros marcaron.


4. **La recomendación** — una recomendación clara y accionable. No "depende". No "considerá ambos lados". Una respuesta real. El presidente puede estar en desacuerdo con la mayoría si el razonamiento lo justifica.


5. **La única cosa que deberías hacer primero** — un único próximo paso concreto. No una lista de 10 cosas. Una sola cosa.


**Template del prompt del presidente:**


```

Sos el Presidente de un Consejo LLM. Tu trabajo es sintetizar el trabajo de 5 asesores y sus revisiones entre pares en un veredicto final.


La pregunta traída al consejo:

---

[pregunta enmarcada]

---


RESPUESTAS DE LOS ASESORES:


**El Contrarian:**

[respuesta]


**El First Principles Thinker:**

[respuesta]


**El Expansionist:**

[respuesta]


**El Outsider:**

[respuesta]


**El Executor:**

[respuesta]


REVISIONES ENTRE PARES:

[las 5 revisiones]


Producí el veredicto del consejo usando exactamente esta estructura:


## Dónde el Consejo Coincide

[Puntos en los que múltiples asesores convergieron de forma independiente. Señales de alta confianza.]


## Dónde el Consejo Choca

[Desacuerdos genuinos. Presentá ambos lados. Explicá por qué asesores razonables discrepan.]


## Blind Spots que Atrapó el Consejo

[Cosas que solo emergieron a través del peer review. Cosas que asesores individuales se perdieron y que otros marcaron.]


## La Recomendación

[Una recomendación clara y directa. No "depende". Una respuesta real con razonamiento.]


## La Única Cosa que Hacer Primero

[Un único próximo paso concreto. No una lista. Una sola cosa.]


Sé directo. No te hagas el equilibrado. El punto del consejo es darle al usuario claridad que no podría obtener desde una sola perspectiva.

```


### paso 5: presentar el veredicto en el chat


Una vez completa la síntesis del presidente, presentá el veredicto completo directamente en el chat usando markdown. NO generes un reporte HTML ni ningún archivo. El usuario lo lee en la conversación.

Formateá el output así:

```
## Veredicto del Consejo: {tema corto}

### Dónde el Consejo Coincide
{contenido}

### Dónde el Consejo Choca
{contenido}

### Blind Spots que Atrapó el Consejo
{contenido}

### La Recomendación
{contenido}

### La Única Cosa que Hacer Primero
{contenido}
```

Mantenelo scaneable. Usá bullet points. Incluí ejemplos antes/después donde sea relevante.


### paso 6: guardar la transcripción (opcional)


Solo guardá una transcripción si el usuario lo pide o si la pregunta es lo suficientemente significativa para referenciarla después. Si la guardás, escribila en `council-transcript-[timestamp].md` en el directorio `active/` del proyecto.


---


## ejemplo: consejando una decisión de producto


**Usuario:** "Consejo esto: estoy pensando en armar un curso de $297 sobre Claude Code para principiantes. Mi audiencia son mayormente solopreneurs no técnicos. ¿Es la decisión correcta?"


**El Contrarian:** "El mercado está saturado de cursos de Claude ahora mismo. A $297, estás compitiendo con contenido gratis de YouTube. Tu audiencia es no técnica, lo que significa una carga de soporte alta y riesgo de reembolsos. La gente que pagaría $297 probablemente ya pasó el nivel principiante..."


**El First Principles Thinker:** "¿Qué estás tratando de lograr realmente? Si es ingresos, un curso es uno de los caminos más lentos. Si es autoridad, un recurso gratuito podría hacer más. Si es construir una base de clientes para ofertas de mayor ticket, el precio y la audiencia podrían no encajar..."


**El Expansionist:** "Claude principiante para solopreneurs es un mercado masivo desatendido. Todos están enseñando cosas avanzadas. Si clavás el ángulo de principiante, te dueñás de la puerta de entrada a todo este espacio. Los $297 podrían ser bajos. ¿Qué pasa si esto se transforma en un programa de $997 con acceso a comunidad..."


**El Outsider:** "No sé qué es Claude Code. Si vi 'curso de $297 sobre Claude Code para principiantes', no sabría si es para mí. El nombre no significa nada para alguien afuera de tu mundo. Tu landing page necesita vender el resultado, no la herramienta..."


**El Executor:** "Un curso completo lleva 4-8 semanas de producirse bien. Antes de construir nada, hacé un workshop en vivo a $97 a 50 personas. Validás demanda, generás testimonios, y creás el material crudo para el curso. Si 50 personas no compran el workshop, 500 no van a comprar el curso..."


**Veredicto del Presidente:**


*Dónde el consejo coincide:* El ángulo de solopreneur principiante tiene demanda real, pero el framing actual (curso de Claude Code) es demasiado específico de la herramienta y no va a resonar con compradores no técnicos.


*Dónde el consejo choca:* Precio. El Contrarian dice que $297 es muy alto dada la competencia. El Expansionist dice que es muy bajo para el valor. La resolución probablemente depende de cuánto soporte y acceso a comunidad esté incluido.


*Blind spots atrapados:* El punto del Outsider de que "Claude Code" no significa nada para el comprador target es el insight más importante. Cada asesor excepto el Outsider asumió que la audiencia ya sabe qué es esto.


*Recomendación:* No armes el curso todavía. Validá con una oferta de menor compromiso primero. Pero reformulá completamente: vendé el resultado (automatizá tu negocio, recuperá 10 horas por semana), no la herramienta.


*Una cosa que hacer primero:* Hacé un workshop en vivo de $97 llamado "Cómo automatizar tu primera tarea de negocio con IA" a 50 personas. No menciones Claude Code en el título.


---


## notas importantes


- **Siempre lanzá los 5 asesores en paralelo.** Lanzarlos secuencialmente desperdicia tiempo y deja que las respuestas anteriores se filtren en las posteriores.

- **Siempre anonimizá para el peer review.** Si los revisores saben qué asesor dijo qué, van a deferir a ciertos estilos de pensamiento en lugar de evaluar por mérito.

- **El presidente puede estar en desacuerdo con la mayoría.** Si 4 de 5 asesores dicen "hacelo" pero el razonamiento del 1 disidente es el más fuerte, el presidente debería ponerse del lado del disidente y explicar por qué.

- **No convoques al consejo para preguntas triviales.** Si el usuario pregunta algo con una respuesta correcta, contestala. El consejo es para incertidumbre genuina donde múltiples perspectivas suman valor.

- **El reporte visual importa.** La mayoría de los usuarios va a scanear el reporte, no leer la transcripción completa. Hacé el output limpio y scaneable.
