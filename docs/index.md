# NexusFlag CTF API

**A Python-based, easily-deployable, no-fuss Open Source API for small community CTF (Capture the Flag) cybersecurity events.**

[![NexusFlag CI](https://github.com/jremes-foss/NexusFlag/actions/workflows/tests.yml/badge.svg)](https://github.com/jremes-foss/NexusFlag/actions/workflows/tests.yml)
[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-blue.svg)](https://github.com/jremes-foss/NexusFlag/blob/main/LICENSE)
[![Python Version](https://img.shields.io/badge/python-3.9%2B-blue?style=flat-square)](https://www.python.org/)

---

## Introduction

Hosting a local Capture the Flag event shouldn't require massive, heavy commercial platforms. **NexusFlag** is a modern, lightweight API built using **FastAPI, SQLAlchemy, and SQLite**. 

Serving as a spiritual successor to **BeeCTF**, NexusFlag updates the vision of community-driven CTF software for the modern era, emphasizing accessibility, easy deployment, and zero bloatware.

---

## Why Choose NexusFlag?

* **⚡ Modern Tech Stack:** Powered by FastAPI for incredible speed and automatic interactive documentation.
* **🐳 Flexible Deployment:** Choose between a rapid **Docker Compose** setup or a **native manual installation**.
* **🎯 Focused Architecture:** Keeps maintenance simple by acting purely as a robust backend API—bring your own front-end or use the built-in Swagger UI.
* **🔓 Open Source:** Licensed under the **GNU AGPL v3.0**, ensuring it remains free and open for community-driven events.

---

## Quick At-a-Glance

| Feature | Specification |
| :--- | :--- |
| **Framework** | FastAPI (Python 3.9+) |
| **Database** | SQLite + SQLAlchemy |
| **Default Admin** | `admin / admin123` |
| **Interactive Docs** | `/docs` (Swagger UI) |
| **Front-End** | API-only (Bring your own front-end) |

---

## Get Started

Ready to spin up your environment? 
* Head to the [Installation Guide](installation.md) for step-by-step instructions on Docker and manual deployment.
* Check out the [API Reference](api.md) to explore endpoints, request shapes, and authentication details.