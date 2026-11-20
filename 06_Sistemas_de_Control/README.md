# 06 — Sistemas de Control

## Función
Diseña **cómo decide el sistema** para alcanzar y mantener un objetivo (una temperatura, una velocidad, una posición) a pesar de las perturbaciones.

Sus responsabilidades son:
- **Modelar** el sistema, ya sea con ecuaciones físicas o mediante **identificación experimental** (aplicar un escalón y medir la respuesta).
- **Elegir la estrategia de control:** lazo abierto, on-off con histéresis, P, PI, PD o PID.
- **Sintonizar** los parámetros (Kp, Ki, Kd).
- **Analizar el desempeño:** tiempo de subida, sobreimpulso, tiempo de establecimiento y error en estado estacionario.
- **Simular** antes de implementar, cuando sea posible.

## Importancia
El control es lo que distingue a un sistema mecatrónico de un circuito que simplemente enciende un motor. Sin control en lazo cerrado, el sistema no puede compensar una batería que se descarga, una carga que cambia o un terreno irregular. Es también la disciplina con mayor base matemática: aquí el cálculo diferencial e integral se vuelve tangible (la **I** del PID es literalmente una integral y la **D**, una derivada).

## Enfoque de aprendizaje
Esta sección va por delante de las asignaturas de control del pensum. Por eso el enfoque es progresivo:
1. **Experimental primero:** control on-off y PID sintonizado a mano, observando el efecto de cada parámetro en gráficas reales.
2. **Formal después:** funciones de transferencia, lugar de las raíces y diagramas de Bode, a medida que lleguen Controles Automáticos I y II.

## Contenido
Una carpeta por proyecto (`MP-XXX_Nombre-Corto/`) con:
- `modelo/` — ecuaciones o datos de identificación.
- `simulacion/` — scripts de Python, Octave o Scilab.
- `sintonia/` — tabla de parámetros probados y sus resultados.
- `graficas/` — respuestas al escalón y a perturbaciones.

## Entradas y salidas
- **Recibe de 01:** las especificaciones de desempeño. **De 04:** el ruido y el tiempo de respuesta del sensor, y la saturación y zona muerta del actuador. **De 05:** los datos registrados.
- **Entrega a 05:** el algoritmo y los parámetros. **A 07:** el desempeño esperado, para verificarlo.

## Criterio de salida
- [ ] Las especificaciones de desempeño están definidas con números (por ejemplo, "sobreimpulso menor al 10 %").
- [ ] Las especificaciones se midieron en el sistema real, no solo en simulación.
- [ ] Hay una tabla de sintonía con los intentos registrados: qué se cambió y qué pasó.

## Herramientas sugeridas
Python (numpy, scipy, python-control y matplotlib), GNU Octave, Scilab/Xcos y el Serial Plotter de Arduino.

## Relación con el pensum del ITLA
Cálculo Diferencial (MAT-101) · Cálculo Integral (MAT-102) · Controles Automáticos I (TMC-204) · Controles Automáticos II (TMC-205) · Sistemas de Control (TMC-301)

## Errores a evitar
- Sintonizar un PID sin graficar la respuesta, solo "a ojo".
- Usar el término integral sin *anti-windup* cuando el actuador se satura.
- Derivar una señal ruidosa sin filtrarla primero.
