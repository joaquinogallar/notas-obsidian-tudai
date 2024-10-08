## Qué es?
- Es una **abstracción** del concepto de **repositorio**.
- Permite agrupar las operaciones lógicas de read/write de entidad(es) específica(s).
- La lógica de negocio accede al repositorio, independientemente de su implementación.
- La implementación puede basarse en [JPA](JPA%20(Java%20Persistence%20API).md), [JPQL](JPQL%20(Java%20Persistence%20Query%20Language).md), etc.

![[PatronRepository.png]]

## Ejemplo
```Java
public interface BookRepository {
	Book getBookById(Long id);
	Book getBookByTitle(String title);
	Book saveBook(Book b);
	void deleteBook(Book b);
}

public class BookRepositoryImpl implements BookRepository {
	private EntityManager em;
	
	public BookRepositoryImpl(EntityManager em) {
		this.em = em;
	}
	
	public Book getBookById(Long id) {
		return em.find(Book.class, id);
	}
	
	public Book getBookByTitle(String title) {
		TypedQuery<Book> q = em.createQuery("SELECT b
		FROM Book b WHERE b.title = :title", Book.class);
		q.setParameter("title", title);
		return q.getSingleResult();
	}
	
	public Book saveBook(Book b) {
		if (b.getId() == null) {
			em.persist(b);
		} else {
			b = em.merge(b);
		}
		return b;
	}
	
	public void deleteBook(Book b) {
		if (em.contains(b)) {
			em.remove(b);
		} else {
			em.merge(b);
		}
	}
}

```