# Qué es?
Conjunto de clases que permiten a las aplcaciones Java comunicarse con distintas tecnologías de base de datos.

No es un **[[ORM (Object Relational Mapping)]]**.

## Pasos
1. Cargar el driver correspondiente de la base de datos.
2. Conectar a la base de  datos.
3. Crear y ejecutar sentencias SQL.
4. Gestionar excepciones SQL.

## Inconvenientes
- Código Java y SQL mezclados.
- Actualizar manualmente el esquema de la base de datos.
- Dependencia de la sintaxis SQL con cada base de datos.
- Lidiar con aspectos de bajo nivel: conexiones, transacciones, etc.