# Sistema RAG Modular - Senior Architecture Implementation

Este repositorio contiene una implementación de un sistema de **Generación Aumentada por Recuperación (RAG)** diseñado bajo principios de arquitectura modular y escalable.

## Características Principales

- **Arquitectura Modular**: Microservicios desacoplados para Ingesta, Recuperación y Generación.
- **Pipeline de Ingesta Avanzado**:
  - Chunking semántico (500-1000 tokens).
  - Embeddings de alta calidad con el modelo `e5-large-v2`.
- **Búsqueda Híbrida**:
  - Recuperación inicial mediante **k-NN** con **FAISS**.
  - Etapa de **Reranking** con **Cross-Encoder** para máxima precisión.
- **Privacidad y Ejecución Local**:
  - Generación mediante el LLM `Nous-Hermes-2` ejecutado localmente vía **Ollama**.
- **Trazabilidad Total**: Citación explícita de las fuentes documentales en cada respuesta.
- **Persistencia Robusta**: PostgreSQL para metadatos, chats y almacenamiento de documentos originales.
- **Evaluación Científica**: Framework **RAGAS** integrado para medir relevancia, fidelidad y cobertura.

## Tecnologías Utilizadas

- **Backend**: FastAPI (Python)
- **Frontend**: React (JavaScript/CSS)
- **Vector DB**: FAISS
- **Base de Datos**: PostgreSQL
- **Orquestación**: Docker & Docker Compose
- **LLM Engine**: Ollama (Nous-Hermes-2)

## Estructura del Proyecto

```text
modular_rag_system/
├── backend/            # API, Ingestión y Lógica RAG
├── frontend/           # Interfaz de usuario en React
├── data/               # Almacenamiento persistente
├── docker-compose.yml  # Orquestación de contenedores
└── README.md           # Esta documentación
```

## Configuración y Ejecución

1. Asegúrate de tener **Docker** y **Docker Compose** instalados.
2. Instala **Ollama** y descarga el modelo: `ollama pull nous-hermes2`.
3. Ejecuta el sistema: `docker-compose up --build`.

---
*Diseñado por Arquitectos Senior de IA para entornos de alto rendimiento.*
