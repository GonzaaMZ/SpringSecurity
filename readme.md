

# GUIA SPRING SECURITY 2

## TEMAS:

- JWT
- ROLES
- Encriptacion Password

## Breve explicacion de cada archivo o clase referida a la seguridad

Security:

	SecurityConfig: 	Clase de configuracion de Spring Security

jwt:

    JwtUtils: Clase de utilidad con metodos para el manejo de JWT (Creacion, Validacion del token, obtener payload)

filter:

__JwtAuthenticationFilter:__

- Responsabilidad: La principal responsabilidad de JwtAuthenticationFilter es manejar el proceso de autenticación basada en JWT.

__Función:__
- Filtrado de Peticiones: Intercepta las peticiones entrantes antes de que lleguen a los controladores de Spring.

 - Extracción del Token: Extrae el token JWT del encabezado de autorización de la solicitud.

- Validación del Token: Valida la firma y la integridad del token utilizando la clave pública o secreta compartida.

 - Autenticación: Autentica al usuario utilizando la información contenida en el token y establece la autenticación en el contexto de seguridad de Spring.


__JwtAuthorizationFilter:__

- Responsabilidad: La principal responsabilidad de JwtAuthorizationFilter es manejar el proceso de autorización basada en JWT.

__Función:__ 

- Filtrado de Peticiones: Intercepta las peticiones entrantes antes de que lleguen a los controladores de Spring (al igual que JwtAuthenticationFilter).

- Obtención de Roles/Permisos: Extrae la información de roles o permisos del token JWT previamente autenticado.

- Configuración de Autorizaciones: Configura las autorizaciones en el contexto de seguridad de Spring basándose en la información de roles/permisos extraída del token.

- Permite o Niega Acceso: Decide si permitir o denegar el acceso a la solicitud en función de las autorizaciones configuradas.

service:

    UserDetailsServiceImpl: implementacion de metodo de consulta del usuario que requiere autenticacion
***