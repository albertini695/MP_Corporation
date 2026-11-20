# Banco de Proyectos — Lista inicial

Son 10 proyectos ordenados por dificultad creciente. No dependen del pensum: están elegidos para **aprender** y para que cada uno reutilice componentes y conocimientos del anterior.

**Kit base común:** Arduino Uno o Nano, protoboard, cables jumper, juego de resistencias y LED, pulsadores, potenciómetros, multímetro, cautín y estaño, y una fuente o batería de 7–12 V.

**Leyenda de secciones:** 02 Mecánica · 03 Electrónica · 04 Sensores y actuadores · 05 Programación · 06 Control · 07 Integración

---

## MP-001 — Semáforo con botón peatonal
- **Dificultad:** 1 · **Secciones:** 03, 05
- **Componentes:** LED rojo, amarillo y verde, resistencias de 220–330 Ω, pulsador.
- **Qué aprendes:** la ley de Ohm (calcular la resistencia de un LED), entradas y salidas digitales, resistencias pull-up, el rebote de los pulsadores (*debounce*), temporización sin bloquear el programa (`millis()` en lugar de `delay()`) y las **máquinas de estados**, que son la base de casi todo el firmware.
- **Criterio de éxito:** el botón responde en menos de 100 ms en cualquier estado del ciclo, y el código no usa `delay()`.
- **Extensión:** un zumbador para accesibilidad y un tiempo de cruce ajustable con un potenciómetro.

## MP-002 — Medidor de distancia ultrasónico calibrado
- **Dificultad:** 1–2 · **Secciones:** 03, 04, 05
- **Componentes:** sensor HC-SR04 y pantalla LCD 16x2 con módulo I2C.
- **Qué aprendes:** el principio de tiempo de vuelo, cómo la temperatura cambia la velocidad del sonido, **curvas de calibración** (regresión lineal), y los conceptos de error, resolución e incertidumbre (por ejemplo, la desviación estándar de 30 mediciones a cada distancia).
- **Criterio de éxito:** una curva de calibración entre 5 y 100 cm con el error documentado en cada punto.
- **Nota:** conecta directamente con Metrología y con Probabilidad y Estadística.

## MP-003 — Control de velocidad y sentido de un motor DC con puente H
- **Dificultad:** 2 · **Secciones:** 03, 04, 05
- **Componentes:** motor DC con reductora, driver TB6612FNG (es más eficiente) o L298N (es más fácil de conseguir, pero pierde unos 2 V), potenciómetro y una fuente separada para el motor.
- **Qué aprendes:** PWM, el funcionamiento de un puente H, el diodo de rueda libre (*flyback*), por qué un motor no se alimenta desde el pin de 5 V del Arduino, la **tierra común** y la corriente de arranque (medida con el multímetro).
- **Criterio de éxito:** controlar la velocidad de 0 a 100 % con el potenciómetro e invertir el sentido sin que el Arduino se reinicie.

## MP-004 — Tacómetro óptico (medición de RPM)
- **Dificultad:** 2–3 · **Secciones:** 02, 04, 05 · *Reutiliza el MP-003.*
- **Componentes:** sensor infrarrojo de ranura (tipo FC-03 o H206) y un disco ranurado (de cartón o impreso en 3D).
- **Qué aprendes:** **interrupciones**, el cálculo de RPM a partir de pulsos, el compromiso entre resolución y número de ranuras, el filtrado con media móvil y la **no linealidad** de un motor real (la zona muerta del PWM).
- **Criterio de éxito:** una gráfica de PWM frente a RPM con al menos 10 puntos, comparada con una medición de referencia.
- **Por qué importa:** es el sensor que necesitarás en el MP-007.

## MP-005 — Termostato con histéresis (control on-off)
- **Dificultad:** 2 · **Secciones:** 03, 04, 05, 06
- **Componentes:** sensor de temperatura DS18B20 (o LM35), ventilador de 12 V y un MOSFET de nivel lógico (IRLZ44N) o un módulo de relé.
- **Qué aprendes:** el **control on-off**, por qué la histéresis evita que el actuador conmute sin parar (*chattering*), el MOSFET como interruptor, y la **adquisición de datos**: enviar los datos por puerto serie, guardarlos en un CSV y graficarlos en Python o Excel.
- **Criterio de éxito:** mantener la temperatura dentro de una banda de ±1 °C y presentar una gráfica de temperatura frente al tiempo.

## MP-006 — Brazo o pinza de 3 grados de libertad con servos
- **Dificultad:** 3 · **Secciones:** 02, 03, 04, 05
- **Componentes:** 3–4 servos (SG90 para la pinza, MG90S o MG996R para la base y el hombro), potenciómetros, estructura de MDF, cartón piedra o pieza impresa, y una fuente externa de 5 V y 2 A o más.
- **Qué aprendes:** el **cálculo de torque** (τ = F · d) **antes** de elegir los servos, el centro de masa, la señal PWM de los servos, la conversión analógica-digital y el mapeo de valores, y una introducción a la **cinemática directa**.
- **Criterio de éxito:** levantar un objeto de masa conocida, comparando el torque calculado en el hombro con el comportamiento real.
- **Extensión:** grabar una secuencia de movimientos y reproducirla.

## MP-007 — Control PID de velocidad de un motor
- **Dificultad:** 3–4 · **Secciones:** 04, 05, 06, 07 · *Reutiliza el MP-003 y el MP-004.*
- **Qué aprendes:** el **lazo cerrado**, el PID discreto, el efecto de cada término (P, I y D), el *anti-windup*, la **respuesta al escalón** y el rechazo de perturbaciones (frenar el eje con una carga).
- **Criterio de éxito:** mantener las RPM dentro de ±5 % del valor deseado ante una carga, y medir el sobreimpulso y el tiempo de establecimiento a partir de una gráfica.
- **Por qué va antes del seguidor de línea:** aquí aprendes PID en un sistema de una sola variable, donde es fácil medir y entender lo que pasa.

## MP-008 — Carro seguidor de línea (de on-off a PID)
- **Dificultad:** 3–4 · **Secciones:** 02, 03, 04, 05, 06, 07
- **Componentes:** chasis 2WD (o uno que ya tengas), driver TB6612FNG, 3–5 sensores infrarrojos TCRT5000 (o una regleta QTR) y una batería.
- **Qué aprendes:** la **integración completa** de un sistema mecatrónico, y la diferencia práctica entre los controles on-off, P y PD.
- **Criterio de éxito:** completar una pista con curvas, comparando el tiempo de vuelta y la oscilación entre los tres tipos de control.

## MP-009 — Seguidor solar de dos ejes
- **Dificultad:** 3–4 · **Secciones:** 02, 03, 04, 06, 07
- **Componentes:** 4 fotorresistencias (LDR) con divisores de tensión, 2 servos en estructura pan-tilt, un panel solar pequeño y un sensor de potencia INA219.
- **Qué aprendes:** la medición diferencial, la zona muerta para evitar oscilaciones, el diseño de una estructura de dos ejes y la **validación experimental**.
- **Criterio de éxito:** comparar durante el mismo período la energía generada con el panel fijo y con el seguidor, y cuantificar la diferencia en porcentaje.

## MP-010 — Clasificador por color con banda transportadora
- **Dificultad:** 4 · **Secciones:** 02 a 08 (proyecto integrador)
- **Componentes:** sensor de color TCS34725, motor para la banda (DC o paso a paso), servo desviador, sensor infrarrojo de presencia y la estructura de la banda.
- **Qué aprendes:** la **automatización industrial secuencial** (una lógica similar a la de un PLC), la sincronización entre el sensor y el actuador, la calibración de color, el conteo de piezas y las máquinas de estados complejas.
- **Criterio de éxito:** clasificar 3 colores con un acierto del 90 % o más en 50 objetos, documentado con una **matriz de confusión**.

---

## Ruta sugerida
```
MP-001 → MP-002 → MP-003 → MP-004 → MP-005 → MP-006 → MP-007 → MP-008 → MP-009 → MP-010
 bases    medir    potencia  sensar    control   mecánica   PID       integrar   validar    sistema
                                       on-off                                               completo
```

## Ideas añadidas después
*(Aquí se agregarán los proyectos de las listas con fuentes y videos.)*

| ID provisional | Idea | Fuente o video | Fecha | Notas |
|----------------|------|----------------|-------|-------|
