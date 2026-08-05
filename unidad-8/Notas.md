# Resumen Detallado Módulo 2 - Unidad 8: Precios, SLAs y Certificación CLF-C02

## 1. Introducción: Importancia de Costos, SLA y Certificación en AWS
En el mundo cloud, no basta con saber usar técnicamente los servicios, sino también entender:
* Cómo gestionamos los costos.
* Qué niveles de disponibilidad (`SLA`) ofrece AWS.
* Cómo certificar estos conocimientos a través de una certificación oficial enfocada en conceptos fundamentales: la **AWS Certified Cloud Practitioner (CLF-C02)**.

---

## 2. Modelos de Precios en AWS
AWS ofrece varios modelos de precios que permiten flexibilidad y optimización según el tipo de uso:

* **On-Demand (Pago por uso):** Pago únicamente por el tiempo que se usa el recurso, sin contratos ni compromisos.
  * *Ideal para:* Principiantes, pruebas y cargas de uso variable o impredecible.
  * *Característica:* Es el modelo más flexible, pero con el costo por unidad más alto.
* **Reserved Instances (Instancias reservadas):** Se compromete a usar cierto recurso por 1 o 3 años a cambio de grandes descuentos.
  * *Ideal para:* Cargas estables y predecibles (ej. entornos de producción).
  * *Desventaja:* Falta de flexibilidad si cambia la demanda.
* **Spot Instances:** Uso de capacidad ociosa a precio muy reducido con la condición de que AWS pueda interrumpirlas en cualquier momento.
  * *Ideal para:* Procesos tolerantes a interrupciones (análisis de datos, simulaciones).
* **Savings Plans:** Modelo flexible que ofrece descuentos similares a las instancias reservadas, comprometiéndose a gastar una cantidad fija por hora durante un período. Más flexible que las *Reserved Instances*.

### Cómo elegir el modelo adecuado:
Depende completamente de si tu uso es predecible, variable o tolerante a interrupciones:
* 🚀 **Inicio o proyectos poco claros** $\rightarrow$ *On-Demand*
* 🏢 **Uso estable y continuo** $\rightarrow$ *Reserved Instances* o *Savings Plans*
* ⚙️ **Procesos flexibles o interrumpibles** $\rightarrow$ *Spot Instances*

> *Nota:* Normalmente, en el día a día se combinan estos modelos para optimizar costos y estabilidad.

---

## 3. Herramientas para Gestión de Costos en AWS
Controlar los costos es esencial para evitar sorpresas. AWS ofrece las siguientes herramientas clave:

* **Billing Dashboard:** Panel central donde se visualiza el gasto total y se monitorea la factura mensual.
* **AWS Cost Explorer:** Permite analizar en detalle el consumo, identificar tendencias y saber qué servicios generan mayores gastos.
* **AWS Budgets:** Establece límites presupuestarios y envía alertas ante riesgos de sobrepasar los umbrales, ayudando a prevenir gastos involuntarios.

*Estas herramientas cumplen roles complementarios para visualizar, analizar y controlar el gasto de manera integral.*

---

## 4. Acuerdos de Nivel de Servicio (SLAs)
Los **SLA** son compromisos formales de AWS que garantizan la disponibilidad de sus servicios expresada en porcentaje durante un período determinado (por ejemplo, `99.9%`). Aunque AWS garantiza ciertos niveles, el diseño de la arquitectura debe considerar resiliencia y alta disponibilidad para minimizar impactos ante fallas.

### Responsabilidad Compartida
* **AWS:** Responsable de la infraestructura física y la disponibilidad de los servicios globales y regionales.
* **Usuario:** Responsable de configurar su aplicación correctamente para cumplir con los requisitos de resiliencia.

### Buenas prácticas para aprovechar los SLAs:
* Uso de múltiples Zonas de Disponibilidad (AZ).
* Evitar la dependencia en un único recurso crítico.
* Implementar estrategias robustas de *backups* y recuperación ante desastres (*Disaster Recovery*).

> *En caso de incumplimiento del SLA, AWS suele otorgar créditos de servicio para compensar al cliente.*

---

## 5. Costo Total de Propiedad (TCO) y Herramientas de Estimación
Al migrar a la nube, es clave prever el costo total, considerando no solo el gasto visible, sino también **costos ocultos** (como mantenimiento, soporte físico y administración) que existen en los ambientes tradicionales *on-premise*. El valor del **TCO** ayuda a comparar de forma más realista la opción Cloud vs. On-Premise.

### Herramienta oficial:
* **AWS Pricing Calculator:** Permite estimar y comparar costos antes de implementar soluciones, validando diferentes escenarios de uso para evitar sorpresas financieras.

---

## 6. Certificación AWS Certified Cloud Practitioner (CLF-C02)
Es la certificación inicial para validar conocimientos fundamentales en AWS, ideal para quienes comienzan o para perfiles no técnicos.

* **Qué es:** Certificación que valida la comprensión básica de la nube y los servicios de AWS.
* **Temas que evalúa:**
  1. Conceptos generales de *Cloud Computing* (`IaaS`, `PaaS`, `SaaS`).
  2. Seguridad y cumplimiento (incluyendo el Modelo de Responsabilidad Compartida).
  3. Servicios principales de AWS (`EC2`, `S3`, `RDS`, `VPC`, `Lambda`, etc.).
  4. Facturación, precios y optimización de costos.
* **Formato de examen:**
  * Preguntas de opción múltiple.
  * Duración: Aproximadamente `90 minutos`.
  * Modalidad: Online o presencial.
  * Nivel: Básico (disponible en español).
  * Enfoque: Preguntas basadas en escenarios reales.
* **Recomendaciones:**
  * Enfocarse en entender conceptos clave y las diferencias lógicas entre servicios.
  * Practicar preguntas tipo examen en lugar de memorizar ciegamente.
* **Importancia:**
  * Introduce formalmente al mundo cloud.
  * Mejora significativamente el perfil profesional.
  * Sirve como base sólida para futuras certificaciones avanzadas (*Associate*, *Professional* o *Specialty*).

---

## 7. Recursos Oficiales para Aprender y Prepararse
AWS dispone de múltiples recursos gratuitos y confiables para el aprendizaje continuo:

* **AWS Skill Builder:** Plataforma oficial con cursos, rutas de aprendizaje, cuestionarios y laboratorios prácticos alineados a certificaciones (desde nivel básico hasta avanzado).
* **Whitepapers (Documentos técnicos):** Documentación oficial con buenas prácticas, explicaciones profundas de conceptos y arquitecturas de referencia.
* **Laboratorios prácticos:** Ejercicios guiados para aplicar conocimientos reales directamente en la consola de AWS.

---

## 8. Conclusión
Entender y gestionar los costos en AWS es tan importante como conocer la tecnología misma. Esta unidad proporciona una base sólida sobre modelos de precios, herramientas de monitoreo, SLAs, TCO y el primer paso formal hacia la certificación con **CLF-C02**. Estos conocimientos combinan lo teórico con lo práctico para asegurar un uso eficiente, optimizado y profesional de la nube.

---

## 9. Glosario Clave (Para repaso rápido)

| Término | Definición rápida |
| :--- | :--- |
| **On-Demand** | Pago por uso estricto, sin compromisos a largo plazo. |
| **Reserved Instances** | Compromiso de 1 a 3 años para obtener grandes ahorros en cargas estables. |
| **Spot Instances** | Uso de capacidad ociosa de AWS a bajo costo, con riesgo de interrupción. |
| **Savings Plans** | Compromiso de gasto mínimo por hora que otorga gran flexibilidad y ahorro. |
| **Billing Dashboard / Cost Explorer / Budgets** | Herramientas del ecosistema de AWS para visualizar, analizar y controlar gastos. |
| **SLA** | Acuerdo formal de nivel de servicio que garantiza la disponibilidad de los recursos. |
| **TCO (Total Cost of Ownership)** | Cálculo financiero que revela los costos reales y totales de una infraestructura. |
| **AWS Pricing Calculator** | Herramienta de estimación previa de costos para planificar soluciones. |
| **CLF-C02** | Examen de certificación inicial que valida los conocimientos básicos de AWS. |
| **AWS Skill Builder** | Plataforma oficial de capacitación y entrenamiento de AWS. |