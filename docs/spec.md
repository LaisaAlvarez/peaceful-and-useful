# Peacefull and usefull — Spec

Entrevista de requerimientos · versión pulida (v4) · Actividad: videojuegos (Hollow Knight) · Preparado el 20 de julio de 2026

Fuente original: `docs/referencias/Peacefull and usefull - Entrevista.pdf`.

## Por qué esta actividad

Videojuegos: exige pensamiento estratégico e inteligencia para resolver problemas — descubrir secretos, atajos y tesoros ocultos. Requiere entender cómo funciona el juego y su sistema, con el objetivo final de completarlo al 100%.

Frecuencia: al menos una vez por semana.

## Preparativos antes de jugar

1. Recoger el cuarto.
2. Ir por una botana que se pueda comer con la mano (papas, galletas), con servilletas cerca.
3. Ropa cómoda: playera holgada, pants, descalza (o calcetines gruesos/pantuflas/tenis).
4. Acomodar almohadas para recargarse (las más gruesas al frente).

## Cómo se juega, paso a paso

Vestimenta: playera oversize y pants cómodo. Herramientas: consola y control, ambos Xbox.

1. Prender la consola (botón con logotipo Xbox).
2. Prender el control (mismo botón).
3. Seleccionar perfil de Xbox.
4. Ingresar contraseña.
5. Con el joystick, seleccionar el engranaje (esquina superior izquierda) y presionar A.
6. Entrar a "Mis juegos" y presionar A de nuevo.
7. Elegir el juego del catálogo — Hollow Knight.

## Reglas

1. Sentirse muy cómoda para empezar a jugar.
2. Tener una botana bien preparada a su gusto.
3. Necesita luz eléctrica (el internet no es necesario).
4. Sentirse a gusto consigo misma.
5. Reglas propias del juego: salvar un mundo perdido tras un apocalipsis; ir descubriendo mundos subterráneos; usar la espada para defenderse/eliminar enemigos; recaudar dinero para objetos; ir revelando el mapa conforme se explora.

Es individual: solo ella, su consola, su control y su juego.

## Entorno

Cuarto personal: minimalista, cama queen size, colcha blanca con flores moradas (no calienta), 4 almohadas grises/blancas con flores moradas, TV de 50", burós de madera clara, paredes beige claro, tocador al lado.

## Qué distingue a un experto

Opina sobre el funcionamiento del juego, su historia y gráficos (estilo caricaturesco, incluso infantil, colorido pero sombrío, personajes entrañables), y sobre la programación/estructura: cómo fue construido, inspiración de sus creadores, cómo se fue desarrollando.

## Fricciones

- **Antes:** el quehacer de la casa completa (sala, cuartos, cocina, comedor, baño).
- **Durante:** encontrar el control por el desorden en casa.

## Qué le gustaría recordar (pendientes de casa)

- Guardar zapatos.
- Guardar lo que acaba de usar (skincare, cuidado personal).
- Llegar con energía del trabajo.
- Preparar desayunos.
- Poner al Roborock a trapear y barrer.
- Lavar trastes.
- Preparar lo del trabajo del día siguiente (ropa, mochila).

Todo esto para poder jugar después sin pendientes en la cabeza.

## Si tuviera un asistente mágico, le pediría...

1. Generar checklist de quehaceres a partir de una foto del cuarto (detectando hasta detalles pequeños), separando en **actividades semanales** y **actividades diarias**.
2. Medir energía, rutina, bioritmo (gallo/búho) y ciclo circadiano — y si se identifica como mujer, sumar días del ciclo menstrual, para estimar energía con más precisión.
3. Generar tiempos estimados para cada actividad de la checklist.
4. Generar recordatorios de cuándo y cómo hacer cada tarea.
5. Programar metas a corto/mediano/largo plazo, con contador de días dedicados y % de avance. Generar un **KPI semanal** (% de días dedicados + % de avance de meta), y preguntar nivel de satisfacción tras cada quehacer con escala de 5 caritas (muy triste → muy alegre).
6. Llevar contador de tiempo de disfrute jugando (ej. Hollow Knight) y preguntar nivel de felicidad al terminar, misma escala de 5 caritas.

## En una frase

Una app de organización que diga exactamente qué hacer escaneando el cuarto por fotografía, con recordatorios, tiempos estimados y medición de bioritmo — y que arme la checklist completa de pendientes.

## Métricas principales (inputs)

1. Fotografía del cuarto al despertar → genera la checklist de quehaceres.
2. Test de identificación (hombre/mujer) → test de ciclo circadiano, niveles de energía, días de menstruación (si aplica) y bioritmo, con preguntas de rutina (hora de despertar, etc.).
3. Con esos resultados, estimación de tiempos y actividades.

> Nota: estas 3 son insumos que alimentan el sistema, no evidencia de que el producto funcione. Ver "Métricas de éxito del producto" más abajo para los outputs que sí miden eso.

## Pantalla principal (visión)

Ilustración de una persona caricaturesca y tranquila tomando té, sentada en el piso sobre un cojín, en un patio con piso de madera y una maceta con bonsái. Colores cálidos (no fríos), té color marrón, persona vestida de anaranjado y rojo, cabello rizado castaño. Aura de tranquilidad.

## Lo que la app haría sola, sin pedírselo

1. Generar checklists de mañana/tarde/semana según el nivel de energía medido en los tests.
2. Generar recordatorios de pendientes.
3. Calcular los KPI de satisfacción, felicidad y rutinas completadas.

## Nombre

**Peacefull and usefull** — sencillo, apacible, que se sienta simple.

## Novedades clave frente a la v1

- Checklist dividida en semanal vs. diaria, no solo por bloque del día.
- Rama de género en el test de energía: hombre → bioritmo/rutina/circadiano; mujer → lo mismo + ciclo menstrual.
- Metas a corto/mediano/largo plazo con contador de días dedicados y % de avance.
- KPI semanal combinando % de días dedicados a la actividad + % de avance de meta.
- Escala de 5 caritas (muy triste → muy alegre) en dos momentos: satisfacción tras el quehacer, felicidad tras la sesión de juego.
- Contador de tiempo de disfrute jugando, no solo tiempo de quehaceres.

## Los 4 tests que arman la energía de hoy

### 1. Test de rutinas

**Qué mide:** horarios reales de vida, para que los bloques de mañana/tarde/noche correspondan al día real, no a horas genéricas.

**Preguntas:**
- ¿Trabajas actualmente? ¿En qué horario (matutino, vespertino, mixto)?
- ¿A qué hora llegas a casa después del trabajo?
- ¿A qué hora te despiertas entre semana?

**Cómo se usa:** define a qué hora del reloj empieza cada bloque — si llegas a casa a las 19:00, el bloque "tarde" arranca ahí, no a una hora inventada.

*Ejemplo:* "Sí, turno matutino" · llega a casa 19:00 · despierta 6:30 → Mañana = 6:30–8:00 · Tarde = 19:00–21:00 · Noche = 21:00–23:00.

### 2. Test de bioritmo (gallo o búho)

**Qué mide:** el cronotipo — si el cuerpo rinde mejor temprano o tarde.

**Preguntas** (cada opción vale 0, 1 o 2 puntos):

| Pregunta | 2 pts | 1 pt | 0 pts |
|---|---|---|---|
| ¿A qué hora despiertas sin alarma? | Antes de las 7:00 | Entre 7:00 y 9:00 | Después de las 9:00 |
| ¿Cuándo tienes la mente más clara? | Mañana | Tarde | Noche |
| Después de comer, ¿cómo sigues? | Con energía | Estable | Con sueño |
| Tu momento ideal para jugar sería... | Mañana temprano | Media tarde | Ya entrada la noche |

**Resultado:** 6–8 pts = Alondra · 3–5 pts = Intermedia · 0–2 pts = Búho. Define la energía *base* de cada bloque del día.

*Ejemplo:* "Antes de las 7:00" (2) + "Tarde" (1) + "Con sueño" (0) + "Media tarde" (1) = 4 puntos → Intermedia → Mañana media · Tarde alta · Noche media.

### 3. Test de ciclo circadiano

**Qué mide:** qué tan descansada llegó hoy, más allá de su cronotipo de siempre.

**Preguntas:**

| Pregunta | Opciones |
|---|---|
| ¿Cuántas horas dormiste anoche? | Menos de 6h · Entre 6 y 8h · Más de 8h |
| ¿A qué hora sientes tu "bajón" de energía más fuerte? | Media mañana · Después de comer · En la noche |
| ¿Tu horario de sueño es parecido todos los días? | Muy variable · Algo variable · Constante |

**Cómo se usa:** si durmió menos de 6h o su horario fue "muy variable", se resta 1 nivel de energía a todos los bloques, sin importar el cronotipo.

*Ejemplo:* "Menos de 6h" · bajón "después de comer" · horario "algo variable" → se activa el modificador de sueño insuficiente → −1 a todos los bloques.

### 4. Test de ciclo menstrual (opcional y oculto por defecto)

**Qué mide:** fase hormonal del día, para quien decida activarlo.

**Cómo no se siente invasivo:** vive detrás de un interruptor "Activar ajuste por ciclo" en Configuración — nunca aparece en la pantalla principal ni se pregunta en el flujo diario. Se activa una sola vez, con lenguaje neutro, y solo entonces pide fecha y duración.

**Preguntas:** fecha de inicio del último periodo y duración promedio del ciclo.

**Fases y su energía típica** (estimación general orientativa, no es diagnóstico médico):

- **Menstrual** (días 1–5 aprox.): energía baja.
- **Folicular** (días 6–13 aprox.): energía en ascenso.
- **Ovulatoria** (alrededor del día 14): energía alta.
- **Lútea** (días 15–24 aprox.): energía en descenso gradual.
- **Lútea tardía / premenstrual** (días 25–28 aprox.): energía baja.

**Cómo se usa:** este modificador se suma al resultado del bioritmo, nunca lo reemplaza.

*Ejemplo (fecha ilustrativa, no es dato real):* último periodo 5 de julio de 2026 · duración promedio 28 días · hoy 20 de julio de 2026 → 15 días transcurridos → 15÷28 = 53.6% del ciclo → fase Ovulatoria → modificador +1.

## Priorización de MVP (qué se construye primero)

El sistema completo (4 tests + algoritmo + metas + KPI semanal) es demasiado para una primera versión. Se construye en 3 fases:

**Fase 1 — MVP núcleo (ya construido como prototipo v1)**
- Checklist guiada a partir de la foto del cuarto.
- Test de bioritmo (4 preguntas) → energía base por bloque genérico (mañana/tarde/noche).
- Plan del día autogenerado y recordatorios.
- Sin metas, sin KPI, sin ciclo circadiano ni menstrual todavía.

**Fase 2 — Enriquecimiento**
- Test de rutinas, para mapear los bloques a los horarios reales de trabajo y sueño.
- Metas a corto/mediano/largo plazo con contador de días y % de avance.
- KPI semanal (adherencia al checklist + avance de meta).
- Escala de 5 caritas: satisfacción tras el quehacer, felicidad tras jugar.

**Fase 3 — Modificadores opcionales de energía**
- Test de ciclo circadiano, para ajustar por qué tan descansada llegó hoy.
- Test de ciclo menstrual — oculto por defecto, activable con el interruptor de Configuración.

## Cómo los 4 tests se convierten en tiempos (el algoritmo)

Los cuatro tests se combinan en este orden para llegar a un número de minutos por tarea:

**1. Energía base por cronotipo.** El quiz de bioritmo (4 preguntas, 0–2 pts cada una) da un puntaje de 0 a 8:

| Puntaje | Cronotipo | Mañana | Tarde | Noche |
|---|---|---|---|---|
| 6–8 | Alondra | Alta | Media | Baja |
| 3–5 | Intermedio | Media | Alta | Media |
| 0–2 | Búho | Baja | Media | Alta |

**2. Modificador por ciclo circadiano.** Si durmió menos de 6 horas o su horario de sueño fue muy irregular esta semana, se resta 1 nivel de energía a todos los bloques del día (sin bajar de Baja), sin importar el cronotipo.

**3. Modificador por ciclo menstrual (si aplica).** Se ubica el día actual dentro del ciclo declarado y se identifica la fase; cada fase suma o resta un nivel a la energía resultante (acotado siempre entre Baja y Alta):

| Fase | % del ciclo | Modificador |
|---|---|---|
| Menstrual | 0–18% | −1 |
| Folicular | 18–46% | 0 |
| Ovulatoria | 46–56% | +1 |
| Lútea | 56–82% | 0 |
| Lútea tardía | 82–100% | −1 |

**4. Los horarios del test de rutinas** no cambian el nivel de energía, pero sí definen a qué hora del reloj corresponde cada bloque.

**5. De energía a minutos.** Cada tarea tiene un tiempo base fijo (ej. tender la cama = 5 min, skincare = 10 min, lavar trastes = 15 min). El tiempo mostrado en el plan del día es ese tiempo base multiplicado por un factor según la energía del bloque: Alta ×0.85, Media ×1.0, Baja ×1.25.

**6. Semana proyectada.** Las tareas diarias siempre se acomodan en algún bloque de hoy; las semanales se reparten entre los próximos 7 días, proyectando la energía de cada día (el cronotipo no cambia, pero la fase del ciclo sí avanza) y colocando las tareas más pesadas en los días con mayor energía proyectada.

## Métricas de éxito del producto (outputs, no solo inputs)

1. **Tasa de adherencia al checklist (%).** Tareas completadas / tareas generadas, por día y como promedio móvil de 7 días.
2. **Racha de días activos.** Días consecutivos con al menos 80% del checklist diario completado — proxy directo de hábito y retención.
3. **Precisión de estimación.** Tiempo real invertido (capturado al marcar la tarea como hecha) contra el tiempo que predijo el algoritmo, para recalibrar los factores de energía con datos reales.
4. **Índice de bienestar semanal.** Promedio de las caritas de satisfacción (post-quehacer) y felicidad (post-juego), más si hay correlación entre adherencia al checklist y disfrute del juego reportado esa misma semana.
5. **% de avance hacia la meta.** El indicador que justifica todo lo demás.

## Ejemplo ilustrativo — no son datos reales

De principio a fin: los 4 tests convertidos en el plan de un día.

- **Paso 1 · Rutinas:** turno matutino · llega a casa 19:00 · despierta 6:30 → Mañana 6:30–8:00 · Tarde 19:00–21:00 · Noche 21:00–23:00.
- **Paso 2 · Bioritmo:** puntaje 4 → Intermedia → energía base: Mañana Media · Tarde Alta · Noche Media.
- **Paso 3 · Ciclo circadiano:** durmió menos de 6h → −1 a todos los bloques → Mañana Baja · Tarde Media · Noche Baja.
- **Paso 4 · Ciclo menstrual:** fase Ovulatoria → +1 a todos los bloques → Mañana Media · Tarde Alta · Noche Media.

*(El mal descanso resta energía, pero la fase ovulatoria la devuelve — por eso el resultado final coincide con la base del bioritmo. Los modificadores pueden cancelarse entre sí, no solo sumarse en la misma dirección.)*

- **Paso 5 · Reparto de tareas y tiempos:** tareas de hoy: lavar trastes (15 min base), skincare (10 min base), tender la cama (5 min base). Se ordenan de mayor a menor y se asignan primero al bloque de mayor energía.

| Bloque | Horario real | Energía | Tarea asignada | Tiempo estimado |
|---|---|---|---|---|
| Mañana | 6:30–8:00 | Media | Rutina de skincare | 10 × 1.0 = 10 min |
| Tarde | 19:00–21:00 | Alta | Lavar los trastes | 15 × 0.85 ≈ 13 min |
| Noche | 21:00–23:00 | Media | Tender la cama | 5 × 1.0 = 5 min |
| **Total del día** | | | | **28 min** |

Con 28 minutos repartidos en el día real, queda libre el resto de la tarde-noche para la sesión de Hollow Knight — que es, al final, todo el punto de la app.

---
*Peacefull and usefull — documento de trabajo personal · v4, con ejemplos completos de cada test.*
