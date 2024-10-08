## Ejemplo unidireccional
```Java
@Entity
public class Alumno {
	@Id
	private int id;
	private String name;

	@ManyToMany
	private Set<Profesor> profesores;
}

@Entity
public class Profesor {
	@Id
	private int id;
	private String name;
}
```

![[ManyToMany.png]]

## Ejemplo bidireccional
```Java
@Entity
public class Alumno {
	@Id
	private int id;
	private String name;

	@ManyToMany(mappedBy = "alumnos")
	private Set<Profesor> profesores;
}

@Entity
public class Profesor {
	@Id
	private int id;
	private String name;

	@ManyToMany
	private Set<Alumno> alumnos;
}
```
- Un profesor tiene muchos alumnos y un alumno tiene muchos profesores.
- Dueño de la relación se especifica explícitamente (mappedBy).


![[ManyToManyBidireccional.png]]