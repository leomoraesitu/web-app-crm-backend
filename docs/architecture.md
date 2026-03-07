
# Architecture — Web App CRM

Arquitetura SaaS multi‑tenant baseada em Firebase.

Componentes:

- FlutterFlow (Frontend)
- Firebase Authentication
- Cloud Firestore
- Firebase Storage

```mermaid
flowchart TD
User --> WebApp
WebApp --> Auth
WebApp --> Firestore
WebApp --> Storage
Auth --> Identity
Identity --> TenantContext
TenantContext --> Companies
TenantContext --> Users
TenantContext --> Leads
```
