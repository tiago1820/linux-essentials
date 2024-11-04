## Virtualización con KVM y Herramientas Relacionadas

## Introducción
En este laboratorio, se exploraron las tecnologías de virtualización en Linux utilizando KVM (Kernel-based Virtual Machine) y herramientas asociadas como QEMU, libvirt, virsh y virt-manager. El objetivo fue aprender a configurar y gestionar máquinas virtuales, así como comprender la arquitectura de la virtualización en Linux.

## Requerimientos
- Sistema operativo: Linux (Debian o Ubuntu recomendado).
- Permisos: Acceso root para instalar paquetes y gestionar servicios.
- Herramientas: KVM, QEMU, libvirt, virsh, virt-manager.

## Pasos Detallados

### 1. Comprender la Arquitectura de Virtualización

- KVM: Módulo del kernel que permite la virtualización.
- QEMU: Emulador que actúa como hardware virtual.
- libvirt: API que facilita la gestión de plataformas de virtualización.
- virsh: Interfaz de línea de comandos para interactuar con libvirt.
- virt-manager: Herramienta gráfica para gestionar máquinas virtuales.

### 2. Verificar la Compatibilidad de Virtualización
Para comprobar si la CPU es compatible con la virtualización, se utilizan los siguientes comandos:
```
lscpu
grep vmx /proc/cpuinfo
grep svm /proc/cpuinfo
```

- vmx: Soporte para Intel VT.
- svm: Soporte para AMD-V.

### 3. Instalar Herramientas de Virtualización
Instala las herramientas necesarias para gestionar la virtualización:
```
apt install virt-manager
apt install virsh
```

### 4. Comandos básicos de virsh
Listar todas las máquinas virtuales disponibles:
```
virsh list --all
```
Iniciar una máquina virtual específica:
```
virsh start --domain nombreDeLaMaquina
virsh start nombreDeLaMaquina
```
Verificar el estado de las máquinas virtuales:
```
virsh list --all
```
Editar la configuración de una máquina virtual:
```
virsh edit --domain debian12
```

### 5. Gestionar el Servicio de libvirt
Iniciar el servicio de libvirt:
```
systemctl start libvirtd.service
```
Verificar si el servicio está habilitado para iniciarse en el arranque:
```
systemctl is-enabled libvirtd.service
```

Deshabilitar el servicio si es necesario:
```
systemctl disable libvirtd.service
```

### 6. Verificar la Distribución del Sistema
Obtener información sobre la distribución actual:
```
lsb_release -a
```
### 7. Configuración de Usuarios
Agregar un usuario al grupo libvirt para permitir la gestión de máquinas virtuales:
```
adduser tiago libvirt
```
Verificar la información del usuario:
```
id tiago
```

## Conclusión
Este laboratorio me proporcionó una comprensión práctica de la virtualización en Linux utilizando KVM y herramientas asociadas. Aprendí a instalar y configurar las herramientas necesarias, verificar la compatibilidad de virtualización y gestionar máquinas virtuales usando tanto la línea de comandos como interfaces gráficas. Estas habilidades son esenciales para la administración de sistemas virtualizados y son aplicables en entornos de servidores y desarrollo.
