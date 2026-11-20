# 05 — Computación y Programación

## Función
Desarrolla **todo el software** de la organización:
- El **firmware** de los microcontroladores: primero Arduino (C/C++); más adelante ESP32 y MicroPython.
- **Scripts de computadora** (Python) para adquirir, graficar y analizar datos de pruebas.
- La **arquitectura del código**: diagramas de flujo, máquinas de estados y organización en funciones y módulos.
- **Bibliotecas propias** reutilizables (por ejemplo, la lectura filtrada de un sensor ya calibrado).
- El **control de versiones** (Git) para no perder nunca una versión que funcionaba.

## Importancia
El software es el "cerebro" del sistema: une los sensores con los actuadores. Bien estructurado, permite modificar un proyecto sin romperlo. Mal estructurado (todo en `loop()`, con `delay()` por todas partes), cada cambio se vuelve un riesgo. Además, los scripts de análisis de datos convierten las pruebas en **evidencia medible**, que es lo que exigen 07 y 08.

## Contenido
| Elemento | Descripción |
|----------|-------------|
| `Biblioteca/` | Funciones y módulos reutilizables entre proyectos. |
| `Herramientas/` | Scripts de Python para leer el puerto serie, guardar CSV y graficar. |
| `MP-XXX_Nombre-Corto/` | El código de cada proyecto, con su diagrama de flujo o máquina de estados. |

## Entradas y salidas
- **Recibe de 03:** el mapa de pines. **De 04:** los protocolos y las ecuaciones de calibración. **De 06:** el algoritmo y los parámetros del controlador.
- **Entrega a 07:** el firmware probado por módulos. **A 06 y a 04:** los datos registrados para análisis.

## Criterio de salida
- [ ] El código compila sin advertencias importantes.
- [ ] Cada módulo (sensor, actuador, lógica) se probó por separado antes de unirlo.
- [ ] Existe un diagrama de flujo o de estados y coincide con el código.
- [ ] El código está comentado y versionado, y la versión estable está marcada.

## Buenas prácticas desde el principio
- Usar `millis()` en lugar de `delay()` cuando el programa deba atender varias cosas.
- Usar **máquinas de estados** para la lógica secuencial.
- Usar constantes con nombre (`const int PIN_MOTOR = 5;`) en lugar de números sueltos.
- Hacer una función por tarea, con un nombre que diga lo que hace.
- Activar el monitor serie para depurar y quitar los mensajes innecesarios en la versión final.

## Herramientas sugeridas
Arduino IDE 2 o PlatformIO, Wokwi (simulador en el navegador), Python con pyserial, pandas y matplotlib, y Git con GitHub.

## Relación con el pensum del ITLA
Fundamentos del Computador (TI-101) · Programación para Mecatrónicos (TMC-101) · Sistemas Digitales (TMC-212) · Microcontroladores (TMC-207) · Redes de Comunicación Industrial (TMC-305)
