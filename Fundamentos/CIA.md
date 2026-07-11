# 🔒 CIA (Confidentiality, Integrity & Availability)

> La tríada CIA representa los tres principios fundamentales sobre los que se construye la seguridad de la información y, por extensión, la seguridad de las aplicaciones.

---

# 🎯 Objetivo

Comprender los principios de **Confidencialidad**, **Integridad** y **Disponibilidad**, y cómo influyen en el diseño, desarrollo y protección de aplicaciones.

---

# 📖 Resumen

La tríada CIA es uno de los modelos más utilizados para evaluar los objetivos de seguridad de un sistema.

Todo control de seguridad implementado en una aplicación busca proteger uno o más de estos principios.

| Pilar | Objetivo |
|--------|----------|
| 🔒 Confidentiality | Evitar el acceso no autorizado a la información. |
| ✅ Integrity | Garantizar que la información no sea modificada de forma indebida. |
| ⚙️ Availability | Garantizar que la información y los servicios estén disponibles cuando se necesiten. |

---

# 🔒 Confidentiality (Confidencialidad)

## ¿Qué protege?

La información solo debe ser accesible para usuarios, sistemas o procesos autorizados.

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

---

# ✅ Integrity (Integridad)

## ¿Qué protege?

Garantiza que la información permanezca correcta, completa y sin modificaciones no autorizadas.

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

---

# 💻 Ejemplo práctico

Supongamos una aplicación bancaria.

| Situación | Pilar afectado |
|-----------|----------------|
| Un usuario accede a cuentas ajenas | 🔒 Confidentiality |
| Un atacante modifica el saldo de una cuenta | ✅ Integrity |
| El sistema deja de responder por un ataque DoS | ⚙️ Availability |

Una misma vulnerabilidad puede afectar más de un principio al mismo tiempo.

---

# 🔗 Relación con Application Security

La tríada CIA se utiliza durante todo el ciclo de vida del desarrollo seguro.

Por ejemplo:

- Threat Modeling
- Secure Design
- Secure Coding
- Security Testing
- Risk Assessment

Comprender estos principios permite seleccionar controles de seguridad adecuados y evaluar correctamente el impacto de una vulnerabilidad.

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
