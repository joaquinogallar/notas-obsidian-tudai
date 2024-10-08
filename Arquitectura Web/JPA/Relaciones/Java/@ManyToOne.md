## Ejemplo Unidireccional
```Java
@Entity
public class Empleado {
	@Id
	@Column(name="ID_Empleado")
	private int eid;
	private String nombre;
	@ManyToOne
	@JoinColumn(name="ID_Departamento")
	private Department department;
}

@Entity
public class Departamento {
	@Id
	@Column(name="ID_Departamento") // nombre de la columna
	private int id;
	private String nombre;
}
```
Empleado es **"dueño"** de la relación y es quien tiene la FK.

![[DB ManyToOne.png]]
