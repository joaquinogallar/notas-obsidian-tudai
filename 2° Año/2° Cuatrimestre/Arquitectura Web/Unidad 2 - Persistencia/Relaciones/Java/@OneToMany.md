## Ejemplo Unidireccional
```Java
@Entity
public class Departamento {
	@Id
	private int id;
	private String name;

	@OneToMany
	private List<Empleado> listaEmpleado;
}

@Entity
public lass Empleado {
	@Id
	@Column(name="ID_Empleado")
	private int eid;
	private String nombre;
}
```
Departamento con muchas empleados. JPA utilizará por defecto una **tabla de unión** (join table).

![[OneToMany.png]]
## Ejemplo Bidireccional
One To Many y Many to One

```Java
@Entity
public class Departamento {
	@Id
	private int id;
	private String name;

	@OneToMany
	private List listaEmpleado;
}

@Entity
public class Empleado {
	@Id
	@Column(name="ID_Empleado")
	private int eid;
	private String name;

	@ManyToOne
	@JoinColumn(name="ID_Departamento")
	private Departamento departamento;
}
```

![[OneToMany&ManyToOne.png]]