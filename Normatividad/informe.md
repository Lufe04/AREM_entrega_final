# Informe Técnico de Cumplimiento Normativo

## Taller 6 — Checklist de Cumplimiento Normativo

---

## Integrantes del equipo
- Luisa Carpintero
- Daniel Martin
- Nicholas Triana

---

## 1. Descripción general del trabajo

El objetivo de este taller fue verificar el cumplimiento legal, normativo y de seguridad de dos sistemas de información:

1. **Caso base en clase — GobData:** Portal estatal de trámites ciudadanos que maneja datos sensibles como identidad, historial clínico, información tributaria y certificados digitales. La evaluación se realizó aplicando un checklist estructurado con base en la Ley 1581 de 2012, el Decreto 1377 de 2013, el Decreto 090 de 2018 y la norma ISO/IEC 27001:2022.

2. **Cliente real — Pecker Nutrition:** Empresa colombiana del sector agropecuario especializada en nutrición animal bajo la filosofía de **formulación abierta**. Pecker desarrolla soluciones nutricionales personalizadas para productores ganaderos, fabricando alimentos balanceados, núcleos vitamínico-minerales, sales mineralizadas y suplementos. Presta además servicios de asesoría técnica personalizada, diagnóstico integral de explotaciones y diseño de planes de alimentación por especie y etapa productiva. El sistema de información de Pecker integra un software de nutrición animal (formulación), un CRM de clientes (ganaderos/haciendas), registros de producción y un sistema contable, todos con información personal y comercialmente sensible.

La metodología empleada consistió en revisar cada control del checklist y asignarle uno de tres estados: **Cumple**, **Parcial** (controles existentes pero incompletos) o **Brecha** (control ausente o claramente insuficiente). Para cada brecha se identificó el hallazgo y se redactó una recomendación concreta.

---

## 2. Proceso de desarrollo

1. **Identificación de normativas aplicables** a cada sistema: para GobData, normativa de protección de datos personales e ISO 27001; para Pecker Nutrition, adicionalmente la normativa sectorial del ICA (Instituto Colombiano Agropecuario), regulaciones de alimentos para animales y normativa sobre protección de secretos comerciales.
2. **Construcción del checklist** con secciones temáticas adaptadas al perfil de cada organización.
3. **Diligenciamiento para GobData** en clase con base en el contexto público del portal.
4. **Aplicación a Pecker Nutrition** considerando su naturaleza B2B, el tipo de datos que maneja (datos de productores ganaderos, formulaciones propietarias, datos laborales) y la normativa ICA aplicable a sus productos.
5. **Análisis de brechas** y redacción de recomendaciones priorizadas por impacto.

---

## 3. Resultados — Caso base GobData

### 3.1 Resumen de cumplimiento

| Sección | Total | Cumple | Parcial | Brecha | N/A |
|---------|:-:|:-:|:-:|:-:|:-:|
| 1. Consentimiento informado | 5 | 2 | 1 | 2 | 0 |
| 2. Derechos del titular (ARCO) | 6 | 2 | 2 | 2 | 0 |
| 3. Política de tratamiento y registro | 4 | 1 | 1 | 2 | 0 |
| 4. Seguridad de la información (ISO 27001) | 10 | 1 | 4 | 5 | 0 |
| 5. Retención y eliminación de datos | 3 | 0 | 0 | 3 | 0 |
| 6. Gestión de incidentes y brechas | 4 | 0 | 2 | 2 | 0 |
| 7. Auditoría, trazabilidad y monitoreo | 4 | 0 | 2 | 2 | 0 |
| 8. Transferencias y encargados | 3 | 0 | 1 | 1 | 1 |
| **TOTAL** | **39** | **6 (15%)** | **13 (33%)** | **19 (49%)** | **1 (3%)** |

### 3.2 Hallazgos críticos en GobData

**1. Ausencia de registro en el RNDBDyF (Brecha crítica — Ley 1581 Art. 25)**
GobData no evidencia el registro de sus bases de datos con información personal ante la SIC. Esto representa un incumplimiento directo de la Ley 1581 y puede resultar en sanciones de hasta 2.000 SMMLV.

**2. Sin política de retención de datos (Brecha — Ley 1581 Art. 4 lit. e)**
El portal acumula datos de décadas de trámites ciudadanos sin una política que defina períodos de conservación ni un proceso de eliminación segura al vencer la finalidad.

**3. Sin cifrado de datos sensibles en reposo (Brecha — ISO 27001 A.8.24)**
No hay evidencia de cifrado en las bases de datos para datos sensibles como historiales médicos o números de identificación. Una brecha comprometería datos de millones de ciudadanos en texto claro.

**4. Ausencia de SIEM y monitoreo continuo (Brecha — ISO 27001 A.8.16)**
Sin plataforma de monitoreo en tiempo real, eventos como acceso masivo no autorizado o exfiltración de datos no serían detectados oportunamente.

**5. Sin protocolo de notificación de brechas a la SIC (Brecha — Decreto 090/2018)**
El Decreto 090 de 2018 obliga a notificar a la SIC en los 15 días hábiles siguientes a conocer la brecha. GobData no tiene este proceso definido.

**Nivel de riesgo GobData:** **ALTO** — El 49% de los controles presentan brechas en áreas críticas como cifrado, monitoreo, retención y gestión de incidentes.

---

## 4. Resultados — Cliente Real: Pecker Nutrition

### 4.1 Contexto del cliente

**Pecker Nutrition** es una empresa privada colombiana del sector agropecuario que crea soluciones nutricionales específicas bajo la filosofía de **formulación abierta**, empleando software de nutrición de vanguardia e ingredientes y aditivos de última generación. Sus líneas de servicio incluyen:

- **Asesoría personalizada:** Diagnóstico integral de la explotación ganadera, presupuestos forrajeros y planes de alimentación ajustados a la base forrajera, modelo animal y objetivos productivos de cada cliente.
- **Formulación y producción:** Diseño y fabricación de núcleos vitamínico-minerales, sales mineralizadas, alimentos balanceados completos y suplementos/complementos nutricionales a la medida.
- **Suministro de ingredientes y aditivos:** Con tecnologías que optimizan los resultados de campo.

**Tipo de información que gestiona:**
- Datos personales de clientes (ganaderos, propietarios de haciendas): nombre, contacto, ubicación de la finca.
- Datos de la explotación: inventario animal, parámetros productivos, base forrajera, resultados diagnósticos.
- Formulaciones nutricionales vinculadas a clientes específicos (secreto comercial + dato personal).
- Datos de empleados y asesores de campo: información laboral, seguridad social, nómina.
- Datos de proveedores: contactos, condiciones comerciales, historial de compras.

**Normativas aplicables:**
- Ley 1581 de 2012 + Decreto 1377 de 2013 (Protección de Datos Personales)
- Decreto 090 de 2018 (Notificación de brechas de datos personales)
- Resolución ICA 150 de 2003 (Registro y control de alimentos para animales)
- Resolución ICA 3168 de 2015 (BPM para fabricantes de alimentos animales)
- Decreto 1840 de 1994 (ICA — insumos agropecuarios)
- Ley 256 de 1996 (Competencia desleal — protección de secretos comerciales)
- Decisión Andina 486 de 2000 (Propiedad industrial — secretos empresariales)
- Ley 1480 de 2011 (Estatuto del Consumidor — trazabilidad de productos)
- ISO/IEC 27001:2022 (Seguridad de la información — referencia de buenas prácticas)

### 4.2 Resumen de cumplimiento

| Sección | Total | Cumple | Parcial | Brecha | N/A |
|---------|:-:|:-:|:-:|:-:|:-:|
| 1. Consentimiento informado | 5 | 0 | 1 | 4 | 0 |
| 2. Derechos del titular (ARCO) | 4 | 0 | 1 | 3 | 0 |
| 3. Política de tratamiento y registro | 4 | 0 | 0 | 4 | 0 |
| 4. Seguridad de la información | 6 | 0 | 2 | 4 | 0 |
| 5. Retención y eliminación | 3 | 0 | 0 | 3 | 0 |
| 6. Gestión de incidentes | 3 | 0 | 0 | 3 | 0 |
| 7. Normativa sectorial ICA | 5 | 2 | 3 | 0 | 0 |
| 8. Secretos comerciales y PI | 3 | 0 | 2 | 1 | 0 |
| **TOTAL** | **33** | **2 (6%)** | **9 (27%)** | **22 (67%)** | **0** |

### 4.3 Hallazgos críticos en Pecker Nutrition

**1. Ausencia total de Política de Tratamiento de Datos Personales (Brecha crítica — Ley 1581 Art. 15)**
Pecker no cuenta con una Política de Tratamiento de Datos Personales publicada ni con un aviso de privacidad accesible para sus clientes, empleados o proveedores. Esto representa el incumplimiento más básico de la Ley 1581 y expone a la empresa a sanciones de la SIC.

**2. Contratos sin cláusula de autorización de tratamiento de datos (Brecha crítica — Ley 1581 Art. 9)**
Los contratos de servicio con ganaderos y productores no incluyen la autorización de tratamiento de datos personales requerida por la Ley 1581. Cada vez que Pecker recolecta datos de diagnóstico, formulación o contacto de un cliente, lo hace sin la base legal adecuada.

**3. Bases de datos no registradas en el RNDBDyF de la SIC (Brecha crítica — Ley 1581 Art. 25)**
Las bases de datos de clientes, empleados y proveedores no están registradas ante la Superintendencia de Industria y Comercio, lo que constituye incumplimiento directo de la ley y puede acarrear multas de hasta 2.000 SMMLV.

**4. Sin controles de seguridad en dispositivos de asesores de campo (Brecha alta — ISO 27001 A.7.8)**
Los asesores de campo acceden al software de nutrición y al correo corporativo desde dispositivos personales sin ningún control de seguridad (PIN, cifrado, borrado remoto). Una pérdida o robo del dispositivo de un asesor podría comprometer formulaciones y datos de múltiples clientes.

**5. Sin control de exportación de formulaciones (Brecha alta — ISO 27001 A.8.12 / Ley 256/1996)**
Cualquier usuario del software de nutrición puede exportar formulaciones de clientes a medios externos sin restricciones ni registro de auditoría. Las formulaciones son el activo más valioso de Pecker y representan simultáneamente un secreto comercial y un dato personal del cliente.

**6. Ausencia completa de gestión de incidentes y notificación a la SIC (Brecha — Decreto 090/2018)**
Pecker no tiene ningún procedimiento para responder ante un incidente de seguridad ni conocimiento de la obligación de notificar a la SIC en los 15 días hábiles establecidos por el Decreto 090 de 2018.

**7. Sin política de retención: datos de clientes inactivos se acumulan sin control (Brecha — Ley 1581 Art. 4 lit. e)**
No existe política que defina cuánto tiempo se conservan los datos de clientes que dejaron de contratar con Pecker. La acumulación indefinida de datos aumenta el riesgo ante cualquier incidente de seguridad.

### 4.4 Aspectos positivos identificados en Pecker Nutrition

- **Registros ICA vigentes** para sus líneas de productos, lo que demuestra cumplimiento de la normativa de insumos agropecuarios.
- **Etiquetado conforme** a los requisitos del ICA (Resolución 150 de 2003).
- **Cláusulas de confidencialidad** en contratos laborales y con clientes (aunque genéricas, representan una base para fortalecer).
- **Proceso de formulación documentado** parcialmente a través del software especializado.

### 4.5 Nivel de riesgo general — Pecker Nutrition

> **MUY ALTO** — El 67% de los controles evaluados presentan brechas. Pecker prácticamente no tiene implementados los requisitos básicos de la Ley 1581 (política, registro SIC, autorizaciones). Aunque su perfil de datos no incluye categorías tan sensibles como datos de salud de personas naturales, sí maneja datos de diagnóstico productivo y formulaciones que tienen un alto valor comercial y están vinculados a personas identificables. La exposición legal ante la SIC es significativa.

---

## 5. Recomendaciones priorizadas para Pecker Nutrition

### Prioridad 1 — Inmediata (0-30 días): Cumplimiento legal básico

| # | Acción | Normativa | Responsable |
|---|--------|-----------|-------------|
| R1 | Redactar y publicar la Política de Tratamiento de Datos Personales en el sitio web y en formatos de servicio | Ley 1581 Art.15 | Gerencia + Asesor legal |
| R2 | Registrar las bases de datos de clientes, empleados y proveedores ante la SIC (RNDBDyF) | Ley 1581 Art.25 | Responsable de datos |
| R3 | Designar un Responsable de Protección de Datos (puede ser interno) y publicar su correo de contacto | Dec.1377 Art.13 | Gerencia |
| R4 | Incluir cláusula de autorización de tratamiento de datos en todos los contratos de servicio nuevos | Ley 1581 Art.9 | Asesor legal |
| R5 | Crear aviso de privacidad para formularios de diagnóstico de campo | Ley 1581 Art.15 | Responsable de datos |

### Prioridad 2 — Corto plazo (30-90 días): Seguridad y procesos

| # | Acción | Normativa | Responsable |
|---|--------|-----------|-------------|
| R6 | Implementar política de contraseñas robustas y MFA para acceso al software de nutrición y sistemas internos | ISO 27001 A.8.5 | TI |
| R7 | Establecer política de seguridad para dispositivos de asesores de campo (PIN obligatorio, cifrado) | ISO 27001 A.7.8 | TI + RRHH |
| R8 | Restringir la exportación de formulaciones del software de nutrición a roles autorizados con log de auditoría | ISO 27001 A.8.12 | TI |
| R9 | Crear canal formal (correo dedicado) para solicitudes ARCO de clientes, empleados y proveedores | Ley 1581 Art.14 | Responsable de datos |
| R10 | Desarrollar procedimiento básico de respuesta a incidentes de seguridad de datos | Decreto 090/2018 | TI + Gerencia |

### Prioridad 3 — Mediano plazo (90-180 días): Madurez del programa

| # | Acción | Normativa | Responsable |
|---|--------|-----------|-------------|
| R11 | Definir e implementar política de retención y eliminación de datos por tipo de titular | Ley 1581 Art.4 | Responsable de datos |
| R12 | Actualizar contratos laborales con cláusula específica de datos personales y NDA reforzado | Ley 1581 / Ley 256 | RRHH + Legal |
| R13 | Documentar proceso de validación de formulaciones conforme BPM del ICA (Res. 3168/2015) | Res. ICA 3168/2015 | Director técnico |
| R14 | Implementar trazabilidad lote-cliente para facilitar retiros de producto si aplica | Res. ICA 150/2003 | Producción |
| R15 | Realizar capacitación en protección de datos personales para todo el equipo | Ley 1581 Art.17 | Responsable de datos |

---

## 6. Investigación complementaria

### Tema: Protección de Datos y Secretos Comerciales en el Sector Agropecuario Colombiano

El sector agropecuario colombiano presenta una intersección particular entre la normativa de protección de datos personales y la protección de secretos comerciales. En el caso de empresas como Pecker Nutrition, las formulaciones nutricionales diseñadas para cada cliente son simultáneamente un activo de propiedad intelectual de la empresa y un dato vinculado a una persona identificable (el productor ganadero). Esta dualidad genera obligaciones en dos frentes normativos distintos.

Desde la perspectiva de la **Ley 1581 de 2012**, los datos del productor recolectados durante el diagnóstico de su explotación (inventario animal, parámetros productivos, base forrajera) son datos personales en tanto permiten identificar a una persona natural. El tratamiento de estos datos sin autorización previa y sin política de privacidad publicada constituye una infracción directa que la SIC puede sancionar con multas de hasta 2.000 SMMLV (artículo 23 de la Ley 1581).

Desde la perspectiva de los **secretos comerciales**, la **Ley 256 de 1996** y la **Decisión Andina 486 de 2000** protegen la información confidencial que tiene valor comercial precisamente por ser secreta. Las formulaciones de Pecker —desarrolladas con software de nutrición especializado y conocimiento técnico propio— califican como secreto empresarial. Sin embargo, esta protección solo opera cuando la empresa toma medidas razonables para mantener la confidencialidad: contratos de confidencialidad, controles de acceso y políticas internas. Una empresa que no documenta ni protege activamente sus formulaciones difícilmente puede alegar protección legal en caso de apropiación indebida por parte de un ex-empleado o competidor.

En cuanto a la **normativa del ICA**, la Resolución 3168 de 2015 establece las Buenas Prácticas de Manufactura (BPM) para fabricantes de alimentos para animales. Un aspecto frecuentemente pasado por alto es que los registros de producción, análisis de calidad y formulaciones exigidos por el ICA también pueden contener datos personales vinculados a clientes (cuando una formulación personalizada se elabora para un productor específico). Esto genera una superposición entre obligaciones del ICA (conservar registros mínimo 2 años post-vencimiento del lote) y obligaciones de la Ley 1581 (tratar los datos con las garantías del caso).

La recomendación principal para Pecker Nutrition es tratar el cumplimiento normativo como un programa integrado: protección de datos personales, seguridad de la información y cumplimiento ICA no son compartimentos separados, sino parte de un mismo sistema de gestión que protege tanto a los clientes como a la propia empresa.

---

## 7. Conclusiones

1. El caso base GobData presenta un nivel de cumplimiento del 15% en controles totalmente satisfechos, con el 49% en brecha. Las deficiencias más críticas son estructurales: ausencia de cifrado, sin monitoreo continuo y sin política de retención.
2. Pecker Nutrition presenta el nivel de cumplimiento más bajo evaluado: apenas el 6% de controles cumplen plenamente. La empresa prácticamente no ha iniciado la implementación de los requisitos básicos de la Ley 1581.
3. La diferencia entre los dos sistemas es relevante: GobData tiene algunos controles implementados (consentimiento, PQRS, TLS) pero deficientes en profundidad; Pecker parte desde una línea base casi nula en protección de datos pero tiene buen desempeño en la normativa sectorial del ICA.
4. Para Pecker, el primer paso es la formalización legal: política de privacidad, registro SIC y cláusulas contractuales. Solo desde esa base tiene sentido construir controles técnicos más avanzados.
5. El cumplimiento normativo en el sector agropecuario es aún incipiente en Colombia, pero la SIC ha comenzado a ampliar sus acciones de vigilancia a pymes y empresas del sector productivo. La anticipación reduce el riesgo sancionatorio y genera confianza con los clientes.

---

_Este informe hace parte de la entrega del Taller 6 del curso AREM (Arquitectura Empresarial) — Universidad de La Sabana. Fecha de elaboración: 10 de abril de 2026._
