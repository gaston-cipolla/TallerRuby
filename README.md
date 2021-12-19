# POLYCONSULTORIO
## TERCER ENTREGA: Estado del proyecto al 20/12/2021.

Se realizaron los requerimientos detallados para la última entrega.

Se adaptaron los requerimientos desarrollados en las primeras entregas dentro de una aplicación web Ruby on Rails.

De las entregas anteriores se mantuvo el modelo original de Appointment y Professional, habiendo incorporando User.

Los elementos del modelo de datos ya no son persistidos en archivos y directorios, para esta nueva etapa hice uso de *ActiveRecord* y *sqlite3*.

* Para el manejo de sesión de usuarios se utilizó la gema *devise*.
* Para la validación de roles y permisos se utilizó la gema *cancancan*.

En el archivo *seeds* se cargó un set inicial de 3 usuarios con sus roles respectivos, 2 profesionales y 2 turnos para poder comenzar con una prueba de la aplicación.
* Este set de datos debe cargarse corriendo el comando *rails db:seed*. Previamente se debe correr el comando *rails db:migrate*.

De las entregas anteriores se mantuvieron la totalidad de las restricciones y reglas de negocio indicadas. Por ejemplo: no poder crear 2 turnos simultáneos para un mismo profesional, no poder borrar profesional con turnos asociados, no poder cargar 2 profesionales con el mismo nombre, no poder crear turnos con fechas pasadas, sólo permitir creación de turnos en horas exactas de 8 a 17 hs., poder exportar grilla de turnos de 4 tipos (diaria o semanal, ambas con un profesional específico o para todos los profesionales), etc.

Para esta nueva entrega se incorporaron las restricciones vinculadas a los usuarios y roles:
* El rol Administración habilita la gestión de la totalidad de las funcionalidades, incluyendo la de crear y modificar usuarios.
* El rol Asistencia habilita la gestión de turnos, y la consulta de profesionales.
* El rol Consulta sólo habilita consulta de turnos y profesionales.
* *Para los 3 perfiles se habilitó la opción de exportar grilla de turnos.*