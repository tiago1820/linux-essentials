### Crear la VM via virt-manager

### Configurar el acceso a la consola de serie:
- Debe ser hecho a travez de virt-manager

```
  nano /etc/default/grub
```
Agrega estas líneas para que el sistema mande la
salida a ttyS0:
```
 GRUB_CMDLINE_LINUX_DEFAULT="console=tty0 console=ttyS0,115200n8"
```

### Debia: Actualiza el GRUB:
```
 update-grub
```
### FEDORA: Para actualizar el GRUB:
### BIOS
```
  grub2-mkconfig -o /boot/grub2/grub.cfg
```
### EFI
```
  sudo grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg
```

### Apaga la vm y despues abra el terminal y inicie la vm via virsh.

### Para listar las VMs:
```
  virsh list --all
```
### Iniciar la vm:
```
  virsh start nombre_de_la_vm
```

### Para verificar que la vm esta en ejecucion:
```
  virsh list
```
### Para conectarse a la consola:
```
 virsh console debian12
```


















