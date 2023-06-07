# PowerPlatform Documentation
Documentation that I usually need for technical proposals on Power Platform


Sobre las copias de seguridad: 
ES: https://learn.microsoft.com/es-es/power-platform/admin/backup-restore-environments
EN: https://learn.microsoft.com/en-us/power-platform/admin/backup-restore-environments

Acerca de las copias de seguridad del sistema:

Las copias de seguridad del sistema no cuentan para la capacidad.
Según el tamaño de los datos, las operaciones de copia y restauración pueden demorar más de 24 horas, especialmente si necesita copiar datos de auditoría.
Se realizan copias de seguridad de todos sus entornos, salvo los entornos de prueba (estándar y basados en suscripción).
Las copias de seguridad del sistema se realizan de forma continuada. La tecnología subyacente utilizada es Azure SQL Database. Consulte la documentación de la base de datos SQL Copias de seguridad automatizadas para obtener detalles.
Debe restaurar un entorno en la misma región en la que se realizó la copia de seguridad.
Cuando un entorno se restaura sobre sí mismo, los registros de auditoría no se eliminan. Por ejemplo, cuando un entorno se restaura sobre sí mismo a un tiempo anterior t1, estarán disponibles los datos de auditoría completos del entorno, incluidos los registros de auditoría que se generaron después de t1.
El entorno de destino se enumera en el menú desplegable Seleccionar el entorno a sobrescribir. Si no ve un entorno, eso significa que el entorno de destino está en la misma geoárea (región geográfica) que el entorno de origen.
Solo los flujos de Power Apps y Power Automate en una solución de Dataverse participan en operaciones de copia de seguridad y restauración.

Retención:
Para entornos de producción que no tienen aplicaciones de Dynamics 365 habilitadas, el periodo de retención predeterminado de copias de seguridad es de solo 7 días. Sin embargo, los administradores pueden cambiar esta configuración y ampliar el período de retención de copias de seguridad para Entornos administrados usando PowerShell. Las opciones posibles son 7, 14, 21 y 28 días.

Cada cuanto se realizan las copias de seguridad: 
https://learn.microsoft.com/es-es/azure/azure-sql/database/automated-backups-overview?view=azuresql
