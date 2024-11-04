### 1. dig (Domain Information Groper):

- Descripción: Herramienta para realizar consultas DNS. Permite obtener información sobre nombres de dominio, como direcciones IP o registros DNS específicos.

- Ejemplo:
Consultar la IP de un dominio:
```
  dig google.com
```
- Esto te muestra los registros A (direcciones IPv4) asociados al dominio google.com.

- Consultar el registro MX (correo) de un dominio:
```
  dig google.com MX
```

### 2. host:

- Descripción: Comando más simple que dig para resolver nombres de dominio y obtener direcciones IP.

- Ejemplo: Consultar la IP de un dominio:

```
  host google.com
```

- Te devuelve la IP asociada a google.com.

- Invertir una IP para obtener su dominio (PTR):

```
  host 8.8.8.8
```

- Muestra el nombre de dominio asociado a la IP.

### 3. ip:

- Descripción: Comando usado para gestionar y consultar configuraciones de red, como interfaces, rutas, y direcciones IP.

- Ejemplo: Ver todas las interfaces de red:

```
  ip link show
```

- Muestra el estado y las configuraciones básicas de las interfaces.

- Asignar una dirección IP a una interfaz:

```
  sudo ip addr add 192.168.1.100/24 dev enp1s0
```

- Esto asigna la IP 192.168.1.100 a la interfaz enp1s0.

### 4. ping:

- Descripción: Comando para probar la conectividad entre dos dispositivos enviando paquetes ICMP.

- Ejemplo:
Verificar la conectividad con una IP o dominio:
```
  ping google.com
```

- Envía paquetes a google.com y muestra el tiempo de respuesta.

- Hacer una prueba con un número limitado de paquetes:

```
  ping -c 4 8.8.8.8
```

- Envia solo 4 paquetes a la dirección IP 8.8.8.8.

### 5. ss (Socket Statistics):

- Descripción: Comando para mostrar información detallada sobre conexiones de red y sockets.

- Ejemplo:
Ver todas las conexiones TCP activas:
```
  ss -t
```

- Muestra todas las conexiones TCP abiertas en el sistema.

- Ver conexiones en escucha (puertos abiertos):
```
  ss -l
```

- Muestra los puertos en los que el sistema está escuchando.