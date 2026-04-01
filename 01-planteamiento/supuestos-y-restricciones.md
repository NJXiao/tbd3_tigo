# Supuestos y Restricciones del Sistema

El presente documento define los supuestos y restricciones considerados para el diseño de la base de datos del sistema de telecomunicaciones, garantizando coherencia con el modelo conceptual y lógico desarrollado.

---

# SUPUESTOS

## 1. Relación Cliente - Línea
Se asume que cada cliente puede tener una o varias líneas telefónicas registradas a su nombre, mientras que cada línea pertenece exclusivamente a un único cliente. Esta estructura permite representar tanto usuarios individuales como clientes corporativos.

---

## 2. Modalidad de la línea
Se asume que cada línea telefónica opera bajo una única modalidad activa (prepago o postpago) en un momento dado, definida en la tabla `linea`.

---

## 3. Recargas
Se asume que las recargas solo pueden ser realizadas por líneas de tipo prepago. Cada recarga está asociada a una única línea y registra el monto, fecha y medio de recarga.

---

## 4. Promociones y doble carga
Se asume que las promociones se aplican sobre recargas, registrándose en la tabla `promocion_aplicada`. En particular, la promoción de doble carga solo puede aplicarse una vez por mes por cada línea, lo cual se controla mediante triggers en la base de datos.

---

## 5. Consumo de servicios
Se asume que el consumo de servicios se registra de manera separada según su tipo:
- Llamadas (`llamada`)
- Mensajes SMS (`sms`)
- Datos móviles (`consumo_datos`)

Esto permite un control detallado y una mejor normalización del sistema.

---

## 6. Consumo de datos móviles
Se asume que el consumo de datos puede estar asociado a un paquete o al saldo disponible, lo cual se indica mediante el atributo `tipo_cobro` en la tabla `consumo_datos`.

---

## 7. Paquetes de servicios
Se asume que los paquetes contienen recursos como minutos, SMS y datos, y tienen una vigencia definida. La compra de paquetes se registra en `compra_paquete`.

---

## 8. Prioridad de uso de paquetes
Se asume que, al momento de consumir servicios, el sistema prioriza el uso de los recursos disponibles en paquetes antes de consumir el saldo de la línea.

---

## 9. Planes de servicio
Se asume que las líneas pueden tener planes asociados, los cuales se gestionan mediante la tabla `linea_plan`, permitiendo mantener un historial mediante fechas de inicio y fin.

---

## 10. Historial de planes
Se asume que los planes no se eliminan, sino que se almacenan históricamente, permitiendo conocer qué plan tenía una línea en un periodo determinado.

---

## 11. Facturación
Se asume que las líneas postpago generan facturas mensuales, las cuales se almacenan en la tabla `factura` junto con sus detalles en `detalle_factura`.

---

## 12. Préstamos de saldo
Se asume que los préstamos se otorgan a líneas prepago bajo ciertas condiciones (como antigüedad), y se registran en la tabla `prestamo` con su respectivo estado.

---

## 13. Asociación de dispositivos
Se asume que cada línea puede estar asociada a un único dispositivo a la vez, mediante el identificador del dispositivo (`id_dispositivo`).

---

## 14. Bloqueos de línea
Se asume que una línea puede ser bloqueada temporalmente por distintos motivos, registrándose en la tabla `bloqueo` con fechas de inicio y fin.

---

## 15. Notificaciones
Se asume que el sistema puede enviar notificaciones a las líneas, las cuales se almacenan en la tabla `notificacion`.

---

## 16. Persistencia de datos
Se asume que el sistema no elimina información histórica relevante, sino que la mantiene para fines de auditoría, análisis y trazabilidad.

---

## 17. Escalabilidad
Se asume que el sistema debe soportar grandes volúmenes de datos, por lo que el diseño está orientado a eficiencia y optimización.

---

# RESTRICCIONES

## 1. Unicidad de datos
- El número telefónico debe ser único.
- El documento de identidad del cliente debe ser único.
- El IMEI del dispositivo debe ser único.

---

## 2. Integridad referencial
- Toda línea debe estar asociada a un cliente.
- Toda recarga debe estar asociada a una línea.
- Toda promoción aplicada debe estar asociada a una recarga existente.
- Toda compra de paquete debe estar asociada a una línea y a un paquete.

---

## 3. Estados controlados
- Estado de línea: activa, suspendida, bloqueada.
- Estado de préstamo: pendiente, pagado.
- Estado de factura: pendiente, pagado.

---

## 4. Restricción de doble carga
No se permite aplicar la promoción de doble carga más de una vez por mes por línea. Esta restricción se implementa mediante triggers en la base de datos.

---

## 5. Consistencia de fechas
- La fecha de fin de un plan debe ser mayor a la fecha de inicio.
- Las fechas de bloqueo deben ser coherentes (inicio < fin).

---

## 6. Valores válidos
- Los montos de recarga deben ser mayores a cero.
- Los valores de consumo no pueden ser negativos.
- Los precios de planes y paquetes deben ser mayores a cero.

---

## 7. Asociación obligatoria
- No se puede registrar consumo sin una línea asociada.
- No se puede registrar una factura sin una línea.

---

## 8. Restricción de modalidad
- Las recargas y préstamos solo aplican a líneas prepago.
- Las facturas solo aplican a líneas postpago.

---

## 9. Uso de paquetes
Si un consumo está asociado a un paquete, este debe existir y estar vigente.

---

## 10. Auditoría implícita
Se asume que ciertas operaciones críticas, como recargas, pueden ser auditadas mediante tablas de log y triggers.
