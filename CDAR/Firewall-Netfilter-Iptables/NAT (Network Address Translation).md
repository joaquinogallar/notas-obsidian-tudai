
![[Nat01.png]]

**NAT** resuelve la pregunta de ¿Cómo podemos dar salida a Internet a una red con direcciones **[[IPs]]** privadas?

![[Nat02.png]]**Todos** los datagramas **saliendo** de la red local tienen la **misma** dirección NAT IP: 138.76.29.7, pero diferentes números de **[[Puertos]]**.

Los datagramas con fuente o destino en la Red local tienen direcciones 10.0.0.X/24.

---
La traducción de direcciones trabaja sobre:
![[Nat03.png]]

---

En la tabla NAT se traduce (IP origen, puerto)  a (IP NAT, nuevo puerto) o viceversa. 

El **nuevo puerto** es un puerto aleatorio.

Para los **datagramas salientes** se reemplaza (IP origen, puerto) de cada datagrama saliente por (IP NAT, nuevo puerto).
Mientras que para los **datagramas entrantes** se reemplaza (IP NAT, nuevo puerto) en campo destino de cada datagrama entrante por correspondiente (IP origen, puerto) almacenado en tabla NAT.
![[Nat04.png]]

[[Apertura-Redireccion de puertos]]