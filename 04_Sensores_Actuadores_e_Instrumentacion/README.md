# 04 — Sensores, Actuadores e Instrumentación

> Sección **nueva**: no estaba en la propuesta original.

## Por qué existe
Un sistema mecatrónico **percibe** (sensores), **decide** (computación y control) y **actúa** (actuadores). Los sensores y actuadores son la **frontera entre el mundo físico y el digital**, y ninguna de las 7 secciones originales los cubría de forma explícita. Sin esta sección, un motor quedaría a medio camino entre Mecánica y Electrónica, y la calibración de un sensor no tendría un lugar propio.

## Función
- **Seleccionar sensores:** según el rango, la resolución, la exactitud, el tiempo de respuesta, la interfaz (analógica, digital, I2C, SPI) y el costo.
- **Seleccionar actuadores:** motores DC, servos, motores paso a paso, relés y solenoides, a partir del torque y la velocidad que entrega 02.
- **Caracterizar:** medir el comportamiento real de cada componente, que casi nunca coincide del todo con la hoja de datos.
- **Calibrar:** obtener curvas de calibración y estimar el error y la incertidumbre.
- **Resumir las hojas de datos** en fichas de componente reutilizables.

## Importancia
Un controlador solo puede ser tan bueno como la medición que recibe: si el sensor miente, el sistema entero actúa mal. Esta sección también crea **conocimiento reutilizable**: la ficha de un HC-SR04 ya calibrado sirve para todos los proyectos futuros que lo usen.

## Contenido
| Elemento | Descripción |
|----------|-------------|
| `Fichas_de_Componentes/` | Una ficha por componente: datos clave de la hoja de datos, pinout, conexión típica, resultados de calibración y errores conocidos. |
| `MP-XXX_Nombre-Corto/` | Selección justificada, datos de calibración (CSV) y gráficas para cada proyecto. |

## Entradas y salidas
- **Recibe de 01:** qué hay que medir o mover. **De 02:** el torque y la velocidad requeridos.
- **Entrega a 03:** las especificaciones eléctricas (tensión, corriente, interfaz). **A 05:** el protocolo de comunicación y la ecuación de calibración. **A 06:** el tiempo de respuesta y el ruido del sensor, y los límites del actuador (saturación, zona muerta).

## Criterio de salida
- [ ] La elección de cada sensor y actuador está justificada frente a los requerimientos.
- [ ] Hay una curva de calibración con varias mediciones por punto y su error documentado.
- [ ] Se conocen los límites reales: rango útil, zona muerta y corriente de arranque.

## Relación con el pensum del ITLA
Metrología (TMA-002) · Probabilidad y Estadística (CBG-210) · Física Eléctrica (FIS-130) · Instrumentación Industrial (TMC-302) · Fundamentos de Máquinas Eléctricas (TMC-303)

## Errores a evitar
- Confiar en el valor de la hoja de datos sin medirlo.
- Tomar una sola medición por punto: sin repetición no hay estimación del error.
- Confundir **resolución** (el cambio más pequeño que se detecta) con **exactitud** (qué tan cerca está del valor real).
