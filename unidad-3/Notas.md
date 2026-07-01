---

## 1. Amazon EC2 (Elastic Compute Cloud)

### ¿Qué es?
Servicio de **Infraestructura como Servicio (IaaS)** que permite crear y gestionar servidores virtuales (*instancias*) en la nube de AWS. Cada instancia funciona como un servidor físico con su propio sistema operativo (SO), CPU, memoria, almacenamiento y red, pero ejecutado sobre la infraestructura global de AWS.

### Usos comunes
* **Hospedaje de aplicaciones empresariales** con control total y acceso raíz al sistema operativo.
* **Entornos de desarrollo y pruebas** rápidos y descartables.
* **Migración de cargas de trabajo** directamente desde entornos locales (*on-premises*).
* **Ejecución de aplicaciones legacy** que no están adaptadas o listas para entornos serverless o de contenedores.
* **Computación de alto rendimiento (HPC)**, procesamiento por lotes (*batch*) y simulaciones complejas.
* **Servidores web** escalables y de alta disponibilidad.

### Componentes principales
* **Instancia EC2:** El servidor virtualizado en sí mismo.
* **AMI (Amazon Machine Image):** Plantilla preconfigurada que contiene el sistema operativo, servidor de aplicaciones y software base necesario para lanzar la instancia.

### Ventajas
* **Escalabilidad bajo demanda:** Capacidad de lanzar, detener o cambiar el tamaño de los recursos en cuestión de minutos.
* **Pago por uso:** Facturación precisa (por segundo en la mayoría de las distribuciones Linux).
* **Diversidad de familias:** Tipos de instancias optimizados para distintas necesidades (cómputo, memoria, almacenamiento, GPU).
* **Alta disponibilidad:** Despliegue sencillo a través de múltiples Zonas de Disponibilidad (AZ).
* **Integración nativa:** Conexión fluida con el ecosistema AWS (S3, RDS, ELB, IAM, etc.).

---

## 2. Escalabilidad y Alta Disponibilidad en AWS

### Auto Scaling
Ajusta de forma automática y dinámica el número de instancias EC2 operativas según la demanda actual del tráfico. Esto garantiza un **rendimiento óptimo** en picos de carga y una **reducción drástica de costos** durante periodos de inactividad.

### Elastic Load Balancing (ELB)
Distribuye el tráfico entrante de las aplicaciones de forma equitativa entre múltiples objetivos (instancias EC2, contenedores o funciones Lambda). 

#### Tipos de Balanceadores:
* **Application Load Balancer (ALB):** Diseñado para tráfico HTTP/HTTPS. Permite enrutamiento avanzado basado en reglas de capa 7 (rutas, subdominios).
* **Network Load Balancer (NLB):** Optimizado para conexiones TCP/UDP de ultra alta performance y baja latencia (capa 4).
* **Gateway Load Balancer (GWLB):** Diseñado para desplegar, escalar y gestionar dispositivos virtuales de terceros (como firewalls o sistemas de prevención de intrusos).

> 💡 **Nota sobre Alta Disponibilidad:** ELB realiza *health checks* (verificaciones de estado) constantes para redirigir el tráfico únicamente a los objetivos saludables, mitigando fallos de infraestructura automáticamente.

---

## 3. Contenedores en AWS: Amazon ECS y AWS Fargate

Los **contenedores** empaquetan el código de una aplicación junto con todas sus dependencias, librerías y configuraciones, asegurando una portabilidad absoluta y una ejecución consistente en cualquier entorno.

### Amazon ECS (Elastic Container Service)
* Servicio de orquestación altamente escalable para ejecutar y administrar contenedores de Docker.
* Se basa en la definición de **Tasks (Tareas)**, que especifican las imágenes de los contenedores, límites de CPU/memoria, variables de entorno y puertos.
* Gestiona de manera automática el ciclo de vida, despliegues, actualizaciones y el escalado de los contenedores.
* Integrado con el ecosistema de seguridad y monitoreo: IAM, AWS ELB, Amazon CloudWatch y Amazon ECR.

### AWS Fargate
* Motor de computación **Serverless** para contenedores que elimina por completo la necesidad de aprovisionar, configurar o administrar servidores físicos o clústeres de EC2.
* Ajusta los recursos de forma automatizada según la demanda del contenedor.
* **Modelo de pago por uso real** basado estrictamente en los vCPU y la memoria consumida por segundo.
* Aislamiento nativo por tarea a nivel de kernel, proporcionando una seguridad robustez por diseño.

### Comparativa: ECS clásico (sobre EC2) vs. AWS Fargate

| Aspecto | ECS (con Instancias EC2) | AWS Fargate (Serverless) |
| :--- | :--- | :--- |
| **Gestión de Infraestructura** | El usuario administra, actualiza y parchea las instancias EC2 subyacentes. | AWS administra la infraestructura. No hay servidores que gestionar. |
| **Configuración** | Control absoluto sobre el tipo de instancia, almacenamiento y red. | Configuración simplificada; solo se definen los vCPU y la memoria de la tarea. |
| **Escalabilidad** | Limitada por la capacidad disponible en el clúster de instancias EC2. | Escalado automático, instantáneo y nativo a nivel de contenedor. |
| **Modelo de Pago** | Se paga por las instancias EC2 activas, independientemente de su uso real. | Se paga exclusivamente por los recursos consumidos por las tareas en ejecución. |
| **Casos de Uso Ideales** | Requerimientos de personalización extrema del SO o políticas de red complejas. | Microservicios, APIs dinámicas, tareas programadas e infraestructuras ágiles. |

---

## 4. AWS Lambda (Serverless)

### ¿Qué es?
Servicio de computación **Serverless** basado en funciones (FaaS) que permite ejecutar código en respuesta a eventos directos sin necesidad de aprovisionar, administrar ni mantener servidores activos.

* **Modelo de Facturación:** Pago estricto por el tiempo de ejecución (medido en milisegundos) y los recursos de memoria asignados. Cero costos cuando el código no se está ejecutando.
* **Lenguajes Soportados Nativamente:** Python, Node.js, Java, Go, Ruby, C# y runtimes personalizados.

### Mecanismos de Activación (Triggers)
Lambda se dispara automáticamente mediante eventos procedentes de otros servicios de AWS, como por ejemplo:
* Carga de archivos en **Amazon S3**.
* Mensajes entrantes en colas de **Amazon SQS** o tópicos de **Amazon SNS**.
* Solicitudes HTTP a través de **Amazon API Gateway**.
* Cambios en tablas de **Amazon DynamoDB**.
* Eventos programados cronológicamente mediante **Amazon EventBridge**.

### Usos comunes
* Procesamiento de datos y transformación de archivos en tiempo real (ej. compresión de imágenes al subirse a S3).
* Automatización de flujos de trabajo e infraestructuras de TI.
* Backend para APIs RESTful ligeras y arquitecturas de microservicios.
* Integración de sistemas distribuidos mediante arquitecturas orientadas a eventos.

### Limitaciones a Tener en Cuenta
* ⏳ **Tiempo máximo de ejecución:** 15 minutos por invocación.
* 🧠 **Memoria máxima:** 10 GB de RAM asignables.
* ❌ No está diseñado para cargas de trabajo de cómputo continuo, persistente o de muy largo plazo.

---

## 5. Resumen de Conceptos Clave y Recomendaciones

* **Amazon EC2:** Elija esta opción cuando requiera **control total** sobre la configuración del sistema operativo, compatibilidad con software heredado (*legacy*) o acceso directo al hardware.
* **Auto Scaling + ELB:** El binomio fundamental para garantizar la **alta disponibilidad**, resiliencia y distribución eficiente del tráfico en cualquier arquitectura web.
* **ECS y Fargate:** Simplifican el despliegue de arquitecturas de contenedores portables. **Fargate** destaca al remover la carga operativa de administración de servidores, siendo la opción predilecta para microservicios modernos.
* **AWS Lambda:** La máxima expresión de la filosofía *Serverless*. Ideal para ejecuciones efímeras guiadas por eventos, optimizando costos y escalando de manera automática desde cero hasta miles de solicitudes concurrentes.
