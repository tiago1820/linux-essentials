Para obtener una lista de todas las interfaces de red disponibles en el sistema:
```
ip link show
```

Para asignar una direccion IP a una interfaz de red:
sudo ip addr add 192.168.0.5/255.255.255.0 dev ens33

Para mostrar la informacion detallada sobre las direcciones IP asignadas a las interfaces de red:
```
ip addr show
```

Para verificar la conectividad de red entre tu maquina y el dispositivo
con la direccion IP "192.168.0.1"
```
  ping -c 3 192.168.0.1
```

Para mostrar la tabla de enrutamiento de IP en el sistema:
```
  ip route show
```

Para agregar una ruta por defecto en la tabla de enrutamiento del sistema:
```
sudo ip route add default via 192.168.0.1
```

Para agregar una dirección IPV6 a una interfaz de red:
```
  sudo ip addr add 2001:db8:0:abcd:0:0:0:7334/64 dev ens33
```

Para enviar un solo paquete de prueba (ICMP echo request) a una dirección IPv6 específica:
```
 ping6 -c 1fe80::010c:29ff:fe33:3b25%ens33
```

Para mostrar el contenido del archivo "/etc/resolv.conf".
Este archivo especifica cómo el sistema debe resolver los nombres de dominio en
direcciones IP mediante el uso de servidores DNS:
```
  cat /etc/resolv.conf
```

Para mostrar información sobre una dirección IP asociada a un nombre de dominio:
```
  host learning.lpi.org
```

Para realizar una consulta DNS para obtener información sobre un dominio:

```
  dig learning.lpi.org
```

Para visualizar las conexiones de red y los sockets en el sistema:
```
  ss
```

Algunas opciones del comando ss:
 -p: Muestra el PID y el nombre del proceso asociado con cada conexión de red o socket.
 -s: Muestra un resumen estadístico de los sockets en el sistema.
 -4: Muestra solo las conexiones que utilizan el protocolo IPv4.
 -6: Muestra solo las conexiones que utilizan el protocolo IPv6.
 -t: Muestra solo las conexiones que utilizan el protocolo TCP.
 -u: Muestra solo las conexiones que utilizan el protocolo UDP.

Comandos utilizados en el capitulo de redes:
 - dig
 - host
 - ip
 - ping
 - ss


