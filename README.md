
# 🚀 Web App CRM — Backend

![SaaS](https://img.shields.io/badge/Architecture-SaaS%20Multi--Tenant-purple)
![Firebase](https://img.shields.io/badge/Backend-Firebase-orange)
![Firestore](https://img.shields.io/badge/Database-Firestore-darkorange)
![FlutterFlow](https://img.shields.io/badge/Frontend-FlutterFlow-blue)
![Security](https://img.shields.io/badge/Security-RBAC%20%2B%20Tenant%20Isolation-green)
![Status](https://img.shields.io/badge/Status-In%20Development-yellow)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

Backend do **Web App CRM**, um sistema **SaaS multiempresa** para gestão de leads, clientes e equipes comerciais.

---

# 📌 Visão Geral

CRM SaaS multiempresa com isolamento lógico de dados por empresa.

Funcionalidades:
- Gestão de empresas (tenants)
- Gestão de usuários e permissões
- Pipeline de vendas em Kanban
- Dashboard comercial
- Gestão de equipes

---

# 🧠 Arquitetura SaaS

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

➡️ [Architecture Documentation](docs/architecture.md)

---

# 🗂 Modelagem de Dados

```mermaid
erDiagram
COMPANIES ||--o{ USERS : possui
COMPANIES ||--o{ LEADS : possui
USERS ||--o{ LEADS : responsavel

COMPANIES {
 string companyId
 string name
}

USERS {
 string userId
 string companyId
 string role
}

LEADS {
 string leadId
 string companyId
 string stage
}
```

➡️ [Data Model Documentation](docs/data-model.md)

---

# 🔐 Segurança

- Firebase Authentication
- Firestore Security Rules
- RBAC
- Isolamento multi-tenant

➡️ [Security Documentation](docs/security.md)

---

# 🚀 Deploy

Pré‑requisitos:

- Node.js
- Firebase CLI

Instalação:

```bash
npm install -g firebase-tools
```

Login:

```bash
firebase login
```

Deploy:

```bash
firebase deploy
```

Deploy específico:

```bash
firebase deploy --only firestore
firebase deploy --only storage
```

---

# 📁 Estrutura

```
web-app-crm-backend
│
├─ docs
│  ├─ architecture.md
│  ├─ data-model.md
│  └─ security.md│
├─ environments
│  ├─ dev
│  └─ prod
├─ firebase
│  ├─ cors
│  ├─ firestore
│  └─ storage
├─ firebase.json
├─ README.md
└─ CHANGELOG.md
```

---

# 👨‍💻 Autor

Léo Moraes
