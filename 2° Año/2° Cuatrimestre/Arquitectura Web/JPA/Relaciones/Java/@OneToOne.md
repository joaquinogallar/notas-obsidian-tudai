## Ejemplo unidireccional
```Java
public class Marido {
	@Id
	private int id;
	@OneToOne
	private Mujer mujer
}

public class Mujer {
	@Id
	private int id;
}
```
Marido es **"dueña"** de la relación ya que tiene la FK. En la BD la tabla Marido, tendrá una columna que representa la relación (FK).

![[OneToOne.png]]

También se puede usar:
```Java
	@OneToOne
	@JoinColumn(name = "ID_Mujer")
```
Para especificar una columna concreta.

## Ejemplo bidireccional
```Java
@Entity
public class Mujer {
	@Id
	private int id;
	@OneToOne
	private Marido marido;
}

@Entity
public class Marido { 
	@Id
	private int id;
	@OneToOne(mappedBy = "marido") // indica que Mujer es la dueña de la relacion
	private Mujer mujer;
}
```
- Ambos mantienen una referencia.
- El dueño de la relación se especifica explícitamente.
- Ambos tienen la anotación **@OneToOne**.
- Uno de ellos debe indicar que la parte contraria es la dueña de la relación (**mappedBy**).

![[OneToOneBidireccional.png]]