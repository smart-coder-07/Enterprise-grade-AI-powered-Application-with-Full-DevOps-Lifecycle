# System Architecture – PureVeg Mumbai

```
[User Devices]
     |
[Angular Frontend (Web/Mobile-first)]
     |
[API Gateway / Load Balancer]
     |
[Java Spring Boot Backend Microservices (REST API)]
     |
----------------------------
|          |              |
[MySQL] [MongoDB]   [AI/Agentic Microservice (Python)]
                            |
                [GenAI APIs, RAG, Agentic Orchestration]
                            |
[3rd Party APIs: Payments, Maps, Notifications]
```

## Key Components

- **Frontend (Angular):** User & partner portals, admin dashboard; responsive UI.
- **Backend (Java Spring Boot):** 
  - REST APIs for user, order, restaurant, payment, admin modules.
  - Auth (JWT, OAuth2), RBAC.
  - Business logic, data validation.
- **AI/Agentic Microservice (Python):**
  - GenAI-powered chatbot (customer support, dish suggestions)
  - Agentic workflows (auto-ticketing, refunds, notifications)
- **Database (MySQL/MongoDB):** 
  - Users, restaurants, orders, menus, ratings, transactions
- **Cache (Redis):** 
  - Sessions, real-time order status
- **Cloud Storage (S3/MinIO/GCS):** 
  - Restaurant images, documents
- **DevOps/Infra:** 
  - Docker, Kubernetes (Helm), Terraform (AWS/GCP), CI/CD (GitHub Actions, ArgoCD, Jenkins)
- **Monitoring & Security:** 
  - Prometheus, Grafana, ELK Stack, secrets mgmt (Vault), SAST/DAST

## Data Flow Example

1. User logs in, searches veg restaurants (frontend → backend)
2. Backend queries DB, returns only verified veg restaurants
3. User places order, payment processed via payment gateway
4. Backend triggers restaurant + agent notification
5. Real-time order status via Redis pub/sub
6. Support queries handled by GenAI chatbot (AI microservice)
7. Agentic workflow auto-assigns support tickets, triggers refunds

## Scalability & Best Practices

- Microservices ready (split backend, AI, frontend)
- K8s for scaling, blue-green/canary deploys
- Secure API gateway, JWT/OAuth2
- Observability, alerting, logs centralization

---

_Diagrams will be refined as codebase grows._