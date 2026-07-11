# 🔒 CIA in Application Security

> La tríada CIA (Confidentiality, Integrity & Availability) constituye uno de los modelos fundamentales para definir los objetivos de seguridad de la información y sirve como base para el diseño y la evaluación de controles de seguridad en aplicaciones y sistemas.

---

# 🎯 Objetivo

Comprender los objetivos de seguridad definidos por la tríada CIA y cómo estos influyen en el diseño de arquitecturas, controles de seguridad y aplicaciones.

---

# 📖 Resumen

La tríada CIA define los principales objetivos de seguridad utilizados para proteger la información y los sistemas.

Todo control de seguridad puede justificarse en función de uno o más objetivos de la tríada CIA.

| Pilar | Objetivo |
|--------|----------|
| 🔒 Confidentiality | Proteger la información frente al acceso no autorizado. |
| ✅ Integrity | Proteger la información frente a modificaciones no autorizadas. |
| ⚙️ Availability | Garantizar el acceso a la información y los servicios cuando sean necesarios. |

---

# 🔒 Confidentiality (Confidencialidad)

## ¿Qué protege?

La información debe ser accesible únicamente para entidades autorizadas (usuarios, procesos o servicios), evitando tanto la divulgación como el acceso no autorizado.

### Ejemplos

- Datos personales
- Historias clínicas
- Información bancaria
- Credenciales
- API Keys

### Controles relacionados

- Access Control
- Least Privilege
- Strong Authentication
- Encryption at Rest
- Encryption in Transit
- Secrets Management
- Data Classification

---

# ✅ Integrity (Integridad)

## ¿Qué protege?

Garantiza que la información permanezca exacta, consistente y protegida frente a modificaciones no autorizadas durante todo su ciclo de vida.

### Ejemplos

- Transferencias bancarias
- Facturas
- Historial médico
- Configuraciones

### Controles relacionados

- Input Validation
- Integrity Verification
- Digital Signature Validation
- Change Control
- Audit Logging
- Data Validation
- Database Integrity Controls

---

# ⚙️ Availability (Disponibilidad)

## ¿Qué protege?

Garantiza que los sistemas y la información puedan utilizarse cuando sean necesarios.

### Ejemplos

- Portales web
- APIs
- Sistemas hospitalarios
- Plataformas bancarias

### Controles relacionados

- High Availability
- Redundancy
- Fault Tolerance
- Capacity Management
- Disaster Recovery
- Backup and Recovery
- Resilience Monitoring
- Resource Protection

---

# 💻 Ejemplo práctico

Supongamos una aplicación bancaria.

| Situación | Pilar afectado |
|-----------|----------------|
| Un usuario accede a cuentas ajenas | 🔒 Confidentiality |
| Una vulnerabilidad permite alterar el saldo de una cuenta. | ✅ Integrity |
| El sistema deja de responder por un ataque DoS | ⚙️ Availability |

Una misma vulnerabilidad puede afectar más de un principio al mismo tiempo.

---
# 🔗 Relación con Application Security

En Application Security, la tríada CIA actúa como un marco de referencia para identificar activos críticos, definir *security requirements* y seleccionar e implementar controles de seguridad durante todo el Software Development Lifecycle (SDLC).

Estos principios están presentes en múltiples actividades del ciclo de desarrollo, por ejemplo:

- Threat Modeling
- Secure Design
- Secure Coding
- Security Testing
- Risk Assessment

Comprender cómo una vulnerabilidad impacta la **Confidentiality**, **Integrity** y/o **Availability** permite priorizar riesgos, seleccionar controles adecuados y tomar mejores decisiones de diseño.

---

# ⚠️ Errores comunes

- Pensar que la seguridad consiste únicamente en proteger la confidencialidad.
- Analizar vulnerabilidades sin evaluar su impacto sobre la Confidentiality, Integrity y Availability.
- Confundir objetivos de seguridad (CIA) con controles o mecanismos de seguridad.
- Diseñar controles considerando únicamente amenazas externas e ignorando amenazas internas, errores de configuración o fallas de diseño.

---

# ✅ Buenas prácticas

- Evaluar el impacto de amenazas y vulnerabilidades sobre la Confidentiality, Integrity y Availability.
- Definir controles de seguridad en función de los objetivos de seguridad del sistema.
- Utilizar la tríada CIA como referencia durante el Threat Modeling y el Secure Design.
- Priorizar los controles según el riesgo y los requisitos del negocio.
---
