# Arquitectura — Task Service

Task Service es un backend **FastAPI + SQLite** orientado a exponer una API REST para gestión de tareas.

---

## 🧠 Visión general
Componentes:
- API REST (FastAPI)
- Persistencia (SQLite + SQLAlchemy)
- Capa de seguridad (dependencias) para JWT y API Key

---

## 🧩 Capas
1) API (routers)
- /tasks (CRUD)
- /reports (reportes: overdue, etc.)

2) Core
- Configuración (.env)
- Reglas de negocio (validaciones simples)

3) DB
- sesión, modelos, CRUD

4) Security (Auth integration)
- Dependencia `require_jwt_user()` para endpoints humanos
- Dependencia `require_api_key_client()` para integraciones
- En el futuro, puede validar consultando al Auth Service o con secreto compartido

---

## 🔗 Integración objetivo (arquitectura real)
- Auth Service = seguridad centralizada
- Task Service = API de tareas
- Automated Task Monitoring System = runner + simulador (consumidor)

Flujo:
- Usuario humano: Swagger → JWT → Task Service
- Runner/Simulador: X-API-Key → Task Service
