JWT represents claims between two parties. JWT has a compact format, making them easy to transport over the network. 
![[jwt.webp]]

It consists of three parts:
- **Header**: Specifies the JWT encoding and signing algorithm, with properties { “alg”: “HS256”, “typ”: “JWT” } where alg is the algorithm that is used to encrypt the JWT.
- **Payload**: Contains the data(Claims) to be sent as JSON property–value pairs within the claims.
- **Signature**: This is created by encrypting, with the algorithm specified in the header: (i) the base64Url-encoded header, (ii) base64Url-encoded payload, and (iii) a secret (or a private key).

## Why and Where should I use JWT?
JWT can be used in both, **authentication** and **authorization**.
- **Authentication**: JWTs can be used for user authentication. Once a user logs in, a JWT is generated on the server and sent to the client. The client includes this token in the header of subsequent requests to authenticate the user.
- **Authorization**: JWTs can also be used to convey information about the user’s permissions and roles. The server can include this information in the payload of the JWT, and the client can use it for authorization purposes.
- **Stateless**: JWTs are often used in **stateless authentication mechanisms**. The server does not need to store the user’s session data, making it scalable, efficient and less complex.
- **Expiration**: JWTs can have an expiration time, after which they are no longer considered valid. This helps enhance security by limiting the window of opportunity for an attacker to use a stolen token.