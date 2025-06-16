# Requirements – PureVeg Mumbai

## Functional Requirements

### User App
- Only allow registration/login for users with verified contact (email/phone)
- Users can view/search only verified pure veg restaurants
- Display filters: cuisine, location, Jain/Satvik/no onion-garlic
- Show menu, dish details (ingredients, tags)
- Cart, place order, order tracking (real-time updates)
- Secure online payment (UPI, card, wallet)
- View order history, repeat orders
- Leave ratings/reviews
- Chatbot support (24x7, GenAI-powered)

### Restaurant Partner Portal
- Partner registration (with pure veg proof/KYC upload)
- Menu CRUD (add/edit/remove dishes)
- Order dashboard (manage, fulfill orders)
- View earnings, payout requests

### Admin Panel
- Onboard/verify restaurants (KYC + manual check)
- Manage all users/restaurants/orders
- Analytics dashboard (orders, users, revenue, complaints)
- Approve/resolve complaints, process refunds

### Platform/Backend
- Secure APIs (JWT auth, rate limiting)
- Store only pure veg restaurant data (no non-veg, strict validation)
- Real-time order status (websocket/push, Redis-backed)
- Payment gateway integration (PCI DSS compliance)
- Notification system (email/SMS/push)

### AI/Agentic
- GenAI chatbot for support, dish suggestions, menu help
- Agentic workflow for auto-ticketing, refunds, reminders

---

## Non-Functional Requirements

- **Security:** OWASP best practices, secure API, encrypted data, secrets management (Vault)
- **Performance:** Search <1s, order flow <2s, scalable to 10k+ concurrent users
- **Availability:** 99.9% uptime, blue-green deploys, auto-recovery
- **Scalability:** Multi-instance, stateless services, K8s ready, CDN for static assets
- **Compliance:** PCI DSS (payments), GDPR (user data), audit logs
- **Monitoring:** Centralized logging (ELK), metrics (Prometheus/Grafana), alerts
- **Documentation:** API docs (Swagger/OpenAPI), onboarding, runbooks

---

## User Stories (Sample)

- As a user, I want to search and order from only 100% veg restaurants so that I can trust what I eat.
- As a restaurant partner, I want to upload my menu and receive/manage orders.
- As an admin, I need to verify that restaurants are pure veg before making them live.
- As a user, I want to get instant help via chatbot if there is a problem with my order.
- As a system, I want all payments to be secure and compliant.

---

_This file will grow with more detailed stories and edge cases._