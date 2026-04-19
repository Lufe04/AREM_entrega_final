# Referencias – Buenas Prácticas de Seguridad
## Taller 5: STRIDE aplicado a Pecker Nutrition

---

## 1. Marco de referencia STRIDE

- **Microsoft Threat Modeling Tool – STRIDE Methodology**  
  Documentación oficial del modelo STRIDE desarrollado por Microsoft para análisis de amenazas por componente.  
  https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-threats

- **OWASP Threat Modeling**  
  Guía de la Open Web Application Security Project sobre modelado de amenazas, incluyendo STRIDE como metodología recomendada.  
  https://owasp.org/www-community/Threat_Modeling

---

## 2. Buenas prácticas para pequeñas y medianas empresas (sector alimentos / manufactura)

- **NIST Cybersecurity Framework (CSF 2.0)**  
  National Institute of Standards and Technology. Framework flexible y escalable aplicable a PyMEs. Define funciones de Identificar, Proteger, Detectar, Responder y Recuperar.  
  https://www.nist.gov/cyberframework

- **ENISA – Cybersecurity for SMEs**  
  Agencia de Ciberseguridad de la Unión Europea. Guía práctica de seguridad para pequeñas empresas con recursos limitados, enfocada en riesgos operativos.  
  https://www.enisa.europa.eu/publications/cybersecurity-guide-for-smes

- **CIS Controls v8 – Implementation Group 1**  
  Centro para la Seguridad en Internet. Define los 18 controles de seguridad esenciales priorizados para organizaciones pequeñas. El IG1 (Implementation Group 1) está diseñado específicamente para empresas con capacidad IT limitada.  
  https://www.cisecurity.org/controls/cis-controls-list

---

## 3. Seguridad en comunicaciones y canales informales

- **WhatsApp Business Security – Meta for Developers**  
  Documentación oficial sobre el cifrado de extremo a extremo de WhatsApp y limitaciones de seguridad empresarial. Explica por qué WhatsApp no es adecuado como sistema formal de captura de pedidos.  
  https://developers.facebook.com/docs/whatsapp/security

- **CISA – Phishing Guidance: Stopping the Attack Cycle at Phase One**  
  Agencia de Ciberseguridad e Infraestructura de EE.UU. Guía práctica para reconocer y prevenir ataques de phishing en canales de correo electrónico.  
  https://www.cisa.gov/resources-tools/resources/phishing-guidance-stopping-attack-cycle-phase-one

---

## 4. Seguridad en almacenamiento en la nube (Dropbox, OneDrive)

- **Dropbox Business – Seguridad y Permisos**  
  Guía oficial de Dropbox sobre configuración de permisos por carpeta, historial de versiones, registro de actividad y autenticación en dos pasos.  
  https://help.dropbox.com/security

- **Microsoft OneDrive – Seguridad empresarial**  
  Documentación de Microsoft sobre controles de seguridad en OneDrive, incluyendo cifrado en reposo, auditoría de acceso y recuperación de versiones.  
  https://learn.microsoft.com/en-us/onedrive/plan-onedrive-enterprise

- **INCIBE – Seguridad en la nube para empresas**  
  Instituto Nacional de Ciberseguridad de España. Guía en español sobre buenas prácticas en uso de almacenamiento en la nube para PyMEs, aplicable al contexto latinoamericano.  
  https://www.incibe.es/empresas/tematicas/cloud

---

## 5. Control de acceso y gestión de identidades (IAM)

- **NIST SP 800-63 – Digital Identity Guidelines**  
  Guía técnica sobre autenticación multifactor, gestión de contraseñas y control de acceso. Referencia estándar para definir requisitos de autenticación según nivel de riesgo.  
  https://pages.nist.gov/800-63-3/

- **Principle of Least Privilege – OWASP**  
  Explicación del principio de mínimo privilegio: cada usuario debe tener acceso únicamente a los recursos que necesita para cumplir su función. Base del control de roles recomendado en el análisis.  
  https://owasp.org/www-community/vulnerabilities/Least_Privilege_Violation

---

## 6. Normativa colombiana aplicable

- **Ley 1581 de 2012 – Protección de Datos Personales (Colombia)**  
  Superintendencia de Industria y Comercio. Ley marco de protección de datos en Colombia. Establece obligaciones para empresas que traten datos personales de ciudadanos colombianos.  
  https://www.sic.gov.co/ley-1581-de-2012

- **Decreto 1377 de 2013 – Reglamentario de la Ley 1581**  
  Define el aviso de privacidad, las políticas de tratamiento de datos y el registro de bases de datos ante la SIC.  
  https://www.funcionpublica.gov.co/eva/gestornormativo/norma.php?i=52829

- **Guía para la implementación del principio de responsabilidad demostrada – SIC**  
  Superintendencia de Industria y Comercio. Guía práctica para que empresas colombianas implementen medidas de seguridad en el tratamiento de datos personales.  
  https://www.sic.gov.co/sites/default/files/files/Nuestra_Entidad/Publicaciones/Guia_accountability.pdf

---

## 7. Continuidad operativa y gestión de backups

- **INCIBE – Plan de Continuidad de Negocio para PyMEs**  
  Guía práctica para elaborar un plan de continuidad que garantice la recuperación operativa ante fallos de servicios críticos (correo, almacenamiento en la nube).  
  https://www.incibe.es/empresas/guias/plan-de-continuidad-de-negocio

- **Regla 3-2-1 de Backup – Acronis**  
  Estándar de la industria para backups: 3 copias de los datos, en 2 medios diferentes, con 1 copia fuera de sitio. Directamente aplicable a la situación de Pecker Nutrition.  
  https://www.acronis.com/en-us/articles/backup-3-2-1-rule/

---

## 8. Seguridad en el sector de manufactura y alimentos

- **ISO/IEC 27001:2022 – Sistemas de Gestión de Seguridad de la Información**  
  Estándar internacional de seguridad de la información. Aunque su implementación completa excede el alcance de una PyME de 8 personas, sus controles del Anexo A sirven como checklist de referencia para identificar brechas.  
  https://www.iso.org/standard/27001

- **FDA Food Safety Modernization Act (FSMA) – Cybersecurity Considerations**  
  Para empresas del sector alimentos que exportan o tienen clientes internacionales, la FDA ha emitido consideraciones sobre seguridad digital en la cadena de producción de alimentos.  
  https://www.fda.gov/food/food-safety-modernization-act-fsma/fsma-final-rule-preventive-controls-human-food
