## Introducción
El objetivo de este laboratorio es configurar una máquina virtual (VM) en Linux y habilitar la salida de la consola serial, lo que facilita la administración de la VM directamente desde la terminal. Esta configuración es útil para administradores de sistemas y aquellos que buscan gestionar VMs sin depender de la interfaz gráfica.

## Requerimientos
1. Sistema Operativo: Linux con virt-manager instalado.
2. Acceso root: Se necesitan permisos de superusuario para configurar el acceso a la consola.
3. Herramientas: virt-manager, nano, virsh, update-grub (para Debian), y grub2-mkconfig (para Fedora).

## Pasos
### 1. Creación de la VM con virt-manager
Abre virt-manager e inicia el proceso de creación de la máquina virtual según tus necesidades (memoria, almacenamiento, sistema operativo, etc.).

### 2. Configurar el Acceso a la Consola Serial
Una vez creada la VM, es necesario configurar la consola serial para que la salida se envíe a ttyS0. Esto se realiza mediante la edición del archivo de configuración de GRUB:
```
nano /etc/default/grub
```
Agrega la siguiente línea en la configuración de GRUB para que el sistema redirija la salida a ttyS0:
```
GRUB_CMDLINE_LINUX_DEFAULT="console=tty0 console=ttyS0,115200n8"
```
### 3. Actualizar GRUB para Reflejar los Cambios
En Debian: Ejecuta el siguiente comando para actualizar GRUB con los cambios realizados:
```
update-grub
```
En Fedora: Usa el comando adecuado según el tipo de arranque de la VM (BIOS o EFI).
- Para BIOS:
```
grub2-mkconfig -o /boot/grub2/grub.cfg
```
- Para EFI:
```
grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg
```
### 4. Reiniciar y Administrar la VM con virsh
- Apaga la VM desde virt-manager o desde la terminal para aplicar los cambios.
- Abre una terminal y usa virsh para administrar la VM:
- Listar todas las VMs:
```
virsh list --all
```
- Iniciar la VM:
```
virsh start nombre_de_la_vm
```
- Verificar que la VM está en ejecución:
```
virsh list
```
- Conectarse a la consola serial de la VM (en este caso, llamada debian12):
```
virsh console debian12
```
## Conclusión
Este procedimiento permite la creación y configuración de una VM en Linux con salida de consola serial habilitada. Aprendí a usar virt-manager para la creación inicial de la VM y virsh para su administración mediante comandos en la terminal. Este método es útil en entornos de servidor donde el acceso a la GUI es limitado.

