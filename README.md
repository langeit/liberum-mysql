# HelpDesk (Port a Python/Flask en MVC)

HelpDesk es un *port/fork* de **Liberum Help Desk**, reescrito desde ASP clásico y bases de datos MSSQL/Access a una arquitectura moderna basada en **Python/Flask** y **MySQL**, con un esquema de datos optimizado y nombres de tablas/campos en español.

El objetivo es mantener la **idea funcional** del software original (gestión de tickets de soporte/helpdesk), pero con:

- Código limpio y modular (patrón **MVC**).
- Base de datos modernizada y coherente.
- Interfaz web actualizable y más fácil de mantener.

> ⚖️ Este proyecto se distribuye bajo la **GNU General Public License versión 2 (GPLv2)**.  
> Véase el archivo `LICENSE` para más detalles.

---

## Índice

- [Origen del proyecto](#origen-del-proyecto)
- [Características principales](#características-principales)
- [Arquitectura](#arquitectura)
- [Requisitos](#requisitos)
- [Instalación](#instalación)
  - [1. Clonar el repositorio](#1-clonar-el-repositorio)
  - [2. Crear y configurar entorno virtual](#2-crear-y-configurar-entorno-virtual)
  - [3. Instalar dependencias](#3-instalar-dependencias)
  - [4. Crear base de datos MySQL](#4-crear-base-de-datos-mysql)
  - [5. Configurar variables de entorno](#5-configurar-variables-de-entorno)
  - [6. Inicializar la base de datos](#6-inicializar-la-base-de-datos)
  - [7. Ejecutar la aplicación](#7-ejecutar-la-aplicación)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Modelo de datos](#modelo-de-datos)
- [Estado del proyecto](#estado-del-proyecto)
- [Licencia](#licencia)
- [Créditos y agradecimientos](#créditos-y-agradecimientos)
- [Contribuir](#contribuir)

---

## Origen del proyecto

Este proyecto es un **port y fork** de:

- **Nombre original:** Liberum Help Desk  
- **Tecnología original:** ASP clásico + base de datos MSSQL/Access  
- **Licencia original:** GNU General Public License versión 2 (GPLv2)  

El código original se encontraba organizado como “código spaghetti”, con lógica de presentación, negocio y acceso a datos mezcladas.  
HelpDesk UTA toma esas ideas funcionales y las reimplementa en una arquitectura moderna, modular y mantenible.

---

## Características principales

- ✅ **Port completo a Python/Flask**:
  - Backend reescrito desde ASP a **Python 3 + Flask**.
  - Uso de patrón **MVC** (Model–View–Controller).

- ✅ **Base de datos MySQL optimizada**:
  - Esquema en **español** (`usuarios`, `problemas`, `notas`, `categorias`, `departamentos`, etc.).
  - Claves foráneas, índices y tipos de datos revisados.
  - Pensado para integrarse fácilmente con herramientas modernas.

- ✅ **Frontend actualizado**:
  - Plantillas HTML basadas en Jinja2.
  - Estructura preparada para integrar cualquier framework CSS (Bootstrap, W3.CSS, etc.).
  - Interfaz web para:
    - Crear y gestionar tickets de soporte.
    - Asignar tickets a representantes.
    - Registrar notas internas/privadas.
    - Cambiar estados y prioridades.

- ✅ **Internacionalización orientada a español**:
  - Nombres de tablas y campos en español.
  - Mensajes de la aplicación adaptables.

- ✅ **Respeto a la licencia GPLv2**:
  - El proyecto mantiene la misma licencia (GPLv2).
  - Se reconocen el origen y autores del proyecto original.

---

## Arquitectura

La aplicación está organizada siguiendo un estilo **MVC en Flask**:

- **Modelos (Models)**  
  Definen las tablas y relaciones de la base de datos (usando SQLAlchemy u otro ORM/driver que se configure).

- **Controladores / Rutas (Controllers)**  
  Blueprints de Flask que gestionan:
  - Autenticación de usuarios.
  - Alta/baja/modificación de tickets.
  - Listados, filtros y búsquedas.
  - Operaciones administrativas.

- **Vistas (Views)**  
  Plantillas Jinja2 que generan las páginas HTML para:
  - Login.
  - Dashboard.
  - Listados de problemas.
  - Detalle de un problema.
  - Formularios de creación/edición.

---

## Requisitos

- **Python** 3.10 o superior (recomendado).
- **MySQL / MariaDB** (5.7+ / 10.3+).
- Librerías Python (ejemplo típico):
  - `flask`
  - `flask_sqlalchemy` o el ORM elegido
  - `flask_migrate` (opcional, para migraciones)
  - `python-dotenv` (opcional, para configuración por `.env`)

*(El listado exacto de dependencias se define en `requirements.txt`.)*

---

## Instalación

### 1. Clonar el repositorio

```bash
git clone https://tu-servidor-o-github/usuario/helpdesk-uta.git
cd helpdesk

