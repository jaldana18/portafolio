# Portafolio — Juan Danilo Aldana

**Desarrollador Full Stack | Backend · CI/CD · Azure · IA**  
Bogotá, Colombia · [LinkedIn](https://www.linkedin.com/in/juan-danilo-aldana-tibabisco-a6745718a/) · juandaniloaldanat@gmail.com

---

## Proyectos

### 1. Services-Plans — Plataforma SaaS *(comercial, código privado)*

Plataforma para centralizar múltiples microservicios en un único portal con gestión de suscripciones y planes integrada.

**El problema que resuelve:**  
Cuando una organización tiene múltiples aplicaciones, termina con N portales independientes — uno por app, con su propio login y su propia gestión. Services-Plans elimina ese problema: los microservicios se embeben en un único portal y se accede con una sola cuenta. Un nuevo servicio no requiere construir un frontend propio.

**Arquitectura:**

```
┌─────────────────────────────────────────┐
│           Services-Plans Platform        │
│                                         │
│  ┌─────────────┐    ┌────────────────┐  │
│  │  Panel Admin │    │ Portal Cliente │  │
│  │  (React)     │    │ (React)        │  │
│  └──────┬──────┘    └───────┬────────┘  │
│         │                   │           │
│  ┌──────▼──────┐    ┌───────▼────────┐  │
│  │  back-admin │    │  back-portal   │  │
│  │  (Node.js)  │    │  (Node.js)     │  │
│  └──────┬──────┘    └───────┬────────┘  │
│         └─────────┬─────────┘           │
│               PostgreSQL                │
└─────────────────────────────────────────┘
         ↕                ↕
   Microservicio A   Microservicio B
   (embebido)        (embebido)
```

**Stack:**
- Backend: Node.js v22, Express v4, Prisma ORM, PostgreSQL
- Frontend: React, Vite, JavaScript
- Auth: JWT multi-tenant con `company_id` y `plan_id`
- Infra: Docker, Docker Compose

**Características técnicas:**
- Autenticación multi-empresa: un usuario puede pertenecer a N empresas
- Control de acceso por plan y features — cada empresa ve solo lo que contrató
- Microservicios embebidos sin necesidad de portal propio por aplicación
- API REST separada para admin y portal cliente
- Docker-ready para desarrollo y producción

---

### 2. Agente de QA con IA *(en desarrollo)*

Sistema de automatización de pruebas que combina Playwright con Claude (IA) para generar y ejecutar pruebas de UX, seguridad y edge cases sobre los desarrollos de la compañía — sin escribir cada test manualmente.

**El problema que resuelve:**  
Los equipos dedican tiempo significativo a escribir suites de prueba. Muchos edge cases y vulnerabilidades se detectan tarde. Este agente usa IA para analizar flujos de usuario y generar automáticamente escenarios de prueba que un humano podría pasar por alto.

**Cómo funciona:**

```
Aplicación objetivo
       │
       ▼
  Agente Claude (analiza interfaz y flujos)
       │
  Genera casos de prueba:
  · UX — flujos críticos del usuario
  · Seguridad — inputs maliciosos, validación de auth
  · Edge cases — límites, vacíos, concurrencia
       │
       ▼
  Playwright ejecuta los tests
       │
       ▼
  Reporte con capturas y logs por escenario
```

**Stack:** Node.js · React · Playwright · Claude CLI (Anthropic) · TypeScript

**Estado:** Fase piloto con un equipo — proyectado para adopción en toda la organización incluyendo automatización en operación.

---

### 3. Backend Módulo Facturador *(código privado)*

API REST multi-tenant para gestión de usuarios, facturas e inventario multi-bodega.

**Stack:** Node.js · TypeScript · TypeORM · SQL Server · Express · Jest

**Características:**
- Arquitectura multi-tenant con Row-Level Security
- Autenticación JWT con refresh tokens
- Control de acceso basado en roles (RBAC)
- Cifrado AES-256-GCM para datos sensibles
- Auditoría completa de operaciones
- Rate limiting y headers de seguridad (Helmet.js)
- Suite de tests con Jest

---

### 4. Sistema de Búsqueda de Empleo Automatizado

[github.com/jaldana18/sistema-busqueda-empleos](https://github.com/jaldana18/sistema-busqueda-empleos)

Herramienta full stack que automatiza la búsqueda de empleo: scraping de ofertas, análisis de compatibilidad con IA y generación de cartas de presentación personalizadas.

**Stack:** Node.js · React · TypeScript · Playwright · Claude API · SQLite

**Pipeline completo:**
```
Scraping (LinkedIn, Computrabajo, Indeed, Elempleo)
       │
       ▼
Filtro por keywords y criterios
       │
       ▼
Análisis de viabilidad con Claude AI
       │
       ▼
Generación de carta de presentación personalizada
       │
       ▼
Dashboard de gestión de postulaciones
```

---

## Logros cuantificables

| Optimización | Antes | Después | Mejora |
|---|---|---|---|
| Tiempos de build CI/CD (Azure DevOps) | 15-25 min | 3-4 min | −83% |
| Datos procesados en BigQuery | 1.5 GB/consulta | 450 MB/consulta | −70% |
| Asignación automática de tareas | 15+ min (manual) | 1-2 seg | −99% |

---

## Stack completo

| Área | Tecnologías |
|---|---|
| Backend | Node.js, Python, Django, .NET, Express, Prisma, REST APIs |
| Frontend | React.js, TypeScript, JavaScript, Vite |
| Bases de datos | SQL Server, MongoDB, PostgreSQL, BigQuery |
| Mensajería y caché | RabbitMQ, Redis, WebSockets |
| CI/CD y nube | Azure DevOps, Azure Cloud, Docker, Linux, Git |
| Automatización e IA | Playwright, Claude, Claude Code CLI, LLM APIs |

---

## Certificaciones

- **Claude Code in Action** — Anthropic (2025)

---

*Abierto a roles Full Stack Semi-Sr / Mid en Bogotá (presencial o híbrido) o remoto LATAM.*
