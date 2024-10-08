
[[Seguridad]]
# Funciones HASH
- Algoritmos que toman un input de tamaño arbitrario (como un archivo o mensaje) y producen un output de tamaño fijo, conocido como hash.
- El hash actúa como una huella digital del contenido original.
- La propiedad más importante de una función hash es que es computacionalmente inviable encontrar dos entradas diferentes que produzcan el mismo hash (resistencia a colisiones).
- Cualquier cambio, incluso mínimo, en el input debería cambiar el hash de manera significativa, lo que se conoce como propiedad de avalancha.
- Son herramientas esenciales para verificar la integridad de los datos, asegurando que el contenido no haya sido alterado de ninguna forma desde su creación.
- Los más populares son: SHA-256 y MD5

## Integridad
**Tamaño del Hash:**
- MD5: Produce un resumen de 128 bits (16 bytes) del mensaje original.
- SHA-256: Parte de la familia SHA-2, produce un resumen de 256 bits (32 bytes). Esto hace que SHA-256 sea más resistente contra ataques, ya que tiene un espacio de hash mucho más grande comparado con MD5.

**Resistencia a Colisiones:**
- MD5: Ha sido ampliamente criticado y dejado de usar en muchos contextos de seguridad debido a su vulnerabilidad a ataques de colisión rápidos. Esto significa que es relativamente más fácil encontrar dos entradas diferentes que resulten en el mismo hash MD5.
- SHA-256: Ofrece una mayor resistencia a colisiones debido a su mayor longitud de bit. No se conocen ataques efectivos de colisión contra SHA-256, lo que lo hace adecuado para uso en aplicaciones de seguridad modernas.

**Velocidad de cómputo**:
- MD5: Generalmente es más rápido en la generación de hashes comparado con SHA-256. Esto puede ser ventajoso para aplicaciones que no son de seguridad, donde la velocidad es más crítica que la integridad máxima.
- SHA-256: Es más lento en comparación con MD5 debido a su mayor complejidad y tamaño de salida. Sin embargo, esta desventaja es compensada por su mayor seguridad.

**Usos**:
- MD5: Debido a sus debilidades, ahora se utiliza principalmente en aplicaciones no críticas o para verificar la integridad de los datos en contextos donde la seguridad no es una gran preocupación, como en la generación de identificadores únicos o en sistemas donde la compatibilidad con legados es necesaria.
- SHA-256: Es ampliamente utilizado en aplicaciones de seguridad críticas, incluyendo protocolos de seguridad, sistemas de cifrado, y más recientemente en la tecnología blockchain y otras aplicaciones de criptografía.

## Kerberos

**¿Qué es?** 
- Es un servicio de autenticación utilizado en redes informáticas abiertas o no seguras

**¿Cuál es su propósito?** 
- Que un cliente pueda demostrar su identidad a un servidor (y viceversa) a través de una conexión de red insegura

**¿Para qué utilizarlo?**
- Para prevenir los ataques de intermediario y garantizar que los datos de las credenciales del usuario no sean interceptadas durante el proceso de autenticación.

**¿Cómo logra su propósito?**
- Se basa en el protocolo de clave simétrica 
- Usa un tercero de confianza, denominado "centro de distribución de claves" (Key Distribution Center), 
**Consta de dos partes lógicas independientes:** 
- Un "servidor de autenticación" (AS o Authentication Server)
- Un "servidor emisor de tickets" (TGS o Ticket Granting Server). 
- Estos "tickets" se utilizan para verificar la identidad de los usuarios.
# VPN (Virtual Private Networks)

Cifra todo el tráfico que pasa a través de el.

Al conectarnos a una VPN, nuestro tráfico irá directo hacia nuestro proveedor de internet, y luego hasta nuestro servidor VPN, para luego partir al destino que corresponda (un equipo dentro de la red de mi empresa o internet).

En general, a menos que tengamos una configuración avanzada de nuestro equipo, al momento de conectarnos a una VPN, estaremos navegando a través de la IP pública de nuestra empresa. La IP pública de nuestra casa, se usará solo para poder llegar hasta nuestra empresa.

## Los protocolos más famosos

**IPSec (Internet Protocol Security)**: es una extensión del protocolo IP. Ofrece suministro de privacidad al usuario, la integridad de los datos y la autenticidad de la información.

**PPTP (Point-to-Point Tunneling Protocol)**: basado en MPPE con claves de 128 bits. Fácil de configurar, pero es más sencillo de descifrar. 

**L2TP/IPSec (Layer 2 Tunneling Protocol)**: es un protocolo de encapsulación, más seguro que PPTP. Se basa en IPSec para proporcionar privacidad a los usuarios remotos de la red

**OpenVPN**: Es considerado uno de los más seguros. Basado en SSL. Se generan certificados que el cliente suministra para realizar la conexión

**SSTP (Secure Socket Tunneling Protocol)**: creado y desarrollado por Microsoft. Es una mejora actualizada del ya existente PPTP. Se considera uno de los más seguros y en Windows viene integrado de serie.  El tráfico PPP o L2TP se envía a través de un canal SSL

**IKEV2**: basado en IPsec, fue desarrollado por Cisco y Microsoft. Es bueno para reestablecer conexiones VPN automáticamente cuando se pierde temporalmente


# Proxy

- **Proxy HTTP**: Este tipo de proxy se utiliza para enrutar las solicitudes HTTP entre el cliente y el servidor final. Puede realizar tareas como filtrado de contenido, registro de solicitudes, autorizaciones, entre otros.  Su objetivo es controlar y gestionar el tráfico HTTP. Por ej: Squid, Nginx, Apache HTTP Server (con módulo mod_proxy)

- **Proxy HTTPS**: Similar al proxy HTTP, pero está diseñado específicamente para manejar el tráfico cifrado HTTPS. Permite la inspección y el enrutamiento de las solicitudes y respuestas HTTPS. Por ej: Burp Suite, Fiddler, mitmproxy.

- **Proxy SOCKS**: Es un protocolo de proxy genérico que puede manejar diferentes tipos de tráfico, incluidos HTTP, HTTPS y aplicaciones de red más complejas. Proporciona una capa adicional de seguridad y puede ser útil en entornos que requieren acceso remoto. Por ej: OpenSSH (con opción de tuneling), Proxifier, Shadowsocks.

- **Proxy inverso**: Se coloca en el lado del servidor y actúa como un intermediario entre los clientes y los servidores finales. Ayuda a equilibrar la carga de tráfico, mejorar el rendimiento y proporcionar funciones de seguridad, como la protección contra ataques DDoS. Por ej: CaddyServer, Traefik, Nginx, HAProxy, Apache HTTP Server (con módulo mod_proxy).

- **Proxy transparente**: Este tipo de proxy no requiere configuración en el cliente. Captura todas las solicitudes de forma transparente y las envía al servidor final. Los clientes no son conscientes de la existencia del proxy. Por ej: Squid, Nginx.

- **Proxy de filtrado de contenido**: Se utiliza para filtrar y controlar el contenido que se muestra a los clientes. Puede bloquear sitios web o aplicar políticas de acceso basadas en categorías de contenido. Por ej: DansGuardian, Privoxy, OpenDNS.

- **Proxy de caché**: Actúa como un intermediario entre los clientes y los servidores finales. Almacena en caché las respuestas de los servidores y las entrega directamente a los clientes si la misma solicitud se realiza nuevamente. Mejora la eficiencia y reduce la carga Por ej: Squid, Varnish, Caddy Server (con configuración de caché).

- **Proxy de carga**: Se utiliza para distribuir la carga de trabajo entre múltiples servidores de destino. Actúa como punto de entrada para las solicitudes y las redirige siguiendo alguna regla, como round-robin, ponderación, etc. Por ej: HAProxy, Nginx, Traefik.

- **Proxy de API**: Actúa como intermediario entre los clientes y los servicios de la API, proporcionando características como autenticación, autorización, enrutamiento, registro y seguimiento de solicitudes, límites de velocidad, transformación de datos, entre otros. Por ej: Kong, Tyk, Traefik.

## Funciones Principales
- **Cacheo**: Su objetivo es acelerar el servicio de request a través de guardar el contenido solicitado de un request previo, evitando tener que hacer el mismo procesamiento varias veces.

- **WEB**: Su objetivo es cachear todo el tráfico de INTERNET. Es el uso más común de los web proxy.

- **Filtrado de contenido**: Provee el control administrativo del contenido que puede ser solicitado o accedido. Es usado generalmente en instituciones como escuelas, para asegurar que el uso de internet se encuentra dentro de las políticas de la institución.

# Web Caches

La web cache puede estar implementada en diferentes niveles, como a nivel de cliente, a nivel de red o a nivel de servidor. 

Un **CDN** (Content Delivery Network / Red de Entrega de Contenido), es una red de servidores distribuidos geográficamente que se utiliza para entregar contenido web de manera eficiente a los usuarios finales.