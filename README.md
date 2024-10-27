# OdooBackUp

Aquí tienes un texto para incluir en el README de tu proyecto en GitHub:

---

## Copia de Seguridad de la Base de Datos de Odoo

Este proyecto incluye un procedimiento para realizar copias de seguridad de la base de datos de Odoo utilizando Docker y PostgreSQL. A continuación, se describe el proceso que seguí:

1. **Acceso al Contenedor**: Primero, accedí al contenedor de Odoo en ejecución con el siguiente comando:
   ```bash
   docker exec -it odoo_container bash
   ```
   (Reemplaza `odoo_container` con el nombre de tu contenedor).

2. **Creación del Respaldo**: Dentro del contenedor, utilicé `pg_dump` para crear un archivo de respaldo de la base de datos PostgreSQL:
   ```bash
   pg_dump -U <usuario> -F c -b -v -f /ruta/donde/guardar/backup.sql <nombre_base_de_datos>
   ```
   Asegúrate de reemplazar `<usuario>`, `/ruta/donde/guardar/backup.sql`, y `<nombre_base_de_datos>` con los valores correspondientes.

3. **Transferencia del Respaldo**: Después de generar el archivo de respaldo, lo copié al sistema local usando el siguiente comando:
   ```bash
   docker cp odoo_container:/ruta/donde/guardar/backup.sql /ruta/local
   ```

Este procedimiento garantiza que dispongo de un respaldo completo y funcional de la base de datos, esencial para la gestión de datos en Odoo. Esta metodología es particularmente útil en entornos de desarrollo y producción que utilizan Docker.

--- 
