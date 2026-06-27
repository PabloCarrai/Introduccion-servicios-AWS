```markdown
# ☁️ AWS Cloud Fundamentals
> **Módulo 1 · Unidad 2:** Introducción a AWS y su Infraestructura Global  
> *Apuntes optimizados para documentación técnica, despliegues y aprendizaje estructurado.*

---

## 📌 Índice de Contenidos
1. [¿Qué es AWS?](#1-qué-es-aws)
2. [Diferenciadores de AWS](#2-diferenciadores-de-aws-frente-a-otros-proveedores)
3. [Infraestructura Global](#3-infraestructura-global-de-aws)
4. [Infraestructura Física vs. Lógica](#4-infraestructura-física-y-lógica)
5. [AWS Management Console](#5-aws-management-console)
6. [Capa Gratuita (Free Tier)](#6-registro-y-capa-gratuita-free-tier-de-aws)
7. [Conclusión](#-conclusión)

---

## 1. ¿Qué es AWS?

**Amazon Web Services (AWS)** es la plataforma de *cloud computing* líder a nivel mundial. Proporciona una infraestructura tecnológica robusta y completamente automatizada bajo demanda a través de Internet, eliminando la necesidad de adquirir, configurar y mantener hardware local o centros de datos físicos.

```text
[Lanzamiento]  2006
[Catálogo]     +200 Servicios Integrales
[Ecosistema]   Computación, Almacenamiento, IA/ML, IoT, Bases de Datos, Analítica

```

* **Innovación Continua:** Permite a startups y corporaciones globales desplegar entornos complejos en minutos.
* **Modelo Híbrido:** Soporta de manera nativa la interconexión con infraestructuras locales preexistentes.

---

## 2. Diferenciadores de AWS frente a otros proveedores

AWS se destaca en el mercado gracias a tres ventajas competitivas críticas:

### 🚀 A. Amplitud y Rapidez de Innovación

Fue el pionero indiscutible de la nube pública y mantiene el catálogo más maduro de servicios gestionados. Desarrolla su propio hardware a medida (como los procesadores *AWS Graviton*) para maximizar el rendimiento por dólar. Sus pilares históricos incluyen:

* **Amazon S3:** Almacenamiento de objetos con durabilidad del 99.999999999% (11 nueves).
* **Amazon EC2:** Capacidad de cómputo seguro y escalable mediante instancias virtuales.
* **AWS Lambda:** Ejecución de código basada en eventos bajo el paradigma *Serverless*.

### 🌍 B. Escala Global y Resiliencia

Su arquitectura está diseñada desde los cimientos para soportar fallos masivos sin interrupción del servicio. Dispone de docenas de regiones interconectadas por una red privada de fibra óptica de alta velocidad exclusiva de Amazon.

### 👥 C. Ecosistema y Comunidad

Posee la mayor red de ingenieros, arquitectos de soluciones y consultoras *partners* del mundo. Esto reduce la curva de aprendizaje y acelera los procesos de migración empresarial.

---

## 3. Infraestructura Global de AWS

La infraestructura de AWS se divide jerárquicamente para ofrecer redundancia geográfica y aislamiento absoluto de fallos:

```text
┌───────────────────────────────────────────────────────────────┐
│              🌎 INFRAESTRUCTURA GLOBAL DE AWS                 │
└───────────────────────────────┬───────────────────────────────┘
                                │
         ┌──────────────────────┴──────────────────────┐
         ▼                                             ▼
 📍 Regiones de AWS                            🛡️ Regiones Especiales
 (Ej: us-east-1, eu-west-1)                    (GovCloud / Militares)
         │
         ├─► 🏢 Zona de Disponibilidad A (AZ) ──► [Centros de Datos]
         ├─► 🏢 Zona de Disponibilidad B (AZ) ──► [Centros de Datos]
         └─► 🏢 Zona de Disponibilidad C (AZ) ──► [Centros de Datos]

```

* **Regiones:** Ubicaciones geográficas independientes en el mundo. Alojan múltiples zonas de disponibilidad físicamente separadas para cumplir con regulaciones locales de datos y reducir la latencia.
* **Zonas de Disponibilidad (AZ):** Uno o más centros de datos discretos dentro de una región. Cada uno cuenta con alimentación eléctrica redundante, sistemas de refrigeración independientes y conectividad de red de ultra baja latencia.
* **Regiones Especiales:** Entornos aislados criptográficamente y físicamente para agencias gubernamentales con estrictos controles de cumplimiento (ej. *ITAR, FedRAMP High*).

---

## 4. Infraestructura Física y Lógica

La separación de estas dos capas define la flexibilidad y la agilidad de la computación en la nube:

| Capa / Dimensión | Componentes Tecnológicos | Garantías y Abstracción |
| --- | --- | --- |
| **🧱 Infraestructura Física** | • Servidores de alta densidad.<br>

<br>• Redes de fibra de baja latencia.<br>

<br>• Generadores de respaldo.<br>

<br>• Seguridad biométrica. | **Seguridad y Cumplimiento:**<br>

<br>Respaldada por auditorías internacionales estrictas: *ISO 27001, SOC 1/2/3, GDPR y PCI DSS*. |
| **⚙️ Infraestructura Lógica** | • Instancias virtuales (**EC2**).<br>

<br>• Almacenamiento (**S3**).<br>

<br>• Redes virtuales (**VPC**).<br>

<br>• Gestión de accesos (**IAM**). | **Elasticidad y Automatización:**<br>

<br>Control total mediante software, permitiendo auto-escalado, backups automáticos y despliegues Multi-AZ. |

> 🔄 **La Sinergia:** El usuario final opera exclusivamente sobre la **Infraestructura Lógica**. AWS gestiona, actualiza y repara la **Infraestructura Física**. Si un componente de hardware falla a nivel físico, los mecanismos lógicos migran la carga de trabajo automáticamente a otro nodo sin que el cliente note degradación alguna.

---

## 5. AWS Management Console

La consola de AWS actúa como el centro de mando operativo de toda la infraestructura del cliente:

* **Interfaz Web:** Panel intuitivo y gráfico idóneo para la experimentación, configuración inicial y monitoreo visual de recursos en tiempo real.
* **Automatización Profesional:** Se complementa con herramientas avanzadas para la integración en metodologías DevOps:
* **AWS CLI:** Control absoluto mediante comandos de terminal y scripts automatizables.
* **AWS CloudFormation:** Framework nativo de **Infraestructura como Código (IaC)** que permite definir arquitecturas completas mediante archivos declarativos en formato JSON o YAML.



---

## 6. Registro y Capa Gratuita (Free Tier) de AWS

Para remover barreras de entrada y potenciar el autoaprendizaje, AWS incluye un beneficio de **12 meses de acceso gratuito** limitado a ciertos umbrales de uso.

### 📊 Cuotas de Consumo Mensual Incluidas

```yaml
# AWS Free Tier - Límites mensuales principales
Amazon_EC2:
  Tiempo: "750 Horas"
  Familias: "t2.micro / t3.micro"
  Uso: "Suficiente para mantener 1 instancia activa 24/7"

Amazon_S3:
  Capacidad: "5 GB de almacenamiento estándar"
  Solicitudes: "20,000 peticiones GET y 2,000 peticiones PUT"

Amazon_RDS:
  Tiempo: "750 Horas de Base de Datos Gestionada"
  Capacidad: "20 GB de almacenamiento SSD para datos"

AWS_Lambda:
  Peticiones: "1,000,000 de solicitudes gratis al mes"
  Computo: "400,000 GB-segundos (Siempre gratuito)"

```

---

## 💡 Conclusión

La **Unidad 2** establece los cimientos conceptuales indispensables sobre los que descansa toda la ingeniería de la nube en AWS. Comprender el funcionamiento de las **Regiones**, las **Zonas de Disponibilidad (AZ)** y la disociación entre la **capa física y lógica** permite diseñar sistemas resilientes, con tolerancia a fallos de nivel empresarial y con una alta eficiencia de costes.

Dominar estos pilares facilita el aprendizaje inmediato de los servicios de cómputo avanzado, microservicios y contenedores de los siguientes módulos.

---

*📚 Documento de estudio estructurado · Curso AWS Cloud Fundamentals.*

```

```
