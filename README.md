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

```bash
openssl rand -base64 24
```

# Crea un Realm llamado: <REALM-NAME>

- Dentro del Realm <REALM-NAME>, crea un Client:
- Client ID: oauth2-proxy
- Client Protocol: openid-connect
- Access Type: confidential
- Root URL: http://localhost:8040
- Valid Redirect URIs:
```bash
http://localhost:8040/oauth2/callback
```