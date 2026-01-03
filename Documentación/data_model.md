# Modelo de Datos — Task Service

Este documento describe el modelo de datos del **Task Service**, responsable de exponer una API REST para gestionar tareas.

El modelo está alineado con el proyecto **Automated Task Monitoring System** para facilitar integración futura.

---

## 🧩 Entidad: Task

### Campos
- id (int, PK)
- title (string, requerido)
- description (string, opcional)
- status (enum): PENDING | DONE | OVERDUE
- priority (enum): LOW | MEDIUM | HIGH
- due_at (datetime ISO, opcional): fecha límite
- overdue_at (datetime ISO, opcional): se establece cuando la tarea pasa a OVERDUE
- source (string): manual | simulator | runner | ...
- external_id (string, opcional): ID proveniente de un sistema externo
- created_at (datetime ISO)
- updated_at (datetime ISO)

---

## 🔐 Consideración de integración (Auth)
Este servicio será protegido por:
- JWT (usuarios humanos) → `Authorization: Bearer <token>`
- API Key (clientes máquina) → `X-API-Key: <key>`

La validación de JWT/API Keys se implementa en capa de dependencias para mantener el código desacoplado.
