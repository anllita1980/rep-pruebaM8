# CI Pipeline Project

Este proyecto es una API básica construida con Node.js y Express que expone endpoints para manejar usuarios. Además, incluye un pipeline de integración continua (CI) configurado con Jenkins.

## Tabla de Contenidos

- [Requisitos](#requisitos)
- [Instalación](#instalación)
- [Scripts disponibles](#scripts-disponibles)
- [Endpoints de la API](#endpoints-de-la-api)
- [Pruebas](#pruebas)
- [Pipeline de Jenkins](#pipeline-de-jenkins)

## Requisitos

- Node.js v20 o superior
- npm (incluido con Node.js)
- Jenkins para ejecutar el pipeline

## Instalación

1. Clona este repositorio:

   ```bash
   git clone https://github.com/anllita1980/rep-pruebaM8.git
   cd https://github.com/anllita1980/rep-pruebaM8.git
   ```

2. Instala las dependencias:

   ```bash
   npm install
   ```

## Scripts disponibles

En el archivo `package.json` se encuentran los siguientes scripts:

- `start`: Inicia la aplicación.

  ```bash
  npm start
  ```

- `build`: Ejecuta un comando de compilación (placeholder en este proyecto).

  ```bash
  npm run build
  ```

- `test`: Ejecuta las pruebas con Jest.

  ```bash
  npm run test
  ```

- `lint`: Ejecuta ESLint para analizar el código.

  ```bash
  npm run lint
  ```

## Endpoints de la API

### GET `/users`

Devuelve una lista de usuarios.

**Respuesta:**

```json
[
  { "id": 1, "name": "Alice", "email": "alice@example.com" },
  { "id": 2, "name": "Bob", "email": "bob@example.com" }
]
```

### GET `/users/:id`

Devuelve un usuario específico por su ID.

**Parámetros:**

- `id` (número): ID del usuario.

**Respuesta:**

```json
{ "id": 1, "name": "Alice", "email": "alice@example.com" }
```

**Error:**

```json
{ "error": "User not found" }
```

## Pruebas

Las pruebas están ubicadas en el directorio `tests/` y se ejecutan con Jest y Supertest.

Ejecuta las pruebas con:

```bash
npm run test
```

## Pipeline de Jenkins

El pipeline está definido en el archivo `Jenkinsfile` y consta de las siguientes etapas:

1. **Checkout**: Clona el repositorio.
2. **Build**: Instala las dependencias y ejecuta el script de compilación.
3. **Test**: Ejecuta las pruebas automatizadas.
4. **Deploy**: Despliega la aplicación ejecutando el comando `npm start`.

### Configuración del Pipeline

1. Asegúrate de tener Jenkins instalado y configurado.
2. Crea un nuevo pipeline en Jenkins y apunta al repositorio de este proyecto.
3. El pipeline utiliza Node.js v20, asegúrate de que esté instalado en el agente de Jenkins.

### Notificaciones

- En caso de éxito, se muestra el mensaje: `✅ Pipeline completado con éxito`.
- En caso de fallo, se muestra el mensaje: `❌ El pipeline ha fallado`.

## Licencia

Este proyecto está bajo la licencia ISC.
