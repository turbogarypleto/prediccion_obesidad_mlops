# ðŸ§  API de PredicciÃ³n del Nivel de Obesidad

## ðŸš€ Proyecto MLOps utilizando FastAPI, Docker y GitHub Actions

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-0.141-009688?logo=fastapi)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Random%20Forest-F7931E?logo=scikitlearn)
![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker)
![Pytest](https://img.shields.io/badge/Pytest-9%20Tests-success?logo=pytest)
![Ruff](https://img.shields.io/badge/Ruff-Code%20Quality-purple)
![GitHub Actions](https://github.com/turbogarypleto/prediccion_obesidad_mlops/actions/workflows/ci.yml/badge.svg)

---

# ðŸ“– DescripciÃ³n

Este proyecto implementa una soluciÃ³n completa de **Machine Learning** siguiendo los principios de **MLOps (Machine Learning Operations)** para predecir el **nivel de obesidad** de una persona utilizando variables antropomÃ©tricas y hÃ¡bitos de vida.

La soluciÃ³n fue desarrollada con un enfoque orientado a producciÃ³n, integrando herramientas ampliamente utilizadas en la industria para el desarrollo, despliegue y mantenimiento de modelos de Machine Learning.

El proyecto contempla todo el ciclo de vida de un modelo:

- ðŸ“Š PreparaciÃ³n de datos
- ðŸ¤– Entrenamiento del modelo
- ðŸ’¾ SerializaciÃ³n del modelo
- ðŸŒ ExposiciÃ³n mediante API REST
- ðŸ“„ DocumentaciÃ³n automÃ¡tica con Swagger
- ðŸ§ª Pruebas automatizadas
- ðŸ³ ContenerizaciÃ³n con Docker
- âš™ï¸ IntegraciÃ³n Continua mediante GitHub Actions

---

# ðŸŽ¯ Objetivos

Este proyecto tiene como objetivos principales:

- Implementar un modelo de clasificaciÃ³n utilizando Machine Learning.
- Exponer el modelo mediante una API REST desarrollada con FastAPI.
- Validar el funcionamiento mediante pruebas unitarias.
- Automatizar la documentaciÃ³n de la API con Swagger.
- Contenerizar la aplicaciÃ³n utilizando Docker.
- Implementar un pipeline de IntegraciÃ³n Continua (CI).
- Aplicar buenas prÃ¡cticas de desarrollo y MLOps.

---

# ðŸ“š Tabla de Contenidos

- ðŸ“– DescripciÃ³n
- ðŸŽ¯ Objetivos
- ðŸ— Arquitectura General
- ðŸ”„ Flujo MLOps
- ðŸ›  TecnologÃ­as Utilizadas
- ðŸ¤– Modelo de Machine Learning
- ðŸ“‚ Estructura del Proyecto
- ðŸ“¦ InstalaciÃ³n
- â–¶ï¸ EjecuciÃ³n Local
- ðŸ³ Docker
- ðŸ³ Docker Compose
- ðŸŒ Endpoints
- ðŸ§ª Testing
- âš™ï¸ GitHub Actions
- ðŸ“Œ Conclusiones

---

# ðŸ“Œ Resumen del Proyecto

| CaracterÃ­stica | Estado |
|----------------|:------:|
| API REST | âœ… |
| Modelo entrenado | âœ… |
| Swagger | âœ… |
| Docker | âœ… |
| Docker Compose | âœ… |
| Pytest | âœ… |
| Ruff | âœ… |
| GitHub Actions | âœ… |

---

# ðŸ— Arquitectura General

```mermaid
flowchart LR
    A[Dataset] --> B[Entrenamiento]
    B --> C[Modelo Random Forest]
    C --> D[FastAPI]
    D --> E[Docker]
    E --> F[GitHub Actions]
    F --> G[Usuario]
```

La arquitectura separa claramente el entrenamiento del modelo y la inferencia, permitiendo reutilizar el modelo entrenado sin necesidad de volver a entrenarlo.

---

# ðŸ”„ Flujo MLOps

```mermaid
flowchart LR
    A[Dataset] --> B[Preprocesamiento]
    B --> C[Entrenamiento]
    C --> D[EvaluaciÃ³n]
    D --> E[Modelo Serializado]
    E --> F[API FastAPI]
    F --> G[Docker]
    G --> H[GitHub Actions]
```

---

# ðŸ›  TecnologÃ­as Utilizadas

| TecnologÃ­a | DescripciÃ³n |
|------------|-------------|
| ðŸ Python 3.10 | Lenguaje de programaciÃ³n |
| âš¡ FastAPI | Framework para la API REST |
| ðŸ“Š Pandas | ManipulaciÃ³n de datos |
| ðŸ¤– Scikit-Learn | Desarrollo del modelo |
| ðŸ§ª Pytest | Pruebas automatizadas |
| ðŸŽ¨ Ruff | Linter y calidad del cÃ³digo |
| ðŸ³ Docker | ContenerizaciÃ³n |
| ðŸ“¦ Docker Compose | OrquestaciÃ³n local |
| âš™ï¸ GitHub Actions | IntegraciÃ³n Continua |
| ðŸš€ Uvicorn | Servidor ASGI |

---

# ðŸ¤– Modelo de Machine Learning

El modelo fue desarrollado utilizando **Scikit-Learn**, implementando un algoritmo de clasificaciÃ³n basado en **Random Forest Classifier**.

## ðŸ“¥ Variables de Entrada

- Gender
- Age
- Height
- Weight
- family_history
- FAVC
- FCVC
- NCP
- CAEC
- SMOKE
- CH2O
- SCC
- FAF
- TUE
- CALC
- MTRANS

## ðŸŽ¯ Variable Objetivo

```
Obesity
```

## ðŸ“ˆ Algoritmo Utilizado

- Random Forest Classifier
- **Accuracy en el set de prueba:** 0.9527 (423 muestras no vistas durante el entrenamiento)

---

# ðŸ“¦ Artefactos Generados

```
models/

â”œâ”€â”€ model.pkl
â”œâ”€â”€ encoders.pkl
â””â”€â”€ metadata.json
```

### model.pkl

Modelo entrenado listo para realizar predicciones.

### encoders.pkl

Codificadores utilizados para transformar las variables categÃ³ricas.

### metadata.json

Contiene informaciÃ³n relevante del modelo:

- Accuracy
- Variables utilizadas
- Variable objetivo
- NÃºmero de muestras
- ParÃ¡metros de entrenamiento

---

# ðŸ“‚ Estructura del Proyecto

```text
obesity-ml-cloud-api/

â”‚
â”œâ”€â”€ app/
â”‚   â”œâ”€â”€ __init__.py
â”‚   â”œâ”€â”€ main.py
â”‚   â””â”€â”€ config.py
â”‚   â”œâ”€â”€ predictor.py
â”‚   â””â”€â”€ schemas.py
â”‚
â”œâ”€â”€ training/
â”‚   â””â”€â”€ train.py
â”‚   â””â”€â”€ evaluate.py
â”‚
â”œâ”€â”€ tests/
â”‚   â””â”€â”€ test_api.py
â”‚
â”œâ”€â”€ models/
â”‚   â”œâ”€â”€ model.pkl
â”‚   â”œâ”€â”€ encoders.pkl
â”‚   â””â”€â”€ metadata.json
â”‚
â”œâ”€â”€ data/
â”‚   â””â”€â”€ Obesity_prediction.csv
â”‚
â”œâ”€â”€ .github/
â”‚   â””â”€â”€ workflows/
â”‚       â””â”€â”€ ci.yml
â”‚
â”œâ”€â”€ Dockerfile
â”œâ”€â”€ docker-compose.yml
â”œâ”€â”€ dockerignore
â”œâ”€â”€.env.example
â”œâ”€â”€ Procfile
â”œâ”€â”€ pyproject.toml
â”œâ”€â”€ requirements.txt
â”œâ”€â”€ README.md
â””â”€â”€ .gitignore
```

---

# ðŸ“ DescripciÃ³n de Carpetas

| Carpeta | DescripciÃ³n |
|----------|-------------|
| ðŸ“‚ app | ImplementaciÃ³n de la API REST |
| ðŸ¤– training | Entrenamiento del modelo |
| ðŸ’¾ models | Modelo entrenado y artefactos |
| ðŸ§ª tests | Pruebas automatizadas |
| ðŸ“Š data | Dataset utilizado |
| âš™ï¸ .github | Pipeline de GitHub Actions |

---

# ðŸ“¦ InstalaciÃ³n

## 1ï¸âƒ£ Clonar el repositorio

```bash
git clone https://github.com/turbogarypleto/prediccion_obesidad_mlops.git

cd prediccion_obesidad_mlops
```

---

## 2ï¸âƒ£ Crear un entorno virtual

### Windows

```bash
python -m venv .venv

.venv\Scripts\activate
```

### macOS / Linux

```bash
python3 -m venv .venv

source .venv/bin/activate
```

---

## 3ï¸âƒ£ Instalar dependencias

```bash
pip install -r requirements.txt
```

---

# â–¶ï¸ EjecuciÃ³n Local

Levantar la API:

```bash
uvicorn app.main:app --reload
```

La aplicaciÃ³n estarÃ¡ disponible en:

```
http://localhost:8000
```

DocumentaciÃ³n Swagger:

```
http://localhost:8000/docs
```

EspecificaciÃ³n OpenAPI:

```
http://localhost:8000/openapi.json
```

---

# ðŸ³ Docker

## Construir la imagen

```bash
docker build -t obesity-api .
```

## Ejecutar el contenedor

```bash
docker run -p 8000:8000 obesity-api
```

---

# ðŸ³ Docker Compose

Levantar el proyecto completo:

```bash
docker compose up --build
```

Detener el proyecto:

```bash
docker compose down
```

Docker Compose construye automÃ¡ticamente la imagen, inicia el contenedor y deja disponible la API en el puerto **8000**.

---

# ðŸŒ Endpoints de la API

La API expone cinco endpoints principales para consultar el estado del servicio, obtener informaciÃ³n del modelo y realizar predicciones individuales y por lotes.

---

## ðŸ  GET /

Retorna informaciÃ³n general de la API.

### Request

```http
GET /
```

### Response

```json
{
  "message": "Obesity Prediction API",
  "version": "1.0.0"
}
```

---

## â¤ï¸ GET /health

Permite verificar que la API y el modelo se encuentran correctamente cargados.

### Request

```http
GET /health
```

### Response

```json
{
  "status": "ok",
  "model_loaded": true
}
```

Este endpoint es utilizado tanto por Docker como por GitHub Actions para verificar que la aplicaciÃ³n se encuentra operativa.

---

## ðŸ“Š GET /model/schema

Entrega la metadata del modelo entrenado.

La informaciÃ³n incluye:

- Variables utilizadas por el modelo.
- Variable objetivo.
- Accuracy del modelo.
- NÃºmero de muestras utilizadas.
- ParÃ¡metros de entrenamiento.

---

## ðŸ”® POST /predict

Realiza una predicciÃ³n para un Ãºnico registro.

### Ejemplo de Request

```json
{
  "Gender": "Male",
  "Age": 25,
  "Height": 1.75,
  "Weight": 82,
  "family_history": "yes",
  "FAVC": "yes",
  "FCVC": 2,
  "NCP": 3,
  "CAEC": "Sometimes",
  "SMOKE": "no",
  "CH2O": 2,
  "SCC": "no",
  "FAF": 1,
  "TUE": 1,
  "CALC": "Sometimes",
  "MTRANS": "Public_Transportation"
}
```

### Ejemplo con curl

```bash
curl -X POST http://localhost:8000/predict \
  -H "Content-Type: application/json" \
  -d '{"Gender":"Male","Age":25,"Height":1.75,"Weight":82,"family_history":"yes","FAVC":"yes","FCVC":2,"NCP":3,"CAEC":"Sometimes","SMOKE":"no","CH2O":2,"SCC":"no","FAF":1,"TUE":1,"CALC":"Sometimes","MTRANS":"Public_Transportation"}'
```
### Response

```json
{
  "prediction": "Normal_Weight"
}
```

---

## ðŸ“¦ POST /predict/batch

Permite enviar mÃºltiples registros para obtener varias predicciones en una Ãºnica solicitud.

### Response

```json
{
  "predictions": [
    "Normal_Weight",
    "Overweight_Level_I"
  ]
}
```

---

# ðŸ“‘ DocumentaciÃ³n Swagger

FastAPI genera automÃ¡ticamente la documentaciÃ³n interactiva de la API.

Disponible en:

```
http://localhost:8000/docs
```

AdemÃ¡s, el esquema OpenAPI puede consultarse en:

```
http://localhost:8000/openapi.json
```

Swagger permite:

- Visualizar todos los endpoints disponibles.
- Ejecutar solicitudes directamente desde el navegador.
- Revisar ejemplos de Request y Response.
- Consultar el esquema completo de la API.

---

# ðŸ§ª Pruebas Automatizadas

El proyecto incorpora pruebas unitarias utilizando **Pytest**.

Para ejecutarlas:

```bash
python -m pytest tests/test_api.py -v
```

Las pruebas consideran los siguientes escenarios:

- âœ… Endpoint raÃ­z.
- âœ… Endpoint Health.
- âœ… Consulta del esquema del modelo.
- âœ… PredicciÃ³n vÃ¡lida.
- âœ… Campo obligatorio faltante.
- âœ… Valor categÃ³rico invÃ¡lido.
- âœ… PredicciÃ³n Batch.
- âœ… Batch con datos invÃ¡lidos.
- âœ… Tipo de dato incorrecto.

Resultado esperado:

```text
==========================
9 passed
==========================
```

---

# ðŸŽ¨ Calidad del CÃ³digo

La calidad del cÃ³digo es validada utilizando **Ruff**.

Ejecutar:

```bash
ruff check .
```

CorrecciÃ³n automÃ¡tica:

```bash
ruff check . --fix
```

---

# âš™ï¸ IntegraciÃ³n Continua (CI/CD)

El proyecto incorpora un pipeline automÃ¡tico utilizando **GitHub Actions**.

Cada vez que se realiza un **Push** o un **Pull Request**, el pipeline ejecuta automÃ¡ticamente las siguientes tareas:

- InstalaciÃ³n de dependencias.
- ValidaciÃ³n del cÃ³digo mediante Ruff.
- EjecuciÃ³n de pruebas unitarias.
- ConstrucciÃ³n de la imagen Docker.
- EjecuciÃ³n del contenedor.
- VerificaciÃ³n del endpoint `/health`.

---

# ðŸ”„ Pipeline de IntegraciÃ³n Continua

```mermaid
flowchart LR
    A[Push o Pull Request] --> B[GitHub Actions]
    B --> C[Instalar Dependencias]
    C --> D[Ruff]
    D --> E[Pytest]
    E --> F[Docker Build]
    F --> G[Docker Run]
    G --> H[Health Check]
    H --> I[Pipeline Exitoso]
```

---

# ðŸ“ˆ Flujo de PredicciÃ³n

```mermaid
flowchart LR
    A[Cliente] --> B[API FastAPI]
    B --> C[ValidaciÃ³n]
    C --> D[Preprocesamiento]
    D --> E[Label Encoder]
    E --> F[Modelo Random Forest]
    F --> G[PredicciÃ³n]
    G --> H[Respuesta JSON]
```

---

# ðŸ³ ContenerizaciÃ³n

La aplicaciÃ³n fue diseÃ±ada para ejecutarse completamente mediante Docker.

Beneficios:

- ðŸ“¦ Portabilidad.
- ðŸ”„ Reproducibilidad.
- ðŸ’» Independencia del sistema operativo.
- ðŸš€ Facilidad de despliegue.

---

# âœ… Buenas PrÃ¡cticas Implementadas

Durante el desarrollo del proyecto se aplicaron diversas buenas prÃ¡cticas de ingenierÃ­a de Machine Learning:

- Arquitectura modular.
- SeparaciÃ³n entre entrenamiento e inferencia.
- Modelo serializado mediante Pickle.
- ValidaciÃ³n de datos con Pydantic.
- DocumentaciÃ³n automÃ¡tica mediante Swagger.
- Pruebas unitarias.
- ContenerizaciÃ³n con Docker.
- IntegraciÃ³n Continua mediante GitHub Actions.
- ValidaciÃ³n de calidad utilizando Ruff.

---

# ðŸš€ Mejoras Futuras

Como trabajo futuro podrÃ­an incorporarse nuevas funcionalidades, entre ellas:

- ðŸ” AutenticaciÃ³n mediante JWT.
- â˜ï¸ Despliegue en Azure, AWS o Google Cloud.
- ðŸ“ˆ Monitoreo del rendimiento del modelo.
- ðŸ“Š IntegraciÃ³n con MLflow.
- ðŸ—„ï¸ Registro de predicciones en una base de datos.
- ðŸ”„ Reentrenamiento automÃ¡tico del modelo.
- ðŸš€ Pipeline de Continuous Deployment (CD).

---

# âš ï¸ Troubleshooting

| Problema | SoluciÃ³n |
|----------|----------|
| Swagger no carga | Verificar que la API estÃ© ejecutÃ¡ndose. |
| Docker no inicia | Ejecutar `docker compose down` y luego `docker compose up --build`. |
| Error `ModuleNotFoundError` | Revisar la estructura del proyecto y el PYTHONPATH. |
| No encuentra `model.pkl` | Confirmar que exista dentro de la carpeta `models`. |
| Fallan las pruebas | Ejecutar `python -m pytest tests/test_api.py -v`. |
| Error en GitHub Actions | Revisar el archivo `ci.yml` y los logs del pipeline. |

---

# ðŸŽ¯ Conclusiones

Este proyecto demuestra la implementaciÃ³n de un flujo completo de **MLOps** para un problema de clasificaciÃ³n utilizando Machine Learning.

La soluciÃ³n integra el entrenamiento del modelo, la serializaciÃ³n de los artefactos, el despliegue mediante una API REST, la documentaciÃ³n automÃ¡tica, las pruebas unitarias, la contenerizaciÃ³n con Docker y la integraciÃ³n continua mediante GitHub Actions.

El resultado es una aplicaciÃ³n modular, reproducible y preparada para ser desplegada en distintos entornos.

---

# âš ï¸ Limitaciones

Si bien el proyecto cumple con los objetivos planteados para la asignatura, existen oportunidades de mejora que podrÃ­an incorporarse en una versiÃ³n de producciÃ³n:

- ðŸ”’ Incorporar autenticaciÃ³n y autorizaciÃ³n mediante JWT para proteger los endpoints.
- â˜ï¸ Desplegar la API en un servicio Cloud (Azure, AWS o Google Cloud).
- ðŸ“Š Implementar monitoreo del rendimiento del modelo y de la API en producciÃ³n.
- ðŸ”„ Automatizar el reentrenamiento del modelo cuando se disponga de nuevos datos.
- ðŸ—„ï¸ Registrar las predicciones en una base de datos para facilitar auditorÃ­as y anÃ¡lisis posteriores.
- ðŸ“ˆ Incorporar mÃ©tricas avanzadas para detectar deriva del modelo (*Model Drift*).
- ðŸš€ Implementar un pipeline completo de **Continuous Deployment (CD)** para automatizar el despliegue.

Estas mejoras no fueron implementadas debido al alcance acadÃ©mico del proyecto, pero representan una evoluciÃ³n natural para una soluciÃ³n orientada a producciÃ³n.

---

# ðŸ‘¨â€ðŸ’» Autores

Este proyecto fue desarrollado por:

- **CristÃ³bal Barrientos**
- **CristÃ³bal Crespo**
- **AndrÃ©s LÃ³pez**

**Programa:** MagÃ­ster en Ciencia de Datos

**Universidad:** Universidad Adolfo IbÃ¡Ã±ez

**AÃ±o:** 2026

# ðŸ¤– Uso de Asistentes de IA

Durante el desarrollo de este proyecto se utilizaron asistentes de IA como
apoyo, conforme a lo permitido en la pauta de evaluaciÃ³n:

- **Claude (Cowork)**: revisiÃ³n de la pauta de evaluaciÃ³n frente al estado del
  repositorio, identificaciÃ³n de brechas respecto a la rÃºbrica, correcciÃ³n del
  pipeline de CI/CD, validaciÃ³n de entradas de la API, y redacciÃ³n del
  borrador del informe tÃ©cnico.

---

# ðŸ“„ Licencia

Este proyecto fue desarrollado con fines acadÃ©micos para la asignatura de **MLOps** del programa de **MagÃ­ster en Ciencia de Datos** de la **Universidad Adolfo IbÃ¡Ã±ez**.

Su uso es exclusivamente educativo.

