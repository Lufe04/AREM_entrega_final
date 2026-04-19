# Informe de Análisis de Seguridad – Pecker Nutrition
## Marco STRIDE aplicado al sistema del cliente real

**Curso:** Arquitectura Empresarial – Universidad de La Sabana  
**Equipo:** Luisa Carpintero, Nicholas Triana, Daniel Martín  
**Fecha:** 17 de abril de 2026  

---

## 1. Contexto del cliente

Pecker Nutrition es una empresa colombiana de 8 empleados dedicada a la fabricación y venta de alimentos balanceados para animales. Opera desde el Terminal Logístico y Empresarial La Paz con una infraestructura tecnológica mínima: un software de formulación aislado, un software contable independiente, Dropbox como repositorio documental y el correo electrónico como canal operativo principal. WhatsApp funciona de facto como el sistema de captura de pedidos y canal comercial.

Esta arquitectura manual, altamente dependiente de personas clave y con escasa integración entre herramientas, presenta una superficie de ataque amplia y poco controlada. A diferencia de empresas con infraestructura IT formalizada, los riesgos en Pecker Nutrition no provienen principalmente de ataques sofisticados, sino de la ausencia de controles básicos que exponen la operación a errores humanos, fraudes internos y pérdida de información crítica.

---

## 2. Proceso crítico evaluado: Gestión de pedidos e información operativa

Se seleccionó el flujo completo de gestión de pedidos e información operativa como el proceso crítico del análisis, dado que:

- Concentra los activos más valiosos de la empresa: fórmulas propietarias, datos de clientes, registros financieros y acuerdos comerciales.
- Es altamente dependiente de herramientas no diseñadas para uso empresarial formal (WhatsApp, correo personal).
- La pérdida, modificación o exposición de cualquier componente de este flujo puede paralizar la operación completa.

### Componentes del flujo evaluado

| Componente | Rol en el sistema | Criticidad |
|---|---|---|
| WhatsApp | Canal de captura de pedidos y negociación comercial | Crítica |
| Correo electrónico | Canal operativo y de comunicación con terceros | Alta |
| Excel / Registros manuales | Consolidación y seguimiento de pedidos | Alta |
| Dropbox | Almacenamiento de fórmulas, documentos y contratos | Crítica |
| Software de formulación | Gestión de recetas y cálculos de producción | Alta |
| Software contable | Registro financiero y facturación | Alta |

---

## 3. Análisis STRIDE

Se aplicó el marco STRIDE sobre los componentes del flujo crítico. A continuación se presenta un resumen de las 8 amenazas identificadas, organizadas por tipo:

### 3.1 Spoofing – Suplantación de identidad

**P1 – Suplantación vía WhatsApp (Nivel de riesgo: Alto)**  
La empresa recibe pedidos exclusivamente por WhatsApp sin ningún mecanismo de verificación de identidad. Un atacante puede crear un número con el nombre y foto de un cliente habitual para ordenar despachos fraudulentos o modificar condiciones comerciales. La ausencia de un sistema formal de pedidos hace que esta amenaza sea de alta probabilidad.

**P2 – Phishing por correo dirigido a empleados clave (Nivel de riesgo: Alto)**  
Sin autenticación multifactor en cuentas de correo ni Dropbox, y sin políticas de verificación de solicitudes sensibles, un correo de phishing dirigido a los responsables documentales puede comprometer toda la base de archivos de la empresa.

### 3.2 Tampering – Manipulación de datos

**P3 – Alteración de registros en Excel sin trazabilidad (Nivel de riesgo: Crítico)**  
Los archivos Excel que consolidan pedidos y producción pueden ser modificados por cualquier persona con acceso sin dejar rastro auditable. Esta es la amenaza de mayor criticidad del análisis: la combinación de alta probabilidad (ocurre por error humano constantemente) con impacto severo (pérdidas económicas no auditables, posibles fraudes) la eleva a nivel crítico.

**P4 – Modificación no autorizada de fórmulas en Dropbox (Nivel de riesgo: Alto)**  
Dropbox no tiene configurados permisos granulares por carpeta. Una modificación accidental o deliberada de una fórmula de concentrado puede resultar en un lote de producción defectuoso, con costos directos de insumos y potenciales daños a los animales.

### 3.3 Repudiation – Repudio de acciones

**P5 – Negación de acuerdos pactados por WhatsApp (Nivel de riesgo: Alto)**  
Sin confirmaciones formales por escrito, clientes o proveedores pueden negar órdenes de compra, precios acordados o cantidades comprometidas. Las conversaciones de WhatsApp no constituyen evidencia legal suficiente en disputas comerciales, y pueden haber sido eliminadas o manipuladas con capturas de pantalla editadas.

### 3.4 Information Disclosure – Divulgación de información

**P6 – Exposición de fórmulas propietarias y datos de clientes (Nivel de riesgo: Crítico)**  
La configuración actual de Dropbox no separa accesos por rol. Terceros (proveedores, colaboradores externos) con acceso compartido pueden visualizar documentos fuera de su alcance autorizado, incluyendo fórmulas que representan la ventaja competitiva central de Pecker Nutrition. Esta amenaza también implica riesgo de incumplimiento de la Ley 1581 de Protección de Datos de Colombia.

### 3.5 Denial of Service – Denegación de servicio

**P7 – Suspensión de cuentas de Dropbox o correo (Nivel de riesgo: Alto)**  
Dado que toda la operación depende de dos servicios en la nube (Dropbox y correo), la suspensión de cualquiera de ellos —por impago, hackeo o violación de términos— paraliza completamente la empresa. El backup mensual en disco duro físico es insuficiente como plan de continuidad.

### 3.6 Elevation of Privilege – Elevación de privilegios

**P8 – Acceso sin control de roles a sistemas financieros y documentales (Nivel de riesgo: Alto)**  
Los sistemas actuales no implementan control de acceso basado en roles. Operarios y personal administrativo tienen acceso a la misma información que gerencia y contabilidad, creando riesgo de fraude interno y violación de la confidencialidad financiera.

---

## 4. Priorización de amenazas

| Amenaza | Tipo STRIDE | Probabilidad | Impacto | Nivel de Riesgo |
|---|---|---|---|---|
| P3 – Manipulación de Excel sin trazabilidad | Tampering | Alta | Severo | **Crítico** |
| P6 – Exposición de fórmulas propietarias | Information Disclosure | Media | Severo | **Crítico** |
| P1 – Suplantación vía WhatsApp | Spoofing | Alta | Alto | **Alto** |
| P2 – Phishing a empleados clave | Spoofing | Alta | Alto | **Alto** |
| P5 – Repudio de acuerdos comerciales | Repudiation | Alta | Alto | **Alto** |
| P7 – Suspensión de servicios en la nube | Denial of Service | Baja | Severo | **Alto** |
| P8 – Acceso sin control de roles | Elevation of Privilege | Alta | Alto | **Alto** |
| P4 – Modificación de fórmulas en Dropbox | Tampering | Media | Alto | **Alto** |

La amenaza P3 es **la más urgente** de mitigar: ocurre en la operación diaria (por error humano, no solo por ataque) y sus consecuencias son inmediatas y difíciles de rastrear sin controles preventivos.

---

## 5. Plan de mitigación priorizado

### Prioridad 1 – Inmediata (0-30 días, sin costo o costo mínimo)

1. **Activar historial de versiones en Dropbox** para todos los archivos críticos.
2. **Habilitar MFA** en todas las cuentas de correo y Dropbox existentes.
3. **Configurar permisos por carpeta en Dropbox**: crear estructura de carpetas segmentada por rol (operativo, administrativo, gerencia) y eliminar acceso compartido genérico.
4. **Establecer protocolo de confirmación de pedidos por correo** (adicional al WhatsApp) como respaldo formal con timestamp.

### Prioridad 2 – Corto plazo (30-90 días)

5. **Migrar registros de pedidos a Google Sheets** con control de versiones y acceso por cuenta individual.
6. **Configurar backup automático semanal** en OneDrive (ya disponible, no utilizado actualmente) como segundo repositorio en la nube.
7. **Crear cuentas individuales** en Dropbox para cada empleado (eliminar cuentas genéricas compartidas).
8. **Capacitación básica en seguridad** para los 8 empleados: reconocimiento de phishing, verificación de identidad en WhatsApp y manejo seguro de documentos.

### Prioridad 3 – Mediano plazo (90-180 días)

9. **Implementar formulario web de pedidos** (Google Forms + hoja de cálculo vinculada) para formalizar la captura de pedidos y eliminar dependencia de WhatsApp.
10. **Revisar permisos en software contable** para implementar acceso restringido por rol.
11. **Política de contraseñas fuerte**: contraseñas de mínimo 12 caracteres, únicas por sistema, almacenadas en gestor de contraseñas (Bitwarden, gratuito).

---

## 6. Impacto normativo y regulatorio

Dado que Pecker Nutrition maneja datos personales de clientes (nombres, contactos, historial de compras), aplican las siguientes normas colombianas:

- **Ley 1581 de 2012** (Protección de Datos Personales): obliga a implementar medidas de seguridad para proteger datos de terceros. El incumplimiento puede generar multas de hasta 2.000 SMMLV.
- **Decreto 1377 de 2013**: reglamento de la Ley 1581, exige registro de bases de datos ante la SIC para empresas que manejan datos personales de más de 5 titulares.

Las amenazas P6 (exposición de datos de clientes) y P5 (falta de evidencia de acuerdos) son las de mayor riesgo regulatorio.

---

## 7. Conclusiones

El análisis STRIDE sobre Pecker Nutrition revela que los riesgos de seguridad más críticos de la empresa no son consecuencia de amenazas tecnológicas avanzadas, sino de la ausencia de controles básicos de gobernanza de información. La informalidad del canal comercial (WhatsApp), la falta de trazabilidad en registros manuales y la configuración genérica de herramientas en la nube crean una superficie de ataque amplia y de fácil explotación.

La buena noticia es que la mayoría de las mitigaciones de mayor impacto tienen costo bajo o nulo: activar funciones ya disponibles en Dropbox, habilitar MFA en cuentas existentes, y establecer protocolos de confirmación formales no requieren inversión tecnológica significativa. El mayor esfuerzo requerido es organizacional: establecer hábitos y procesos que complementen las herramientas existentes antes de considerar inversiones en nuevos sistemas.

Se recomienda priorizar las acciones de la Prioridad 1 antes de cualquier inversión en automatización, dado que implementar nuevos sistemas sobre una base de gobernanza deficiente únicamente amplía la superficie de riesgo.
