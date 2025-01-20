# Authentication Mechanisms

## Stateful Authentication (Cookie/Session)
This is the default and traditional method for handling user authentication. In this approach, the backend is responsible for creating, storing the session ID, and verifying the user’s identity.

### How it Works?
The server creates a **session ID** upon a user’s login request, storing it in either a database or an in-memory cache on the server. This session ID is then stored on a cookie in the user’s browser. With each subsequent request, the server receives the cookie containing the session ID and validates the user’s identity by comparing it with the corresponding session information stored on the server.

![[statefulAuth.webp]]

### Disadvantages
- **Scalability**: This approach might have challenges in highly scalable systems, as it requires server-side storage for session data.
- **Complexity**: Implementing and managing session data, can add complexity to the system.

## Stateless Authentication (Token)
Issuing a token upon successful authentication.
The token is sent to the server with each request for authorization.  
It is Stateless and scalable.
  
![[statelessAuth.webp]]
**[[JWT (JSON Web Token)]]**