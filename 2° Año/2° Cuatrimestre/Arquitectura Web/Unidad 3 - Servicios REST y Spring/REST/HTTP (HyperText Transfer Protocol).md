Protocolo de transferencia de texto (JSON).

# Métodos
![[MetodosCRUD.png]]
1. **Create**: envía una respuesta a la que se vincula un objeto de tipo JSON llamado **body** con los datos del nuevo elemento. (**[[Status Codes]]**: **201, 400**)
2. **Read**: obtiene todos los datos, también se pueden filtrar por atributos o cantidad de elementos. (**[[Status Codes]]**: **200, 404**)
3. **Update**: actualiza un elemento, se necesita un **identificador** de ese elemento y un **body** con los nuevos datos.
4. **Delete**: elimina un elemento, se necesita un **identificador** para borrar el elemento en cuestion.