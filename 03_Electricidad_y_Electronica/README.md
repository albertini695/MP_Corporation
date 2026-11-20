# 03 — Electricidad y Electrónica

## Función
Diseña y construye los **circuitos que alimentan, protegen e interconectan** el sistema.

Sus responsabilidades son:
- La **alimentación**: elegir las baterías o fuentes, los reguladores de tensión y la distribución de energía.
- El **presupuesto de potencia**: sumar el consumo de todos los componentes y compararlo con la capacidad de la fuente.
- Los **esquemáticos** versionados.
- Las **etapas de potencia**: transistores, MOSFET, relés y drivers de motor.
- Las **protecciones**: fusibles, diodos de rueda libre, protección contra polaridad inversa y condensadores de desacople.
- El **montaje**: primero en protoboard, luego en placa perforada y, más adelante, en PCB.
- Las **mediciones** de verificación con el multímetro (tensiones, corrientes y continuidad).

## Importancia
Es el "sistema circulatorio" del proyecto. Muchas fallas que parecen de programación son en realidad eléctricas: reinicios aleatorios por caídas de tensión, lecturas erráticas por falta de tierra común, o un microcontrolador quemado por la corriente inversa de un motor. Además, esta es la sección donde un error puede dañar componentes o causar un accidente.

## Límite con la sección 04
- **03** diseña el circuito que **alimenta y acondiciona** los sensores y actuadores.
- **04** decide **qué** sensor o actuador usar y **caracteriza su comportamiento**.

Ejemplo: 04 elige el motor y mide su corriente de arranque; 03 diseña el puente H y la fuente que soportan esa corriente.

## Contenido
Una carpeta por proyecto (`MP-XXX_Nombre-Corto/`) con:
- `esquematicos/` — fuente (KiCad, Fritzing) y PDF.
- `calculos/` — resistencias, potencias disipadas y presupuesto de potencia.
- `mediciones/` — tensiones y corrientes medidas, con fotos.
- `pcb/` *(cuando aplique)*

## Entradas y salidas
- **Recibe de 01:** el diagrama de bloques. **De 02:** el espacio de montaje. **De 04:** las especificaciones eléctricas de los sensores y actuadores.
- **Entrega a 05:** el mapa de pines (qué pin hace qué). **A 07:** el circuito armado y verificado.

## Criterio de salida
- [ ] Hay un esquemático actualizado y que coincide con el circuito armado.
- [ ] El presupuesto de potencia muestra que la fuente da al menos un 20 % más de lo que consume el sistema.
- [ ] Las tensiones se midieron en los puntos clave antes de conectar el microcontrolador.
- [ ] La tierra es común y hay protecciones en las cargas inductivas.

## Herramientas sugeridas
KiCad (esquemáticos y PCB), Tinkercad Circuits y Falstad (simulación), multímetro, y una fuente con límite de corriente si es posible.

## Relación con el pensum del ITLA
Física Eléctrica (FIS-130) · Circuitos Eléctricos I y II (TMC-102, TMC-103) · Electrónica I y II (TMC-201, TMC-203) · Electrónica Digital (TMC-202) · Sistemas Digitales (TMC-212) · Electrónica Industrial (TMC-206)

## Errores a evitar
- Alimentar motores o servos desde el pin de 5 V del Arduino.
- Olvidar la tierra común entre la fuente del motor y el microcontrolador.
- Conectar cargas inductivas (motores, relés, solenoides) sin diodo de rueda libre.
- Modificar el circuito con la alimentación conectada.
