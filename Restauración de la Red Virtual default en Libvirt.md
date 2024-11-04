## Restauración de la Red Virtual default en Libvirt
En algunos casos, como después de una actualización, la red virtual predeterminada default configurada por libvirt puede dejar de estar disponible. Este documento detalla los pasos necesarios para restaurarla.

### Problema
La red virtual default no está presente en el sistema, lo cual impide el acceso a la red de las máquinas virtuales que dependen de esta configuración.

### Verificar las Redes Disponibles
Para comprobar las redes configuradas en libvirt, utiliza el siguiente comando:
```
virsh net-list --all
```
Ejemplo de salida:
```
root@debian:/etc/libvirt/qemu/networks# ls
autostart  default.xml.dpkg-backup
root@debian:/etc/libvirt/qemu/networks#
```

En el directorio /etc/libvirt/qemu/networks, existe un archivo llamado default.xml.dpkg-backup, lo que indica que el archivo de configuración de la red default fue respaldado (probablemente durante una actualización del sistema o de libvirt). Para restaurar esta red, renombra el archivo para que libvirt pueda reconocerlo de nuevo.

## Pasos para Restaurar la Red default

### 1. Renombrar el Archivo de Respaldo
Renombra el archivo de respaldo para que libvirt lo detecte como la red default:
```
mv /etc/libvirt/qemu/networks/default.xml.dpkg-backup /etc/libvirt/qemu/networks/default.xml
```
### 2. Definir la Red en Libvirt
Con el archivo renombrado, carga su configuración en libvirt:
```
virsh net-define /etc/libvirt/qemu/networks/default.xml
```
### 3. Iniciar la Red y Configurar Autoinicio
Inicia la red y configúrala para que se active automáticamente en cada inicio del sistema:
```
virsh net-start default
virsh net-autostart default
```
### 4. Verificar que la Red Esté Activa
```
  virsh net-list --all
```
## Verificación Final
Si la red se ha restaurado correctamente, deberías poder iniciar tu máquina virtual debian12 nuevamente usando:
```
virsh start debian12
```
Este procedimiento asegura que la red virtual default esté disponible y configurada para su uso en libvirt, permitiendo que las máquinas virtuales conectadas a esta red funcionen correctamente.




























