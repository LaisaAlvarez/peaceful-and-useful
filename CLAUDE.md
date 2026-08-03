# CLAUDE.md

<!-- El cerebro del proyecto. Claude lee este archivo automáticamente al abrir la carpeta. -->

## Qué es este proyecto

App de organización personal para Laisa: checklist manual de quehaceres (7 tareas por defecto + lo que ella agregue a mano), cruzada con su nivel de energía (bioritmo, rutinas, ciclo circadiano y opcionalmente ciclo menstrual) para estimar tiempos por tarea, y le deja tiempo libre para su hobby — Hollow Knight. Ver spec completo en [docs/spec.md](docs/spec.md) — ojo, el spec original describe una foto del cuarto como punto de partida de la checklist; se decidió NO construir eso (ver Changelog 2026-08-03).

## Con qué lo hacemos

- HTML/CSS/JS en un solo archivo (`index.html`), sin build ni dependencias externas.
- Soporta modo claro/oscuro vía `prefers-color-scheme` y `data-theme`.
- Vive en `C:\Radec-Claude\proyectos\Sesión1\peaceful-and-useful`.

## Stack y versiones

- **Stack real:** HTML + CSS + JavaScript vanilla, todo en un único archivo (`index.html`, ~1139 líneas). Sin frameworks, sin build, sin `package.json` ni dependencias de ningún tipo.
- **Python / pandas / Node:** no se usan. Verificado en esta máquina (2026-07-29): no hay intérprete de Python instalado (`python`/`python3` solo abren el instalador de Microsoft Store), no hay Node ni `pip`. No hay ningún paso de procesamiento fuera del navegador.
- **Datos de entrada:** no hay archivos externos — `datos/` está vacío. La única "semilla" es el arreglo `DEFAULT_TASKS` (7 tareas) hardcodeado dentro del `<script>` de `index.html`. Todo lo demás (checklist editada, resultados de tests, meta, historial de 7 días) lo genera la usuaria en vivo y se guarda en `localStorage` bajo las claves `pu_state` (estado del día) y `pu_history` (historial rodante de 7 días) — no hay backend ni base de datos.
- **Corte de fecha para los cálculos:** no aplica. No hay un snapshot con fecha fija — el plan del día y las métricas se recalculan sobre lo que haya en `localStorage` en el momento de abrir la página, comparado contra la fecha de hoy (`todayKey()`, calculada con `toISOString()` en UTC — nota: cerca de medianoche esto puede desfasarse un día respecto a la hora local de México; no se ha corregido).
- **Cómo se corre:** abrir `index.html` directamente en el navegador (doble clic o arrastrarlo a una pestaña). No requiere servidor.
- **Cómo se verifica:**
  1. Abrir `index.html` y confirmar que cargan todas las secciones (Escanea tu cuarto, Energía, Plan del día, Recordatorios, Meta, Bienestar y KPI).
  2. En "Escanea tu cuarto", marcar una tarea como hecha y confirmar que desaparece del bloque correspondiente en "Plan del día".
  3. Completar el test de energía (incluye horarios de rutina + sueño) y confirmar que el Plan del día muestra horarios reales y minutos ajustados por energía (×0.85 alta / ×1.0 media / ×1.25 baja).
  4. En "Tu meta", marcar el día como cumplido y confirmar que la barra de progreso y el KPI semanal se actualizan.
  5. Recargar la página y confirmar que todo lo anterior sigue ahí (persistencia en `localStorage`).

## Cómo trabajar aquí

- Seguir la priorización de MVP del spec: Fase 1 (checklist + bioritmo, ya construida como prototipo v1) → Fase 2 (rutinas, metas, KPI semanal, caritas) → Fase 3 (circadiano, ciclo menstrual).
- No adelantar features de una fase posterior sin terminar la anterior.
- Los datos reales (fotos, CSV, exports) van en `datos/`; todo lo que Claude genere va en `outputs/`, nunca sobre-escribir `index.html` directo sin confirmar.

## Comandos clave

- Se corre abriendo `index.html` directo en el navegador (no requiere servidor ni build).

## Qué evitar

- No moverse en la computadora de Laisa sin permiso — avisar siempre qué se hace y dónde.
- No implementar el test de ciclo menstrual visible por defecto: debe vivir oculto tras un interruptor en Configuración (ver spec).
- No mezclar este proyecto con `mi-proyecto/` (su iniciativa de KPIs de auditoría en RADEC) — son cosas separadas.

## Changelog

### 2026-07-20 — Fase 1 (MVP núcleo)
- Primera versión funcional: hero ilustrado, checklist guiada por foto ("Escanea tu cuarto"), test de bioritmo de 4 preguntas, Plan del día autogenerado por bloques (mañana/tarde/noche) y Recordatorios vía Notification API. Persistencia en `localStorage` (`pu_state`).

### 2026-07-21 — Fase 2 (enriquecimiento)
- Test de rutinas (hora de despertar + hora de llegada a casa): los bloques mañana/tarde/noche ahora usan horarios reales en vez de genéricos.
- Test de ciclo circadiano (horas dormidas + regularidad del sueño) como modificador de energía.
- Los minutos del Plan del día ahora se ajustan por la energía del bloque (×0.85 alta / ×1.0 media / ×1.25 baja).
- Tarjeta de Meta: texto + días objetivo, botón "marcar hoy como cumplido", barra de progreso.
- Tarjeta de Bienestar y KPI semanal: escalas de 5 caritas (satisfacción tras el quehacer, felicidad tras jugar), historial rodante de 7 días (`pu_history`), adherencia, racha de días activos, KPI semanal e índice de bienestar.

### 2026-07-29 — Documentación
- Se agregaron las secciones "Stack y versiones" y este "Changelog" — verificando el stack real de la máquina (sin Python/Node instalados) en vez de asumirlo.

### 2026-07-31 — Navegación por pantallas y hueco de spec cerrado
- Se reemplazó el scroll único por navegación real con barra inferior de 5 pestañas: Checklist, Energía, Tu plan, KPI, Ajustes.
- Nueva pantalla "Tu plan" (resultados): al calcular la energía ahora se navega ahí automáticamente — cronotipo y bloques de energía se presentan como un resultado propio, no como un párrafo más en el scroll.
- Nueva pantalla "Ajustes" (Configuración): el ajuste por ciclo hormonal se movió aquí, detrás de un interruptor "Activar ajuste por ciclo" — cierra el hueco del spec ("nunca en Home") que antes vivía colapsado en el test de energía.
- "Fase 2" (Meta + Bienestar/KPI) se agrupó en la pantalla "KPI" con tarjetas de estadística más grandes, estilo tablero.
- Bug corregido: el interruptor visual (`.toggle`) tapaba al checkbox real y no respondía a clics — afectaba también los 3 interruptores de Recordatorios, ya existentes antes de este cambio. Se corrigió con `pointer-events:none` en `.track`/`.thumb`.
- Pendiente del spec, todavía sin construir: calibración de precisión ("Calibrando… X/15", spec Parte 9) y validación de brillo/nitidez de la foto del cuarto vía Canvas API (spec Parte 10).

### 2026-08-03 — Ilustración del Home
- El dibujo SVG hecho a mano (persona + bonsái) se reemplazó por `outputs/hero.webp` — una imagen generada por Laisa con IA a partir de un prompt basado en referencias de estilo suyas, no arte de stock de terceros.
- Motivo: 3 intentos de mejorar el SVG a mano (más "realismo", cabello, bonsái) no dieron buen resultado — dibujar curvas orgánicas a ciegas, sin ver mientras se dibuja, no es viable con este método.
- Se quitó la animación de vapor (`.steam`, `@keyframes rise`) por quedar sin uso al ya no existir el SVG que la llevaba.

### 2026-08-03 (tarde) — Home real + checklist plano
- Home pasó de ser un encabezado siempre visible a una pantalla propia: al abrir la app solo se ve la intro + "Comenzar"; la barra de pestañas y el resto de la app están ocultos hasta hacer clic. Gotcha técnico: el atributo `hidden` no le ganaba a las reglas propias de `.tabbar`/`main` (`display:flex`/`display:block`) — hubo que forzarlo con `#tabbar[hidden], #mainApp[hidden]{ display:none !important; }`.
- Checklist dejó de agrupar tareas por zona (Dormitorio/Cuidado personal/Cocina/Otros) — ahora es una lista plana. Verificado con prueba real: los pendientes agregados a mano (zona "Otros") ya se repartían por energía en "Tu plan" desde antes (esa lógica nunca miró la zona), el agrupamiento visual solo daba la impresión falsa de que quedaban aislados.

### 2026-08-03 (noche) — Botón único, borrar tareas, horario laboral, tareas con hora fija
- El botón "Comenzar" se oculta después de usarlo (ya no se queda ahí una vez dentro de la app).
- Cada tarea del checklist tiene botón de eliminar (✕) — antes solo se podían agregar o marcar como hechas, nunca borrar.
- Nuevo campo "Te vas a trabajar" en el test de energía. El bloque Mañana ahora es literalmente despiertas→te vas, en vez de un +90min genérico que no reflejaba jornadas laborales reales (ej. despertar 6:00 y salir 6:30 — antes igual mostraba hasta las 7:30). Verificado con ambos casos (coincidente y no coincidente con el +90min viejo) para confirmar que de verdad se reemplazó la fórmula, no que coincidía por casualidad.
- Las tareas nuevas pueden llevar una hora fija opcional (campo de hora junto a "Agregar"). Si la tienes, la tarea se ancla al bloque real más cercano a esa hora (sin multiplicar su tiempo por el factor de energía, porque es un compromiso de horario, no algo elástico) y se muestra con una etiqueta de hora. Lo que no tiene hora fija sigue repartiéndose por energía exactamente igual que antes.
- **Decisión de alcance:** se eliminó por completo la subida de foto del cuarto (input, vista previa, y el texto "Escanea tu cuarto"). Laisa decidió que el flujo sea más manual: checklist de 7 tareas por defecto + botón "Agregar otro pendiente" ya cubre el caso de uso sin necesitar analizar la foto por contenido. La validación de calidad de foto (spec Parte 10) queda descartada junto con esto, no solo pendiente.
- El resumen de "Qué es este proyecto" arriba se actualizó para reflejar esto — el `docs/spec.md` original (ya calificado con 100/100) se deja intacto como registro histórico, no se edita.
