## Corrección del Huso Horario en Linux

## 1. Introducción
En este laboratorio, aborda el proceso para corregir el huso horario en un sistema Linux. El objetivo es asegurar que el sistema tenga la configuración de hora correcta para la región geográfica correspondiente, lo que es esencial para la correcta sincronización de eventos y actividades. A través de varios comandos, se exploraron las herramientas disponibles para gestionar la fecha y hora del sistema.

## 2. Requerimientos
- Sistema operativo Linux.
- Acceso a la línea de comandos.
- Permisos de superusuario (root) para cambiar la configuración del huso horario.

## 3. Pasos Detallados

### Paso 1: Verificar la Configuración Actual del Huso Horario
Ejecuté el siguiente comando para mostrar la configuración actual de fecha y hora:
```
timedatectl
```

Propósito: Este comando proporciona información sobre la hora actual, la zona horaria establecida y el estado de la sincronización del reloj.

### Paso 2: Listar las Zonas Horarias Disponibles
Para identificar las zonas horarias que puedo utilizar, ejecuté:
```
timedatectl list-timezones
```

Propósito: Este comando lista todas las zonas horarias disponibles en el sistema, lo que permite seleccionar la correcta.

### Paso 3: Filtrar Zonas Horarias por Región
```
timedatectl list-timezones | grep America
```

Propósito: Este comando filtra las zonas horarias para mostrar solo aquellas que pertenecen a la región de América, facilitando la búsqueda.

### Paso 4: Cambiar la Zona Horaria
Una vez identificada la zona horaria deseada, ejecuté el siguiente comando para establecerla:
```
sudo timedatectl set-timezone America/Argentina/Buenos_Aires
```
Propósito: Este comando cambia la zona horaria del sistema a "America/Argentina/Buenos_Aires". El uso de sudo asegura que tengo los permisos necesarios para realizar este cambio.

### Paso 5: Verificar el Cambio de Zona Horaria
Finalmente, verifiqué la configuración de la hora del sistema con:
```
date
```
Propósito: Este comando muestra la fecha y hora actual del sistema, lo que permite confirmar que la zona horaria ha sido ajustada correctamente.

## 4. Conclusión
Este laboratorio me permitió comprender cómo gestionar y corregir la configuración del huso horario en un sistema Linux. Aprendí a utilizar el comando timedatectl para listar y establecer zonas horarias, así como a verificar la hora actual del sistema. Este conocimiento es fundamental para la administración de sistemas, asegurando que los registros y eventos se sincronicen adecuadamente con la hora local.
