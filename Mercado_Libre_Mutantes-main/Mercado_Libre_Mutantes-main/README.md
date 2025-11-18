# 🧬 Mutant Detection API

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://example.com) [![Java](https://img.shields.io/badge/Java-17-blue)](https://adoptopenjdk.net/) [![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)

## 📝 Descripción

Proyecto Java **Spring Boot** que expone una API REST para detectar si una secuencia de ADN corresponde a un mutante. La lógica busca más de una secuencia de cuatro letras iguales `(A, T, C, G)` en **horizontal**, **vertical** o **diagonal**.

## 🛠️ Tecnologías

| Tecnología | Versión |
|---|---|
| **Java** | 17 |
| **Spring Boot** | - |
| **Maven** | - |
| **Spring Data JPA** | H2 en memoria |
| **Swagger/OpenAPI** | Documentación automática |

## ⚡ Uso rápido

### 1️⃣ Compilar y ejecutar tests

```powershell
./mvnw.cmd -B clean test# 🧬 Mutant Detection API

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://example.com) [![Java](https://img.shields.io/badge/Java-17-blue)](https://adoptopenjdk.net/) [![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)

## 📝 Descripción

Proyecto Java **Spring Boot** que expone una API REST para detectar si una secuencia de ADN corresponde a un mutante. La lógica busca más de una secuencia de cuatro letras iguales `(A, T, C, G)` en **horizontal**, **vertical** o **diagonal**.

## 🛠️ Tecnologías

| Tecnología | Versión |
|---|---|
| **Java** | 17 |
| **Spring Boot** | - |
| **Maven** | - |
| **Spring Data JPA** | H2 en memoria |
| **Swagger/OpenAPI** | Documentación automática |

## ⚡ Uso rápido

### 1️⃣ Compilar y ejecutar tests

```powershell
./mvnw.cmd -B clean test# 🧬 Mutant Detection API

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://example.com) [![Java](https://img.shields.io/badge/Java-17-blue)](https://adoptopenjdk.net/) [![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)

## 📝 Descripción

Proyecto Java **Spring Boot** que expone una API REST para detectar si una secuencia de ADN corresponde a un mutante. La lógica identifica **más de una secuencia de cuatro letras iguales** `(A, T, C, G)` en horizontal, vertical o diagonal.

## 🛠️ Tecnologías

| Tecnología | Versión |
|---|---|
| **Java** | 17 |
| **Spring Boot** | - |
| **Maven** | - |
| **Spring Data JPA** | H2 en memoria |
| **Swagger/OpenAPI** | Documentación automática |

## ⚡ Inicio Rápido

### Compilar y ejecutar tests

```powershell
./mvnw.cmd -B clean test# Mutant Detection API

## Descripción

Proyecto Java (Spring Boot) que expone una API REST para detectar si una secuencia de ADN corresponde a un mutante. La lógica busca más de una secuencia de cuatro letras iguales (A, T, C, G) en horizontal, vertical o diagonal.

## Tecnologías

- Java 17
- Spring Boot
- Maven
- Spring Data JPA (H2 en memoria para desarrollo)
- Swagger/OpenAPI (documentación)

## Uso rápido

1. Compilar y ejecutar tests:

    ```powershell
    ./mvnw.cmd -B clean test
    ```

2. Empaquetar y ejecutar jar:

    ```powershell
    ./mvnw.cmd -B clean package
    java -jar target\MercadoLibre-1.0-SNAPSHOT.jar
    ```

## Endpoints principales

- `POST /mutant` — Recibe JSON `{ "dna": ["ATGC...", ...] }` y devuelve:
  - `200 OK` si es mutante
  - `403 Forbidden` si no es mutante
  - `400 Bad Request` para entradas inválidas
- `GET /stats` — Devuelve estadísticas: `count_mutant_dna`, `count_human_dna`, `ratio`
- `GET /` — Página de inicio con enlaces a la documentación y `/stats`

## Despliegue

- El puerto se configura mediante la variable de entorno `PORT`. En `src/main/resources/application.properties` está: `server.port=${PORT:8080}`.
- Dockerfile multi-stage incluido para construir y ejecutar la JAR.
- Para ejecutar con Docker (si Docker está instalado):

    ```powershell
    docker build -t mutant-api:latest .
    docker run -e PORT=8080 -p 8080:8080 mutant-api:latest
    ```

## Documentación

- Swagger UI disponible en `/swagger-ui.html` o `/swagger-ui/index.html` cuando la aplicación está corriendo.

## Archivos relevantes

- `src/main/java/org/example/mercadolibre/controller/MutantController.java` — endpoints HTTP
- `src/main/java/org/example/mercadolibre/service/MutantService.java` — lógica de detección
- `src/main/java/org/example/mercadolibre/repository/DnaRepository.java` — persistencia
- `src/main/resources/application.properties` — configuración (puerto, H2, Swagger)
- `Dockerfile` — imagen multi-stage para build y ejecución
- `render.yaml` — configuración de despliegue para Render