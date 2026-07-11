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

---
---
---
---

# Página 4

# 🐞 Vulnerabilities: comprendiendo dónde puede fallar el sistema

Una vez identificados los activos y las amenazas que podrían afectarlos, la siguiente pregunta es:

> **¿Qué debilidades podrían permitir que esas amenazas se materialicen?**

En Application Security, esta pregunta permite pasar de escenarios potenciales a condiciones concretas de la aplicación que pueden ser explotadas.

Una amenaza representa aquello que podría salir mal.

Una **vulnerabilidad (Vulnerability)** representa una condición que puede permitir que ese escenario ocurra.

Comprender esta diferencia evita tratar cada hallazgo técnico como un riesgo crítico y permite concentrar los esfuerzos de remediación en las debilidades que realmente exponen activos de valor.

---

# 📖 ¿Qué es una Vulnerability?

Desde una perspectiva de seguridad, una **Vulnerability** es una debilidad presente en el diseño, la implementación, la configuración o la operación de un sistema que puede ser explotada o activada por una fuente de amenaza.

En una aplicación, una vulnerabilidad puede existir en diferentes niveles:

- Arquitectura.
- Diseño.
- Código fuente.
- Configuración.
- Dependencias.
- Infraestructura.
- Procesos operativos.
- Controles de seguridad.

Esto significa que las vulnerabilidades no son exclusivamente errores de programación.

Una aplicación cuyo código no contiene fallas evidentes aún puede ser vulnerable debido a una decisión de diseño insegura, una configuración incorrecta o un control de acceso insuficiente.

---

# 🧩 Weakness vs Vulnerability

Los términos **Weakness** y **Vulnerability** suelen utilizarse indistintamente, pero representan niveles de abstracción diferentes.

Una **Weakness** describe un tipo de error o condición que puede introducir problemas de seguridad.

Una **Vulnerability** es una instancia concreta de una debilidad dentro de un producto, componente o sistema determinado que puede generar un impacto negativo.

```text
Weakness
    │
    ▼
Patrón de error
    │
    ▼
Implementación concreta
    │
    ▼
Vulnerability
```

Por ejemplo:

| Concepto | Ejemplo |
|----------|---------|
| Weakness | Falta de validación adecuada sobre datos no confiables |
| Vulnerability | Un parámetro específico de una API permite ejecutar una SQL Injection |
| Impacto posible | Lectura o modificación no autorizada de información |

La distinción es importante porque permite trabajar en dos niveles diferentes:

- Corregir una vulnerabilidad elimina una instancia concreta del problema.
- Eliminar la debilidad del proceso de desarrollo ayuda a evitar que el mismo tipo de problema vuelva a introducirse.

Desde una perspectiva de AppSec madura, no alcanza con corregir findings individuales. También resulta necesario identificar los patrones de ingeniería que los producen.

---

# 🗂️ CWE y CVE no representan lo mismo

Dos de los identificadores más utilizados en la industria son **CWE** y **CVE**.

Aunque están relacionados, cumplen funciones diferentes.

## CWE — Common Weakness Enumeration

**CWE** clasifica tipos comunes de debilidades de software y hardware.

Ejemplos:

- `CWE-79` — Improper Neutralization of Input During Web Page Generation.
- `CWE-89` — Improper Neutralization of Special Elements Used in an SQL Command.
- `CWE-798` — Use of Hard-coded Credentials.
- `CWE-862` — Missing Authorization.

CWE responde principalmente a la pregunta:

> **¿Qué clase de debilidad permitió que apareciera el problema?**

## CVE — Common Vulnerabilities and Exposures

**CVE** identifica vulnerabilidades públicamente divulgadas en productos o componentes concretos.

Un registro CVE permite que fabricantes, equipos de seguridad, herramientas y organizaciones se refieran de manera consistente a la misma vulnerabilidad.

CVE responde principalmente a la pregunta:

> **¿Qué vulnerabilidad específica fue identificada en un producto determinado?**

La relación puede representarse de la siguiente manera:

```text
CWE
Tipo de debilidad
      │
      ▼
CVE
Instancia conocida en un producto
```

No todas las vulnerabilidades de una aplicación tienen un CVE.

Las fallas encontradas en código desarrollado internamente, por ejemplo, pueden ser vulnerabilidades reales aunque nunca sean publicadas ni reciban un identificador CVE.

---

# 🔍 Vulnerability vs Finding

Otro error frecuente consiste en asumir que cada resultado generado por una herramienta representa automáticamente una vulnerabilidad confirmada.

No es así.

Un **Finding** es una observación que requiere análisis.

Puede terminar clasificado como:

- True Positive.
- False Positive.
- Accepted Risk.
- Informational Finding.
- Security Improvement.
- Vulnerability confirmada.

Por ejemplo, una herramienta SAST puede detectar la construcción dinámica de una consulta SQL.

Sin embargo, antes de confirmar una vulnerabilidad es necesario analizar:

- Si el dato puede ser controlado por un usuario.
- Si atraviesa validaciones o transformaciones.
- Si se utilizan consultas parametrizadas.
- Si el flujo es alcanzable.
- Si la operación se ejecuta con privilegios relevantes.
- Si existe un activo que pueda verse comprometido.

```text
Scanner Result
      │
      ▼
Technical Validation
      │
      ▼
Exploitability Analysis
      │
      ▼
Business Context
      │
      ▼
Confirmed Vulnerability
```

Las herramientas proporcionan evidencia y puntos de investigación.

La decisión final requiere contexto técnico y de negocio.

---

# ⚠️ Vulnerability no es lo mismo que Risk

Una vulnerabilidad no representa por sí sola el riesgo completo.

Para evaluar su relevancia deben considerarse otros elementos:

- El activo afectado.
- La amenaza asociada.
- La posibilidad de explotación.
- Los privilegios necesarios.
- La exposición del componente.
- Los controles existentes.
- El impacto técnico.
- El impacto para el negocio.

Dos aplicaciones pueden contener la misma debilidad y, aun así, presentar niveles de riesgo completamente diferentes.

Por ejemplo, una vulnerabilidad de SQL Injection en un entorno de laboratorio aislado no presenta el mismo riesgo que una vulnerabilidad equivalente en una API pública que procesa operaciones financieras.

```text
Vulnerability
      +
Threat Context
      +
Asset Value
      +
Likelihood
      +
Business Impact
      =
Risk
```

La severidad técnica representa una entrada para la evaluación.

No reemplaza el análisis de riesgo.

---

# 🧱 Origen de las vulnerabilidades

Las vulnerabilidades pueden introducirse en cualquier etapa del Software Development Lifecycle (SDLC).

| Etapa | Ejemplo |
|-------|---------|
| Requirements | No definir requisitos de autorización para operaciones sensibles |
| Design | Confiar en validaciones realizadas únicamente en el cliente |
| Development | Concatenar datos no confiables en una consulta SQL |
| Build | Incorporar una dependencia vulnerable |
| Deployment | Publicar una interfaz administrativa en Internet |
| Operations | Mantener credenciales expuestas o componentes sin actualizar |

Esta distribución demuestra por qué Application Security no puede reducirse a escanear código antes de llegar a producción.

Una parte significativa de las vulnerabilidades tiene su origen en decisiones tomadas antes de que el código sea escrito o después de que la aplicación haya sido desplegada.

---

# 🐛 Security Bug vs Design Flaw

Desde una perspectiva de ingeniería, resulta útil distinguir entre un **Security Bug** y un **Design Flaw**.

## Security Bug

Es un error introducido durante la implementación.

Ejemplos:

- Una salida no codificada correctamente.
- Una comparación insegura de tokens.
- Una validación de longitud ausente.
- Una consulta construida mediante concatenación.

## Design Flaw

Es una debilidad que surge de una decisión incorrecta en la arquitectura o en el diseño del sistema.

Ejemplos:

- Confiar en el frontend para autorizar operaciones.
- Utilizar una cuenta compartida para múltiples servicios.
- No separar funciones administrativas de operaciones regulares.
- Permitir que un único componente acceda a todos los datos de la plataforma.

| Característica | Security Bug | Design Flaw |
|----------------|--------------|-------------|
| Origen habitual | Implementación | Arquitectura o diseño |
| Detección | SAST, DAST, Code Review | Threat Modeling, Architecture Review |
| Alcance | Generalmente localizado | Puede afectar múltiples componentes |
| Remediación | Cambio de código específico | Rediseño parcial o completo |

Las herramientas automatizadas suelen tener mayor capacidad para detectar errores de implementación que fallas de diseño.

Por ese motivo, actividades como **Threat Modeling**, **Secure Design Review** y **Architecture Risk Analysis** resultan necesarias incluso cuando existe una cobertura amplia de SAST, DAST o SCA.

---

# 🧬 First-Party y Third-Party Vulnerabilities

Las vulnerabilidades pueden originarse tanto en código propio como en componentes externos.

## First-Party Vulnerabilities

Se encuentran en código, configuraciones o diseños creados por la propia organización.

Ejemplos:

- Broken Access Control.
- Business Logic Flaws.
- Insecure Direct Object References.
- Validación insuficiente.
- Gestión insegura de sesiones.

## Third-Party Vulnerabilities

Se encuentran en componentes incorporados a la aplicación.

Ejemplos:

- Librerías.
- Frameworks.
- Imágenes de contenedores.
- Paquetes del sistema operativo.
- Plugins.
- SDKs.
- Servicios externos.

Cuando una aplicación incorpora una dependencia, también incorpora parte del riesgo asociado a ese componente y a su cadena de dependencias.

Esto no significa que todas las vulnerabilidades reportadas en una dependencia sean explotables dentro de la aplicación.

Para determinar su relevancia es necesario evaluar:

- Si la versión vulnerable está realmente desplegada.
- Si la funcionalidad afectada se utiliza.
- Si el código vulnerable es alcanzable.
- Si existe exposición suficiente para explotarlo.
- Si hay controles que reduzcan la posibilidad o el impacto.

---

# 🏛️ Architecture Perspective

> 💡 **Una vulnerabilidad localizada puede generar un compromiso sistémico.**

La ubicación inicial de una vulnerabilidad no determina necesariamente el alcance final del incidente.

Una debilidad aparentemente limitada al frontend, una API o un pipeline puede permitir acceder progresivamente a activos más críticos.

```text
Exposed Secret
      │
      ▼
CI/CD Access
      │
      ▼
Artifact Modification
      │
      ▼
Production Deployment
      │
      ▼
Application Compromise
```

En este escenario, el problema inicial puede parecer una simple exposición de credenciales.

Sin embargo, la arquitectura y los privilegios asociados permiten convertir esa exposición en un compromiso de la cadena de suministro y del entorno productivo.

Por este motivo, el análisis de una vulnerabilidad debe considerar:

- Las relaciones entre componentes.
- Los Trust Boundaries.
- Las identidades involucradas.
- Los privilegios disponibles.
- Las rutas de escalamiento.
- El radio de impacto o **Blast Radius**.

Un finding debe analizarse dentro de la arquitectura completa, no únicamente dentro del componente donde fue descubierto.

---

# 💡 Pensar como un Application Security Engineer

Cuando se identifica una posible vulnerabilidad, un Application Security Engineer no debería limitarse a preguntar:

> **¿Qué severidad le asignó la herramienta?**

También debería analizar:

- ¿Cuál es la causa raíz?
- ¿Qué activo puede verse comprometido?
- ¿Qué Threat Source podría explotarla?
- ¿El flujo vulnerable es realmente alcanzable?
- ¿Qué condiciones deben cumplirse?
- ¿Qué privilegios necesita el atacante?
- ¿Qué Trust Boundaries puede atravesar?
- ¿Existen controles preventivos o compensatorios?
- ¿Cuál es el Blast Radius?
- ¿El problema puede repetirse en otros componentes?
- ¿La remediación corrige la causa raíz o solo esta instancia?

Estas preguntas permiten diferenciar la gestión superficial de findings de un verdadero proceso de ingeniería de seguridad.

---

# 🔗 Relación con otros conceptos

Las vulnerabilidades constituyen el punto de conexión entre una amenaza potencial y un riesgo concreto.

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
Likelihood + Impact
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

Sin una vulnerabilidad o condición explotable, una amenaza puede no materializarse.

Sin un activo de valor y un impacto asociado, una vulnerabilidad puede no representar un riesgo relevante para el negocio.

---

## 📌 Key Takeaways

- Una vulnerabilidad es una debilidad que puede ser explotada o activada por una Threat Source.
- Las vulnerabilidades pueden originarse en requisitos, diseño, código, dependencias, configuración u operación.
- Una Weakness describe un tipo de error; una Vulnerability representa una instancia concreta.
- CWE clasifica debilidades, mientras que CVE identifica vulnerabilidades públicamente divulgadas.
- Un resultado de una herramienta es un Finding hasta que sea validado y contextualizado.
- Vulnerability, Severity y Risk no son conceptos equivalentes.
- Las fallas de diseño requieren Threat Modeling y revisiones de arquitectura, no únicamente scanners.
- El análisis debe considerar la causa raíz, la explotabilidad, los activos afectados y el Blast Radius.

---

## 📚 Referencias

- [NIST CSRC Glossary — Vulnerability](https://csrc.nist.gov/glossary/term/vulnerability)
- [NIST CSRC Glossary — Software Vulnerability](https://csrc.nist.gov/glossary/term/software_vulnerability)
- [NIST SP 800-30 Rev. 1 — Guide for Conducting Risk Assessments](https://csrc.nist.gov/pubs/sp/800/30/r1/final)
- [NIST SP 800-115 — Technical Guide to Information Security Testing and Assessment](https://csrc.nist.gov/pubs/sp/800/115/final)
- [CWE — Common Weakness Enumeration](https://cwe.mitre.org/)
- [CVE Program — Overview](https://www.cve.org/about/overview)
- [OWASP Vulnerability Management Guide](https://owasp.org/www-project-vulnerability-management-guide/)
- [OWASP Risk Rating Methodology](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology)
- *Alice & Bob Learn Application Security* — capítulos sobre Secure Design, Secure Code, Common Pitfalls y Testing.

---
---
---
---
---


# Página 5


# 📉 Risk: comprendiendo qué tan importante es un problema

Una vez identificados los activos, las amenazas y las vulnerabilidades, surge una nueva pregunta.

> **¿Qué problemas deberían resolverse primero?**

En una aplicación real no todas las vulnerabilidades poseen la misma importancia.

Tampoco todas las amenazas representan el mismo nivel de preocupación para una organización.

El objetivo de la gestión del riesgo consiste precisamente en responder esa pregunta.

Comprender el riesgo permite priorizar esfuerzos, asignar recursos y seleccionar controles de seguridad de manera proporcional al impacto que un incidente podría generar sobre el negocio.

En Application Security, prácticamente todas las decisiones importantes terminan reduciéndose a una evaluación de riesgo.

---

# 📖 ¿Qué es el Risk?

Desde la perspectiva de Application Security, el **Risk** representa la posibilidad de que una amenaza comprometa un activo explotando una vulnerabilidad y genere consecuencias negativas para la organización.

En otras palabras, el riesgo no depende únicamente de la existencia de una vulnerabilidad.

También depende del contexto en el que esa vulnerabilidad existe.

Por ese motivo, dos aplicaciones pueden contener exactamente la misma debilidad y, sin embargo, presentar niveles de riesgo completamente diferentes.

El riesgo siempre debe analizarse considerando:

- El activo afectado.
- La amenaza asociada.
- La vulnerabilidad existente.
- La probabilidad de explotación.
- El impacto potencial para el negocio.

---

# 🧩 Vulnerability no es Risk

Uno de los errores más frecuentes consiste en utilizar ambos términos como si fueran equivalentes.

No lo son.

Una vulnerabilidad describe una debilidad.

El riesgo describe las consecuencias que esa debilidad podría generar bajo determinadas condiciones.

Por ejemplo.

Una aplicación interna contiene una SQL Injection.

¿Representa un riesgo?

La respuesta correcta es:

> **Depende.**

Depende de cuestiones como:

- ¿Quién puede acceder a la aplicación?
- ¿Qué información protege?
- ¿Qué privilegios posee?
- ¿Existen controles compensatorios?
- ¿La vulnerabilidad es realmente explotable?
- ¿Cuál sería el impacto para el negocio?

La vulnerabilidad puede ser idéntica.

El riesgo no.

---

# 🎯 El contexto cambia completamente el riesgo

Consideremos dos aplicaciones.

## Aplicación A

- Laboratorio interno.
- Sin información sensible.
- Acceso únicamente desde una red aislada.

Contiene una SQL Injection.

---

## Aplicación B

- API pública.
- Procesa pagos.
- Disponible desde Internet.
- Contiene información financiera.

También posee una SQL Injection.

---

Desde una perspectiva técnica ambas aplicaciones contienen exactamente la misma vulnerabilidad.

Sin embargo, el riesgo asociado es completamente diferente.

Esto demuestra que el riesgo no depende únicamente del problema técnico.

Depende del contexto del negocio.

---

# ⚖️ Factores que influyen sobre el riesgo

Aunque diferentes metodologías utilizan distintos modelos de evaluación, la mayoría considera factores similares.

| Factor | Pregunta |
|----------|----------|
| Asset Value | ¿Qué tan importante es el activo? |
| Threat | ¿Quién podría intentar comprometerlo? |
| Vulnerability | ¿Existe una debilidad explotable? |
| Likelihood | ¿Qué probabilidad existe de explotación? |
| Impact | ¿Qué consecuencias tendría? |
| Existing Controls | ¿Qué controles reducen actualmente ese riesgo? |

La combinación de estos elementos permite comprender la exposición real del sistema.

---

# 📊 Likelihood e Impact

Es habitual encontrar representaciones simplificadas del riesgo como:

```text
Risk = Likelihood × Impact
```

Aunque esta aproximación resulta útil para comprender el concepto, en la práctica el análisis suele incorporar muchos más elementos.

Por ejemplo:

- Exposición del sistema.
- Facilidad de explotación.
- Capacidades del atacante.
- Controles existentes.
- Valor del activo.
- Requisitos regulatorios.
- Dependencias afectadas.

Por este motivo, Application Security rara vez utiliza una única fórmula para representar el riesgo.

---

# 🏛️ Architecture Perspective

> 💡 **La arquitectura modifica el riesgo incluso cuando la vulnerabilidad permanece igual.**

Supongamos que una vulnerabilidad permite ejecutar código remoto.

En una arquitectura monolítica, el atacante podría comprometer toda la aplicación.

En una arquitectura basada en microservicios con identidades separadas, segmentación de red y privilegios mínimos, el mismo exploit podría afectar únicamente un servicio específico.

La vulnerabilidad no cambió.

La arquitectura sí.

Y con ella cambió el riesgo.

Por este motivo, una buena arquitectura constituye uno de los controles de seguridad más efectivos.

---

# 🧱 Riesgo técnico vs Riesgo de negocio

Application Security actúa como un puente entre el mundo técnico y las necesidades del negocio.

Por ese motivo resulta útil distinguir dos perspectivas diferentes.

## Technical Risk

Describe la probabilidad de explotación desde una perspectiva técnica.

Por ejemplo:

- Complejidad del exploit.
- Accesibilidad del componente.
- Privilegios requeridos.
- Controles existentes.

---

## Business Risk

Describe las consecuencias que tendría un incidente para la organización.

Por ejemplo:

- Pérdidas económicas.
- Interrupción del negocio.
- Daño reputacional.
- Incumplimiento regulatorio.
- Pérdida de clientes.

Un Security Engineer necesita comprender ambas perspectivas para priorizar correctamente las actividades de remediación.

---

# 💡 Pensar como un Application Security Engineer

Cuando un ingeniero de Application Security recibe un hallazgo crítico, rara vez comienza preguntando:

> **¿Qué CVSS tiene?**

Normalmente comienza preguntándose:

- ¿Qué activo protege esta aplicación?
- ¿Cuál sería el impacto para el negocio?
- ¿Quién podría explotarlo?
- ¿Qué controles existen actualmente?
- ¿Qué tan probable es que ocurra?
- ¿Cuál sería el Blast Radius?
- ¿Debemos corregir inmediatamente o aceptar el riesgo?

Estas preguntas permiten transformar una lista de vulnerabilidades en un proceso real de gestión del riesgo.

---

# 🔗 Relación con otros conceptos

El riesgo conecta todos los conceptos vistos hasta el momento.

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

Comprender el riesgo permite seleccionar controles proporcionados, justificar inversiones en seguridad y priorizar aquellas actividades que generan mayor reducción del riesgo para la organización.

---

## 📌 Key Takeaways

- Una vulnerabilidad no representa necesariamente un riesgo elevado.
- El riesgo depende del contexto técnico y del negocio.
- Dos aplicaciones con la misma vulnerabilidad pueden presentar riesgos completamente diferentes.
- La arquitectura influye directamente sobre el nivel de riesgo.
- Application Security busca reducir el riesgo, no eliminar todas las vulnerabilidades.
- Toda decisión de seguridad debería estar respaldada por una evaluación de riesgo.

---

## 📚 Referencias

- NIST SP 800-30 Rev.1 — Guide for Conducting Risk Assessments
- NIST SP 800-37 Rev.2 — Risk Management Framework
- NIST SP 800-160 Vol.1 — Systems Security Engineering
- NIST CSRC Glossary — Risk
- OWASP Risk Rating Methodology
- OWASP ASVS
- OWASP SAMM
- Microsoft Security Development Lifecycle (SDL)
- Microsoft Threat Modeling
- *Alice & Bob Learn Application Security* — capítulos relacionados con diseño seguro y análisis de riesgos.
