### Comunicarse con GitHub a travez de SSH

1. Para renerar una clave SSH:
```
  ssh-keygen -t rsa -b 4096 -C "tu-email@example.com"
```
 - Elija una ubicación para guardar la clave(opcional)

 - Ingresa una frase de paso(opcional

2. Para iniciar el agente de SSH en segundo plano(si necesario)
```
 eval "$(ssh-agent -s)"
```

3. Para añadir tu clave SSH al agente:
```
 ssh-add ~/.ssh/id_rsa
```

4. Para copiar el contenido de la clave pública:
```
 cat ~/.ssh/id_rsa.pub
```
 - Copie el contenido.

5. Ve a GitHub:

 - Settings
 - SSH and GPG Keys
 - New SSH key
 - Pega tu clave pública en el campo "Key". Agrear Title
 - Add SSH key

6. Para cambiar la URL del repositorio remoto de HTTPS a SSH:

- Entre en el repositorio local, y use este comando:
```
  git remote set-url origin git@github.com:tu-usuario/tu-repositorio.git
```

7. Para verificar que el cambio fue exitoso:
```
 git remote -v
```

8. Para probar la conexión SSH:
```
 ssh -T git@github.com
```






