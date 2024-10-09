Se comunica mediante **protocolos Web** (ex: **HTTP**) independientemente de la tecnología. Transfiere datos en formate **JSON**.

# Principios
1. Usar métodos **[[HTTP (HyperText Transfer Protocol)]]** explícitamente como acciones sobre recursos.
2. Exponer recursos a través de su **URL**
	- **Estructura**:
		- http://www.miservicio.com/recursos/usuarios
		- http://www.miservicio.com/recursos/usuarios/{idUsuario}
		- http://www.miservicio.com/recursos/usuarios/{idUsuario}/actividades
		- http://www.miservicio.com/recursos/usuarios/{idUsuario}/actividades/{idActividad}
3. Sin **[[Estados]]** (stateless) 
4. Transferir los datos de recursos mediante **XML**, **JSON** o ambos.