- A veces se requiere una sentencia **SQL nativa** en lugar de una sentencia JPQL.
- Las consultas SQL nativas pueden ser definidas de manera **estática** como se hace con las consultas con nombre, obteniendo los mismos beneficios de eficiencia y rendimiento.
- Tanto las consultas con nombre como las consultas nativas SQL estáticas son muy útiles para definir consultas inmutables (por ejemplo, buscar todas las instancias de una entidad en la  base de datos).
- Las candidatas son aquellas consultas que se mantienen inmutables entre distintas ejecuciones del programa **(sin parámetros dinámicos)**, y que son **usadas frecuentemente**.

```Java
public static void main(String[] args) {
	EntityManagerFactory emf = Persistence
	.createEntityManagerFactory("introduccionJPA");
	EntityManager em =
	emf.createEntityManager();
	
	Query query = em.createNativeQuery("SELECT * FROM Profesor", Profesor.class);
	List<Profesor> resultados =
	query.getResultList();
	for(Profesor p : resultados) {
		System.out.println(p.getNombre());
	}
	
	em.close();
	emf.close();
}
```