# task-service

API backend en Python para gestión de tareas, desarrollada con **FastAPI + SQLite**.
Este servicio está diseñado para integrarse con:

- **Task Monitoring Auth Service** (JWT + API Keys)
- **Automated Task Monitoring System** (runner/simulador como consumidor)

## 📌 Estado del proyecto
🟡 En implementación (API + DB local)

## 🧠 Descripción general
Task Service permite:
- CRUD completo de tareas (PENDING/DONE/OVERDUE)
- Reportes básicos (por ejemplo, tareas vencidas)
- Preparación para protección de endpoints vía JWT y API Key

## 📚 Documentación
Ver carpeta `Documentación/`:
- `ARCHITECTURE.md`
- `DATA_MODEL.md`
- `USER_GUIDE.md`

## ⚙️ Requisitos
- Python 3.10+
- Git
