
1. Conectar pendrive a tu computadora.

2. Para identificar el dispositivo USB:
```
 lsblk
```
3. Para desmontar el dispositivo USB:
```
 sudo umount /dev/sdb* ("sdb" por ejemplo)
```

4. Para escribir la ISO de Debian en el pendrive:
```
 sudo dd if=/path/to/debian.iso of=/dev/sdb bs=4M status=progress
```
5. Para sincronizar los datos y asegurarte de que todos los datos han sido
escritos correctamente al USB:
```
 sync
```
6. Para expulsar el USB de forma segura:
```
 sudo eject /dev/sdb
```






