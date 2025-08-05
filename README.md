# How to Install Keycloak with Nginx Using Docker Compose

## Prerequisites:

We must've installed and understood:

1. Docker
2. Docker Compose
3. cURL

## Testing Keycloak endpoint

Real Settings -> OpenID Endpoint Configuration -> "token_endpoint":"http://localhost:8040/realms/master/protocol/openid-connect/token"

```
curl -H "Content-Type: application/x-www-form-urlencoded" -d "client_id=admin-cli" -d "username=admin" -d "password=admin" -d "grant_type=password" http://localhost:8040/realms/master/protocol/openid-connect/token
```

# Auth2
- your-client-secret por el secreto real del cliente configurado en Keycloak.
- oauth2-proxy es el nombre del client creado en Keycloak.
- random-32-byte-secret== lo puedes generar con este comando:

bash
````
head -c24 /dev/urandom | base64
```