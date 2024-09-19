
1. fdisk -l:

Muestra una lista de todos los discos y particiones disponibles en el sistema. Es un paso inicial para identificar los discos antes de realizar cualquier cambio.

2. fdisk /dev/sdb:

Abre la utilidad fdisk para el disco /dev/sdb, que es el disco en el que se va a trabajar (probablemente un disco adicional al sistema principal).

3. n:

En fdisk, este comando crea una nueva partición (n es para "new").

4. p:

Especifica que la nueva partición será "primaria" (p es para "primary").

5. 1:

Asigna el número de la partición como 1, es decir, la primera partición en este disco.

6. 2048:

Este valor indica el primer sector donde comienza la partición. 2048 es un valor común para el primer sector, dejando espacio para los encabezados del disco.

7. +15GB:

Indica el tamaño de la partición. En este caso, se está creando una partición de 15 GB.

8. w:

Este comando escribe los cambios en el disco, es decir, finaliza la creación de la partición.

9. fdisk -l:

Muestra nuevamente la lista de discos y particiones para verificar que la nueva partición /dev/sdb1 fue creada correctamente.


10. mkfs.ext4 /dev/sdb1:

Formatea la partición /dev/sdb1 con el sistema de archivos ext4, preparándola para almacenar datos.

11. mkdir /data:

Crea un nuevo directorio llamado /data, que será el punto de montaje de la nueva partición.

12. mount /dev/sdb1 /data:

Monta la partición recién creada /dev/sdb1 en el directorio /data, permitiendo que se pueda acceder y escribir en ella.

13. vi /etc/fstab:

Abre el archivo /etc/fstab en el editor vi. Este archivo define los sistemas de archivos que deben montarse automáticamente al iniciar el sistema.

14. /dev/sdb1 /data ext4 defaults 0 0:

Esta línea se agrega a /etc/fstab para que la partición /dev/sdb1 se monte automáticamente en el directorio /data cada vez que el sistema arranque.
ext4 especifica el tipo de sistema de archivos.
defaults establece las opciones de montaje por defecto.
0 0 desactiva la comprobación de archivos al arrancar (el primer 0) y la comprobación de respaldo del sistema de archivos (el segundo 0).








































