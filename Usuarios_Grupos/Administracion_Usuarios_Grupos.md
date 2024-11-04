## Administración de Usuarios y Grupos en Linux

## 1. Introducción
En este laboratorio, se simula tareas típicas de un administrador de sistemas Linux relacionadas con la gestión de usuarios y grupos. Aprendo a crear, modificar y gestionar cuentas de usuario, así como a manejar la información de grupos y privilegios de acceso en el sistema. También explorare cómo funcionan los archivos críticos que almacenan esta información y cómo utilizarlos de manera efectiva.

## 2. Requerimientos
- Sistema operativo Linux (preferiblemente una distribución como Debian o Fedora).
- Acceso a la línea de comandos.
- Permisos de superusuario (root) para realizar cambios en la gestión de usuarios y grupos.

## 3. Pasos Detallados

### Paso 1: Exploración de Archivos de Usuarios y Grupos
Primero, examinaremos los archivos que contienen la información de usuarios y grupos.

1. Visualizar el contenido del archivo /etc/passwd:
```
cat /etc/passwd
```
Propósito: Este archivo contiene todos los atributos de las cuentas de usuario, excluyendo los hashes de contraseñas.

2. Visualizar el contenido del archivo /etc/group:
```
cat /etc/group
```
Propósito: Este archivo muestra todos los atributos de las cuentas de grupo locales.

3. Visualizar el contenido del archivo /etc/shadow:
```
sudo cat /etc/shadow
```

Propósito: Este archivo contiene los hashes de las contraseñas de los usuarios y es accesible solo por procesos privilegiados.

### Paso 2: Creación y Gestión de Usuarios

A continuación, crearemos nuevos usuarios y les asignaremos grupos.

1. Crear un nuevo usuario llamado jorge:
```
sudo useradd -m jorge
```
Propósito: Crea una nueva cuenta de usuario y su directorio personal.

2. Establecer una contraseña para el usuario jorge:
```
sudo passwd jorge
```
Propósito: Asigna una contraseña al usuario recién creado.

3. Crear un grupo llamado desarrolladores:
```
sudo groupadd desarrolladores
```
Propósito: Crea un nuevo grupo para gestionar permisos de desarrollo.

4. Agregar el usuario jorge al grupo desarrolladores:
```
sudo usermod -aG desarrolladores jorge
```
Propósito: Asigna al usuario jorge al grupo desarrolladores, permitiendo el acceso a los recursos compartidos.

### Paso 3: Modificación de Información de Usuario
Ahora modificaremos la información del usuario.

1. Cambiar el shell del usuario jorge a /bin/bash:
```
sudo chsh -s /bin/bash jorge
```
Propósito: Cambia el shell predeterminado del usuario a bash.

2. Modificar la información del usuario en el campo GECOS:
```
sudo chfn jorge
```

Propósito: Permite editar la información de usuario, como nombre completo y número de teléfono.

### Paso 4: Verificación de Usuarios y Grupos
Ahora, verificaremos el estado de los usuarios y grupos.

1. Listar los ID de usuario y grupo del usuario jorge:
```
id jorge
```
Propósito: Muestra los UID y GIDs del usuario para verificar su asignación.

2. Ver los usuarios que han iniciado sesión recientemente:
```
last
```
Propósito: Proporciona un historial de las últimas sesiones de usuarios en el sistema.

3. Verificar qué usuarios están actualmente conectados:
```
who
```
Propósito: Muestra una lista de usuarios actualmente conectados al sistema.

4. Ver información adicional sobre los usuarios conectados:
```
w
```
Propósito: Proporciona una visión más detallada de la actividad de los usuarios conectados.

### Paso 5: Conceder Permisos de sudo y Ejecutar Comandos con Privilegios
Primero, necesitamos otorgarle permisos de sudo al usuario jorge para que pueda ejecutar comandos con privilegios elevados.

1. Agregar el usuario jorge al grupo sudo:
```
usermod -aG sudo jorge
```

- Para Fedora:
```
usermod -aG wheel jorge
```

Propósito: Este comando añade al usuario jorge al grupo sudo, otorgándole los permisos necesarios para ejecutar comandos con privilegios de superusuario.

2. Confirmar que jorge tiene permisos de sudo:
- Cambia al usuario jorge:
```
su - jorge
```

- Ejecuta un comando con sudo para verificar:
```
sudo whoami
```
- Nota: Si es la primera vez que jorge usa sudo, se le pedirá que confirme con su contraseña.

Propósito: Este paso permite verificar que jorge tiene permisos de sudo. El comando sudo whoami debería devolver "root" si se han otorgado correctamente los permisos.

3. Ejecutar un comando como superusuario (opcional):
```
sudo apt update
```
Propósito: Este comando actualiza la lista de paquetes del sistema, confirmando que jorge tiene permisos de superusuario.


## 4. Conclusión
Este laboratorio me permitió familiarizarme con las herramientas y comandos esenciales para la gestión de usuarios y grupos en un sistema Linux. Aprendi a crear y modificar cuentas de usuario, gestionar grupos, y verificar la información de acceso y actividad del sistema. Estos son pasos fundamentales para cualquier administrador de sistemas que busca mantener la seguridad y la organización en el entorno Linux.