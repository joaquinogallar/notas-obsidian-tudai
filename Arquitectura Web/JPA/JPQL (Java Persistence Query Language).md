## Qué es?
- Leguaje de consultas de persistencia en Java [**JPA**](JPA%20(Java%20Persistence%20API).md)
- JPQL permite realizar consultas en base de **multitud de criterios** (como por ejemplo en valor de una propiedad, o condiciones booleanas) y obtener más de una objeto por consulta.
- JPQL permite escribir consultas **portables** que funcionan con independencia de la BD y su dialecto SQL particular.
- El lenguaje de las consultas es muy parecido a SQL.

![[JPQL.png]]

---
## Consultas
```sql
SELECT p FROM Pelicula p

SELECT p FROM Pelicula p
WHERE p.duracion < 120

SELECT p FROM Pelicula p
WHERE p.duracion BETWEEN
90 AND 150

UPDATE Articulo a
SET a.descuento = 15

DELETE FROM Pelicula p
WHERE p.duracion > 190

SELECT COUNT(p) FROM
Pelicula p
```
- El alias de un objeto nos permite **acceder** a sus **atributos**.
- Algunos operadores: **>,<, =, AND, OR, NOT,BETWEEN**.
- Algunas funciones agregadas: **AVG, COUNT, MAX, MIN, SUM**.
- Tipo de operaciones:
	- **SELECT** ... **FROM**
	- **UPDATE** ... **SET**
	- **DELETE FROM**

### Relacionadas
```sql
SELECT c
FROM Cliente c JOIN c.ordenes o
WHERE c.estado = 1 AND o.precioTotal > 10000

SELECT c
FROM Cliente c, IN(c.ordenes) o
WHERE c.estado = 1 AND o.precioTotal > 10000

SELECT e
FROM Equipo e, IN(e.jugadores) j
WHERE j.direccion.ciudad = :ciudad

SELECT c
FROM Cliente c JOIN c.direccion d
WHERE d.calle = ‘calle1’
```
Podemos utilizar **JOIN** y también **IN()***.

### Parámetros
#### Con nombres
Podemos usar **parámetros** con nombres. Para esto se usan **":"** antes del nombre dado al parámetro (:nombreParam).

Los **parámetros** se especifican **luego del objeto Query** de la siguiente forma:
```Java
em.createQuery(
	"SELECT c FROM Customer c WHERE c.name LIKE :custName")
	.setParameter("custName", name) // especificación de parametros
	.getResultList();
```

#### Con Posición
Podemos usar **parámetros** con posiciones. Para esto se usa **"?"** y a continuación la posición del parámetro en la consulta.

Los **parámetros** se especifican **luego del objeto Query** de la siguiente forma:
```Java
em.createQuery(
	"SELECT c FROM Customer c WHERE c.name LIKE ?1")
	.setParameter(1, name)
	.getResultList();
```

---
## Ejecución de Sentencias

- El lenguaje JPQL puede integrarse a través de implementaciones de la **interfaz Query**.
- Dichas implementaciones se obtienen a través del **EntityManager**.
- Los más usados son:
	- [**createQuery**(String jpql)](createQuery.md)
	- [**createNamedQuery**(String name)](createNamedQuery.md)
	- [**createNativeQuery**(String sql)](createNativeQuery.md)

### TypedQuery
- Sigue siendo JPQL.
- Cuando se conoce el tipo de retorno.
- Y es más confiable en términos de los resultados.

```Java
public UserEntity getUserByIdWithTypedQuery(Long id) {
	TypedQuery<UserEntity> typedQuery = getEntityManager().createQuery("SELECT u FROM UserEntity u WHERE u.id=:id",UserEntity.class);
	typedQuery.setParameter("id", id);
	return typedQuery.getSingleResult();
}
```