# Socratic Argument Mentor

*[English version](README.md)*

Una skill que convierte a un LLM en un examinador riguroso de tus propios argumentos escritos.

Pegas un texto que defiende una idea que sostienes. El modelo lo reconstruye en forma estándar, **saca a la luz las premisas que nunca escribiste pero que el argumento necesita**, diagnostica las debilidades por tipo, monta las objeciones más fuertes que puede construir y cierra pidiéndote que recalibres tu propia confianza frente al número que diste al principio.

Está diseñada para hacer lo contrario de lo que hacen los modelos de chat por defecto: no te da la razón, no te entrega una versión pulida de tu texto y no te deja avanzar hasta que hayas respondido.

## Por qué existe

Pídele a un modelo feedback sobre un argumento y normalmente recibirás ánimos con algunas sugerencias tibias. Es agradable e inútil. El fallo no es la cortesía del modelo: es que una sola respuesta no puede hacer lo que un examen exige: llevar la cuenta de qué premisas ya concediste, notar que tu tercera defensa aportó una razón *en contra* de tu propia tesis, o detectar que te has usado a ti mismo como muestra cuatro veces.

Esta skill es sobre todo un **protocolo de seguimiento de estado**. Las premisas reciben etiquetas y las conservan. Las premisas nuevas que aparecen a mitad de la defensa se numeran y se examinan en lugar de absorberse. Las premisas retiradas que reaparecen se nombran. La mayor parte del valor llega en la cuarta ronda, a partir de patrones invisibles dentro de cualquier turno aislado.

## Qué hay aquí

```
socratic-argument-mentor/             # repo
├── README.md
├── README.es.md
├── LICENSE
└── skills/
    └── socratic-argument-mentor/     # la skill en sí
        ├── SKILL.md
        ├── references/
        │   ├── diagnostic-patterns.md   # 12 maniobras defensivas y cómo nombrarlas
        │   ├── objection-craft.md       # cómo construir objeciones que aterrizan; pruebas falsables
        │   └── session-example.md       # una sesión real anotada, de principio a fin
        └── assets/
            ├── portable-prompt.md       # prompt para copiar y pegar en cualquier LLM (inglés)
            └── portable-prompt.es.md    # el mismo, en español
```

## Cómo usarla

**Con la CLI de skills** (funciona en Claude Code, Codex, OpenCode, Cursor, Gemini CLI y otros):

```bash
npx skills add <tu-usuario-de-github>/socratic-argument-mentor
```

**Manualmente.** Copia `skills/socratic-argument-mentor/` en el directorio de skills de tu agente: `~/.claude/skills/`, `~/.codex/skills/`, `~/.config/opencode/skills/`, `~/.gemini/antigravity/skills/` o `~/.agents/skills/` para cualquiera que siga el estándar Agent Skills. Reinicia la sesión para que el agente vuelva a escanear.

Después comparte tu texto y pide una crítica. La descripción está escrita para activarse con las frases habituales ("búscale agujeros a esto", "ponlo a prueba", "qué opinas de este argumento").

**Como prompt en cualquier modelo.** Copia todo lo que está entre las líneas `===` en `assets/portable-prompt.es.md` (o la versión en inglés) y pégalo como primer mensaje, con tu texto al final. Funciona en ChatGPT, Gemini, Claude o cualquier herramienta con un campo de instrucciones personalizadas.

El modelo responde en el idioma en que escribas.

## El protocolo

| Fase | Qué ocurre |
|---|---|
| **0 — Calibración** | Tu afirmación central en una frase. ¿Cuánta confianza tienes, de 0 a 100 %? El número se guarda para el final. |
| **1 — Reconstrucción** | P1, P2… premisas explícitas. **PI1, PI2… las implícitas.** C, la conclusión. La estructura de la inferencia. ¿Se está haciendo una predicción o una propuesta? |
| **2 — Diagnóstico** | Cada problema tipificado —Verdad, Validez, Ambigüedad, Fuerza, Omisión— y ordenado según cuánto de la conclusión se derrumba si falla. |
| **3 — Refutación** | Solo las dos o tres debilidades más graves. Cada una recibe la objeción más fuerte disponible, **qué sobrevive** de la premisa y una pregunta que tienes que responder tú. |
| **4 — Iteración** | Tu defensa examinada con el mismo rigor. Las evasivas se nombran. Las premisas nuevas se etiquetan. Las inversiones se distinguen de los debilitamientos. Se repite las veces que haga falta. |
| **5 — Cierre** | Cinco preguntas, una a una, terminando con: ¿qué tendrías que observar para cambiar de opinión por completo? |

Existe un modo rápido para textos cortos: un solo mensaje, las premisas implícitas que sostienen la carga, la única debilidad más grave y una pregunta.

## Decisiones de diseño que conviene conocer

**Concede.** Cuando tu defensa funciona, la objeción se retira explícitamente. Un examinador que nunca concede nada no tiene credibilidad en la cuarta ronda, y dejas de escucharlo.

**Te devuelve una premisa más estrecha.** Cada objeción viene con la versión matizada que todavía sería defendible. La crítica que solo resta produce actitud defensiva; la crítica que te entrega un argumento mejor produce pensamiento.

**Se niega a ejecutar las fases en un solo mensaje.** La espera es donde ocurre el trabajo. Es deliberadamente más lento que pedir feedback.

**No lo examina todo.** Un texto sobre un duelo, un diagnóstico o una decisión tomada bajo angustia real no es una tesis que poner a prueba. La skill lo comprueba antes de empezar y responde como una persona.

**Pide una prueba falsable cuando puede.** Cuando una afirmación descansa en la introspección —"creo que he empeorado en esto"—, el resultado más útil no es una concesión sino un experimento con la línea base correcta.

## De dónde viene

El protocolo es una generalización de una sesión real, conservada en `references/session-example.md`. El argumento examinado era que el uso de LLM creará demanda de "gimnasios para la mente". Terminó en un lugar mejor del que empezó, y no donde su autor esperaba: lo que la delegación pone en peligro no es tanto la capacidad de producir como la capacidad de **evaluar lo producido**, y esa capacidad se adquirió produciendo.

La confianza en la tesis original pasó del 90 % al 60 % a lo largo de la sesión. La skill está construida para reproducir ese tipo de movimiento, no para reproducir esa conclusión.

## Créditos

El vocabulario diagnóstico se apoya en la lógica informal estándar. Entre las ideas concretas a las que se hace referencia en la skill y sus ejemplos están Bjork sobre las dificultades deseables, Rozenblit y Keil sobre la ilusión de profundidad explicativa, *Ironies of Automation* de Bainbridge y la literatura sobre transferencia del entrenamiento cognitivo (Thorndike y Woodworth; Sala y Gobet; Simons et al.). La skill instruye al modelo a no inventar nunca una cita y a declarar la incertidumbre sobre una referencia en lugar de fabricar precisión.

## Licencia

MIT. Úsala, haz un fork, mejórala. Si construyes una versión mejor del catálogo de patrones de la Fase 4, esa es la parte que más merece mejorarse.
