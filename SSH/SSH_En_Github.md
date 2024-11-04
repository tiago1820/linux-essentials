## Comunicación con GitHub a través de SSH

Proceso de configuración de una clave SSH para poder comunicarte con GitHub de manera segura. Al utilizar SSH, puedes interactuar con tus repositorios sin necesidad de ingresar tus credenciales cada vez.

### 1. Generar una Clave SSH
Para crear una nueva clave SSH, ejecuta el siguiente comando en tu terminal:
```
ssh-keygen -t rsa -b 4096 -C "tu-email@example.com"
```

- Opcional: Se te pedirá que elijas una ubicación para guardar la clave. Puedes presionar Enter para aceptar la ubicación predeterminada.

- Opcional: También puedes ingresar una frase de paso para mayor seguridad.

### 2. Iniciar el Agente SSH
Si es necesario, inicia el agente SSH en segundo plano con el siguiente comando:
```
eval "$(ssh-agent -s)"
```
### 3. Añadir la Clave SSH al Agente
Agrega tu clave SSH al agente SSH ejecutando:
```
ssh-add ~/.ssh/id_rsa
```

### 4. Copiar el Contenido de la Clave Pública
Para copiar el contenido de tu clave pública, utiliza el siguiente comando:
```
cat ~/.ssh/id_rsa.pub
```
Copia el contenido que se muestra en la terminal.

### 5. Agregar la Clave Pública a GitHub
1. Accede a tu cuenta de GitHub.
2. Ve a Settings.
3. Selecciona SSH and GPG Keys.
4. Haz clic en New SSH Key.
5. Pega tu clave pública en el campo Key y agrega un título descriptivo.
6. Haz clic en Add SSH key para guardar.

### 6. Cambiar la URL del Repositorio Remoto de HTTPS a SSH
Para cambiar la URL del repositorio remoto de HTTPS a SSH, entra en el directorio de tu repositorio local y ejecuta:
```
git remote set-url origin git@github.com:tu-usuario/tu-repositorio.git
```

### 7. Verificar el Cambio
Para confirmar que el cambio se realizó correctamente, utiliza el siguiente comando:
```
git remote -v
```
### 8. Probar la Conexión SSH
Finalmente, prueba la conexión SSH con el siguiente comando:
```
ssh -T git@github.com
```
Si la configuración es correcta, deberías ver un mensaje de bienvenida que confirma que la autenticación fue exitosa.

## Conclusión

Este laboratorio te ha aprendi a configurar una clave SSH para interactuar con GitHub de manera segura. Utilizar SSH te permite gestionar tus repositorios sin tener que introducir tu nombre de usuario y contraseña cada vez, facilitando así el flujo de trabajo con Git y GitHub.

