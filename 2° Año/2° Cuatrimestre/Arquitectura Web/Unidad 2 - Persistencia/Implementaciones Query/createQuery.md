## Características
- Se obtiene una implementación de Query mediante el método createQuery(String) de EntityManager.
- getResultList() retorna un objeto List con todas las entidades devueltas por la sentencia JPQL.
- Esta sentencia es **“dinámica”**, ya que es generada cada vez que se ejecuta.
- Ejecución de sentencias con parámetros dinámicos. mediante el método setParameter().

## Ejemplos
```Java
public static void main(String[] args) {
	EntityManagerFactory emf = Persistence
	.createEntityManagerFactory("introduccionJPA");
	EntityManager em = emf.createEntityManager();
	
	String jpql = "SELECT a FROM Alumno a";
	Query query = em.createQuery(jpql);
	List<Alumno> resultados = query.getResultList();
	for(Alumno p : resultados) {
		System.out.println(p.getNombre());
	}
		
	em.close();
	emf.close();
}
```

```Java title:parametroOpcion1
// se puede modificar sin problemas
String jpql = "SELECT p FROM Pelicula p WHERE p.duracion > ?1 AND p.genero = ?2"
Query query = em.createQuery(jpql);
query.setParameter(1, 180);
query.setParameter(2, "Accion");
List<Pelicula> resultados = query.getResultList();
```

```java title:parametrosOpcion2
String jpql = "SELECT p FROM Pelicula p WHERE p.duracion > :duracion AND p.genero = :genero"
Query query = em.createQuery(jpq);
query.setParameter("duracion", 180);
query.setParameter("genero", "Accion");
List<Pelicula> resultados = query.getResultList();
```

```java title:parametrosOpcion3 
String jpql = "SELECT p FROM Pelicula p WHERE p.duracion > :duracion AND p.genero = :genero";
List<Pelicula> resultados = em.createQuery(jpql)
	.setParameter("duracion", 180) 
	.setParameter("genero", "Accion")
	.getResultList();
```