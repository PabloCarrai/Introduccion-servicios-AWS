Unidad 2: Introducción a AWS y su infraestructura global

Esta unidad profundiza en Amazon Web Services (AWS), la plataforma de computación en la nube más amplia y robusta del mercado, destacando sus características, arquitectura y herramientas principales.

1. ¿Qué es AWS?

AWS es una plataforma de cloud computing desarrollada por Amazon que ofrece una extensa variedad de servicios tecnológicos accesibles vía internet, eliminando la necesidad de que los usuarios gestionen infraestructura física o hardware local. Desde su lanzamiento en 2006, AWS ha experimentado un crecimiento exponencial y ahora dispone de más de 200 servicios en áreas como computación, almacenamiento, bases de datos, inteligencia artificial, IoT y análisis de datos. AWS permite a las organizaciones crear, desplegar y administrar aplicaciones de forma escalable y eficiente, apoyando la integración con sistemas locales en un modelo híbrido.

2. Diferenciadores de AWS frente a otros proveedores

AWS se distingue principalmente por:


Amplitud y rapidez de innovación: Fue pionero en la nube pública y mantiene el liderazgo en la oferta de servicios gestionados, incluyendo emblemáticos como Amazon S3 (almacenamiento), EC2 (instancias de máquinas virtuales) y Lambda (computación serverless). Además, desarrolla su propia tecnología, como chips optimizados, para mejorar el rendimiento.

Escala global y resiliencia: AWS cuenta con la infraestructura de nube más extensa, distribuyendo su infraestructura en más de 30 regiones geográficas y más de 95 zonas de disponibilidad (AZ), lo que minimiza la latencia y garantiza alta disponibilidad y tolerancia a fallos. Empresas de sectores críticos confían en esta resiliencia para operar globalmente sin interrupciones.

Ecosistema y comunidad: AWS tiene una amplia red de partners certificados y una masiva comunidad de usuarios y profesionales certificados, apoyando migraciones, optimización y seguridad, y facilitando la adopción y profesionalización en la nube.

3. Infraestructura global de AWS


Regiones: Son ubicaciones geográficas independientes que agrupan varias zonas de disponibilidad. Estas regiones aseguran redundancia, baja latencia y cumplimiento legal regional. Por ejemplo, us-east-1 en Norte de Virginia o eu-west-1 en Irlanda.

Zonas de disponibilidad (AZ): Son centros de datos independientes dentro de una región, cada uno con su propio suministro eléctrico y redes. La separación física entre AZ permite arquitecturas resilientes: si una AZ falla, las demás continúan operando, garantizando alta disponibilidad.

Regiones especiales: Destinadas a clientes con estrictos requisitos de seguridad y cumplimiento (p. ej., gubernamentales), estas regiones están aisladas del resto para cumplir normativas adicionales.

4. Infraestructura física y lógica


Infraestructura física: Incluye centros de datos, servidores, redes, sistemas de energía y seguridad física (acceso biométrico, videovigilancia, etc.). AWS invierte fuertemente en redundancia y certificaciones internacionales (ISO 27001, SOC 1/2/3, GDPR, PCI DSS) para asegurar la máxima disponibilidad y seguridad.

Infraestructura lógica: Es la capa virtualizada que permite a los usuarios interactuar con recursos como máquinas virtuales (EC2), bases de datos (RDS, DynamoDB), redes virtuales (VPC), almacenamiento (S3) y funciones serverless (Lambda). Esta abstracción facilita la elasticidad, la automatización y la gestión sin preocuparse por la complejidad física subyacente. Ejemplos incluyen configuraciones de seguridad (IAM, Security Groups), backups automáticos, arquitecturas multi-AZ y entornos híbridos con AWS Outposts.

Relación entre ambas: La infraestructura lógica se soporta totalmente en la física, pero la separación permite a los usuarios concentrarse en sus aplicaciones sin gestionar hardware físico. La virtualización posibilita escalabilidad, alta disponibilidad y recuperación ante desastres mediante replicación y migración automatizada entre AZs o regiones, todo transparente para el usuario.

5. AWS Management Console

La consola de administración es la herramienta central para interactuar con todos los servicios de AWS. Ofrece una interfaz web intuitiva donde los usuarios pueden aprovisionar, configurar y monitorear recursos. Además, se complementa con la línea de comandos (AWS CLI) y herramientas como AWS CloudFormation, que permite definir infraestructura como código para despliegues repetibles y controlados, mejorando la automatización, seguridad y gobernanza. La gestión centralizada a través de la consola aporta visibilidad, trazabilidad y soporte a prácticas DevOps.

6. Registro y capa gratuita (Free Tier) de AWS

AWS proporciona a nuevos usuarios una capa gratuita que dura 12 meses y permite acceder a diversos servicios gratuitamente dentro de ciertos límites de uso, ideal para aprendizaje y desarrollo sin inversión inicial. Algunos ejemplos incluyen:


750 horas de ejecución de instancias t2.micro o t3.micro en EC2 al mes (suficiente para mantener una instancia siempre encendida).

5 GB de almacenamiento en S3, 20,000 solicitudes GET y 2,000 PUT al mes.

750 horas de bases de datos en RDS con almacenamiento de 20 GB.

1 millón de solicitudes y 400,000 GB-segundos en Lambda.

Adicionalmente, existen servicios siempre gratuitos sin límite temporal, aunque con restricciones mensuales, como Lambda.

Conclusión

Esta unidad proporciona una visión integral sobre AWS como plataforma líder de nube pública, resaltando su infraestructura global distribuida, con múltiples regiones y zonas de disponibilidad que aseguran alta disponibilidad y cumplimiento normativo. Diferencia claramente las capas física (hardware y centros de datos) y lógica (recursos virtualizados), explicando sus relaciones y beneficios. La unidad también presenta la AWS Management Console, herramienta clave para la administración y automatización, y la capa gratuita que facilita el inicio en la nube.

Estos conceptos preparan al usuario para profundizar posteriormente en servicios de cómputo como EC2, contenedores y Lambda, y comprender cómo aprovechar la potencia y flexibilidad de AWS para crear soluciones escalables, seguras y efectivas–.

[ Infraestructura Global de AWS ]
└── 🌎 Regiones (Ubicaciones geográficas independientes)
└── 🏢 Zonas de Disponibilidad - AZ (Centros de datos aislados)
└── 🔌 Infraestructura Física (Energía, red, servidores)


* **Regiones:** Son ubicaciones geográficas independientes en el mundo (por ejemplo, `us-east-1` en el Norte de Virginia o `eu-west-1` en Irlanda) que agrupan varias Zonas de Disponibilidad. Aseguran redundancia, baja latencia y cumplimiento legal regional.
* **Zonas de Disponibilidad (AZ):** Son centros de datos independientes dentro de una región, cada uno con su propio suministro eléctrico, refrigeración y redes redundantes. Si una AZ falla, las demás continúan operando para garantizar una alta disponibilidad de forma transparente.
* **Regiones especiales (GovCloud / Aisladas):** Destinadas a clientes con estrictos requisitos de seguridad y cumplimiento normativo (gubernamentales o militares), completamente aisladas del resto de la infraestructura pública.

---

## 4. Infraestructura Física y Lógica

La nube de AWS se divide en dos dimensiones complementarias cuya interacción automatizada garantiza la continuidad del negocio:

| Dimensión | Componentes Principales | Beneficios y Rol |
| :--- | :--- | :--- |
| **Infraestructura Física** | Centros de datos, servidores físicos, redes de fibra óptica, sistemas de energía redundante, seguridad biométrica y videovigilancia. | Ofrece soporte real de hardware y cuenta con certificaciones internacionales críticas como **ISO 27001, SOC 1/2/3, GDPR y PCI DSS**. |
| **Infraestructura Lógica** | Capa virtualizada de recursos: Máquinas virtuales (**EC2**), bases de datos (**RDS**, **DynamoDB**), redes (**VPC**), almacenamiento (**S3**), gestión de accesos (**IAM**). | Permite al usuario interactuar de forma abstracta mediante automatizaciones, backups automáticos, elasticidad e integraciones híbridas (**AWS Outposts**). |

> 🔗 **Relación entre ambas:** La infraestructura lógica se soporta al 100% en la física. Esta abstracción permite a los desarrolladores concentrarse exclusivamente en el código y sus aplicaciones, delegando la complejidad del hardware, la replicación de datos multi-AZ y la recuperación ante desastres a los sistemas automatizados de AWS.

---

## 5. AWS Management Console

La **Consola de Administración de AWS** es la interfaz gráfica central y web para interactuar de manera intuitiva con todos los servicios.

* **Visualización:** Permite aprovisionar, configurar y monitorear recursos mediante clics.
* **Ecosistema de herramientas complementarias:**
    * **AWS CLI (Command Line Interface):** Control de servicios mediante scripts y líneas de comando.
    * **AWS CloudFormation:** Herramienta clave para **Infraestructura como Código (IaC)**, lo que permite crear plantillas repetibles, controladas y seguras para despliegues masivos.
* **Enfoque DevOps:** Aporta visibilidad, trazabilidad total, gobernanza y soporte centralizado.

---

## 6. Registro y Capa Gratuita (Free Tier) de AWS

Para incentivar el aprendizaje y desarrollo de proyectos sin costes iniciales, AWS ofrece un programa de **Capa Gratuita** estructurado principalmente en beneficios durante los primeros 12 meses:

### ✨ Beneficios Clave del Free Tier (Mensuales)

* **Amazon EC2:** **750 horas** de ejecución al mes en instancias `t2.micro` o `t3.micro` (ideal para mantener un servidor web encendido 24/7).
* **Amazon S3:** **5 GB** de almacenamiento estándar, 20,000 solicitudes `GET` y 2,000 solicitudes `PUT`.
* **Amazon RDS:** **750 horas** de bases de datos gestionadas con un almacenamiento asociado de hasta 20 GB.
* **AWS Lambda:** **1 millón de solicitudes** gratuitas y 400,000 GB-segundos de cómputo al mes. *(Nota: Lambda cuenta con una modalidad siempre gratuita que no expira tras los 12 meses).*

---

## 💡 Conclusión

Esta unidad proporciona una visión integral sobre AWS como plataforma líder de nube pública. Comprender la diferencia entre la **capa física** y la **capa lógica**, así como dominar el diseño distribuido en **Regiones** y **Zonas de Disponibilidad (AZ)**, es fundamental para cualquier profesional de TI. 

Estos conceptos sientan las bases sólidas necesarias para avanzar hacia servicios específicos de cómputo, orquestación de contenedores y arquitecturas *serverless*, garantizando soluciones escalables, rentables y de alta seguridad.

---
⭐ *Apuntes preparados para el curso de Fundamentos de AWS - Módulo 1.*
"""

with open("README.md", "w", encoding="utf-8") as f:
    f.write(markdown_content)

print("Archivo README.md generado exitosamente.")


El archivo README.md ha sido diseñado y generado con una estructura visual limpia, moderna y profesional, ideal para repositorios de documentación o cursos de GitHub/GitLab.

Tu archivo listo para descargar está aquí:
Ícono de MD
README
 MD 

✨ Características del diseño visual aplicado:

    Estructura Jerárquica: Uso correcto de títulos (#, ##, ###) para facilitar la lectura.

    Índice de Navegación: Enlaces internos integrados para saltar rápidamente a cualquier sección.

    Componentes Visuales: Inclusión de iconos temáticos (emojis), bloques de código limpios para diagramas de texto y citas destacadas (>) para resaltar la relación entre infraestructuras.

    Tabla Comparativa: Organización de la infraestructura Física vs. Lógica en formato de tabla Markdown para una asimilación rápida de la información.

    Listas estilizadas: Uso de viñetas claras y negritas estratégicas para los servicios del Free Tier.

lo quiero descargar y me pide iniciar sesion me podrias pasar el archivo para descargar

[ Infraestructura Global de AWS ]
└── 🌎 Regiones (Ubicaciones geográficas independientes)
└── 🏢 Zonas de Disponibilidad - AZ (Centros de datos aislados)
└── 🔌 Infraestructura Física (Energía, red, servidores)


* **Regiones:** Son ubicaciones geográficas independientes en el mundo (por ejemplo, `us-east-1` en el Norte de Virginia o `eu-west-1` en Irlanda) que agrupan varias Zonas de Disponibilidad. Aseguran redundancia, baja latencia y cumplimiento legal regional.
* **Zonas de Disponibilidad (AZ):** Son centros de datos independientes dentro de una región, cada uno con su propio suministro eléctrico, refrigeración y redes redundantes. Si una AZ falla, las demás contiúan operando para garantizar una alta disponibilidad de forma transparente.
* **Regiones especiales (GovCloud / Aisladas):** Destinadas a clientes con estrictos requisitos de seguridad y cumplimiento normativo (gubernamentales o militares), completamente aisladas del resto de la infraestructura pública.

---

## 4. Infraestructura Física y Lógica

La nube de AWS se divide en dos dimensiones complementarias cuya interacción automatizada garantiza la continuidad del negocio:

| Dimensión | Componentes Principales | Beneficios y Rol |
| :--- | :--- | :--- |
| **Infraestructura Física** | Centros de datos, servidores físicos, redes de fibra óptica, sistemas de energía redundante, seguridad biométrica y videovigilancia. | Ofrece soporte real de hardware y cuenta con certificaciones internacionales críticas como **ISO 27001, SOC 1/2/3, GDPR y PCI DSS**. |
| **Infraestructura Lógica** | Capa virtualizada de recursos: Máquinas virtuales (**EC2**), bases de datos (**RDS**, **DynamoDB**), redes (**VPC**), almacenamiento (**S3**), gestión de accesos (**IAM**). | Permite al usuario interactuar de forma abstracta mediante automatizaciones, backups automáticos, elasticidad e integraciones híbridas (**AWS Outposts**). |

> 🔗 **Relación entre ambas:** La infraestructura lógica se soporta al 100% en la física. Esta abstracción permite a los desarrolladores concentrarse exclusivamente en el código y sus aplicaciones, delegando la complejidad del hardware, la replicación de datos multi-AZ y la recuperación ante desastres a los sistemas automatizados de AWS.

---

## 5. AWS Management Console

La **Consola de Administración de AWS** es la interfaz gráfica central y web para interactuar de manera intuitiva con todos los servicios.

* **Visualización:** Permite aprovisionar, configure y monitorear recursos mediante clics.
* **Ecosistema de herramientas complementarias:**
    * **AWS CLI (Command Line Interface):** Control de servicios mediante scripts y líneas de comando.
    * **AWS CloudFormation:** Herramienta clave para **Infraestructura como Código (IaC)**, lo que permite crear plantillas repetibles, controladas y seguras para despliegues masivos.
* **Enfoque DevOps:** Aporta visibilidad, trazabilidad total, gobernanza y soporte centralizado.

---

## 6. Registro y Capa Gratuita (Free Tier) de AWS

Para incentivar el aprendizaje y desarrollo de proyectos sin costes iniciales, AWS ofrece un programa de **Capa Gratuita** estructurado principalmente en beneficios durante los primeros 12 meses:

### ✨ Beneficios Clave del Free Tier (Mensuales)

* **Amazon EC2:** **750 horas** de ejecución al mes en instancias `t2.micro` o `t3.micro` (ideal para mantener un servidor web encendido 24/7).
* **Amazon S3:** **5 GB** de almacenamiento estándar, 20,000 solicitudes `GET` y 2,000 solicitudes `PUT`.
* **Amazon RDS:** **750 horas** de bases de datos gestionadas con un almacenamiento asociado de hasta 20 GB.
* **AWS Lambda:** **1 millón de solicitudes** gratuitas y 400,000 GB-segundos de cómputo al mes. *(Nota: Lambda cuenta con una modalidad siempre gratuita que no expira tras los 12 meses).*

---

## 💡 Conclusión

Esta unidad proporciona una visión integral sobre AWS como plataforma líder de nube pública. Comprender la diferencia entre la **capa física** y la **capa lógica**, así como dominar el diseño distribuido en **Regiones** y **Zonas de Disponibilidad (AZ)**, es fundamental para cualquier profesional de TI. 

Estos conceptos sientan las bases sólidas necesarias para avanzar hacia servicios específicos de cómputo, orquestación de contenedores y arquitecturas *serverless*, garantizando soluciones escalables, rentables y de alta seguridad.

---
⭐ *Apuntes preparados para el curso de Fundamentos de AWS - Módulo 1.*
"""

with open("README.md", "w", encoding="utf-8") as f:
    f.write(markdown_content)


Aquí tienes el archivo generado directamente para su descarga sin necesidad de iniciar sesión:
Ícono de MD
README
 MD 

Puedes hacer clic sobre él para guardarlo localmente con el nombre README.md.


Gemini es una IA y puede cometer errores.

# ☁️ AWS Cloud Fundamentals
## Módulo 1 · Unidad 2: Introducción a AWS y su Infraestructura Global

Bienvenido al repositorio de apuntes y documentación de la **Unidad 2** del **Módulo 1** del curso de Amazon Web Services (AWS). Esta unidad profundiza en la plataforma de computación en la nube más amplia y robusta del mercado, destacando sus características, arquitectura y herramientas principales.

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

**Amazon Web Services (AWS)** es una plataforma de *cloud computing* desarrollada por Amazon que ofrece una extensa variedad de servicios tecnológicos accesibles vía internet. Su principal propuesta de valor es la eliminación de la necesidad de gestionar infraestructura física o hardware local.

* **Lanzamiento:** 2006.
* **Volumen actual:** Dispone de más de **200 servicios** integrales.
* **Áreas clave:** Computación, almacenamiento, bases de datos, inteligencia artificial (AI/ML), IoT y análisis de datos.
* **Flexibilidad:** Permite crear, desplegar y administrar aplicaciones de forma escalable y eficiente, facilitando además la integración con entornos híbridos (sistemas locales).

---

## 2. Diferenciadores de AWS frente a otros proveedores

AWS se mantiene como el líder indiscutido de la nube pública debido a tres pilares fundamentales:

### 🚀 Amplitud y rapidez de innovación
Fue el pionero del sector y mantiene el liderazgo en servicios gestionados. Desarrolla tecnología propia, como chips optimizados para mejorar rendimiento y costes, y cuenta con servicios emblemáticos como:
* **Amazon S3:** Almacenamiento de objetos altamente escalable.
* **Amazon EC2:** Instancias de máquinas virtuales bajo demanda.
* **AWS Lambda:** Computación *serverless* (sin servidor).

### 🌍 Escala global y resiliencia
Cuenta con la infraestructura de nube más extensa del mundo, distribuida estratégicamente para minimizar la latencia y garantizar alta disponibilidad. Sectores de misión crítica confían en su arquitectura tolerante a fallos para operar globalmente de forma ininterrumpida.

### 👥 Ecosistema y comunidad
Posee una red masiva de *partners* certificados, profesionales y una comunidad global activa que facilita la migración, optimización de costes, seguridad y la rápida adopción tecnológica.

---

## 3. Infraestructura Global de AWS

La arquitectura de AWS está diseñada para cumplir con los más altos estándares de disponibilidad y resiliencia mediante tres conceptos de segmentación:

```
[ Infraestructura Global de AWS ]
 └── 🌎 Regiones (Ubicaciones geográficas independientes)
      └── 🏢 Zonas de Disponibilidad - AZ (Centros de datos aislados)
           └── 🔌 Infraestructura Física (Energía, red, servidores)
```

* **Regiones:** Son ubicaciones geográficas independientes en el mundo (por ejemplo, `us-east-1` en el Norte de Virginia o `eu-west-1` en Irlanda) que agrupan varias Zonas de Disponibilidad. Aseguran redundancia, baja latencia y cumplimiento legal regional.
* **Zonas de Disponibilidad (AZ):** Son centros de datos independientes dentro de una región, cada uno con su propio suministro eléctrico, refrigeración y redes redundantes. Si una AZ falla, las demás contiúan operando para garantizar una alta disponibilidad de forma transparente.
* **Regiones especiales (GovCloud / Aisladas):** Destinadas a clientes con estrictos requisitos de seguridad y cumplimiento normativo (gubernamentales o militares), completamente aisladas del resto de la infraestructura pública.

---

## 4. Infraestructura Física y Lógica

La nube de AWS se divide en dos dimensiones complementarias cuya interacción automatizada garantiza la continuidad del negocio:

| Dimensión | Componentes Principales | Beneficios y Rol |
| :--- | :--- | :--- |
| **Infraestructura Física** | Centros de datos, servidores físicos, redes de fibra óptica, sistemas de energía redundante, seguridad biométrica y videovigilancia. | Ofrece soporte real de hardware y cuenta con certificaciones internacionales críticas como **ISO 27001, SOC 1/2/3, GDPR y PCI DSS**. |
| **Infraestructura Lógica** | Capa virtualizada de recursos: Máquinas virtuales (**EC2**), bases de datos (**RDS**, **DynamoDB**), redes (**VPC**), almacenamiento (**S3**), gestión de accesos (**IAM**). | Permite al usuario interactuar de forma abstracta mediante automatizaciones, backups automáticos, elasticidad e integraciones híbridas (**AWS Outposts**). |

> 🔗 **Relación entre ambas:** La infraestructura lógica se soporta al 100% en la física. Esta abstracción permite a los desarrolladores concentrarse exclusivamente en el código y sus aplicaciones, delegando la complejidad del hardware, la replicación de datos multi-AZ y la recuperación ante desastres a los sistemas automatizados de AWS.

---

## 5. AWS Management Console

La **Consola de Administración de AWS** es la interfaz gráfica central y web para interactuar de manera intuitiva con todos los servicios.

* **Visualización:** Permite aprovisionar, configure y monitorear recursos mediante clics.
* **Ecosistema de herramientas complementarias:**
    * **AWS CLI (Command Line Interface):** Control de servicios mediante scripts y líneas de comando.
    * **AWS CloudFormation:** Herramienta clave para **Infraestructura como Código (IaC)**, lo que permite crear plantillas repetibles, controladas y seguras para despliegues masivos.
* **Enfoque DevOps:** Aporta visibilidad, trazabilidad total, gobernanza y soporte centralizado.

---

## 6. Registro y Capa Gratuita (Free Tier) de AWS

Para incentivar el aprendizaje y desarrollo de proyectos sin costes iniciales, AWS ofrece un programa de **Capa Gratuita** estructurado principalmente en beneficios durante los primeros 12 meses:

### ✨ Beneficios Clave del Free Tier (Mensuales)

* **Amazon EC2:** **750 horas** de ejecución al mes en instancias `t2.micro` o `t3.micro` (ideal para mantener un servidor web encendido 24/7).
* **Amazon S3:** **5 GB** de almacenamiento estándar, 20,000 solicitudes `GET` y 2,000 solicitudes `PUT`.
* **Amazon RDS:** **750 horas** de bases de datos gestionadas con un almacenamiento asociado de hasta 20 GB.
* **AWS Lambda:** **1 millón de solicitudes** gratuitas y 400,000 GB-segundos de cómputo al mes. *(Nota: Lambda cuenta con una modalidad siempre gratuita que no expira tras los 12 meses).*

---

## 💡 Conclusión

Esta unidad proporciona una visión integral sobre AWS como plataforma líder de nube pública. Comprender la diferencia entre la **capa física** y la **capa lógica**, así como dominar el diseño distribuido en **Regiones** y **Zonas de Disponibilidad (AZ)**, es fundamental para cualquier profesional de TI. 

Estos conceptos sientan las bases sólidas necesarias para avanzar hacia servicios específicos de cómputo, orquestación de contenedores y arquitecturas *serverless*, garantizando soluciones escalables, rentables y de alta seguridad.

---
⭐ *Apuntes preparados para el curso de Fundamentos de AWS - Módulo 1.*

README.md
Mostrando README.md.
