# 02 — Mecánica y Diseño CAD

## Función
Diseña y fabrica **todo lo que tiene forma, masa y movimiento**: la estructura, el chasis, los soportes, los mecanismos, la transmisión (engranajes, poleas, ejes, ruedas) y las uniones.

Sus responsabilidades son:
- Calcular las **cargas, fuerzas y torques** que deberá soportar o generar el sistema.
- Elegir los **materiales** (MDF, acrílico, PLA/PETG, aluminio, cartón piedra) según su resistencia, su costo y la facilidad para trabajarlos.
- Hacer **bocetos, modelos CAD y planos acotados**.
- Definir el **método de fabricación**: corte manual, impresión 3D, corte láser o piezas compradas.
- Verificar las dimensiones de las piezas fabricadas.

## Importancia
La mecánica pone los límites físicos de todo el sistema. Un mal cálculo de torque inutiliza el motor mejor programado, y un chasis que vibra arruina las lecturas de cualquier sensor. Además, **el torque que se calcula aquí es la entrada de 04** para elegir motores y servos. Si se elige el actuador primero, se diseña al revés.

## Contenido
Una carpeta por proyecto (`MP-XXX_Nombre-Corto/`) con:
- `calculos/` — cargas, torque y relación de transmisión (con el procedimiento, no solo el resultado).
- `cad/` — modelos fuente (`.f3d`, `.step`, `.sldprt`, etc.).
- `planos/` — PDF de los planos acotados.
- `fabricacion/` — archivos STL o DXF y notas de fabricación.

## Entradas y salidas
- **Recibe de 01:** los requerimientos (dimensiones, carga útil, velocidad).
- **Entrega a 04:** el torque y la velocidad que necesita cada eje.
- **Entrega a 03:** el espacio disponible y los puntos de montaje para las placas y la batería.
- **Entrega a 07:** la estructura fabricada y verificada.

## Criterio de salida
- [ ] El cálculo de torque o de carga está documentado con un margen de seguridad (un factor de 1.5 a 2 para proyectos básicos).
- [ ] Hay un plano o modelo con las medidas críticas.
- [ ] La pieza está fabricada y se verificó con regla o calibrador.
- [ ] Se previó el espacio para el cableado y el acceso para cambiar la batería.

## Herramientas sugeridas
Onshape (funciona en el navegador, gratis para uso personal), Fusion 360, FreeCAD y SolidWorks (si está disponible en el ITLA). Calibrador vernier y escuadra.

## Relación con el pensum del ITLA
Dibujo Técnico (CAD-001) · Fundamentos de CAD (CAD-101) · CAD Avanzado (CAD-102) · Ingeniería de los Materiales Aplicada (TMC-100) · Física Mecánica (FIS-120) · Estática y Dinámica Aplicada (TMC-200) · Procesos de Manufactura (TMA-005) · Programación Básica CNC (TMA-301)

## Errores a evitar
- Diseñar sin dejar espacio para los tornillos, los cables o la batería.
- Ignorar el peso de la batería en el cálculo de la carga.
- Fijar los ejes del motor directamente a las ruedas sin acople, sin considerar el desalineamiento.
