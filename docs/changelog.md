# Revision History

All notable changes, updates, and bug fixes for **NexusFlag** are tracked in this document.

---

## v1.1.5

### Maintenance Release
* Update uvicorn dependency from `0.22.0` to `0.54.0`.

---

## v1.1.4

### Maintenance Release
* Update fastapi from `0.100.0` to `0.141.1`.

---

## v1.1.3

### Maintenance Release
* Update python-multipart dependency from version `0.0.6` to version `0.0.32`.

---

## v1.1.2

### Maintenance Release
* Update pytest-asyncio dependency from version `1.3.0` to `1.4.0`.

---

## v1.1.1

### Maintenance Release
* Update pydantic from `2.0.0` to `2.13.4`.

---

## v1.1.0

### Feature Release
* Add Global Notification system to NexusFlag.

---

## v1.0.6

### Maintenance Release
* Update python-jose from `3.3.0` to `3.5.0`.

---

## v1.0.5

### Maintenance Release
* Bump bcrypt from `4.0.1` to `5.0.0`.

---

## v1.0.4

### Maintenance Release
* Bump factory-boy from `3.3.0` to `3.3.3`.

---

## v1.0.3

### Maintenance Release
* Bump pytest-asyncio from `0.23.5` to `1.3.0`.

---

## v1.0.2

### Maintenance Release
* Update Docker base image from `python:3.12-slim` to `python:3.14-slim`.

---

## v1.0.1

### Maintenance Release
* Update httpx dependency from `0.27.0` to `0.28.1`.

---

## v1.0.0

I am excited to announce the first stable release of NexusFlag, a lightweight, high-performance CTF (Capture The Flag) platform built with FastAPI and SQLAlchemy. This version establishes the core engine for challenge management, real-time scoring, and secure asset distribution.

### Key Features
* **Dynamic Challenge Engine:** Support for multiple categories (Web, Pwn, Forensics, etc.) with configurable point values and difficulty levels.
* **Secure File Distribution:** Integrated admin upload system with a secure, authenticated download route for players, preventing unauthorized asset access.
* **Advanced Scoring Logic:** First Blood Bonus (automatic 10% point boost for the first player to solve a challenge) and Anti-Replay Guards (built-in logic to prevent double-scoring on solved challenges).
* **Admin Management API:** Dedicated endpoints for challenge creation and file management with role-based access control (RBAC).

### Technical Stack
* **Framework:** FastAPI (Python 3.12+)
* **Database:** SQLAlchemy 2.0 (Modern Declarative Mapping)
* **Testing:** Full test suite powered by pytest and factory-boy.
* **Security:** JWT-based authentication and secure path-traversal protection for file handling.