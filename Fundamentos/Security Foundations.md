# Página 1

# 🎯 Security Objectives

> Los **Security Objectives** representan las propiedades de seguridad que una organización espera preservar sobre sus activos. Constituyen el fundamento sobre el cual se construyen los requisitos de seguridad, se evalúan los riesgos y se seleccionan los controles que protegerán una aplicación durante todo su ciclo de vida.

---

# 🎯 Objetivo

Comprender qué son los **Security Objectives**, por qué representan el punto de partida de Application Security y cómo se relacionan con conceptos como **Assets**, **Threats**, **Vulnerabilities**, **Risk** y **Security Controls**.

---

# 📖 Introducción

Application Security suele asociarse con vulnerabilidades como **SQL Injection**, **Cross-Site Scripting (XSS)** o **Broken Access Control**.

Sin embargo, desde una perspectiva de ingeniería, esas vulnerabilidades representan únicamente una parte del problema.

Antes de analizar vulnerabilidades, seleccionar herramientas o implementar controles, es necesario comprender **qué necesita ser protegido** y **por qué**.

Ese es precisamente el propósito de los **Security Objectives**.

Los objetivos de seguridad no describen tecnologías, productos ni mecanismos de protección.

Describen las propiedades que un sistema debe preservar para que continúe siendo confiable desde la perspectiva del negocio.

Esta distinción resulta fundamental.

Por ejemplo, **Encryption**, **Multi-Factor Authentication (MFA)**, **Input Validation** o un **Web Application Firewall (WAF)** no son objetivos de seguridad.

Son mecanismos utilizados para proteger determinados objetivos.

Comprender esta diferencia permite tomar decisiones de seguridad basadas en riesgo y no únicamente en la implementación de tecnologías.

---

# 🏗️ El punto de partida de Application Security

En Application Security, la seguridad no comienza con una vulnerabilidad.

Tampoco comienza con un control.

Comienza con un **activo**.

Toda aplicación existe para procesar, almacenar o transmitir información que posee algún valor para una organización.

Ese valor puede encontrarse en diferentes tipos de activos, por ejemplo:

- Información financiera.
- Datos personales (PII).
- Historias clínicas.
- Credenciales.
- Propiedad intelectual.
- Secretos comerciales.
- APIs críticas.
- Procesos de negocio.

Si un activo pierde valor como consecuencia de un incidente de seguridad, el negocio experimenta algún tipo de impacto.

Por ese motivo, el objetivo de Application Security no consiste únicamente en encontrar vulnerabilidades.

Su propósito es proteger aquellos activos cuyo compromiso tendría consecuencias para la organización.

---

# 🧩 Security Objectives como parte del proceso de diseño

Un error frecuente consiste en pensar inmediatamente en tecnologías de seguridad durante las primeras etapas de un proyecto.

Preguntas como las siguientes suelen aparecer muy temprano:

- ¿Necesitamos cifrar la base de datos?
- ¿Deberíamos implementar MFA?
- ¿Hace falta un WAF?
- ¿Necesitamos un SIEM?
- ¿Conviene utilizar OAuth?

Todas estas preguntas son válidas.

Sin embargo, ninguna puede responderse correctamente hasta comprender primero qué propiedades necesitan preservarse sobre los activos del sistema.

Desde una perspectiva de arquitectura, el proceso de análisis suele seguir un orden similar al siguiente.

```text
Comprender el negocio
          │
          ▼
Identificar los activos
          │
          ▼
Identificar amenazas
          │
          ▼
Identificar vulnerabilidades
          │
          ▼
Evaluar riesgos
          │
          ▼
Definir Security Objectives
          │
          ▼
Seleccionar Security Controls
```

Este enfoque permite justificar cada decisión técnica en función del riesgo que intenta reducir y evita incorporar controles innecesarios o insuficientes.

---

# 💡 Pensar como un Application Security Engineer

Una diferencia importante entre un enfoque reactivo y uno orientado al diseño consiste en el orden en que se analizan los problemas.

Un enfoque reactivo suele comenzar preguntando:

> **¿Cómo evitamos SQL Injection?**

Un ingeniero de Application Security normalmente comienza con una pregunta diferente.

> **¿Qué activo estamos intentando proteger?**

A partir de esa respuesta resulta posible identificar:

- Las amenazas que afectan al activo.
- Las vulnerabilidades que podrían ser explotadas.
- El riesgo asociado.
- El impacto para el negocio.
- Los objetivos de seguridad que deben preservarse.
- Los controles necesarios para reducir ese riesgo.

Este cambio de perspectiva transforma la seguridad de una actividad basada en vulnerabilidades hacia una disciplina de ingeniería orientada al riesgo y al diseño seguro.

Es precisamente esta forma de razonamiento la que sustenta actividades como **Threat Modeling**, **Secure Design**, **Risk Assessment** y **Security Architecture**.

---

Los conceptos desarrollados en este documento constituyen la base sobre la cual se construyen el resto de los temas de este repositorio.

En los próximos capítulos profundizaremos en cada uno de ellos.

```text
Security Objectives
│
├── CIA Triad
├── Assets
├── Threats
├── Vulnerabilities
├── Risk
├── Security Controls
├── Defense in Depth
├── Least Privilege
├── Threat Modeling
└── Secure Design
```

Comprender cómo se relacionan estos conceptos permite analizar la seguridad de una aplicación desde una perspectiva sistémica y no únicamente desde la existencia de vulnerabilidades individuales.

---

# 📚 Referencias

Este documento sintetiza conceptos ampliamente utilizados por la industria y desarrollados por diferentes organismos y marcos de referencia.

- NIST SP 800-30 — *Guide for Conducting Risk Assessments*
- NIST SP 800-37 — *Risk Management Framework (RMF)*
- NIST SP 800-53 — *Security and Privacy Controls for Information Systems and Organizations*
- NIST SP 800-160 — *Systems Security Engineering*
- FIPS 199 — *Standards for Security Categorization of Federal Information and Information Systems*
- OWASP Application Security Verification Standard (ASVS)
- OWASP Software Assurance Maturity Model (SAMM)
- OWASP Developer Guide
- CISA — *Secure by Design / Secure by Default*
- Microsoft Security Development Lifecycle (SDL)
- *Alice & Bob Learn Application Security* – Chapter 1. :contentReference[oaicite:0]{index=0}

---

---
---
---

# Página 2

# 📦 Assets: identificando qué debe protegerse

Toda iniciativa de Application Security comienza con una pregunta aparentemente sencilla.

> **¿Qué estamos intentando proteger?**

Aunque pueda parecer una pregunta básica, representa el punto de partida de prácticamente todas las disciplinas relacionadas con la seguridad de aplicaciones, incluyendo:

- Threat Modeling
- Risk Assessment
- Secure Design
- Security Architecture
- Security Requirements
- Security Testing

Si un equipo no puede identificar con claridad cuáles son los activos de valor dentro de un sistema, difícilmente podrá evaluar riesgos, priorizar amenazas o justificar la implementación de controles de seguridad.

En otras palabras:

> **No existe un análisis de seguridad efectivo sin comprender primero qué activos poseen valor para el negocio.**

---

# 📖 ¿Qué es un Asset?

Desde la perspectiva de Application Security, un **Asset** es cualquier recurso que posee valor para una organización y cuya pérdida de **Confidentiality**, **Integrity** o **Availability** podría generar consecuencias para el negocio.

Es importante comprender que ese valor no siempre es económico.

Dependiendo del contexto, un activo puede tener un valor:

- Económico.
- Operativo.
- Legal.
- Reputacional.
- Estratégico.

Por este motivo, una aplicación no protege únicamente datos.

Protege todo aquello cuya pérdida pueda afectar la capacidad de una organización para operar, cumplir con regulaciones o mantener la confianza de sus clientes.

---

# 🏢 El valor de un activo depende del contexto

Uno de los errores más frecuentes consiste en asumir que todos los activos poseen el mismo nivel de criticidad.

No es así.

El valor de un activo depende completamente del contexto del negocio.

Por ejemplo, una dirección de correo electrónico puede representar un activo de bajo impacto para un blog personal.

Sin embargo, ese mismo dato puede convertirse en información crítica dentro de una entidad financiera, un sistema gubernamental o una plataforma de salud, donde puede utilizarse para identificar usuarios, iniciar procesos de recuperación de credenciales o facilitar campañas de phishing dirigidas.

Lo mismo ocurre con las APIs.

Una API que expone información pública posee un nivel de criticidad muy diferente al de una API responsable de autorizar transferencias bancarias o procesar pagos.

Application Security siempre evalúa los activos considerando el contexto donde existen y el impacto que tendría su compromiso para el negocio.

---

# 🧩 Clasificación de Assets

Aunque existen diferentes formas de clasificarlos, una división práctica para Application Security consiste en agruparlos de la siguiente manera.

| Categoría | Ejemplos | Objetivos de seguridad más relevantes |
|------------|----------|----------------------------------------|
| Business Assets | Procesos de negocio, servicios, reputación | CIA |
| Information Assets | PII, PHI, secretos, credenciales | Confidentiality |
| Software Assets | Código fuente, APIs, microservicios, librerías | Integrity |
| Infrastructure Assets | Kubernetes, bases de datos, servidores, servicios Cloud | Availability |

Cada categoría posee amenazas, riesgos y controles diferentes.

Comprender esta clasificación facilita la construcción de modelos de amenazas más precisos y permite priorizar correctamente las actividades de seguridad.

---

# 🎯 Una aplicación protege múltiples activos

Consideremos una aplicación bancaria simplificada.

```text
                    Banking Application
                             │
        ┌────────────────────┼────────────────────┐
        │                    │                    │
        ▼                    ▼                    ▼
 Authentication         Banking API          Database
        │                    │                    │
        ▼                    ▼                    ▼
 Credentials         Business Logic      Financial Records
        │
        ▼
 Session Tokens
```

Cada componente incorpora nuevos activos con distintos niveles de criticidad.

| Componente | Activo principal | Criticidad |
|------------|-----------------|------------|
| Frontend | Session Cookies | Alta |
| Authentication Service | Credenciales y Tokens | Crítica |
| Banking API | Lógica de negocio | Crítica |
| Database | Información financiera | Crítica |

Este ejemplo demuestra que una aplicación rara vez protege un único activo.

En la práctica, un sistema moderno puede contener cientos o incluso miles de activos distribuidos entre múltiples componentes.

---

# ⚠️ Algunos activos suelen pasar desapercibidos

Cuando se pregunta qué activos posee una aplicación, la mayoría de los equipos responde inmediatamente:

- La base de datos.
- La información de clientes.
- Las credenciales.

Sin embargo, algunos de los activos más críticos suelen ser invisibles durante las primeras etapas del análisis.

Por ejemplo:

- Variables de entorno.
- Archivos de configuración.
- Certificados digitales.
- Claves privadas.
- Secretos almacenados en CI/CD.
- Azure Key Vault.
- AWS Secrets Manager.
- Kubernetes Secrets.
- Modelos de Machine Learning.
- Algoritmos propietarios.
- Reglas de negocio.

En numerosos incidentes de seguridad, estos activos representan el punto de entrada que posteriormente permite comprometer activos de mucho mayor valor.

---

# 🏛️ Architecture Perspective

> 💡 **Un mismo activo rara vez existe en una única ubicación.**

En arquitecturas modernas, un activo suele encontrarse replicado en distintos componentes del sistema.

Por ejemplo, una credencial puede existir simultáneamente en:

- Azure Key Vault.
- Variables de entorno.
- Memoria del proceso.
- Archivos de configuración.
- Caché.
- Logs.
- Backups.
- Herramientas de CI/CD.

Cada nueva copia incrementa la superficie de ataque de la aplicación.

Por este motivo, durante actividades como **Threat Modeling**, **Attack Surface Analysis** o **Risk Assessment**, no resulta suficiente identificar un activo.

También es necesario comprender **dónde existe**, **quién puede acceder a él**, **cómo se transmite** y **durante cuánto tiempo permanece expuesto**.

---

# 💡 Pensar como un Application Security Engineer

Cuando un ingeniero de Application Security participa en un Threat Modeling, normalmente evita comenzar buscando vulnerabilidades.

En cambio, suele iniciar la conversación con preguntas como:

- ¿Qué activos existen?
- ¿Cuál es su valor para el negocio?
- ¿Quién es propietario del activo?
- ¿Quién debería poder acceder?
- ¿Dónde se almacena?
- ¿Cómo se transmite?
- ¿Qué ocurriría si este activo perdiera su Confidentiality?
- ¿Qué ocurriría si perdiera su Integrity?
- ¿Qué ocurriría si dejara de estar disponible?

Responder estas preguntas permite construir un modelo de amenazas mucho más preciso y seleccionar controles de seguridad alineados con el riesgo real del sistema.

Esta forma de razonamiento representa una diferencia importante entre un enfoque reactivo basado en vulnerabilidades y un enfoque de ingeniería orientado al diseño seguro.

---

# 🔗 Relación con otros conceptos

La identificación de activos constituye el punto de partida para múltiples disciplinas dentro de Application Security.

```text
Assets
   │
   ├── Threats
   ├── Vulnerabilities
   ├── Risk
   ├── Security Objectives
   ├── Threat Modeling
   ├── Secure Design
   ├── Security Requirements
   └── Security Controls
```

Comprender correctamente qué activos existen y cuál es su valor para el negocio permite priorizar riesgos, justificar controles y tomar decisiones de diseño más informadas durante todo el Software Development Lifecycle (SDLC).

---

---
---
---

# Página 3

# ⚠️ Threats: comprendiendo qué puede salir mal

Una vez identificados los activos de una aplicación, la siguiente pregunta surge de manera natural.

> **¿Qué podría comprometer esos activos?**

Responder esta pregunta constituye uno de los objetivos principales de disciplinas como **Threat Modeling**, **Risk Assessment** y **Security Architecture**.

Mientras que los **activos** representan aquello que posee valor para una organización, las **amenazas (Threats)** representan situaciones capaces de comprometer ese valor.

Comprender correctamente las amenazas permite anticipar escenarios de ataque antes de que una vulnerabilidad sea descubierta o explotada.

---

# 📖 ¿Qué es una Threat?

Desde la perspectiva de Application Security, una **Threat** representa la posibilidad de que una **Threat Source** materialice un **Threat Event** capaz de comprometer uno o más **Security Objectives** de un activo.

Es importante destacar que una amenaza no implica necesariamente que exista una vulnerabilidad explotable.

Una organización puede enfrentarse diariamente a miles de amenazas sin experimentar incidentes de seguridad.

El incidente ocurre únicamente cuando una amenaza logra aprovechar una vulnerabilidad existente.

---

# 🧩 Threat vs Threat Source

Uno de los conceptos que más confusión genera consiste en utilizar los términos **Threat** y **Threat Source** como si fueran sinónimos.

No lo son.

Una **Threat Source** representa el origen de una amenaza.

Una **Threat** representa el escenario o evento que podría afectar un activo.

Distinguir ambos conceptos resulta especialmente importante durante actividades de **Threat Modeling**, donde primero se identifican las posibles fuentes de amenaza y posteriormente los escenarios que podrían materializarse sobre los activos del sistema.

Por ejemplo.

| Threat Source | Threat |
|---------------|--------|
| Cybercriminal | Credential Theft |
| Insider | Data Exfiltration |
| Malware | Ransomware Encryption |
| Developer Error | Secret Exposure |
| Cloud Misconfiguration | Public Data Exposure |
| Natural Disaster | Datacenter Outage |

Comprender esta diferencia facilita el análisis de riesgos y permite construir modelos de amenazas mucho más precisos.

---

# 🏢 Las amenazas no siempre son ataques

Uno de los errores más frecuentes consiste en asociar una amenaza únicamente con un atacante.

Sin embargo, muchas amenazas no poseen un origen malicioso.

Algunos ejemplos incluyen:

- Errores de configuración.
- Fallas de hardware.
- Dependencias vulnerables.
- Errores humanos.
- Cortes de energía.
- Desastres naturales.
- Fallas de software.
- Errores operativos.

En consecuencia, una amenaza no debe interpretarse únicamente como una acción maliciosa, sino como cualquier condición capaz de afectar los objetivos de seguridad del sistema.

Desde la perspectiva del negocio, todas ellas representan amenazas porque pueden afectar la **Confidentiality**, **Integrity** o **Availability** de los activos.

---

# 👥 Clasificación de Threat Sources

En términos generales, las fuentes de amenaza pueden agruparse en cuatro grandes categorías.

| Categoría | Ejemplos |
|------------|----------|
| External | Cybercriminals, Competitors, Nation-State Actors |
| Internal | Employees, Contractors, Administrators |
| Technological | Hardware Failure, Software Failure |
| Environmental | Floods, Fire, Earthquake, Power Outage |

Cada categoría requiere estrategias de mitigación diferentes.

Por ejemplo, un firewall no mitiga el impacto de una inundación, mientras que un plan de **Disaster Recovery** puede reducir significativamente sus consecuencias.

---

# 🎯 Una misma amenaza puede comprometer múltiples activos

Consideremos una API encargada de procesar pagos.

```text
Internet
      │
      ▼
API Gateway
      │
      ▼
Payment API
      │
      ▼
Payment Database
```

Una amenaza como **Credential Theft** puede comprometer simultáneamente:

- Cuentas de usuarios.
- Tokens de autenticación.
- APIs.
- Bases de datos.
- Información financiera.

En consecuencia, las amenazas rara vez afectan un único activo.

Normalmente producen efectos en cascada dentro de la arquitectura.

---

# 🏛️ Architecture Perspective

> 💡 **Las amenazas atraviesan arquitecturas, no componentes aislados.**

Cuando un atacante compromete una aplicación, rara vez obtiene acceso inmediato al activo que realmente le interesa.

Normalmente progresa entre distintos componentes de la arquitectura.

```text
Internet
     │
     ▼
Frontend
     │
     ▼
Authentication
     │
     ▼
API
     │
     ▼
Database
```

Cada componente representa un posible punto de **detección**, **contención** o **mitigación** dentro de la arquitectura.

Por ese motivo, durante un **Threat Modeling** no se analizan únicamente los activos.

También se analizan las posibles rutas que una amenaza podría seguir para alcanzarlos.

---

# 💡 Pensar como un Application Security Engineer

Cuando un ingeniero de Application Security identifica un activo crítico, normalmente evita comenzar buscando vulnerabilidades.

En cambio, suele iniciar la conversación con preguntas como:

- ¿Quién podría estar interesado en este activo?
- ¿Cuál sería su motivación?
- ¿Qué capacidades técnicas necesitaría?
- ¿Qué Trust Boundaries debería atravesar?
- ¿Qué camino seguiría para alcanzarlo?
- ¿Qué impacto tendría su compromiso?
- ¿Qué Security Controls protegen actualmente este activo?
- ¿Existen controles compensatorios si alguno falla?

Estas preguntas permiten pasar de un análisis centrado en vulnerabilidades hacia un análisis orientado al riesgo y al diseño seguro.

---

# 🔗 Relación con otros conceptos

Las amenazas representan el vínculo entre los activos y el proceso de gestión del riesgo.

```text
Assets
    │
    ▼
Threat Sources
    │
    ▼
Threats
    │
    ▼
Vulnerabilities
    │
    ▼
Risk
    │
    ▼
Security Objectives
    │
    ▼
Security Controls
```

Comprender correctamente las amenazas constituye uno de los pilares del **Threat Modeling** y permite priorizar los esfuerzos de seguridad sobre aquellos escenarios que representan un mayor riesgo para el negocio.

---

## 📌 Key Takeaways

- Toda amenaza busca comprometer uno o más activos.
- Una amenaza no implica necesariamente la existencia de una vulnerabilidad explotable.
- Las **Threat Sources** representan el origen de las amenazas.
- Una misma amenaza puede comprometer múltiples activos distribuidos en la arquitectura.
- Comprender las amenazas permite priorizar riesgos antes de seleccionar controles.
- El objetivo del Threat Modeling consiste en identificar estos escenarios antes de que puedan materializarse.

---

> 📖 **Próxima sección:** [Vulnerabilities](06-Vulnerabilities.md)
