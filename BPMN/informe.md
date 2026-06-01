# Taller 1 – BPMN  
## Informe del Proceso del Cliente  
### Pecker Nutrition S.A.S.

---

## 1. Descripción del Proceso

**Pecker Nutrition S.A.S.** es una empresa del sector agroindustrial especializada en alimentación animal, con un enfoque diferencial basado en la **personalización del concentrado** según las necesidades específicas de cada hato productivo. La compañía opera bajo una filosofía de **fórmula abierta**, lo que implica una relación cercana y recurrente con sus clientes.

El proceso seleccionado corresponde al **agendamiento de entregas para clientes frecuentes**, el cual actualmente se realiza de manera manual a través de llamadas telefónicas. Este método requiere la intervención directa del personal operativo para identificar al cliente, revisar su historial de pedidos, confirmar cantidades y fechas, y registrar la solicitud, generando una alta carga operativa y riesgos de error.

El proceso propuesto busca automatizar el agendamiento de pedidos frecuentes mediante un **bot de WhatsApp**, conectado a una **base de datos de clientes**, permitiendo identificar al cliente, filtrar pedidos habituales y confirmar entregas de manera más ágil y eficiente.

---

## 2. Diferencias frente al Caso Base (Clínica Salud Viva)

Aunque el proceso seleccionado es análogo al caso base de la Clínica Salud Viva (agendamiento de citas médicas), se identifican diferencias relevantes:

- El caso base se centra en la prestación de un servicio médico, mientras que el proceso de Pecker Nutrition está orientado a la gestión de **entregas de productos físicos**.
- El canal de interacción cambia de una plataforma web a un **canal conversacional (WhatsApp)**.
- En Pecker Nutrition existe un mayor nivel de **personalización**, ya que los pedidos dependen del historial y formulación específica de cada cliente.
- El proceso clínico es ocasional, mientras que el proceso seleccionado es **frecuente y repetitivo**, lo que incrementa el impacto de la automatización.
- Las reglas de negocio se basan en disponibilidad de producto y pedidos previamente definidos, no en disponibilidad de personal médico.

---

## 3. Justificación del Rediseño del Proceso

El rediseño del proceso se justifica por los siguientes factores:

- Reducción de la carga operativa asociada a tareas repetitivas.
- Mejora en la experiencia del cliente al permitir autogestión del pedido.
- Disminución de errores derivados del registro manual de información.
- Mayor escalabilidad del proceso sin incremento proporcional de recursos humanos.
- Alineación con la estrategia de negocio basada en cercanía, personalización y eficiencia operativa.

Desde la perspectiva de Arquitectura Empresarial, este proceso fortalece la **capa de negocio**, habilitando futuras mejoras en las capas de aplicaciones, datos e infraestructura.

---

## 4. Buenas Prácticas BPMN Aplicadas

El modelado del proceso se apoya en las siguientes buenas prácticas BPMN:

- Modelar desde la perspectiva del negocio.
- Utilizar nombres claros y descriptivos en las actividades (verbo + objeto).
- Emplear gateways únicamente cuando existe una decisión real en el flujo.
- Mantener diagramas simples y legibles.
- Separar responsabilidades mediante roles claramente definidos.
- Identificar y documentar reglas de negocio implícitas.

Estas prácticas garantizan que el modelo BPMN sea comprensible, reutilizable y apto para futuras iniciativas de automatización.

---

## 5. Ejemplos de BPMN y Automatización en la Industria

En diferentes sectores se evidencian casos exitosos de procesos modelados con BPMN y automatizados posteriormente:

- Proveedores agroindustriales que automatizan pedidos recurrentes basados en ciclos productivos.
- Distribuidores B2B que implementan reorden automático según historial de consumo.
- Empresas logísticas que utilizan bots conversacionales para coordinar entregas.
- Plataformas de comercio B2B como Amazon Business, donde los clientes gestionan pedidos frecuentes de manera autónoma.

Estos ejemplos demuestran la efectividad de BPMN como herramienta para optimizar procesos repetitivos y de alto impacto operativo.

---

## 6. Conclusión

El proceso de agendamiento de entregas automatizado en Pecker Nutrition S.A.S. evidencia cómo BPMN permite comprender, rediseñar y optimizar procesos críticos del negocio. La propuesta presentada mejora la eficiencia operativa, reduce errores y refuerza la alineación entre estrategia, procesos y tecnología, consolidando a BPMN como un elemento clave dentro de la Arquitectura Empresarial.
