### Qué es?
JPA es una API estándar de Java para implementar un **[[ORM (Object Relational Mapping)]]**.

Es una **abtracción** sobre JDBC

![[JPA abstraccion de JDBC.png]]

JPA solo es la API. Para usarla, se necesita una **implementación** o **proveedor** de la misma, como **Hibernate**.

Se configura a través de metadatos.

## [Asociaciones](2°%20Año/2°%20Cuatrimestre/Arquitectura%20Web/Unidad%202%20-%20Persistencia/Relaciones/Asociación.md) en JPA
Anotaciones en JPA para las asociaciones:
- [**@ManyToOne**](@ManyToOne.md)
- [**@OneToMany**](@OneToMany.md)
- [**@OneToOne**](@OneToOne.md)
- [**@ManyToMany**](@ManyToMany.md)

**transient** ignora el atributo a la hora de mapearlo a la base de datos
```java title:atributoTransient
private transient String noMapear;
```
### Tipos de Lectura
- **Lazy**: Leer una propiedad desde la base de datos la primera vez que un cliente intenta acceder a su valor.
- **Eager**: Leerla cuando la entidad que la contiene es creada.

Para relaciones [**One to One**](@OneToOne.md) y [**Many to One**](@ManyToOne.md) por defecto utilizamos **Eager**.
Para relaciones [**One to Many**](@OneToMany.md) y [**Many to Many**](@ManyToMany.md) por defecto utilizamos **Lazy**.

```Java
@OneToMany(fetch = FetchType.EAGER) // se puede modificar el tipo de lectura
private List<Pedido> pedidos;
```

### Propiedades de las Anotaciones de Asociación
| Propiedad         | Descripción                                                                                                                                                                                        |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Target Entity** | Para especificar el tipo (clase) de la entidad a la que se hace referencia. Por defecto, i**nfiere el tipo**.                                                                                      |
| **Cascade**       | Para especificar que las operaciones de persistencia pueden abarcar también a las referencias. Por defecto **es vacío.** Probar "ALL".                                                             |
| **Fetch**         | Para especificar el tipo de lectura de la referencia.                                                                                                                                              |
| **mappedBy**      | Para especificar el dueño del relación en las asociaciones bidireccionales. Solo puede utilizarase en anotaciones como **One-to-Many** o **One-to-One** (Many-to-One, **NO** tiene esta propiedad) |
