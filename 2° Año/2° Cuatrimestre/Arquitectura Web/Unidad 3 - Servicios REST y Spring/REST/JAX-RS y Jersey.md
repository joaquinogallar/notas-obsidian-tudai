- **JAX-RS (Java API for RESTful Web Services)**: API estándar de Java para construir servicios con interfaz **[[REST (Representational State Transfer)]]**.
- **Jersey**: implementación de referencia de **JAX-RS**.
![[JAX-RS y Jersey.png]]

# Mapeo requests HTTP a métodos Java:
- **@Path("/path")**
- **@GET - @PUT - @POST - @DELETE - @HEAD**
- **@Produces(MediaType.X)**
- **@Consumes(MediaType.X)**
	- MediaType.APPLICATION_JSON
	- MediaType.APPLICATION_XML
	- MediaType.TEXT_HTML
	- MediaType.TEXT_PLAIN

# Extraer informacion de las requests
- **@PathParam("param")**
- **@QueryParam("param")**
- **@MatrixParam("param")**
- **@HeaderParam("param")**
- **@CookieParam("param")**
- **@FormParam("param")**
- **@DefaultValue("value")**
- **@Context**