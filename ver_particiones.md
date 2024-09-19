
1. Muestra el uso del espacio en disco de los sistemas de archivos montados, con el tipo de sistema de archivos. Es útil para conocer cuánto espacio está en uso y cuánto está libre.
```
 df -Th
```

2. Lista todos los dispositivos de bloques (discos duros, particiones, etc.) en tu sistema en forma de árbol, mostrando su jerarquía y puntos de montaje. Es útil para ver cómo están organizadas las particiones y los discos.
```
 lsblk
```

3. Simula una verificación del sistema de archivos de la partición /dev/sda1 sin hacer cambios. El parámetro -N asegura que no se realicen modificaciones, solo muestra qué verificaciones se realizarían si ejecutaras el comando real.
```
 fsck -N /dev/sda1
```

4. Muestra las particiones que están actualmente montadas. Al agregar grep "^/dev", filtras solo las líneas que corresponden a dispositivos de bloque, como discos duros o particiones montadas.
```
 mount | grep "^/dev"
```

5. Muestra información sobre el contenido de la partición /dev/sda1. El comando file identifica el tipo de archivo o sistema de archivos presente en el dispositivo. Con -sL, obtienes información sobre un archivo especial como un dispositivo de bloque.
```
 file -sL /dev/sda1
```

6. Muestra información detallada sobre la partición /dev/sda1, como el tipo de sistema de archivos (ext4, NTFS, etc.), UUID (identificador único de la partición), y otras propiedades.
```
  blkid /dev/sda1
```

7. Muestra el contenido del archivo /etc/fstab, que es donde se definen los sistemas de archivos que deben montarse automáticamente al iniciar el sistema. Es útil para verificar si una partición está configurada para montarse automáticamente.
```
 cat /etc/fstab
```









