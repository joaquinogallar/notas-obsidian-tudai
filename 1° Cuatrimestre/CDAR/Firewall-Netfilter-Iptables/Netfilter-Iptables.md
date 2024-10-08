**Netfilter** es un framework del kernel de Linux que permite realizar diversas operaciones con la red, como:
- Filtrado de paquetes.
- Traducción de direcciones y puertos.
- Rastreo de conexiones.
- Otro tipo de operaciones de manipulación de paquetes.

Sistema de intercepción de paquetes en su recorrido por el Kernel (a partir de v 2.4) basado en la definición de puntos especiales en el recorrido que hacen los paquetes por el kernel (puntos de intercepción o **HOOKS**). En estos **Hooks**, es posible colocar código para filtrar, inspeccionar o modificar los paquetes mediante **iptables**. Este código implementa diferentes funciones (Firewalls, NAT, etc)

Implementaciones más conocidas sobre **netfilter**:
- **iptables**: permite manipular paquetes a nivel IP y transporte
- **ip6tables**: IPtables para IP versión 6
- **arptables**: permite manipular las tablas [[ARP (Address Resolution Protocol)]]
- **ebtables**: permite manipular los frames ethernet
- **nftables**: nueva versión de IPTables (incluye todos los anteriores)

La utilidad **iptables** es configurar las reglas de filtrado de **netfilter**.

Hay 3 conceptos básicos en **iptables**:

**Reglas**:  especifica una condición y una acción
![[Iptables01.png]]
[[Comandos Netfilter]]
[[Condiciones Netfilter]]
[[Acciones Netfilter]]

**Cadenas**: Las reglas se agrupan en listas ordenadas de reglas, llamadas cadenas y a su vez las cadenas se agrupan en tablas.
- [[INPUT]]
- [[FORWARD]]
- [[OUTPUT]]
- [[PREROUTING]]
- [[POSTROUTING]]

Una cadena es parte de una tabla, que está ubicada en cierto punto (HOOK) del recorrido de los paquetes. Las cadenas **Iptables** se llaman igual que los **Hooks** de **Netfilter**.

**Tablas**: Las tablas son estructuras organizativas que contienen las cadenas y las reglas de **iptables**.
- **NAT** = Tabla responsable de reescribir direcciones o puertos. **[[NAT (Network Address Translation)]]**
- **FILTER** = Tabla responsable del filtrado de paquetes.
- **MANGLE** = Tabla responsable de ajustar opciones de paquetes, manejar calidad de servicio, marcado o valores de TTL.
- **RAW** = Seguimiento que hace el kernel de las conexiones (por ej TCP) de la máquina.

![[Netfilter-Iptables01.png]]
![[Netfilter-Iptables02.png]]