# Guion de exposición · Unidad 1

Pitch de 3Buapp para nuam. Cinco oradores, ≈2 minutos cada uno (≈10 minutos). El orden sigue la presentación.

| # | Orador | Tema | Láminas |
|---|---|---|---|
| 1 | Cristóbal Pontigo | Apertura y contexto | 01–04 |
| 2 | Alejandro Belvie | El problema y la regla | 05–07 |
| 3 | José Campos Rios | La solución | 08–10 |
| 4 | M. Angel Smith L. | Alcance, tecnología y seguridad | 11–13 |
| 5 | Diego Andrés Zapata Machuca | Implementación, beneficios y cierre | 14–17 |

## 1. Cristóbal Pontigo · Apertura y contexto (láminas 01–04)

- **01 · Portada.** Saludo. Somos 3Buapp y venimos a mostrarles cómo dejar de digitar a mano las calificaciones tributarias.
- **02 · Equipo.** Presenta a los cinco, una frase por rol, y anuncia que cada uno muestra una parte de la solución.
- **03 · Su contexto.** nuam integra las bolsas de Santiago, Colombia y Lima. El emisor entrega el certificado, la corredora registra y valida, el cliente recibe la información.
- **04 · El desafío.** Solo en acciones 2025: 763 calificaciones × 30 factores = 22.890 valores que hoy se digitan casi a mano. Los puntos coral se encienden solos: si fallara 1 de cada 17, serían 44 calificaciones con error de digitación. La proporción es ilustrativa.

**Pase →** Alejandro muestra lo que cuesta un solo error.

## 2. Alejandro Belvie · El problema y la regla (láminas 05–07)

- **05 · El costo del error.** F08 debía ser 0,60 y se digitó 0,66: la suma llega a 1,06. Ese error viaja a los certificados de todos los clientes del dividendo y, en un sector regulado, puede terminar en sanciones. 3Buapp lo detiene antes de grabar.
- **06 · Hoy vs. con 3Buapp.** Recorre las 5 debilidades del proceso actual y lo que cambia con 3Buapp en cada una. Cierra con la causa raíz: falta una fuente única que estandarice, valide y registre.
- **07 · La regla, automatizada.** El certificado trae un monto por columna; el factor es la porción que le toca a cada una (barra a la izquierda, formulario de 3Buapp a la derecha). Factor = monto de la columna ÷ suma de montos, con 8 decimales. F08–F33 se calculan solos; F34–F37 se ingresan. El rango de la suma lo confirmamos con ustedes.

**Pase →** José muestra cómo se ve esto en 3Buapp.

## 3. José Campos Rios · La solución (láminas 08–10)

- **08 · La solución.** Un solo lugar para cargar, calcular, validar y conservar el historial de cada calificación. Viene como aplicación web y como app de escritorio para equipos autorizados.
- **09 · Cómo funciona.** Avanza con la flecha: cada pulsación muestra la siguiente etapa, en menos de 40 s en total: cargar (previsualizar el CSV; PDF asistido), revisar (DEMO-C suma 1,06 y queda rechazada, el mismo error de la lámina 05; las otras dos filas siguen), aprobar (supervisor en cargas masivas) y auditar.
- **10 · Dato oficial y local.** El dato de la bolsa queda en solo lectura. Los ajustes de la corredora se guardan aparte, con auditoría, y prevalecen en la vista consolidada.

**Pase →** Angel explica qué entregamos primero y cómo está construido.

## 4. M. Angel Smith L. · Alcance, tecnología y seguridad (láminas 11–13)

- **11 · Alcance.** La primera entrega cubre lo esencial: accesos, cálculo, carga CSV y auditoría (12 de 20 historias, las fichas enmarcadas como MVP). Aprobación, PDF y accionistas vienen después; lo deseable lo priorizan ustedes.
- **12 · Quién hace qué, y desde dónde.** Arriba la web: desde cualquier equipo se consulta, se previsualiza un CSV y se ingresa un registro. Abajo el escritorio: solo en equipos autorizados se hacen cargas masivas, aprobaciones y cambios o eliminaciones. Ambos usan una sola base, donde viven las reglas y los permisos por canal. Es mínimo privilegio; el escritorio llega en la segunda etapa.
- **13 · Seguridad.** Cada cambio guarda valor anterior, nuevo, quién y cuándo. Roles, datos aislados por corredora, MFA y bitácora que no se puede borrar. Señala la línea de tiempo: se ingresó 0,66, se corrigió a 0,60 y el supervisor aprobó. Cierra el caso de Alejandro.

**Pase →** Diego explica cómo lo implementamos y a qué nos comprometemos.

## 5. Diego Andrés Zapata Machuca · Implementación, beneficios y cierre (láminas 14–17)

- **14 · Implementación.** 5 ciclos de 2 semanas (10 semanas). Al final de cada ciclo, su equipo revisa avances reales.
- **15 · Beneficios.** Cinco indicadores medibles: cero errores de suma, las 763 calificaciones del período cargadas en ≤30 s, 100 % de trazabilidad, ≥95 % de campos leídos desde PDF y ≥99,5 % de disponibilidad.
- **16 · Lo que necesitamos.** Tres definiciones de su equipo: rango de la suma, los 30 factores y la llave del registro.
- **17 · Próximo paso.** De la digitación manual a un proceso trazable. Proponemos una sesión con su equipo para validar reglas y casos reales. Gracias; quedamos atentos a sus preguntas.
- **$ · Valores (solo de palabra).** El precio no va en pantalla. Si lo preguntan: se cotiza según los módulos de la primera entrega y la cantidad de corredoras; lo presentamos en la sesión de validación. [Definan el rango que dirán.]

**Pase →** Preguntas. El detalle técnico está en el botón «Anexos».
