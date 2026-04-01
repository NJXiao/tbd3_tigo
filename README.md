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

##  Estructura del Proyecto
El repositorio está organizado de la siguiente manera:
tbd3_tigo/
│
├── .gitignore
├── README.md
├── LICENSE
│
├── 00-administrativo/
│   ├── cronograma.md
│   ├── integrantes.md
│   ├── roles-del-equipo.md
│
├── 01-planteamiento/
│   ├── escenario-problema.pdf
│   ├── problema-mejorado.md
│   ├── alcance.md
│   ├── objetivos.md
│   ├── supuestos-y-restricciones.md
│   └── reglas-del-negocio.md
│
├── 02-requerimientos/
│   ├── requerimientos-almacenamiento.md
│   ├── requerimientos-seguridad.md    (Confidencialidad, Integridad, Roles)
│   ├── diccionario-preliminar-datos.md
│   ├── catalogo-entidades.md
│   └── casos-de-uso-basicos.md
│
├── 03-modelo-conceptual/
│   ├── diagrama-er-v1.png
│   ├── diagrama-er-v1.pdf
│   ├── diagrama-er-v2.png
│   ├── diagrama-er-v2.pdf
│   ├── descripcion-entidades.md
│   ├── descripcion-relaciones.md
│   └── cardinalidades-y-opcionalidades.md
│
├── 04-modelo-logico/
│   ├── esquema-relacional-v1.md
│   ├── normalizacion.md
│   ├── dependencias-funcionales.md
│   ├── paso-er-a-relacional.md
│   └── tablas-definitivas.md
│
├── 05-modelo-fisico/
│   ├── diagrama-fisico.png
│   ├── diagrama-fisico.pdf
│   ├── tipos-de-datos.md
│   ├── claves-primarias-y-foraneas.md
│   ├── restricciones.sql
│   └── indices.sql
│   └── estrategias-encriptacion.md  (Qué datos sensibles se encriptan)
│
├── 06-sql/
│   ├── 01-create-database.sql
│   ├── 02-create-tables.sql
│   ├── 03-alter-constraints.sql
│   ├── 04-indexes.sql
│   ├── 05-views.sql
│   ├── 06-inserts-catalogos.sql
│   ├── 07-inserts-pruebas.sql
│   ├── 08-consultas-basicas.sql
│   ├── 09-consultas-avanzadas.sql
│   ├── 10-procedimientos.sql
│   ├── 11-triggers.sql
│   └── 12-respaldo-estructura.sql
│   ├── 13-seguridad-roles.sql       (CREATE ROLE, GRANT, REVOKE)
│   └── 14-seguridad-auditoria.sql    (Tablas de log, triggers de auditoría)
│
├── 07-seguridad/
│   ├── politica-seguridad-bd.md
│   ├── analisis-riesgos-bd.md
│   ├── usuarios-y-roles.md
│   ├── matriz-privilegios.md
│   ├── control-acceso.md
│   ├── auditoria.md
│   ├── respaldo-y-recuperacion.md
│   ├── cifrado-y-proteccion-datos.md
│   ├── buenas-practicas.md
│   ├── incidentes-y-mitigacion.md
│   └── sql/
│       ├── 01-create-users.sql
│       ├── 02-create-roles.sql
│       ├── 03-grants.sql
│       ├── 04-revokes.sql
│       ├── 05-vistas-seguras.sql
│       ├── 06-auditoria.sql
│       └── 07-backup-restore.md
│
├── 08-datos/
│   ├── datos-prueba/
│   │   ├── clientes.csv
│   │   ├── lineas.csv
│   │   ├── planes.csv
│   │   ├── paquetes.csv
│   │   ├── recargas.csv
│   │   ├── prestamos.csv
│   │   └── facturas.csv
│   └── catalogos/
│       ├── tipos-cliente.csv
│       ├── tipos-linea.csv
│       ├── estados-linea.csv
│       ├── tipos-paquete.csv
│       └── medios-recarga.csv
│
├── 09-consultas-y-reportes/
│   ├── consultas-requeridas.md
│   ├── reportes-esperados.md
│   ├── evidencias-consultas/
│   │   ├── consulta-01.png
│   │   ├── consulta-02.png
│   │   └── consulta-03.png
│   └── resultados.sql
│
├── 10-documentacion-tecnica/
│   ├── diccionario-datos.md
│   ├── manual-instalacion.md
│   ├── manual-ejecucion.md
│   ├── decisiones-diseno.md
│   └── problemas-y-soluciones.md
│
├── 11-presentacion/
│   ├── diapositivas.pdf
│   ├── diapositivas.pptx
│   ├── resumen-defensa.md
│
├── 12-entregables/
│   ├── hito-1/
│   ├── hito-2/
│   ├── hito-final/
│   └── versiones-enviadas.md
│
└── 99-anexos/
    ├── imagenes/
    ├── referencias/
    ├── borradores/
    └── material-docente


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
- **Nicole Jhuliana**

---

##  Notas Finales

Este proyecto representa una simulación de un sistema real de telecomunicaciones, aplicando principios de ingeniería de software y diseño de bases de datos para resolver problemas complejos de gestión de información.

---

##  Licencia

Este proyecto es de carácter académico y educativo.

