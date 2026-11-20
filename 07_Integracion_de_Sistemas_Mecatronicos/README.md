# 07 — Integración de Sistemas Mecatrónicos

> Sustituye a la sección original "Sistemas Mecatrónicos". Pasa al final y cambia de nombre porque, en esta estructura, su papel no es estudiar los subsistemas por separado (eso lo hacen 02 a 06), sino **unirlos y demostrar que funcionan juntos**. Coincide con la asignatura Integración de Sistemas Mecatrónicos (TMC-304).

## Función
- **Ensamblar** los subsistemas mecánico, eléctrico, de sensores y actuadores, y de software.
- Gestionar las **interfaces** entre secciones: ¿la placa cabe en el chasis?, ¿la batería soporta el pico de corriente con todos los motores?, ¿el código responde a tiempo con todo conectado?
- Hacer **pruebas de integración**, de forma incremental: subsistema por subsistema, no todo de golpe.
- **Verificar** cada requerimiento de 01 con una prueba y una medición.
- Llevar el **registro de fallas** con su causa raíz y la sección responsable.

## Importancia
La mecatrónica es, por definición, **sinergia**: el sistema completo hace algo que ninguna de sus partes hace por separado. También aparecen problemas que no existían por separado, como el ruido eléctrico de los motores que afecta a los sensores, las vibraciones que aflojan conexiones o las caídas de tensión cuando todo funciona a la vez. Esta sección encuentra esos problemas y los devuelve a la sección que debe resolverlos.

## Flujo de retroalimentación
Cuando una prueba falla, se registra la falla, se identifica la **causa raíz** y se devuelve el problema a la sección responsable (02, 03, 04, 05, 06 o incluso 01, si el requerimiento estaba mal definido). La corrección no se "parcha" en 07.

## Contenido
Una carpeta por proyecto (`MP-XXX_Nombre-Corto/`) con:
- `plan_de_pruebas.md` — qué se prueba, cómo y con qué criterio.
- `matriz_de_verificacion.md` — requerimiento, prueba, resultado medido y si cumple.
- `registro_de_fallas.md` — fecha, síntoma, causa raíz, sección responsable y solución.
- `evidencias/` — fotos, videos y datos de las pruebas.

## Entradas y salidas
- **Recibe:** los subsistemas terminados de 02 a 06 y los requerimientos de 01.
- **Entrega a 08:** el sistema verificado, con resultados medidos.
- **Devuelve a 01–06:** las fallas que hay que corregir.

## Criterio de salida
- [ ] Cada requerimiento tiene una prueba con resultado medido.
- [ ] Todos los requerimientos críticos se cumplen, o los incumplimientos están justificados.
- [ ] El sistema funcionó varias veces seguidas, no solo una.
- [ ] No quedan fallas abiertas sin registrar.

## Relación con el pensum del ITLA
Integración de Sistemas Mecatrónicos (TMC-304) · Robótica (TMC-306) · Proyecto Final (CBG-301)

## Errores a evitar
- Conectar todo a la vez y probar al final: si falla, no se sabe qué fue.
- Declarar "funciona" sin datos: una demostración que salió bien una vez no es una verificación.
- Corregir fallas sin anotarlas, y repetirlas en el proyecto siguiente.
