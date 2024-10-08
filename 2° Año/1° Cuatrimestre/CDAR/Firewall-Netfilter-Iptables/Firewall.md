
## Filtrado de paquetes
Sistema o grupo de sistemas utilizados para **separar** una máquina o una subred (zona protegida) del resto de la red (zona de riesgo).
Un cortafuegos o **firewall** es un elemento de hardware o software que se utiliza para controlar las comunicaciones, ya sea permitiéndolas o bien prohibiéndolas según las políticas de red que hayan sido definidas.

**Perímetro interno**: Donde se sitúan todos los recursos sensibles a un posible ataque.

**Perímetro externo**: Donde se sitúan los recursos menos sensibles que necesitan ser accesibles desde la red externa por motivos funcionales.
![[Firewall01.png]]

**Como trabaja?**
- Establece **políticas de control** entre ambos entornos.
- **Filtrado de paquetes,** consiste en denegar o permitir el flujo de información entre la red interna que deseamos proteger y el resto o la red externa. 
- Actúan sobre la **capa de red y la de transporte** de la pila TCP/IP. Analizan la cabecera sin llegar a los datos

---
## Políticas por defecto
Existen dos esquemas o políticas por defecto a la hora de configurar un firewall, **aceptación** o **rechazo**.
- En la primera se filtran o rechazan conexiones consideradas peligrosas mientras que se acepta o admite todo el resto
- En la segunda se aceptan aquellas conexiones que se consideran legales o válidas mientras que se filtra o rechaza el resto

---
## Limitaciones
Tráfico que no puede analizar
- Tráfico que no lo atraviesa (puertas traseras - backdoor)‏
- Ataques desde la red interna
- Servicios públicos: e-mail, virus, spam, web, ftp
- Robo de información de empleados.
- Ataques de ingeniería social
- Servicios mal configurados

En lo que es Firewall entra mucho los siguientes conceptos de **[[Seguridad]].**