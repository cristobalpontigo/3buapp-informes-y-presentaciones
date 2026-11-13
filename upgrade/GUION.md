# Guion para presentar en equipo

3Buapp · Propuesta para nuam.

Guion para las 17 láminas de la propuesta de 3Buapp, con la facturación electrónica como etapa 3. El reparto es sugerido y organiza la exposición; no cambia las tareas de desarrollo del equipo. Reservar unos dos minutos por integrante, más preguntas. El tiempo real debe comprobarse ensayando en voz alta.

Las indicaciones en cursiva son acciones; no se leen al público.

| # | Orador | Tema | Láminas |
|---|---|---|---|
| 1 | Cristóbal Pontigo | Abrir la propuesta y explicar el contexto | 01–04 |
| 2 | Alejandro Belvie | Explicar el problema y el cálculo con el ejemplo | 05–07 |
| 3 | José Campos Rios | Presentar la solución y conducir la demostración | 08–10 |
| 4 | M. Angel Smith L. | Explicar qué se propone y quién puede hacer cada operación | 11–13 |
| 5 | Diego Andrés Zapata Machuca | Presentar el plan, los indicadores y el próximo paso | 14–17 |

## 1. Cristóbal Pontigo · láminas 01–04 · unos 2 minutos

Abrir la propuesta y explicar el contexto.

### 01 · Del certificado al registro tributario

*Mirar al público al abrir; evitar leer el subtítulo completo.*

Hola a todos. Somos el equipo de 3Buapp. Nuestra propuesta busca ordenar el trabajo tributario de las corredoras: recibir información, calcular los factores, revisar los datos y conservar su historial. Hoy vamos a explicar el problema, cómo lo abordaríamos y qué debemos confirmar con nuam antes de avanzar.

### 02 · El equipo detrás de 3Buapp

*Presentar los cinco nombres, sin leer los usuarios de GitHub.*

Somos Angel, Alejandro, José, Diego y Cristóbal. Distribuimos el trabajo entre plataforma y seguridad, reglas de negocio, pantallas, pruebas y cargas. Cada parte aporta al mismo objetivo: que el dato pueda revisarse desde que llega hasta que se utiliza. Esta lámina muestra las tareas de desarrollo del equipo.

### 03 · Tres mercados y un proceso tributario

*Señalar emisor, corredora y cliente.*

nuam integra las bolsas de Chile, Colombia y Perú. Las empresas entregan información sobre sus dividendos y las corredoras preparan el desglose tributario que necesitan sus clientes. Ese desglose se llama calificación tributaria. Nuestro foco está en ayudar a la corredora a recibir, revisar y organizar esos datos.

### 04 · Los valores que se gestionan

*Señalar 763, luego 30 y finalmente 22.890. Esperar a que se enciendan los puntos coral.*

El informe toma como referencia 763 calificaciones de acciones del ejercicio 2025, con 30 factores cada una. Son 22.890 valores por gestionar. Cada punto representa una calificación. Si fallara una de cada 17, serían 44 con error de digitación: son los puntos coral, y la proporción es ilustrativa. Ese volumen permite entender por qué copiar y revisar todo a mano puede tomar tiempo y aumentar el riesgo de errores.

**Pase →** Alejandro explicará dónde aparece el riesgo y cómo se revisa el cálculo.

## 2. Alejandro Belvie · láminas 05–07 · unos 2 minutos

Explicar el problema y el cálculo con el ejemplo.

### 05 · Un error se multiplica

*Seguir los tres pasos: certificado, planilla con 0,66 y suma 1,06.*

En este ejemplo, el valor correcto era 0,60, pero se ingresó 0,66. La suma termina en 1,06 y supera el límite del ejemplo. Si ese dato se utiliza después, el error llega a todos los clientes que recibieron ese dividendo. Proponemos detectarlo antes de guardar. Los números de esta lámina son ilustrativos; no representan un incidente confirmado del cliente.

### 06 · Hoy y con 3Buapp

*Recorrer las cinco filas; detenerse en validación e historial.*

El diagnóstico plantea dificultades al copiar datos, recibir distintos formatos y reconstruir los cambios. Por eso proponemos una carga con revisión previa, reglas comunes y un historial. También separamos los datos oficiales de los ajustes de cada corredora. Estas conclusiones se basan en la documentación; aún deben contrastarse con los usuarios. En facturación todavía no afirmamos que exista doble digitación.

### 07 · Ocho decimales

*Señalar la barra del certificado y luego el formulario, sin leer los ocho decimales.*

El certificado trae un monto por columna, y el factor es la porción que le toca a cada una. En el ejemplo, la columna 8 trae 600.000 de un millón: el factor F08 es 0,6, expresado con ocho decimales. Los factores F08 a F33 se calculan; los últimos cuatro se ingresan directamente. La misma regla debe aplicarse en cada forma de ingreso. El rango que se suma sigue pendiente de confirmación con nuam: F08 a F16 o F08 a F19.

**Pase →** José mostrará cómo sería trabajar con esta información en 3Buapp.

## 3. José Campos Rios · láminas 08–10 · unos 2 minutos

Presentar la solución y conducir la demostración.

### 08 · Un solo lugar para revisar y confirmar

*Señalar las tres etiquetas y aclarar que son etapas.*

3Buapp reúne carga, cálculo y revisión en un mismo lugar. La primera etapa es la web; después viene el escritorio. Y en una tercera etapa suma un facturador conectado al SII, para emitir facturas y notas desde el mismo dato validado. Esta mejora queda fuera del MVP y requiere confirmar los datos comerciales que se facturan.

### 09 · Acompañar al dato paso a paso

*Pulsar Cargar, Revisar, Aprobar y Auditar, en ese orden. Dejar una pausa breve en cada paso.*

Primero, Cargar: vemos el archivo antes de incorporarlo. Luego, Revisar: 3Buapp calcula cada fila; la tercera suma 1,06 y queda rechazada, igual que el error de la lámina 5, mientras las otras dos siguen. En Aprobar, un supervisor decide si la carga puede continuar. Finalmente, Auditar conserva quién realizó la operación y qué cambió. Es una simulación con datos de ejemplo. La lectura de PDF también requiere que una persona revise lo extraído.

### 10 · El dato oficial conserva su origen

*Señalar la fuente oficial y luego el ajuste local.*

El dato de la bolsa se conserva en solo lectura. Si la corredora necesita corregirlo, guarda una versión propia, separada y con historial. En la consulta se utiliza esa versión local cuando existe. Así se puede trabajar con el ajuste y volver al dato original para entender de dónde salió cada valor.

**Pase →** Angel explicará el alcance, los accesos y la seguridad.

## 4. M. Angel Smith L. · láminas 11–13 · unos 2 minutos

Explicar qué se propone y quién puede hacer cada operación.

### 11 · Primero lo indispensable

*Señalar el recuadro MVP con sus 12 fichas y luego los otros dos grupos.*

El informe actualizado propone 20 historias, 30 requisitos funcionales y 15 de calidad y seguridad. La distribución es de 12 historias esenciales, cuatro importantes y cuatro deseables. La nueva historia de facturación está en las deseables y corresponde a la etapa 3. Estos totales incluyen la mejora futura; no significan que todo se construya en el MVP.

### 12 · Quién hace qué y desde dónde

*Señalar web, escritorio y base; después la casilla de DTE.*

La propuesta separa el trabajo según su riesgo. La web permite consultar, previsualizar e ingresar registros individuales. El escritorio concentra las operaciones de mayor impacto. Firmar y enviar documentos al SII también es crítico: va por el escritorio, con el certificado digital custodiado. Se propone una API de un proveedor compatible con esa forma de firma. Desde la web solo se consultan los estados y PDF de los DTE.

### 13 · Cada cambio deja una huella

*Recorrer la línea de tiempo: 0,66 ingresado, 0,60 corregido, carga aprobada. Luego las cuatro insignias.*

El historial permite saber qué cambió, cuándo y quién lo hizo: aquí se ve el 0,66 de la lámina 5, su corrección y la aprobación. Los permisos dependen del rol y cada corredora ve solo sus datos. Para facturación se agrega la custodia del certificado y el control de equipos autorizados. Es una decisión de seguridad de 3Buapp. Además, usar un proveedor no reemplaza la habilitación de la corredora ante el SII.

**Pase →** Diego cerrará con el plan de trabajo y las definiciones que necesitamos.

## 5. Diego Andrés Zapata Machuca · láminas 14–17 · unos 2 minutos

Presentar el plan, los indicadores y el próximo paso.

### 14 · Avances cada dos semanas

*Recorrer los cinco ciclos y señalar la línea inferior.*

El plan inicial propone cinco ciclos de dos semanas, con una revisión junto a nuam en cada uno. Primero se trabaja en accesos y registros; después, en cálculos, cargas, lectura asistida de PDF y reportes, según prioridad. Después del MVP vienen el escritorio y, en una tercera etapa, la facturación electrónica. Estas mejoras no están incluidas en las diez semanas.

### 15 · Lo que gana el equipo

*Señalar los cinco indicadores sin prometer resultados ya obtenidos.*

Mantuvimos cinco indicadores: errores de suma, tiempo de carga, trazabilidad, lectura de PDF y disponibilidad. Son metas para las pruebas, no resultados ya demostrados. Por ejemplo, queremos evitar registros con suma mayor a uno y dejar cada cambio en la bitácora. Para el SII se deberá medir el resultado de los DTE; no prometemos cero rechazos.

### 16 · Cuatro definiciones para partir

*Señalar las cuatro filas; dar énfasis a la nueva pregunta.*

Necesitamos confirmar el rango de suma, los 30 factores y cómo se identifica cada registro. La cuarta definición es la facturación: qué emiten hoy, con qué sistema y quién tiene el certificado digital. También debemos acordar si los certificados de calificación y las declaraciones juradas saldrán desde 3Buapp. Son procesos distintos de las facturas.

### 17 · Próximo paso

*Mirar al público; mantener la lámina durante las preguntas.*

El siguiente paso es revisar estas definiciones con nuam y trabajar con casos representativos. La idea es que cada registro conserve su origen, sus cálculos y sus cambios. Con esa base podemos avanzar por etapas y evaluar después la facturación electrónica. Muchas gracias; quedamos atentos a sus preguntas.

## Respuestas para ensayar

Apoyo fuera del tiempo principal. Los cinco anexos permiten ampliar la explicación.

**¿La facturación está incluida en el MVP?**
No. Es la etapa 3, posterior a la web y al escritorio. Tiene una historia nueva, HU-20, con prioridad Could y sin plazo comprometido en las diez semanas iniciales.

**¿El proveedor evita toda certificación?**
No. Se propone un proveedor de mercado para facilitar la integración. Debemos verificar la habilitación de la corredora y de los DTE que emitirá. El SII certifica esos documentos, no el software como producto.

**¿Por qué se firma desde escritorio?**
Es la política de seguridad propuesta por 3Buapp para las operaciones críticas. No es una exigencia literal del SII. El proveedor debe admitir firma desde equipos autorizados; esa compatibilidad se valida antes de elegirlo.

**¿Los factores de dividendos generan una factura?**
Por sí solos, no. La factura de comisiones o servicios necesita datos comerciales y tributarios adicionales. Hay que confirmar esos campos y su relación con la operación antes de implementarla.

**¿Qué significa que un DTE esté enviado?**
Solo que se remitió. Hay que consultar la respuesta y distinguir el estado del envío del resultado de cada documento: aceptado, aceptado con reparos o rechazado. Un envío pendiente no es una aceptación.

**¿Ya confirmaron una doble digitación al facturar?**
No. La propuesta busca reutilizar datos, pero debemos conocer el proceso real de la corredora. No lo presentamos como un problema demostrado.
