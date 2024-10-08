**Regla**:
```
iptables [–t <tabla>] <comando> [<cadena>] [<condición>][<acción>]
```
En donde lo que se encuentra dentro de […] significa “opcional”.

```
iptables [-t <tabla>] -L [<cadena>] [-v]
```
**-L**: **Lista las reglas**. Si se omite la cadena el comando actúa sobre todas. Con -v se mostrara también el numero de paquetes y bytes que han cumplido la condición de cada regla.


```
iptables [-t <tabla>] -D <cadena> <numregla>
```
**-D**: Borra una regla dado su numero de regla.

```
iptables [-t <tabla>] -A <cadena> <condicion> <accion>
```
**-A**: Añade una regla al final.
