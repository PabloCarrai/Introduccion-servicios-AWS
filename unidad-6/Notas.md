# Resumen Completo de la Unidad 6: Almacenamiento Avanzado y Bases de Datos en AWS

## 1. Introducción y Objetivos Generales

Esta unidad profundiza en los principales servicios de almacenamiento y gestión de datos en AWS, enfatizando características avanzadas para asegurar, escalar y optimizar el manejo de la información en la nube. 

### Temas abordados
- Funcionalidades avanzadas de **Amazon S3**
- Tipos de almacenamiento en AWS: **bloque** y **archivos**
- Uso de **AWS Backup** para protección y recuperación de datos
- Bases de datos relacionales con **Amazon RDS**
- Bases de datos NoSQL con **DynamoDB**
- Comparación entre modelos relacionales y NoSQL para diversas aplicaciones

> **Objetivo:** Que los participantes comprendan las capacidades de estos servicios, sus ventajas y casos de uso para tomar decisiones informadas en la arquitectura de soluciones en AWS.

---

## 2. Amazon S3 Avanzado

Amazon S3 es uno de los servicios más utilizados en AWS para almacenar objetos en la nube, destacando por su escalabilidad y alta disponibilidad.

### Funcionalidades Avanzadas

* **Versionado (*Versioning*):**  
  Permite mantener múltiples versiones de un mismo objeto. Cada cambio o eliminación crea una versión adicional en lugar de sobrescribir el archivo. 
  * *Recuperación:* Ayuda a restaurar datos ante errores humanos o cambios accidentales.
  * *Delete Marker:* Al eliminar un archivo, S3 coloca una marca de borrado (*delete marker*), ocultando la versión actual sin eliminar las versiones anteriores.

* **Políticas de ciclo de vida (*Lifecycle Policies*):**  
  Reglas automáticas para mover objetos a diferentes clases de almacenamiento (ej. acceso infrecuente o archivo/Glacier) o eliminarlos tras un período determinado, optimizando costos a largo plazo.

* **Políticas de bucket (*Bucket Policies*):**  
  Configuraciones en formato JSON que controlan quién puede acceder a los buckets y qué acciones específicas puede realizar cada usuario.

> **Buenas prácticas:** Gestionar correctamente las políticas de acceso, sincronizar versiones y automatizar la eliminación o archivado de objetos antiguos.

---

## 3. Tipos de Almacenamiento en AWS

AWS ofrece distintos modelos de almacenamiento según los requerimientos del sistema:

### a) Almacenamiento en Bloque: Amazon EBS (*Elastic Block Store*)
- Organizado en bloques de tamaño fijo, accesibles desde el sistema operativo.
- Se utiliza principalmente adjunto a instancias **EC2**, funcionando como discos duros virtuales.
- **Ventajas:**
  - Baja latencia y alto rendimiento.
  - Persistencia independiente de la vida de la instancia EC2.
  - Soporte de *snapshots* para respaldo.
- **Casos de uso:** Bases de datos relacionales, sistemas operativos y aplicaciones con acceso rápido y constante a disco.

### b) Almacenamiento de Archivos: Amazon EFS (*Elastic File System*)
- Organiza los datos en una estructura jerárquica de carpetas y archivos.
- Se puede montar en múltiples instancias EC2 de manera simultánea para compartir datos.
- **Casos de uso:** Ambientes distribuidos, servidores de archivos web y aplicaciones que requieren acceso compartido en tiempo real.

| Tipo de Almacenamiento | Servicio AWS | Nivel de Acceso | Caso Uso Principal |
| :--- | :--- | :--- | :--- |
| **Bloque** | Amazon EBS | Disco / Sistema Operativo | SO, Bases de Datos |
| **Archivos** | Amazon EFS | Red / Archivos Compartidos | Servidores Web, Archivos Compartidos |

---

## 4. AWS Backup

Solución centralizada para automatizar y gestionar copias de seguridad en los servicios de AWS.

- **Backup Plans:** Permiten definir políticas sobre cuándo y cómo se realizan las copias.
- **Protección Multirecurso:** Automatiza la protección de EC2, RDS, EFS, DynamoDB, entre otros.
- **Mecanismos de Protección:**
  - Backups automáticos y *snapshots* manuales.
  - Cifrado automático y control de acceso mediante **AWS IAM**.
  - Protección contra eliminación accidental.
  - Copia entre regiones (*Cross-Region Copy*) para resiliencia ante desastres.
- **Point-in-Time Recovery (PITR):** Permite restaurar los datos a un segundo exacto dentro del período de retención configurado.

---

## 5. Bases de Datos Relacionales: Amazon RDS

Amazon RDS es un servicio gestionado que facilita la configuración, operación y escalado de bases de datos relacionales.

### Características Principales
- **Motores soportados:** MySQL, PostgreSQL, MariaDB, Oracle, SQL Server y Amazon Aurora.
- **Respaldos:** Backups automáticos y *snapshots* manuales.
- **Alta Disponibilidad (Multi-AZ):** Replica la base de datos sincrónicamente en otra Zona de Disponibilidad. En caso de fallo, AWS ejecuta un *failover* automático.
- **Seguridad:** Cifrado en reposo/tránsito y control de acceso con IAM.

### Casos de Uso
- Aplicaciones web y móviles.
- Sistemas ERP y CRM.
- Plataformas de e-commerce.
- Aplicaciones que requieren consistencia fuerte y transacciones **ACID**.

---

## 6. Bases de Datos NoSQL: Amazon DynamoDB

Servicio completamente gestionado de base de datos NoSQL diseñado para cargas de trabajo masivas con latencia ultra baja.

- **Modelo de datos:** Clave-valor y documentos JSON.
- **Ventajas:**
  - Escalabilidad automática y casi ilimitada.
  - Tiempos de respuesta de un solo dígito en milisegundos.
  - Soporte de *backups on-demand* y PITR.
  - Integración nativa con arquitecturas *Serverless* (ej. AWS Lambda).
- **Casos de uso:** Juegos en línea, aplicaciones IoT, captura de eventos masivos y sistemas distribuídos de alta escala.

> **Limitación:** No está optimizado para relaciones complejas, *joins* o esquemas altamente normalizados (en estos casos es preferible RDS).

---

## 7. Comparativa: RDS vs. DynamoDB

| Aspecto | Amazon RDS | Amazon DynamoDB |
| :--- | :--- | :--- |
| **Modelo de Datos** | Relacional (SQL, tablas, esquemas fijos) | NoSQL (Clave-Valor, Documento) |
| **Complejidad** | Datos estructurados, relaciones complejas, transacciones ACID | Datos semi-estructurados, escalabilidad masiva |
| **Escalabilidad** | Vertical (escalar instancia) y Read Replicas | Horizontal, automática y casi ilimitada |
| **Consultas** | SQL complejo (Joins, agregaciones) | Operaciones simples por clave (sin Joins) |
| **Uso Típico** | Sistemas transaccionales, ERP, CRM, E-commerce | Apps en tiempo real, Juegos, IoT, Serverless |

---

## 8. Conclusión

1. **Estrategia de Almacenamiento:** Es clave diferenciar entre almacenamiento de objetos (S3), bloques (EBS) y archivos (EFS) según los requerimientos de acceso y rendimiento.
2. **Selección de Bases de Datos:** Depende de la naturaleza de los datos. **RDS** destaca en consistencia transaccional y relaciones complejas, mientras que **DynamoDB** resalta en velocidad, volumen y flexibilidad NoSQL.
3. **Gestión Integral:** La implementación de políticas de ciclo de vida en S3 y estrategias centralizadas con **AWS Backup** garantizan seguridad, alta disponibilidad y optimización de costos.

---

## 9. Glosario de Conceptos Clave

- **Amazon S3:** Servicio de almacenamiento de objetos escalable y seguro.
- **Versionado:** Control que preserva múltiples versiones de un archivo para evitar pérdidas accidentales.
- **Lifecycle Policies:** Reglas de automatización para mover o eliminar objetos en S3.
- **Bucket Policies:** Políticas de acceso basadas en JSON asignadas a un bucket de S3.
- **Amazon EBS:** Almacenamiento en bloque de alto rendimiento para instancias EC2.
- **Amazon EFS:** Sistema de archivos de red compartido para múltiples instancias.
- **AWS Backup:** Servicio para centralizar y automatizar respaldos en AWS.
- **Amazon RDS:** Servicio gestionado para bases de datos relacionales (SQL).
- **Multi-AZ:** Despliegue en múltiples Zonas de Disponibilidad para tolerancia a fallos.
- **Amazon DynamoDB:** Base de datos NoSQL gestionada de clave-valor y documento.
- **PITR (Point-in-Time Recovery):** Capacidad de restauración de datos a un segundo específico en el tiempo.