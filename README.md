# Python Microservice Template (DEV)

**ALARM!!!** This project is under development and nothing is working here 👺

Unified python microservice template

## Project struct

```
python_microservice_template/
├── alembic/                    # Database migrations
├── src/                        # Project sources
|   ├── api/
|   |   ├── middlewares/        # Middlewares
|   |   ├── routes/             # Routes
|   |   |   └── v1/
|   |   ├── schemas/            # Pydantic schemas
|   |   |   └── v1/
|   |   ├── depends.py          # Dependencies
|   |   └── server.py           # Server
|   ├── celery/
|   |   ├── tasks/              # Tasks
|   |   └── app.py              # Celery app initialization
|   ├── core/
|   |   ├── config.py           # Application configuration
|   |   ├── database.py         # Initializing the database
|   |   ├── exceptions.py       # Custom exceptions
|   |   └── logger.py           # Logger Settings
|   ├── entities/               # Entities
|   ├── grpc/
|   |   ├── generated/          # Generated code from .proto
|   |   ├── services/           # gRPC services
|   |   └── server.py           # gRPC server initialization
|   ├── kafka/
|   |   ├── consumers.py        # Kafka consumers
|   |   ├── producers.py        # Kafka producers
|   |   └── schemas.py          # Kafka message schemas
|   ├── repositories/           # Repositories
|   ├── services/
|   |   └── example.py          # Business logic
|   └── cli.py                  # Cli app
├── protobufs/                  # Proto files
|   └── example.proto
├── tests/
|   |   ├── e2e/                # End-to-end tests
|   |   └── unit/               # Unit tests
├── .dockerignore
├── .env.example                # Environment variables (Example)
├── alembic.ini                 # Database migration settings
├── mypy.ini                    # MyPy settings
├── pytest.ini                  # PyTest settings
├── Dockerfile
├── docker-compose.yaml
└── pyproject.toml              # Project dependencies
```

## Tasks

Make sure that the [poe](https://pypi.org/project/poethepoet/) installed.

### Run tests

```shell
poe test -v tests/
```

### Generate proto

```shell
poe gen_proto protobufs/example.proto
```

### Cleanup project from Docker

This command stops and deletes containers and deletes images related to this project.

```shell
poe docker_cleanup
```