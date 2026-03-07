
# Security Model

## Estratégia

1. Autenticação via Firebase Auth
2. Autorização via RBAC
3. Isolamento multi‑tenant

Exemplo conceitual:

```javascript
match /leads/{leadId} {
allow read, write: if request.auth != null
&& request.auth.token.companyId == resource.data.companyId;
}
```
