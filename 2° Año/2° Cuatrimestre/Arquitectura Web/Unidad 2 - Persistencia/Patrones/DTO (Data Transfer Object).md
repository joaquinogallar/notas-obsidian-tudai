## Qué es?
En un backend Java, normalmente se tiene una capa de **servicios o presentación**, que **"expone"** datos a los clientes.

Por distintas razones, no se quiere exponer directamente las entidades y sus datos, sino un **"resume"** de una o varias entidades.

- Ofrece seguridad, separación de intereses, performance, reducir invocaciones, etc.
- **Normalmente**, un DTO es una entidad de transferencia de datos, de **solo lectura**.

![[DTOMapping.png]]

## Ejemplos
### JPA
```Java
@Entity
@Table(name="customers")
public class Customer {
	@Id
	@GeneratedValue(strategy= GenerationType.IDENTITY)
	private Long id;
	
	@Column(name="firstname")
	private String firstname;
	
	@Column(name="lastname")
	private String lastname;
	
	@Column(name="password")
	private String password;
	/** GET and SET */
}

@Entity
@Table(name="address")
public class Address {
	@Id
	@GeneratedValue(strategy=
	GenerationType.IDENTITY)
	private Long id;
	
	@ManyToMany()
	@JoinColumn(name="fk_customer")
	private Customer customer;
	
	@Column(name="country")
	private String country;
	
	@Column(name="address")
	private String address;
	
	@Column(name="zipcode")
	private String zipCode;
	/** GET and SET */
}

public class CustomerDTO implements Serializable {
	private Long id;
	private String FullName;
	private String country;
	private String Address;
	private String zipCode;
	/** GET and SET */
}
```

### Servicio
```Java
@Path("customers")
public class CustomerService {
	@GET
	@PathParam("{customerId}")
	private Response findCustomer(@PathParam("customerId") Long customerId) {
		//Entity
		Customer customer = customerDAO.findCustomerById(customerId); 
		
		//Entity
		Address address = addressDAO.findAddressByCustomer(customerId); 
		
		//Create dto
		CustomerDTO dto = new CustomerDTO();
		dto.setAddress(address.getAddress());
		dto.setCountry(address.getCountry());
		dto.setZipCode(address.getZipCode());
		dto.setFullName(customer.getFirstname() + " " + customer.getLastname());
		dto.setId(customer.getId());
		
		//Return DTO
		return Response.ok(dto, MediaType.APPLICATION_JSON).build();
	}
}
```