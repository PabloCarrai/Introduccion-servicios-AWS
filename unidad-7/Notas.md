# 🛡️ Resumen Detallado para Estudiar: Seguridad, Identidad y Monitoreo en AWS

---

## 1. AWS Identity and Access Management (IAM)

* **Qué es:** Servicio que controla el acceso a recursos AWS. Permite definir *quién* accede y *qué acciones* puede realizar.
* **Componentes principales:**
  * 👤 **Usuarios:** Personas o aplicaciones con credenciales únicas (contraseña para consola, *Access Key* para API/CLI).
  * 👥 **Grupos:** Agrupan usuarios para asignar permisos colectivamente, facilitando la administración.
  * 📜 **Políticas:** Documentos JSON que definen permisos (qué acciones están permitidas o denegadas, sobre qué recursos y bajo qué condiciones).
  * 🛡️ **Roles:** Identidades temporales que pueden ser asumidas por usuarios o servicios. No tienen credenciales permanentes y se usan para delegar permisos, acceso entre cuentas o acceso temporal a servicios (ej. EC2 accediendo a S3).
* **Seguridad:** 
  * Se aplica la regla de **"no acceso por defecto"**: ningún usuario tiene permisos hasta que se le asignan explícitamente.
  * 📱 **MFA (Autenticación Multifactor):** Requiere un segundo factor (ej. código desde app) para autenticar; muy recomendado para usuarios administradores y la cuenta *root*.

> **💡 Buenas prácticas de IAM:**
> * No usar la cuenta *root* para tareas diarias.
> * Crear usuarios individuales (nunca compartir credenciales).
> * Asignar permisos a grupos, no a usuarios directamente.
> * Aplicar el principio de menor privilegio.
> * Habilitar MFA.
> * Rotar credenciales periódicamente.

---

## 2. Principio de Menor Privilegio

* **Qué es:** Otorgar únicamente los permisos estrictamente necesarios para realizar una tarea, ni más ni menos.
* **Importancia:** Minimiza riesgos de accesos indebidos, errores humanos o escalamiento de privilegios que podrían comprometer datos o servicios.
* **Aplicación en AWS:**
  * Crear políticas específicas, evitando permisos amplios o genéricos (`*`).
  * Asignar permisos según funciones y responsabilidades (ej. separar desarrolladores de administradores).
  * Utilizar roles para servicios en lugar de credenciales estáticas.
  * Empezar con un esquema de mínimos permisos e ir ampliando solo si es estrictamente necesario.

---

## 3. AWS Organizations

* **Para qué sirve:** Facilita administrar múltiples cuentas AWS de forma centralizada. Es ideal para separar entornos (desarrollo, pruebas, producción), equipos o proyectos.
* **Estructura:**
  * 🏛️ **Cuenta de administración:** Cuenta principal que controla la organización.
  * 🏢 **Cuentas miembro:** Cuentas separadas para distintos usos.
  * 🗂️ **Unidades Organizativas (OUs):** Agrupaciones jerárquicas dentro de la organización para aplicar políticas y administrar mejor.
* **Ventajas:**
  * Centraliza y consolida la facturación.
  * Aplica **Políticas de Control de Servicios (SCP)** para restringir permisos a nivel de toda la organización.
  * Mejora sustancialmente la seguridad y el control.

---

## 4. Monitoreo y Auditoría: CloudWatch vs. CloudTrail

### 📈 Amazon CloudWatch
* Servicio de monitoreo **en tiempo real**.
* Recopila métricas de rendimiento (uso de CPU, memoria), logs y eventos.
* Permite configurar alarmas y acciones automáticas.
* **Enfoque:** Rendimiento y estado operativo de los recursos.

### 🕵️‍♂️ AWS CloudTrail
* Servicio de **auditoría** que registra todas las acciones realizadas en la cuenta (*quién hizo qué, cuándo y desde dónde*).
* Esencial para la trazabilidad, detección de accesos no autorizados e investigaciones de incidentes.
* **Enfoque:** Actividad administrativa y cambios de API.

> **⚖️ Diferencia clave:** 
> * **CloudWatch** mira el *rendimiento y estado técnico*. 
> * **CloudTrail** mira la *actividad y las acciones* de los usuarios/servicios. *(Su uso conjunto ofrece una visión 360°).*

---

## 5. AWS Config

* **Qué es:** Servicio para el seguimiento y auditoría de configuraciones de recursos a lo largo del tiempo.
* **Funcionalidad:**
  * Mantiene un historial detallado de configuraciones y sus cambios.
  * Permite definir reglas de configuración para evaluar el cumplimiento de políticas internas o normativas de la industria.
  * Ayuda a detectar desviaciones (*drift*) o configuraciones inseguras de manera temprana.
* **Diferencia con los anteriores:** CloudTrail registra *acciones*, CloudWatch monitorea *rendimiento*, y AWS Config monitorea la *evolución y estado de la configuración*.

---

## 6. Protección Avanzada: AWS Shield y AWS KMS

* 🛡️ **AWS Shield:**
  * Servicio que protege contra ataques de denegación de servicio (**DDoS**) para garantizar la disponibilidad.
  * *Shield Standard:* Gratuito y de protección básica automática.
  * *Shield Advanced:* Protección profunda con monitoreo avanzado y soporte especializado.
* 🔑 **AWS Key Management Service (KMS):**
  * Servicio para administrar claves de cifrado y proteger datos en reposo y en tránsito.
  * Permite crear, controlar y auditar el uso de las claves.
  * Se integra de forma nativa con servicios como S3, RDS y EBS.

---

## 7. 📌 Resumen: Puntos Clave para Recordar

* Gestiona identidades estrictamente mediante **IAM** (usuarios, grupos, roles y políticas).
* Aplica siempre el **principio de menor privilegio**.
* Utiliza **AWS Organizations** para escalar el control en múltiples cuentas.
* Monitorea la salud con **CloudWatch** y audita la actividad con **CloudTrail**.
* Supervisa los cambios de infraestructura con **AWS Config**.
* Protege la infraestructura contra DDoS con **Shield** y asegura los datos mediante el cifrado de **KMS**.
* Activa **MFA** en cuentas críticas y evita el uso cotidiano de la cuenta *root*.

---

## 8. 📖 Glosario / Terminología Clave

* **IAM User:** Persona o aplicación con credenciales de acceso a AWS.
* **IAM Group:** Conjunto de usuarios que comparten un set común de permisos.
* **IAM Role:** Identidad asumible de forma temporal, ideal para servicios o federación, sin credenciales permanentes.
* **Policy:** Documento estructurado en JSON que define explícitamente los permisos.
* **MFA:** Autenticación multifactor (capa adicional de seguridad).
* **SCP (Service Control Policy):** Políticas de control de servicios utilizadas en AWS Organizations para fijar límites máximos de permisos.