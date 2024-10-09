![[Capas.png]]
- **Persistencia**:
	- **Models**: el *objeto* a nivel *BD*.
	- **[[DTO (Data Transfer Object)]]**: objeto a nivel lenguaje.
	- **Mapper**: conversión de un modelo a un **Dto**.
- **Servicio**:
	- **Services**: operaciones listadas por el servicio.
	- **[[Repository]] / DAOs (Data Access Objetcs)**: interfaz de la capa de persisitencia.
- **Seguridad**: 
	- **Config y security**: configuraciones del portal y administración de tokens de autenticación. Uso de roles y permisos.
- **Controladores**:
	- Lleva a cabo la maniupulación de todo, desde la invocación hasta preparar la respuesta, Aquí es donde se publican los serivicios que provee esta aplicación.

**[[Arquitectura por Tiers]]**