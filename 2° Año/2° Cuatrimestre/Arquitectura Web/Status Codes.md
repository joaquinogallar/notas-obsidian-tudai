## 1xx - Información
- **100 Continue**: El servidor ha recibido los encabezados de la solicitud y el cliente puede continuar enviando el cuerpo de la solicitud.
- **101 Switching Protocols**: El servidor acepta cambiar a un protocolo diferente según lo solicitado por el cliente.

## 2xx - Éxito
- **200 OK**: La solicitud ha tenido éxito.
- **201 Created**: La solicitud ha tenido éxito y se ha creado un nuevo recurso.
- **202 Accepted**: La solicitud ha sido aceptada para su procesamiento, pero el procesamiento no se ha completado.
- **204 No Content**: La solicitud ha tenido éxito, pero no hay contenido para devolver.

## 3xx - Redirección
- **301 Moved Permanently**: El recurso solicitado ha sido trasladado permanentemente a una nueva URI.
- **302 Found**: El recurso solicitado se encuentra temporalmente en otra URI.
- **304 Not Modified**: El recurso no ha sido modificado desde la última solicitud.

## 4xx - Error del Cliente
- **400 Bad Request**: La solicitud no se puede procesar debido a un error del cliente (por ejemplo, sintaxis incorrecta).
- **401 Unauthorized**: La solicitud requiere autenticación.
- **403 Forbidden**: El servidor ha comprendido la solicitud, pero se niega a autorizarla.
- **404 Not Found**: El recurso solicitado no se pudo encontrar.
- **409 Conflict**: Conflicto en la solicitud, a menudo utilizado en operaciones de actualización o eliminación.

## 5xx - Error del Servidor
- **500 Internal Server Error**: Se ha producido un error en el servidor y no se pudo completar la solicitud.
- **502 Bad Gateway**: El servidor, actuando como puerta de enlace, recibió una respuesta inválida del servidor de origen.
- **503 Service Unavailable**: El servidor no está disponible temporalmente, generalmente debido a mantenimiento.

## Códigos de Estado para Operaciones CRUD

| Operación CRUD | Código de Estado | Descripción                                         |
|----------------|------------------|-----------------------------------------------------|
| **Crear**      | 201 Created       | Se ha creado un nuevo recurso.                      |
| **Leer**       | 200 OK           | La solicitud ha tenido éxito y se devuelve el recurso. |
| **Actualizar** | 200 OK o 204 No Content | 200 si se devuelve el recurso actualizado, 204 si no se devuelve contenido. |
| **Eliminar**   | 204 No Content    | La eliminación fue exitosa y no hay contenido que devolver. |
| **Error de Cliente** | 400 Bad Request, 404 Not Found, 409 Conflict | Usar según el tipo de error encontrado. |

