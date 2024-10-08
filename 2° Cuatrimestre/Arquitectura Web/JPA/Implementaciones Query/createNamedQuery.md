## Características
- Una vez definidos, **no pueden ser modificados**.
- Son leídos y transformados en sentencias SQL cuando el programa arranca **por primera vez**.
- Las consultas con nombre son definidas mediante metadatos (anotación @NamedQuery).
- El nombre de la consulta debe ser **único** dentro de su unidad de persistencia.
- Es una buena idea utilizar una constante definida dentro de la propia entidad, y usarla como nombre de la consulta.

## Ejemplos
```Java
@Entity
@NamedQuery(name=Alumno.BUSCAR_TODOS, query="SELECT a FROM
Alumno a")
public class Alumno{
	public static final String BUSCAR_TODOS =
	"Alumno.buscarTodos";
	// ...

	public static void main(String[] args) {
		EntityManagerFactory emf = Persistence
		.createEntityManagerFactory("introduccionJPA");
		EntityManager em = emf.createEntityManager();
		
		Query query = em.createNamedQuery(Alumno.BUSCAR_TODOS);
		List<Alumno> resultados = query.getResultList();
		for(Alumno p : resultados) {
			System.out.println(p.getNombre());
		}
			
		em.close();
		emf.close();
	}
}
```