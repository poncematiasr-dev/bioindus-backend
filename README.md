# Bioindus Backend

Backend del proyecto Bioindus. Organiza el código en capas separadas (routers, servicios, repositorios y schemas) para mantener la lógica de negocio independiente del acceso a datos.

## Estructura del proyecto

```
bioindus-backend/
├── app/
│   ├── main.py
│   ├── api/               # Routers (endpoints)
│   ├── core/              # Config, seguridad, dependencias
│   ├── models/            # Modelos SQLAlchemy / Pydantic
│   ├── repositories/      # Capa Repository (acceso a datos)
│   ├── services/          # Lógica de negocio
│   └── schemas/           # Schemas de entrada/salida
├── alembic/               # Migraciones de PostgreSQL
├── tests/
├── .github/
│   └── workflows/         # CI/CD (GitHub Actions)
├── Dockerfile             # (opcional pero recomendado)
├── requirements.txt / pyproject.toml
├── .env.example
└── README.md
```

## Capas de la aplicación

- **api/:** define los endpoints y recibe las solicitudes HTTP.
- **services/:** contiene la lógica de negocio.
- **repositories/:** es el único lugar que accede a la base de datos.
- **schemas/:** define los datos de entrada y salida de la API.
- **models/:** define los modelos de datos (SQLAlchemy y Pydantic).
- **core/:** concentra la configuración, la seguridad y las dependencias compartidas.

## Requisitos

- Python 3.10 o superior
- PostgreSQL
- Docker (opcional)

## Instalación

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/<usuario>/bioindus-backend.git
   cd bioindus-backend
   ```

2. Crear y activar un entorno virtual:

   ```bash
   python -m venv .venv
   source .venv/bin/activate   # En Windows: .venv\Scripts\activate
   ```

3. Instalar las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

4. Copiar el archivo de variables de entorno y completarlo:

   ```bash
   cp .env.example .env
   ```

## Migraciones

Las migraciones de base de datos se gestionan con Alembic en la carpeta `alembic/`.

## Tests

```bash
pytest
```

## Configuración

Las variables de entorno se definen en el archivo `.env`, que no se sube al repositorio. El archivo `.env.example` sirve como referencia de las variables necesarias.

## Licencia

Uso interno del proyecto Bioindus.