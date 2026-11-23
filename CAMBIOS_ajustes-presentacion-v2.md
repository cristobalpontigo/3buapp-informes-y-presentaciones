# Cambios: rama `ajustes-presentacion-v2`

Ajustes a la presentación v2 y su guion para que coincidan con el **informe v2.1**.

## 1. Contexto

- **Proyecto:** 3buapp. Es la presentación (v2) y el guion del informe del equipo.
- **Repo:** `cristobalpontigo/3buapp-informes-y-presentaciones`.
- **Rama:** `ajustes-presentacion-v2`. Va con un PR hacia `main`, sin merge.
- **Referencia:** informe v2.1 (`INFORME_3Buapp_v2 (2).docx`).
- **Cómo se hizo:** se reemplazaron solo los textos exactos. Los archivos de 6,6 MB no se reformatearon.

## 2. Proceso

1. **Tarea inicial:** corregir la cantidad de casos de prueba en la lámina 14.
2. **Revisión de las 15 láminas,** una por una, comparándolas con el informe v2.1.
3. **Ajuste del guion** para que diga lo mismo que las láminas.
4. **Guardado y commits:** 4 commits, uno por tema.

## 3. Cambios en la presentación

Los cambios van en `index.html` y en `presentacion v2/index.html`, que son iguales.

| Lámina | Antes | Ahora | Motivo |
|---|---|---|---|
| 2 | "Ya construido" | "Reportado por el equipo" | El informe lo presenta como algo que reporta el equipo. |
| 2 | "CI en verde" | "Integración continua" | Falta adjuntar la evidencia de CI. |
| 8 | ingresar · modificar · eliminar · **copiar** · cargar | ingresar · modificar · eliminar · cargar | Copiar (HU-19) quedó fuera del MVP. |
| 12 | "**siete** controles listos, **dos** en curso y uno planificado" | "**tres** controles listos, **seis** en curso o por probar y uno planificado" | Tabla 18 del informe v2.1. |
| 12 | Listos: A01, A02, A03, A04, A08, A09, A10 · En curso: A06, A07 · Planificado: A05 | Listos: **A02, A08, A10** · En curso o por probar: **A01, A03, A04, A06, A07, A09** · Planificado: **A05** | Tabla 18 del informe v2.1. |
| 14 | "+**14** casos críticos en el informe (CP-02 a CP-**15**)" | "+**23** casos críticos en el informe (CP-02 a CP-**24**)" | El informe v2.1 tiene 24 casos (CP-01 a CP-24). |

### Detalle de la lámina 12 (OWASP Top 10)

| Estado | Control | Nota |
|---|---|---|
| Implementado | A02 Criptografía | TLS · bcrypt (proveedor) |
| Implementado | A08 Integridad | CI + PR revisado |
| Implementado | A10 SSRF | por diseño: sin URL del usuario |
| En curso o por probar | A01 Control de acceso | RLS · falta prueba integral |
| En curso o por probar | A03 Inyección | RPC · Zod · en curso |
| En curso o por probar | A04 Diseño inseguro | cálculo por validar |
| En curso o por probar | A06 Componentes | lockfile · Dependabot |
| En curso o por probar | A07 Autenticación | MFA · faltan pruebas |
| En curso o por probar | A09 Registro | triggers · falta cobertura |
| Planificado | A05 Configuración | CSP y cabeceras |

## 4. Cambios en el guion

Los cambios van en `presentacion v2/GUION.md` y en `presentacion v2/guion.html`, con el mismo texto en los dos.

| Parte | Antes | Ahora |
|---|---|---|
| Lámina 2 | "Abajo, lo que ya está construido." | "Abajo, lo que el equipo reporta como construido." |
| Lámina 12 | "siete controles implementados, dos en curso (dependencias, y autenticación, donde falta la prueba con un usuario real) y uno planificado" | "tres controles listos (criptografía, integridad y SSRF), seis en curso o por probar (entre ellos control de acceso, autenticación y registro) y uno planificado" |
| Lámina 14 | "En el informe hay 14 casos críticos más." | "En el informe hay 23 casos críticos más." |
| Pregunta sobre MFA | "Está implementado (login, inscripción del factor y exigencia por rol, también comprobada en la base al aprobar). Falta la prueba con un usuario real" | "Está integrado según el equipo (login, desafío del factor y exigencia por rol, también comprobada en la base al aprobar). Falta probar la inscripción y los roles con un usuario real" |

## 5. Commits

| Commit | Mensaje |
|---|---|
| `9798c2d` | fix: lamina 2 indica lo construido como reportado por el equipo |
| `b91ee31` | fix: quita copiar de las acciones de la lamina 8 (HU-19 fuera del MVP) |
| `9c0a144` | fix: ajusta estados OWASP de la lamina 12 segun el informe v2.1 |
| `be1fbf4` | fix: corrige cantidad de casos de prueba en lamina 14 |

## 6. Lo que no se tocó

- **Lámina 3 ("Ciclo 2 de 5"):** está correcta, porque ya van en el ciclo 2.
- **Láminas 4, 6, 13 y 15:** quedan como están.
- **El informe del repo** (`presentacion v2/INFORME_3Buapp_v2.docx` / `.pdf`): sigue siendo la v2.0 y hay que subir la v2.1.

## 7. Pendientes menores (para que decida Cristóbal)

- Cambiar "mayor que 1" por "límite" en las láminas 2, 4, 7 y 14, y en el guion de las láminas 2 y 7.
- En la lámina 7, los decimales: hoy dice "8 decimales"; según el informe, los montos van con 4 y los factores con 8.
- En la lámina 7, agregar "por confirmar con nuam" a las columnas 34 a 37.
- En la lámina 3, la fecha del kanban.

## 8. Estado

- Los 4 commits están guardados en local, en la rama `ajustes-presentacion-v2`.
- **Falta el push y el PR:** la cuenta `Diegozapa23` solo tiene permiso de lectura en el repo. Hace falta que Cristóbal la agregue como colaboradora con permiso **Write** (Settings → Collaborators).
