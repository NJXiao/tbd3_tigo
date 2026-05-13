#  Sistema de Gestión de Telecomunicaciones - Tigo Bolivia

##  Descripción del Proyecto

El presente proyecto tiene como objetivo el diseño e implementación de una base de datos para una empresa de telecomunicaciones que opera en Bolivia, enfocada en la gestión de servicios de telefonía móvil.

El sistema permite administrar de manera eficiente la información relacionada con clientes, líneas telefónicas, planes de servicio, recargas, paquetes, consumo de servicios (llamadas, SMS y datos móviles), préstamos, promociones y facturación.

Este proyecto ha sido desarrollado como parte de la materia **Base de Datos I**, aplicando conceptos de modelamiento conceptual, lógico y físico, así como buenas prácticas de diseño de bases de datos.

---

##  Objetivos

### Objetivo General
Diseñar una base de datos robusta, escalable y normalizada que permita gestionar eficientemente los servicios de telecomunicaciones.

### Objetivos Específicos
- Modelar las entidades y relaciones del sistema mediante diagramas ER.
- Definir un esquema relacional coherente y normalizado.
- Implementar la base de datos en PostgreSQL.
- Garantizar la integridad de los datos mediante restricciones y claves foráneas.
- Implementar reglas de negocio mediante triggers y funciones.
- Permitir el análisis del consumo de los usuarios.


---

##  Alcance del Sistema

El sistema permite:

- Gestión de clientes y múltiples líneas telefónicas.
- Registro de recargas y promociones (incluyendo doble carga).
- Administración de planes y paquetes de servicios.
- Registro detallado de consumo:
  - Llamadas
  - SMS
  - Datos móviles
- Gestión de préstamos de saldo.
- Generación de facturación para clientes postpago.
- Control de estados de líneas (activas, suspendidas, bloqueadas).
- Registro de dispositivos asociados a líneas.

---

##  Tecnologías Utilizadas

- **PostgreSQL** → Sistema gestor de base de datos
- **SQL** → Lenguaje de consulta y definición de datos
- **Draw.io / DB Designer** → Modelado de diagramas ER
- **GitHub** → Control de versiones

---

##  Características del Diseño

- Modelo normalizado (evita redundancia de datos)
- Uso de claves primarias y foráneas
- Integridad referencial garantizada
- Manejo de historial (planes, consumo, etc.)
- Separación de tipos de consumo (llamadas, SMS, datos)
- Implementación de reglas de negocio mediante triggers:
  - Restricción de doble carga mensual
- Diseño escalable para grandes volúmenes de datos

---

##  Seguridad

El sistema contempla:

- Control de accesos mediante roles
- Restricciones de integridad
- Posibilidad de auditoría mediante triggers
- Protección de datos sensibles

---

##  Resultados Esperados

- Organización eficiente de la información
- Consultas rápidas y optimizadas
- Control detallado del comportamiento de los usuarios
- Base sólida para sistemas reales de telecomunicaciones

---

##  Integrantes

- **Alan Mauricio Gomez Alanes**
- **Nicole Jhuliana Herbas Guzman**

---

##  Notas Finales

Este proyecto representa una simulación de un sistema real de telecomunicaciones, aplicando principios de ingeniería de software y diseño de bases de datos para resolver problemas complejos de gestión de información.

---

##  Licencia

Este proyecto es de carácter académico y educativo.

