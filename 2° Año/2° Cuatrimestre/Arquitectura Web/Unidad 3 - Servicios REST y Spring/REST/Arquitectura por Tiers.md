# Tier 3
![[Tiers01.png]]
- **Rest Controller**: Capa que se encarga de presentar nuestra **API REST**, convirtiendo **Json** a **POJO (Plain Old Java Object)** y vice-versa.
- **Service**: Capa que implementa la lógica del negocio. Abstrae de la presentación.
- **JPARepository**: Capa que define las operaciones que se pueden hacer con la base de datos.
![[Tiers02.png]]

## Diferencias con un enfoque de tier 2
La diferencia radica en donde se realiza la lógica de negocios. En una tier 2, la lógica de negocios se realiza del lado del cliente, mientras que en una tier 3 se crea un nuevo componente encargado de manejarla, dejando que el cliente solo se encargue de la vista y el servidor de la base de datos. Esto a pesar de volver mas complejo el código tiene la ventaja de una mayor escalabilidad y control.

Ejemplo tier 2: app escritorio.
Ejemplo tier 3: ecommerce.
