# Desafio Node.js

## Requisitos:

- Usar status codes REST.
- Validar los datos de entrada.
- Implementar JWT stateless.
- Usar persistencia de datos.
- Usar un linter (Eslint, Jshiint).
- Usar frameworks como Express, Hapi o similares.
- Deployar API en la nuve (heroku, next, aws, google cloud, etc).
- El desafio deve entregarse en Github.

## Deseado
 - Tests unitarios y de API.
 - Criptografia no reversível (hash) para password y token.

## Registro de usuario (Sign up)

Este endpoint deve recibir un objeto siguiendo el siguiente modelo:

```
{
 "name": "string",
 "email": "string",
 "password": "string",
 "telephones": [
   {
     "number": "number",
     "area_code": "number"
   }
 ]
}
```

En caso de exito retorna 200:

```
{
 "id": "string",
 "created_at": "date"
 "modified_at": "date"
 
}
```

En caso de error retornar status code y mensaje de error correspondiente.

# Login de usuarios (Sign in)

Este endpoint deve recibir un objeto con `email` y `password`

En caso que el email exista y el password sea igual al persistido, retorna un token JWT el cual deve incluir en el payload : `email`, `id`.

En caso de login inválido deve retornar 401 y mensaje de error apropiado.

# Buscar usuario

Este endpoint deve recibir un header:

```
Header
Authorization: Bearer <token>
```

Donde  `token` es el retornado en el endpoint de login.

En caso de token invalido deve retornar 401 y mensaje de error apropiado.

En caso de exito retorna `email`, `id`, `telephones`, `created_at`, `modified_at`
