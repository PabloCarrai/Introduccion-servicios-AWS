# Introducción a Cloud Computing (Computación en la Nube)

Una guía completa sobre los fundamentos, características, modelos de servicio y despliegue de la computación en la nube.

---

## 📌 ¿Qué es Cloud Computing?

Básicamente, es el **consumo de servicios informáticos a través de Internet**. Tanto el hardware como el software son brindados por un proveedor especializado —como *Microsoft Azure*, *Amazon Web Services (AWS)* y *Google Cloud Platform (GCP)*— y el usuario los consume pagando exclusivamente por el uso que hace de ellos.

---

## 🚀 Características Principales

* **Autoservicio bajo demanda:** No se requiere la intervención del proveedor; el cliente accede y gestiona su servicio de forma autónoma según sus necesidades.
* **Acceso a través de la red:** Los servicios están disponibles de manera global a través de Internet desde cualquier dispositivo compatible.
* **Elasticidad y escalabilidad:** Los recursos se ajustan de manera rápida y automática (hacia arriba o hacia abajo) de acuerdo con la demanda del negocio.
* **Uso medido y facturación por consumo:** Se paga únicamente por los recursos informáticos realmente utilizados, similar a un servicio público.
* **Multitenencia (o multiarrendamiento):** Varios usuarios comparten la misma infraestructura física del proveedor, pero manteniendo sus datos y entornos completamente aislados y seguros.
* **Automatización:** Tareas esenciales como el mantenimiento, la actualización, el monitoreo y el escalamiento son ejecutadas de manera automatizada por la plataforma.

---

## 💡 Beneficios y Desventajas

### ✅ Beneficios
1. **Reducción de costos:** Elimina la necesidad de comprar hardware costoso, licencias y de disponer de espacio físico, lo que reduce drásticamente la inversión inicial.
2. **Mayor agilidad y rapidez en la innovación:** Permite adquirir nueva infraestructura bajo demanda en cuestión de minutos, agilizando el lanzamiento de nuevos productos al mercado.
3. **Escalabilidad global:** Capacidad para crecer o decrecer la potencia informática en segundos para adaptarse a audiencias globales.
4. **Foco en el negocio:** El proveedor se encarga de la gestión técnica y operativa de la infraestructura, permitiéndote concentrarte puramente en el desarrollo tecnológico y los objetivos de tu negocio.
5. **Colaboración eficiente:** La nube facilita el trabajo en equipo permitiendo el acceso y edición de documentos y sistemas en tiempo real desde cualquier lugar.

### ❌ Desventajas
1. **Dependencia de la conexión a Internet:** Es indispensable contar con un acceso a red estable para interactuar con los servicios.
2. **Seguridad y privacidad:** Al estar alojados en servidores de terceros, los datos no se encuentran bajo el control físico absoluto del usuario.
3. **Pérdida de control:** Se delega la gestión profunda de los sistemas y la infraestructura subyacente al proveedor.
4. **Costos a largo plazo:** Si no se gestionan de forma correcta los recursos, los costos pueden elevarse significativamente. La práctica de **FinOps** se encarga específicamente de optimizar estos gastos.
5. **Migración compleja:** Trasladar sistemas heredados (*legacy*) hacia la nube puede requerir un gran esfuerzo de rearquitectura.
6. **Vinculación con el proveedor (*Vendor Lock-in*):** Cambiar de un proveedor de nube a otro puede resultar difícil y costoso, por lo que es vital elegirlos cuidadosamente desde el inicio.

---

## 📐 Modelos de Servicio en la Nube (IaaS, PaaS, SaaS)

Los servicios se agrupan en tres grandes categorías según el nivel de control y abstracción que requiera el proyecto:

### 🧱 1. Infraestructura como Servicio (IaaS)
* **¿Qué es?:** Es el modelo más básico. El proveedor ofrece infraestructura de TI pura (servidores, almacenamiento, redes y virtualización) a través de Internet.
* **Uso ideal:** Se suele utilizar en proyectos que requieren entornos altamente personalizados, migraciones directas de servidores locales (*Lift and Shift*) o control total del sistema operativo.

### ⚙️ 2. Plataforma como Servicio (PaaS)
* **¿Qué es?:** El proveedor ofrece un entorno completo de desarrollo e implementación listo para usar, abstrayendo la gestión del sistema operativo y los servidores.
* **Uso ideal:** Ideal para desarrolladores. Permite concentrarse puramente en escribir código, administrar aplicaciones y bases de datos sin preocuparse por parches de seguridad ni mantenimiento de hardware.

### 💻 3. Software como Servicio (SaaS)
* **¿Qué es?:** El proveedor entrega aplicaciones informáticas completas y listas para su consumo final a través de un navegador web o aplicación.
* **Uso ideal:** Para usuarios finales que necesitan una solución inmediata sin involucrarse en el desarrollo ni en el despliegue técnico (ej. Microsoft 365, Gmail, Salesforce).

---

## 🤝 El Modelo de Responsabilidad Compartida

Este modelo define de forma clara **quién se hace cargo de qué** dentro del entorno de la nube. La responsabilidad varía drásticamente según el modelo de servicio elegido:

| Componente / Capa | Infraestructura (IaaS) | Plataforma (PaaS) | Software (SaaS) |
| :--- | :--- | :--- | :--- |
| **Infraestructura Física (Centros de Datos, Red)** | 🏢 Proveedor | 🏢 Proveedor | 🏢 Proveedor |
| **Sistemas Operativos y Entornos** | 👤 **Cliente** | 🏢 Proveedor | 🏢 Proveedor |
| **Lógica de la Aplicación** | 👤 **Cliente** | 👤 **Cliente** | 🏢 Proveedor |
| **Datos, Accesos y Seguridad de Usuarios** | 👤 **Cliente** | 👤 **Cliente** | 👤 **Cliente** |

* **En IaaS:** El proveedor se encarga de la infraestructura física; el cliente es responsable de todo lo que se ejecuta sobre ella (S.O., aplicaciones, configuraciones).
* **En PaaS:** El proveedor maneja la infraestructura, el S.O., las bases de datos y el entorno de ejecución. El cliente se encarga de la lógica de la aplicación y de sus datos.
* **En SaaS:** El proveedor se encarga de casi todo el ecosistema. El cliente solo gestiona el acceso de sus usuarios, las políticas básicas de seguridad y los datos que introduce en la plataforma.

---

## 🌐 Modelos de Despliegue

Hacen referencia a cómo se estructura, localiza y entrega la infraestructura en la nube según las necesidades normativas y de negocio:

### 🏛️ Nube Pública
Tanto los recursos de cómputo como los servidores son propiedad del proveedor y se accede a ellos a través de Internet de manera pública. Varios usuarios (*tenants*) comparten la infraestructura física, aunque lógicamente se encuentra totalmente aislada, cifrada y segura.

### 🔒 Nube Privada
Es de uso exclusivo para una sola organización. Los recursos informáticos no se comparten con ningún otro cliente. Puede estar alojada físicamente en el centro de datos local de la empresa (*On-Premise*) o ser gestionada externamente por un tercero, brindando el máximo nivel de control y cumplimiento regulatorio.

### 🔀 Nube Híbrida
Combina de forma inteligente entornos de nube pública y nube privada, permitiendo que los datos y las aplicaciones se compartan entre ellas. Es ideal para empresas que desean mantener datos altamente sensibles en un entorno privado, pero aprovechar la escalabilidad masiva de la nube pública para aplicaciones web generales.