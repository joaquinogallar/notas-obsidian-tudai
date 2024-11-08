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

# Características de REST
1. **Cliente-Servidor**  
   La arquitectura se basa en una separación entre el cliente (que realiza las solicitudes) y el servidor (que responde con los datos). Esto permite escalar y mejorar cada parte de forma independiente.
2. **Sin Estado (Stateless)**  
   Cada solicitud del cliente al servidor debe contener toda la información necesaria para que el servidor la procese. Esto significa que el servidor no mantiene el estado de las solicitudes previas, simplificando el escalado.
3. **Caché**  
   Las respuestas del servidor pueden indicar si la información es cacheable. Esto permite almacenar en caché datos que no cambian frecuentemente, reduciendo la carga del servidor y mejorando el rendimiento.
4. **Interfaces Uniformes**  
   REST utiliza convenciones estandarizadas, como los métodos HTTP (GET, POST, PUT, DELETE, etc.), para realizar diferentes acciones. Cada URL representa un recurso, y las acciones se realizan sobre estos recursos mediante los métodos.
5. **Representación de Recursos**  
   Los recursos pueden representarse en diferentes formatos (JSON, XML, HTML, etc.). JSON es el formato más común en APIs REST modernas debido a su simplicidad.
6. **Sistema en Capas**  
   Un sistema REST puede tener múltiples capas (servidores intermedios, cachés, etc.), y cada capa puede trabajar de manera independiente, lo que mejora la seguridad y el escalado del sistema.
