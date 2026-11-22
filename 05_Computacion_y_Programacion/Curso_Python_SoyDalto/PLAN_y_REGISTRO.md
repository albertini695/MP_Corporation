# Curso de Python desde Cero (Soy Dalto): plan de evaluación y registro

- **Curso:** Curso de PYTHON desde CERO (Completo), de Soy Dalto
- **Enlace:** https://www.youtube.com/watch?v=nKPbfIU442g
- **Estudiante:** Steven
- **Propósito:** tener una base de Python antes de los proyectos básicos de MP Corporation (área 05 Computación y Programación)

---

## 1. Módulos

| Módulo | Sección del video | Tramo | Preguntas |
|---|---|---|---|
| M1 | Todo sobre Python + Primeros pasos | 0:00 – 32:43 | 10 |
| M2 | Fundamentos (datos simples, variables, datos compuestos, operadores aritméticos, de comparación y lógicos, condicionales) | 32:43 – 1:46:08 | 15 |
| M3 | Sección básica (métodos de cadenas, listas y diccionarios, input, Ejercicios prácticos 1) | 1:46:08 – 3:06:55 | 15 |
| M4 | Sección intermedia (Variables 2.0, Diccionarios 2.0, for, while, funciones integradas, funciones propias, lambda, Ejercicios prácticos 2) | 3:06:55 – 5:17:41 | 15 |
| M5 | Sección semiavanzada (módulos, enrutamiento, paquetes, TXT, CSV, archivos, gráficos) | 5:17:41 – 7:11:24 | 15 |
| M6 | Sección avanzada (excepciones, expresiones regulares y su análisis, ejercicio de regex) | 7:11:24 – 8:02:26 | 12 |
| PF | Proyecto final (todo el curso) | — | — |

## 2. Cómo se evalúa cada módulo (100 puntos; para aprobar hacen falta 90)

### 2.1 Cuestionario: 40 puntos
- Selección múltiple, una pregunta a la vez: respondes, te corrijo y te explico por qué, y luego viene la siguiente.
- Cada pregunta vale 40/N puntos (N = número de preguntas del módulo).
- Las preguntas se basan en el comportamiento real de Python 3, no solo en lo que dice el video. Si el video simplifica algo o no lo dice con exactitud, se señala.

### 2.2 Práctica: 60 puntos
| Criterio | Puntos |
|---|---|
| Funcionamiento correcto: cumple todos los requisitos del enunciado | 25 |
| Aplicación correcta de los conceptos del módulo | 15 |
| Robustez y verificación: casos límite y pruebas con varios datos, con la salida real pegada | 10 |
| Legibilidad y buenas prácticas: nombres descriptivos, PEP 8, estructura y comentarios útiles | 10 |

Reglas de la práctica:
- Se entrega el código **y** la salida real de la terminal. Si falta la salida, la práctica no se evalúa.
- El código lo escribe Steven. Si la solución no es propia, la práctica se anula.
- Se pueden usar conceptos que todavía no se vieron, salvo que el enunciado lo prohíba.

### 2.3 Aprobación e intentos
- **Nota del módulo = cuestionario + práctica.** Con 90 o más, el módulo queda aprobado y pasas al siguiente.
- Con menos de 90 se repite el proceso completo, con preguntas nuevas y una práctica nueva. Recibes un informe con los fallos, la causa de cada uno, cómo mejorar y qué minutos del video volver a ver.
- Cada módulo admite **hasta 3 intentos**. Si al tercero no se aprueba: sesión de refuerzo enfocada en los fallos y repaso de los tramos indicados del video, y después empieza un nuevo ciclo de 3 intentos. (Regla propuesta por Claude; se puede cambiar.)

## 3. Proyecto final (100 puntos; para aprobar hacen falta 90)
Un proyecto integrador con enfoque mecatrónico (por ejemplo, procesar y graficar datos de sensores). El enunciado se define al terminar M6.

| Criterio | Puntos |
|---|---|
| Requisitos funcionales | 30 |
| Integración de los contenidos del curso | 20 |
| Robustez: validación de entradas, excepciones y archivos | 15 |
| Estructura modular y legibilidad | 15 |
| Documentación: README y ejemplos de ejecución | 10 |
| Defensa: preguntas sobre su propio código | 10 |

## 4. Fe de erratas del autor (se tiene en cuenta al evaluar)
- **29:10:** Prettier no define el estilo del código; automatiza su formateo para que sea consistente y cumpla normas de estilo predefinidas.
- **2:38:10:** en diccionarios, `pop()` elimina **un solo** elemento. El segundo parámetro es el valor que se devuelve si la clave no existe.
- **3:04:54:** "hablar un 30 % más rápido" se calcula **dividiendo** entre 1.3, no multiplicando.

## 5. Registro de progreso

| Módulo | Intento | Cuestionario (/40) | Práctica (/60) | Total | Estado | Fecha |
|---|---|---|---|---|---|---|
| M1 | 1 | 40 | 34 | 74 | No aprobado: repetir | 2026-11-20 |
| M1 | 2 | 40 | 52 | 92 | **Aprobado** | 2026-11-21 |
| M2 | — | — | — | — | Pendiente | — |
| M3 | — | — | — | — | Pendiente | — |
| M4 | — | — | — | — | Pendiente | — |
| M5 | — | — | — | — | Pendiente | — |
| M6 | — | — | — | — | Pendiente | — |
| PF | — | — | — | — | Pendiente | — |

### Observaciones por intento
- **M1 · Intento 1 (74/100):** cuestionario perfecto. En la práctica no se cumplieron los requisitos de la Parte 3: faltaron las 4 llamadas a `print()` y la línea `2 + 3` sola. La explicación de REPL frente a script fue imprecisa. En la Parte 4 el error se atribuyó a VS Code en lugar del intérprete y faltó mostrar la corrección: el archivo final todavía tiene `Print`. Comentarios con `##`, líneas muy largas y la variable `Oración` no siguen PEP 8.
- **M1 · Intento 2 (92/100, aprobado):** cuestionario perfecto. Explicaciones excelentes de expresión frente a instrucción y de `SyntaxError` (fase de compilación) frente a `NameError` (tiempo de ejecución). Intérprete igualado a 3.14. Descuentos: «MP Corporation» en lugar de «MP CORPORATION»; fecha `2026-21-11` inválida (el formato ISO es `2026-11-21`); la línea 1 supera los 88 caracteres; el archivo final quedó sin guardar.
