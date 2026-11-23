# Guion de exposición · Segunda entrega (Unidad 2)
### 3Buapp · Sistema de gestión tributaria para corredoras de bolsa · Cliente: nuam
**Asignatura:** Proyecto Integrado (TIHV43) · INACAP Santiago Sur
**Docente:** Pedro Bustamante Toledo
**Duración:** 10 a 12 minutos (unos 2 minutos por integrante) + preguntas
**Base:** Informe de la segunda entrega, versión 2.0 (`INFORME_3Buapp_v2.pdf`). Toda cifra del guion sale del informe o del repositorio.

---

## Roles y tiempos

| # | Orador | Tema | Láminas | Tiempo |
|---|---|---|---|---|
| 1 | Cristóbal Pontigo | Del diagnóstico al diseño y cronograma Scrumban | 01 – 03 | 2:00 |
| 2 | M. Angel Smith L. | Arquitectura 4+1 | 04 – 06 | 2:15 |
| 3 | José Campos Rios | Interfaces y prototipos | 07 – 09 | 2:00 |
| 4 | Diego Andrés Zapata M. | Modelo de datos, RLS y OWASP | 10 – 12 | 2:15 |
| 5 | Alejandro Belvie | Plan de pruebas, metas y cierre | 13 – 15 | 2:00 |

Regla para todos: las láminas tienen poco texto a propósito. Cada una abre con una frase simple bajo el título (para todo público) y luego el visual técnico. Dilo en ese orden: primero la idea en palabras simples, después señala el diagrama. La lámina 07 es de mensaje (título grande a la izquierda, como en la primera presentación); el resto son técnicas.

---

## 1. Cristóbal Pontigo (01–03)

### 01 · Del diagnóstico al diseño técnico
> "Buenos días, profesor. Somos el equipo de 3Buapp. En la primera entrega diagnosticamos el problema; en esta presentamos el diseño técnico: cronograma, arquitectura 4+1, interfaces, base de datos, seguridad y pruebas. Además, parte de ese diseño ya está construido."

### 02 · Del problema al plano
> "En la primera entrega encontramos cinco problemas; están en las tarjetas de arriba. Debajo de cada uno, cómo lo resuelve 3Buapp: cada emisor tenía su formato, ahora hay un CSV estándar validado; nadie revisaba el cálculo, ahora la base calcula y frena una suma mayor que 1; los cambios no dejaban rastro, ahora todo queda registrado; el dato oficial se mezclaba, ahora cada corredor ve lo suyo, y una carga mala llegaba a todos, ahora un supervisor la aprueba antes. Abajo, lo que el equipo reporta como construido."

### 03 · Scrum marca el ritmo. Kanban, el flujo
> "Usamos Scrumban. A la izquierda, la parte Scrum: trabajamos en ciclos de dos semanas que siempre siguen la misma rueda: planificar, construir, mostrar al cliente y mejorar. Vamos en el ciclo 2 de 5. A la derecha, la parte Kanban: nuestro tablero real. Cada cuadrito es una tarea y su color es quién la tiene. Es nuestro tablero de GitHub tal como está hoy, con sus estados reales: 7 terminadas (PR integrado), 7 en revisión (PR abierto), 11 listas para empezar y 11 por hacer. Así cualquiera ve en qué está el proyecto sin leer código."

**Pase:** "Angel explica cómo está organizada la solución."

---

## 2. M. Angel Smith L. (04–06)

### 04 · Cinco preguntas, un mismo sistema
> "Para describir la arquitectura usamos el modelo 4+1 de Kruchten, que la explica con cinco preguntas. Al centro, la más importante: ¿para qué existe? Calcular sin errores, que ninguna carga entre sin revisión, saber quién cambió qué y que un corredor no vea a otro. Alrededor, cuatro miradas: qué partes tiene, en qué orden pasan las cosas, cómo se organiza el código y dónde funciona. Cada una tiene su diagrama UML en el informe."

### 05 · Subir no es grabar
> "Esta es la vista de procesos, contada con las personas. El operador sube el archivo y ve al tiro qué filas tienen errores. 3Buapp guarda la carga, pero como pendiente: todavía no toca ninguna calificación. Luego un supervisor, que no puede ser quien la subió y que entró con doble factor, la revisa. Si aprueba, recién ahí se aplican las filas y queda todo en la auditoría. Si rechaza, debe dar un motivo y no cambia nada."

### 06 · Dónde vive cada pieza
> "La solución vive en tres lugares. En tu equipo, el navegador solo muestra pantallas. En internet, Vercel revisa que tengas sesión y doble factor. En la nube, Supabase guarda los datos, las contraseñas cifradas y los archivos, y ahí se calcula y se aplican los permisos. Entre cada lugar, la conexión va cifrada. Abajo, lo que viene después del MVP: escritorio, lectura de PDF y facturación."

**Pase:** "José muestra cómo se ve esto para el operador."

---

## 3. José Campos Rios (07–09)

### 07 · Diseñada para no equivocarse
> "Esta es la pantalla real del prototipo para ingresar una calificación. (1) Va por pasos: primero los datos básicos, después los montos. (2) Este medidor muestra la suma de factores: verde si da 1, rojo y bloqueado si la supera. (3) Las cifras van alineadas y con 8 decimales, para compararlas fácil. (4) Las columnas 34 a 37 son casos especiales y se ingresan directo."

### 08 · Todo el período en una grilla
> "Este es el prototipo del mantenedor. (1) Filtros por mercado, origen y período. (2) Los 30 factores a 8 decimales. (3) El origen de cada calificación, bolsa o corredor. (4) Las acciones. Reemplaza la planilla: las 763 calificaciones del período, 200 por página."

### 09 · Cientos de filas, cero sorpresas
> "Esta es la carga masiva. (1) Es un asistente de tres pasos: elegir el archivo, validarlo y enviarlo a aprobación. (2) Este archivo trae 214 filas: 209 válidas y 5 con error. (3) Cada error dice la fila, el campo y la causa exacta. (4) Al enviar, la carga queda pendiente, no se graba: va a la bandeja del supervisor, que debe ser otra persona y entrar con doble factor."

**Pase:** "Diego explica cómo se guardan y protegen estos datos."

---

## 4. Diego Andrés Zapata M. (10–12)

### 10 · Diez tablas, tres garantías
> "La base tiene diez tablas, agrupadas por lo que guardan: quién es cada usuario, el dato tributario con sus 30 factores, cómo entró cada carga, el historial y las reglas configurables. Lo importante son tres garantías: los factores se guardan exactos, con 8 decimales y sin redondeo; la llave de la calificación impide duplicados, y la auditoría guarda el antes y el después de cada cambio, sin que nadie pueda borrarla."

### 11 · Cada corredor ve solo lo suyo
> "Las corredoras compiten entre sí. A la izquierda está toda la tabla: calificaciones de la bolsa, de Andes y de Pacífico. Cuando un analista de Andes consulta, la base filtra y le devuelve solo lo de la bolsa y lo suyo; lo mismo para Pacífico. Abajo está la regla real de nuestra migración. El filtro lo hace la base de datos, no la pantalla, así que aunque alguien manipule la aplicación no puede ver datos de otro."

### 12 · Los diez riesgos, revisados
> "Revisamos los diez riesgos de OWASP y los ordenamos por estado: tres controles listos (criptografía, integridad y SSRF), seis en curso o por probar (entre ellos control de acceso, autenticación y registro) y uno planificado (cabeceras de seguridad). Abajo, una idea simple: cada dato se valida tres veces, en el navegador, en el servidor y en la base. Las contraseñas se guardan con hash bcrypt."

**Pase:** "Alejandro cierra con cómo lo vamos a probar."

---

## 5. Alejandro Belvie (13–15)

### 13 · Nada se integra sin pasar las pruebas
> "La estrategia es una pirámide: muchas pruebas unitarias con Vitest, integración sobre las funciones SQL con PGlite y algunas E2E con Playwright, más pruebas de seguridad, estrés y aceptación. Siendo honestos con el estado: hoy corren 9 pruebas en CI y probamos la aprobación de cargas con dos corredores. El 80 % de cobertura del cálculo y las 5.000 filas en 30 segundos son metas del plan, no resultados todavía."

### 14 · Lo que gana la corredora
> "Arriba, lo que gana la corredora: cero sumas inválidas grabadas, 30 segundos para validar 5.000 filas, el 100 % de los cambios auditados, ninguna carga sin segunda revisión y 99,5 % de disponibilidad. Son metas, a confirmar con el cliente. Abajo, cómo lo probamos: el caso del documento de nuam. 192.770.580 dividido por 368.745.318 debe dar exactamente 0,52277431, igual en el navegador y en la base. En el informe hay 23 casos críticos más."

### 15 · Del plano a la construcción
> "Cerramos con lo que viene. Una sola lógica de negocio y tres formas de usarla: primero la aplicación web, que es el MVP para enero; después la aplicación de escritorio, para que las operaciones críticas se hagan solo en equipos autorizados; y en una tercera etapa, si nuam lo valida, la facturación electrónica conectada al SII mediante un proveedor. Muchas gracias; quedamos atentos a sus preguntas. Y si quieren probarlo, este es el mismo QR de la primera presentación: lleva a la demo."

---

## Preguntas probables

**¿Por qué Scrumban y no Scrum?** El cliente aún debe aclarar puntos del requerimiento (rango 8–16 u 8–19, llave de la calificación). Los ciclos dan revisión con el cliente; el tablero y el límite de trabajo en curso absorben cambios sin romper el ritmo.

**¿Cómo garantizan que un corredor no vea a otro?** RLS en PostgreSQL: cada consulta usa el JWT del usuario y la política compara `corredor_id` con `mi_corredor()`. No depende de un `WHERE` en el código ni de la interfaz. Caso de prueba CP-10.

**¿Por qué el cálculo está en la base y también en el navegador?** El navegador solo previsualiza (decimal.js) para responder al instante; el valor que se graba lo calcula `calcular_factores()`. Ambos se validan con el mismo caso del HDU.

**¿Qué pasa si se elimina una calificación?** Se borra de la tabla, pero su contenido completo queda en `auditoria.antes` con usuario y fecha. En la Unidad 1 se propuso eliminación lógica; el cambio se valida con nuam en el ciclo 2.

**¿Vitest en vez de Jest?** Vitest funciona nativamente con TypeScript y ESM, sin configuración de Babel, y es rápido en CI.

**¿El doble factor ya funciona?** Está integrado según el equipo (login, desafío del factor y exigencia por rol, también comprobada en la base al aprobar). Falta probar la inscripción y los roles con un usuario real, que depende de los datos de prueba (DI-1).
