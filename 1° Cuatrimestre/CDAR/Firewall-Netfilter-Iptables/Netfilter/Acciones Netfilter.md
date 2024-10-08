```
-j ACCEPT
```
- Acepta el paquete.

```
-j DROP
```
- Permite descartar el paquete sin procesarlo.

```
-j REJECT
```
- Tiene el mismo efecto que **DROP**, pero retorna un paquete de error al origen.

```
-j SNAT --to-source [<dirIP>][:<puerto>]
```
- Realiza **Source NAT** sobre los paquetes salientes (es decir, se cambia dirección IP y/o puerto origen). Solo se puede realizar en la cadena [[POSTROUTING]]. Esta regla hace que también se cambie automáticamente la dirección de destino del tráfico entrante de respuesta al saliente de la misma conexión.

```
-j DNAT --to-destination [<dirIP>][:<puerto>]
```
- Realiza **Destination NAT** sobre los paquetes entrantes (es decir, se cambia dirección IP y/o puerto destino). Solo se puede realizar en la cadena [[PREROUTING]]. Esta regla sólo es necesaria para abrir puertos, es decir, permitir tráfico entrante nuevo.

```
-j MASQUERADE --to-source [<dirIP>][:<puerto>]
```
- Permite realizar enmascaramiento IP o NAPT. Esto consiste en que el servidor identifica que uno de los equipos de la red intenta conectar a una dirección de fuera de ésta, y es el mismo servidor el que realiza la petición, en lugar de que la máquina cliente lo haga. Así, el servidor toma la dirección IP y puerto de la máquina que hace la solicitud, la "enmascara" con la dirección IP y puerto que le ha sido asignada, la envía, y cuando llega el paquete de respuesta lo "reenvía" a la máquina y puerto que realizó la petición.