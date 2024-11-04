## Introducción
En este laboratorio, se configuró un entorno simulado de gestión de usuarios y grupos en Linux. Este entorno representa un equipo de trabajo con diferentes roles de usuario, cada uno con permisos específicos. Aprendí a crear, modificar y eliminar usuarios y grupos, además de aplicar configuraciones de seguridad básicas.

## Requerimientos
1. Sistema operativo Linux.
2. Acceso root para ejecutar comandos de gestión de usuarios y grupos.
3. Herramientas: useradd, groupadd, userdel, groupdel, passwd, chage.

## Pasos
### 1. Creación de Grupos
Ejecuté los siguientes comandos para crear los grupos sys_admin, web_admin y db_admin. Los GIDs se obtuvieron luego de la creación.
```
groupadd sys_admin
groupadd web_admin
groupadd db_admin
getent group sys_admin web_admin db_admin
```
Propósito: Estos grupos se utilizarán para definir permisos específicos para los diferentes tipos de usuarios en el sistema.

### 2. Creación de Usuarios y Asignación a Grupos
Se crearon los usuarios carol y dave, asignándoles grupos específicos según el rol:
```
useradd -u 1035 -m -g sys_admin -G web_admin,db_admin carol
useradd -u 1036 -m -g web_admin -G db_admin dave
```
Propósito: Asegurar que cada usuario tenga un UID específico y pertenezca a los grupos necesarios para su rol.

### 3. Configuración de Contraseñas y Políticas de Seguridad
- Cambio de contraseñas: Configuré las contraseñas iniciales y forcé a dave a cambiar su contraseña en el primer inicio de sesión:
```
passwd carol
passwd dave
passwd -e dave
```
- Política de cambio de contraseña para Carol: Definí que Carol debe cambiar su contraseña cada 90 días:
```
chage -M 90 carol
```
Propósito: Estas configuraciones mejoran la seguridad, especialmente en entornos de trabajo con múltiples usuarios.

### 4. Verificación de Permisos de Archivos
Revisé los permisos de archivos críticos para la gestión de contraseñas y grupos:
```
ls -l /etc/passwd /etc/group /etc/shadow /etc/gshadow
```
Resultado: /etc/shadow está protegido, como corresponde en sistemas con contraseñas ocultas.

### 5. Eliminación de Usuarios y Grupos
Eliminé a dave, carol y los grupos creados tras concluir el ejercicio:
```
userdel -r dave
userdel -r carol
groupdel sys_admin
groupdel web_admin
groupdel db_admin
```
Propósito: Liberar recursos del sistema y asegurarse de que no quedan usuarios ni grupos innecesarios.

## Conclusión
Este laboratorio me permitió comprender cómo gestionar usuarios y grupos en Linux y aplicar políticas de seguridad para un entorno de trabajo simulado. Aprendí a usar comandos clave, como useradd, groupadd, passwd, y chage, y entendí la importancia de proteger archivos sensibles como /etc/shadow. Este ejercicio es útil para cualquiera que administre sistemas Linux y quiera asegurar el control de acceso a usuarios.
