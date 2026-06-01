# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 7 - Integración de Vistas de Arquitectura_

## 👥 Integrantes del equipo
- Daniel Martin
- Nicholas Triana
- Luisa Carpintero

---

## 🧠 Descripción general del trabajo

El objetivo del taller consistió en integrar las diferentes vistas arquitectónicas desarrolladas durante el curso AREM en una representación coherente y alineada con las necesidades del cliente real: Pecker Nutrition.

La actividad se desarrolló a partir del análisis de la arquitectura AS-IS de la empresa, identificando cómo interactúan las capas de negocio, información, aplicaciones, infraestructura y seguridad. El propósito principal fue visualizar de manera integral la situación actual de la organización y detectar las principales problemáticas relacionadas con la baja integración tecnológica y la alta dependencia de procesos manuales.

El trabajo incluyó la construcción de un tablero integrado en draw.io, la documentación narrativa de las relaciones entre capas y el análisis crítico de la coherencia arquitectónica de la empresa.

---

## 🔧 Proceso de desarrollo

El desarrollo del taller inició con la revisión de los entregables previos elaborados durante el curso, especialmente los modelos BPMN, diagramas de aplicaciones y modelos de datos realizados para Pecker Nutrition.

Posteriormente, el equipo definió una estructura arquitectónica organizada por capas:

- Vista de Negocio
- Vista de Información
- Vista de Aplicaciones
- Vista de Infraestructura
- Vista de Seguridad

Se decidió representar las relaciones entre capas mediante conexiones jerárquicas para mostrar cómo los procesos de negocio dependen de aplicaciones específicas, las cuales a su vez requieren infraestructura tecnológica y mecanismos de seguridad.

### Herramientas utilizadas

- Draw.io para modelado visual
- PlantUML para diagramación preliminar
- Markdown para documentación técnica
- Referencias TOGAF y BPMN para alineación metodológica

### Ajustes realizados durante el modelado

Inicialmente se planteó una representación centrada únicamente en procesos, pero posteriormente se decidió incluir también las vistas de información y seguridad para obtener una arquitectura más completa y coherente.

Adicionalmente, se ajustó el modelo para reflejar explícitamente:

- Dependencia de herramientas manuales
- Ausencia de integración entre sistemas
- Riesgos operativos asociados a la gestión documental y de pedidos

---

## 🧩 Análisis del modelo propuesto

El modelo entregado se estructura en cinco capas arquitectónicas conectadas entre sí:

1. Negocio
2. Aplicaciones
3. Información
4. Infraestructura
5. Seguridad

La arquitectura representa adecuadamente las necesidades actuales del cliente, evidenciando cómo los procesos operativos dependen de herramientas no integradas como WhatsApp, Excel, Dropbox y software aislados.

El modelo permite visualizar:

- Cuellos de botella operativos
- Dependencia humana crítica
- Falta de trazabilidad
- Riesgos asociados a la gestión manual de información

### Supuestos tomados

Para la construcción del modelo se asumió que:

- La empresa no dispone actualmente de un ERP integrado.
- Los procesos de comunicación y pedidos se realizan principalmente mediante WhatsApp y correo electrónico.
- La infraestructura tecnológica es básica y parcialmente apoyada en servicios cloud.
- No existen políticas formales avanzadas de seguridad informática.

Estos supuestos fueron tomados con base en la información suministrada durante el desarrollo del caso.

---

## 📈 Diagrama final entregado

> Archivo: `tablero-integrado-cliente.drawio`

El diagrama final representa la integración de todas las vistas arquitectónicas del cliente Pecker Nutrition y muestra las relaciones entre procesos de negocio, aplicaciones utilizadas, infraestructura tecnológica y mecanismos de seguridad existentes.

---

## 📋 Tabla de actores, entidades o componentes

| Nombre del elemento | Tipo | Descripción | Responsable |
|---------------------|------|-------------|-------------|
| Cliente | Actor | Realiza pedidos de alimentos balanceados | Cliente |
| Área Comercial | Actor | Gestiona negociación y recepción de pedidos | Empresa |
| Producción | Actor | Fabrica concentrados y procesa pedidos | Empresa |
| Contabilidad | Actor | Genera facturación y registro financiero | Empresa |
| WhatsApp | Aplicación | Canal principal de recepción de pedidos | Empresa |
| Excel | Aplicación | Herramienta manual de registro operativo | Empresa |
| Dropbox | Aplicación | Almacenamiento documental | Empresa |
| Pedido | Entidad | Registro de solicitud de compra | Empresa |
| Factura | Entidad | Documento contable asociado al pedido | Empresa |
| Fórmula | Entidad | Información técnica de producción | Empresa |

---

## 🔍 Investigación complementaria

### Tema investigado:
Integración de vistas arquitectónicas bajo TOGAF y buenas prácticas de documentación empresarial.

### Resumen:

Se investigó cómo marcos de arquitectura empresarial como TOGAF proponen organizar las vistas arquitectónicas mediante capas estructuradas que permitan alinear negocio y tecnología. La arquitectura empresarial busca garantizar que las decisiones tecnológicas soporten adecuadamente los objetivos estratégicos de la organización.

También se revisaron ejemplos de documentación arquitectónica empresarial en plataformas como Microsoft Azure Architecture Center y AWS Well-Architected Framework, donde se evidencia la importancia de representar relaciones claras entre negocio, aplicaciones, infraestructura y seguridad.

La investigación permitió comprender que una arquitectura integrada facilita la identificación de riesgos operativos, redundancias tecnológicas y oportunidades de transformación digital, aspectos directamente relacionados con la situación actual de Pecker Nutrition.

---

## 📚 Referencias

- [1] The Open Group. *TOGAF Standard Version 9.2*. 2018. https://www.opengroup.org/togaf
- [2] OMG. *Business Process Model and Notation (BPMN) Version 2.0*. https://www.omg.org/spec/BPMN/
- [3] Microsoft Azure Architecture Center. https://learn.microsoft.com/azure/architecture/
- [4] AWS Well-Architected Framework. https://aws.amazon.com/architecture/well-architected/
- [5] Bass, Len; Clements, Paul; Kazman, Rick. *Software Architecture in Practice*. Addison-Wesley.

---

_Este documento hace parte de la entrega del Taller 7 del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._