# GRUB Instalation

## 1. Inicia o Live CD desde o sistema com problema.

## 2. Identifica a partiçao onde esta instalado o Debian com problema.
```
  sudo fdisk -l
```
 - Por exemplo: /dev/vda1

## 3. Monte o sistema de arquivos da partiçao raiz.
```
  sudo mount /dev/vda1 /mnt
```

- Monte as patiçoes especiais necessarias para o chroot.
```
  sudo mount --bind /dev /mnt/dev
  sudo mount --bind /proc /mnt/proc
  sudo mount --bind /sys /mnt/sys
```
## 4. Acesse a instalaçao com chroot.
```
  sudo chroot /mnt
```

- Agora esta dentro da instalaçao de Debian

## 5. Reinstalar GRUB

```
  apt update
  apt install grub-pc
```

- Reinstalar GRUB, para um sistema baseado em BIOS:
```
  grub-install /dev/vda
```

- Atualizar a configuraçao do GRUB:
```
  update-grub
```

## 6. Sair do chroot e desmontar
```
  exit
```

- Desmontar as partiçoes montadas anteriormente:
```
  sudo umount /mnt/dev
  sudo umount /mnt/proc
  sudo umount /mnt/sys
  sudo umount /mnt
```

## 7. Reiniciar o sistema
```
  sudo reboot
```

- Retire o Live CD para permitir que arranque desde o disco rigido.







 























