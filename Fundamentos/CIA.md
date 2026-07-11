# 🔒 CIA (Confidentiality, Integrity & Availability)

> La tríada CIA (Confidentiality, Integrity & Availability) constituye uno de los modelos fundamentales para definir los objetivos de seguridad de la información y sirve como base para el diseño y la evaluación de controles de seguridad en aplicaciones y sistemas.

---

# 🎯 Objetivo

Comprender los objetivos de seguridad definidos por la tríada CIA y cómo estos influyen en el diseño de arquitecturas, controles de seguridad y aplicaciones.

---

# 📖 Resumen

La tríada CIA es uno de los modelos más utilizados para evaluar los objetivos de seguridad de un sistema.

Todo control de seguridad puede justificarse en función de uno o más objetivos de la tríada CIA.

| Pilar | Objetivo |
|--------|----------|
| 🔒 Confidentiality | Evitar el acceso no autorizado a la información. |
| ✅ Integrity | Garantizar que la información no sea modificada de forma indebida. |
| ⚙️ Availability | Garantizar que la información y los servicios estén disponibles cuando se necesiten. |

---

# 🔒 Confidentiality (Confidencialidad)

## ¿Qué protege?

La información debe ser accesible únicamente para sujetos autorizados, evitando tanto la divulgación como el acceso no autorizado.

### Ejemplos

- Datos personales
- Historias clínicas
- Información bancaria
- Credenciales
- API Keys

### Controles relacionados

- Authentication
- Authorization
- Encryption
- Secrets Management
- Key Management
- Data Classification
- Access Control

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

- Hashes
- Digital Signatures
- Input Validation
- Audit Logs
- Message Authentication Codes (MAC)
- Checksums
- Database Constraints

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

- Backups
- High Availability
- Load Balancing
- Monitoring
- Disaster Recovery
- Redundancy
- Fault Tolerance
- Auto Scaling
- Rate Limiting
- Capacity Planning

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

Comprender cómo una vulnerabilidad impacta la **Confidentiality**, **Integrity** y/o **Availability** permite priorizar riesgos, seleccionar controles adecuados y tomar decisiones de diseño más informadas.

---

# ⚠️ Errores comunes

- Pensar que la seguridad consiste únicamente en proteger la confidencialidad.
- Analizar vulnerabilidades sin evaluar qué principios afectan.
- Diseñar controles considerando solo ataques externos.

---

# ✅ Buenas prácticas

- Analizar el impacto de cada vulnerabilidad sobre la tríada CIA.
- Diseñar controles considerando los tres principios.
- Utilizar la CIA como referencia durante el Threat Modeling.

---

# 📚 Conceptos relacionados

- Defense in Depth
- Least Privilege
- Zero Trust
- Threat Modeling
- Risk
- Attack Surface
