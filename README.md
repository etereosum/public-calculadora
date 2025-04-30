
# 🧪 Prueba Técnica – Calculadora Dinámica en Node.js

## 🎯 Objetivo

El propósito de esta prueba es desarrollar un pequeño sistema en **Node.js** que funcione como una **calculadora dinámica**.  
El sistema debe recibir **objetos JSON** que describen operaciones matemáticas, validarlos, ejecutar las operaciones solicitadas y devolver el resultado correspondiente.  
Además, se deben implementar **pruebas automatizadas** que verifiquen el comportamiento correcto del sistema.

---

## 🧱 ¿Qué es un nodo?

Un **nodo** es un objeto que describe una operación matemática con los siguientes atributos:

```json
{
  "operation": "add",
  "params": [1, 2, 3]
}
```

Al procesar el nodo, se debe agregar una propiedad `response` con el resultado:

```json
{
  "operation": "add",
  "params": [1, 2, 3],
  "response": 6
}
```

---

## ✅ Operaciones permitidas

| Operación    | Descripción                              | Ejemplo          | Resultado |
|--------------|------------------------------------------|------------------|-----------|
| `add`        | Suma                                     | [4, 5, 6]        | 15        |
| `subtract`   | Resta secuencial                         | [20, 5, 3]       | 12        |
| `multiply`   | Multiplicación secuencial                | [2, 3, 4]        | 24        |
| `divide`     | División secuencial                      | [100, 5, 2]      | 10        |
| `sqrt`       | Raíz cuadrada (solo un número)          | [81]             | 9         |
| `power`      | Potenciación: base y exponente          | [3, 4]           | 81        |

---

## 🔧 Funciones a desarrollar

### 1. `processNode(node)`

- Verifica que `operation` sea válida.
- Verifica que `params` no esté vacío y contenga solo números.
- Ejecuta la operación.
- Devuelve el objeto original con el campo `response`.

### 2. `processMultipleNodes(nodes)`

- Recibe un array de nodos.
- Procesa cada uno utilizando `processNode`.
- Retorna el array con los resultados.

---

## 🧪 Pruebas automatizadas

Crear el archivo `tests/processNode.test.js` que incluya pruebas para:

- ✅ Operaciones válidas (`add`, `subtract`, etc.).
- ❌ Operaciones inválidas.
- ❌ Parámetros vacíos o incorrectos.
- ✅ Múltiples nodos procesados correctamente.

---

## 📁 Estructura del proyecto recomendada

```
/node-processor/
├── src/
│   ├── index.js
│   ├── processNode.js
│   └── processMultipleNodes.js
├── tests/
│   └── processNode.test.js
├── package.json
└── README.md
```

---

## 📝 Criterios de evaluación

- Lógica correcta de operaciones.
- Validación de entradas y manejo de errores.
- Código limpio, modular y bien estructurado.
- Pruebas automatizadas funcionales.
- Buenas prácticas y claridad.

---

## 📤 Entregables

- Repositorio en GitHub o GitLab.
- Incluir instrucciones en `README.md` sobre:
  - Instalación de dependencias (`npm install`)
  - Ejecución de pruebas (`npm test`)
  - Ejecución del sistema principal (si aplica)

---

## ⏳ Tiempo estimado

Hasta el sábado `[fecha límite]` para completar y enviar el enlace del repositorio.

---

**¡Mucho éxito!**

---

## 🧪 Casos de prueba para `processMultipleNodes(nodes)`

A continuación se presentan algunos ejemplos de entrada y salida esperada para validar el correcto funcionamiento de la función `processMultipleNodes`.

### 🔹 Ejemplo 1: Suma y multiplicación

**Entrada:**
```json
[
  { "operation": "add", "params": [1, 2, 3] },
  { "operation": "multiply", "params": [4, 5] }
]
```

**Salida esperada:**
```json
[
  { "operation": "add", "params": [1, 2, 3], "response": 6 },
  { "operation": "multiply", "params": [4, 5], "response": 20 }
]
```

---

### 🔹 Ejemplo 2: Varias operaciones válidas

**Entrada:**
```json
[
  { "operation": "add", "params": [1, 2] },
  { "operation": "subtract", "params": [10, 5] },
  { "operation": "multiply", "params": [3, 3] },
  { "operation": "divide", "params": [8, 2] },
  { "operation": "sqrt", "params": [16] },
  { "operation": "power", "params": [3, 2] }
]
```

**Salida esperada:**
```json
[
  { "operation": "add", "params": [1, 2], "response": 3 },
  { "operation": "subtract", "params": [10, 5], "response": 5 },
  { "operation": "multiply", "params": [3, 3], "response": 9 },
  { "operation": "divide", "params": [8, 2], "response": 4 },
  { "operation": "sqrt", "params": [16], "response": 4 },
  { "operation": "power", "params": [3, 2], "response": 9 }
]
```

---

Estos casos deben ser validados mediante pruebas automatizadas en el archivo `tests/processNode.test.js`.
