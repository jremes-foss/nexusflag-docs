# Installation Guide

NexusFlag supports two primary installation methods: a rapid **Docker** setup or a **native manual installation**. Choose the method that best fits your environment.

### Prerequisites

* **OS:** Linux, macOS, or WSL (Windows Subsystem for Linux)
* **Python:** 3.9+ (Tested up to 3.14-alpha) for manual installation
* **Tools:** `pip3`, `python3-venv`
* **Docker Compose:** Required if you choose the Docker installation method ([Install Docker Compose](https://docs.docker.com/compose/))

## Method 1: Quick Start with Docker (Recommended)

The fastest way to get NexusFlag up and running is using Docker. This automatically pulls the environment, installs dependencies, and seeds your initial database.

### 1. Clone the Repository

```bash
git clone https://github.com/jremes-foss/NexusFlag.git
cd NexusFlag
```

### Launch with Docker Compose

```bash
docker-compose up --build
```

Once running, the API will be available with the following specifications:

- API Base: `http://localhost:8000`
- Interactive Documentation (Swagger): `http://localhost:8000/docs`
- Default Admin Credentials: admin / admin123

### Useful Docker Commands

View logs for debugging

```bash
docker-compose logs -f
```

Stop the services

```bash
docker-compose down
```

## Method 2: Manual Installation

If you prefer to run NexusFlag in a native environment, follow these steps.

### Clone the Repository

```bash
git clone https://github.com/jremes-foss/NexusFlag.git
cd NexusFlag
```

### Set Up Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Initialise and Seed the Database

```bash
export PYTHONPATH=$PYTHONPATH:.
python3 seed.py
```

### Running API Manually

Once installed and seeded, run the API using Uvicorn with auto-reload enabled:

```bash
uvicorn app.main:app --reload
```

### Troubleshooting

Database schema changes: If you modify the database models, delete the `nexus_flag.db` file and re-run `python3 seed.py` to apply your changes cleanly.
