# MP Corporation
*Mechatronic Projects Corporation — nombre provisional*

> Laboratorio personal para aprender, diseñar, construir, probar y documentar proyectos mecatrónicos.

---

## 1. Qué es (y qué no es todavía)

En esta etapa, MP Corporation es un **laboratorio personal de aprendizaje**: un sistema ordenado para desarrollar proyectos mecatrónicos, empezando por los básicos y avanzando a los intermedios.

**Todavía no es una empresa.** La misión, la visión, los valores, la estructura legal y el modelo de negocio se definirán más adelante, cuando haya un portafolio de proyectos terminados que lo justifique.

**Principio rector:** *aprender construyendo, y documentar todo lo que se construye.*

---

## 2. Arquitectura: 9 secciones

| N.º | Carpeta | Función en una línea |
|----|---------|----------------------|
| 00 | `00_Gestion_Planificacion_y_Recursos` | Dirige y coordina: registro de proyectos, plantillas, inventario, seguridad y hoja de ruta. |
| 01 | `01_Fase_Preliminar` | Convierte una idea en un proyecto viable: investigación, fuentes, requerimientos y lista de materiales. |
| 02 | `02_Mecanica_y_Diseno_CAD` | Estructura, mecanismos, transmisión, cálculos de carga, planos y fabricación. |
| 03 | `03_Electricidad_y_Electronica` | Alimentación, esquemáticos, circuitos, etapas de potencia y protección. |
| 04 | `04_Sensores_Actuadores_e_Instrumentacion` | Selección, caracterización y calibración de sensores y actuadores. |
| 05 | `05_Computacion_y_Programacion` | Firmware, scripts de análisis de datos y control de versiones. |
| 06 | `06_Sistemas_de_Control` | Modelado, control on-off y PID, sintonización y análisis de respuesta. |
| 07 | `07_Integracion_de_Sistemas_Mecatronicos` | Ensamblaje del sistema completo, pruebas y verificación de requerimientos. |
| 08 | `08_Portafolio_y_Lecciones_Aprendidas` | Documentación final, evidencias (fotos y video) y lecciones aprendidas. |

### Cambios respecto a la propuesta original de 7 secciones

| Original | Ahora | Motivo |
|----------|-------|--------|
| 1. Planificación, estructura e implementación | **00** Gestión, Planificación y Recursos | Se le añade la gestión de recursos (inventario y seguridad). La "implementación" pasa a 07, porque ejecutar no es lo mismo que planificar. |
| 7. Fase preliminar | **01** Fase Preliminar | Pasa al principio porque es el primer paso de todo proyecto y alimenta a todas las demás secciones. |
| 5. Mecánica | **02** Mecánica y Diseño CAD | El CAD y la fabricación se declaran de forma explícita. |
| 4. Electrónica y electricidad | **03** Electricidad y Electrónica | Sin cambios de fondo. |
| — | **04** Sensores, Actuadores e Instrumentación | **Nueva.** Es la frontera entre el mundo físico y el digital. Sin ella, un motor o un sensor quedaría a medio camino entre Mecánica y Electrónica. |
| 3. Computación y programación | **05** Computación y Programación | Sin cambios de fondo. |
| 6. Sistemas de Control | **06** Sistemas de Control | Sin cambios. |
| 2. Sistemas Mecatrónicos | **07** Integración de Sistemas Mecatrónicos | Pasa al final, porque solo se integra cuando los subsistemas existen. Incluye las pruebas y la validación. |
| — | **08** Portafolio y Lecciones Aprendidas | **Nueva.** Lo que no está documentado no se puede demostrar ante universidades, becas, empleadores o futuros clientes. |

---

## 3. Cómo funcionan juntas

La organización funciona como un programa modular:

- **00** es el `main`: coordina, pero no hace el trabajo técnico.
- **01** es la entrada de datos: define qué se va a construir.
- **02 a 06** son módulos especializados que trabajan en paralelo.
- **07** es el ensamblador: une los módulos y prueba que funcionen juntos.
- **08** es la salida: el resultado documentado.
- El **ID del proyecto** (`MP-001`, `MP-002`…) es la "variable" que viaja entre módulos y los conecta.

```
                 00 Gestión (supervisa y registra todo)
                               │
 01 Fase Preliminar ──┬──► 02 Mecánica ──────────┐
                      ├──► 03 Electrónica ───────┤
                      ├──► 04 Sensores/Actuad. ──┼──► 07 Integración ──► 08 Portafolio
                      ├──► 05 Programación ──────┤          │
                      └──► 06 Control ───────────┘          │
                      ▲                                     │
                      └──── retroalimentación: una falla ───┘
                            vuelve a la sección responsable
```

Las secciones 02 a 06 no siempre intervienen todas: un proyecto básico puede usar solo 03 y 05. La ficha del proyecto indica cuáles participan.

---

## 4. Ciclo de vida de un proyecto

| Estado | Significado | Para avanzar se necesita |
|--------|-------------|--------------------------|
| Idea | Registrada en el banco de ideas (01) | Una descripción breve y al menos una fuente |
| Investigación | En análisis en 01 | Requerimientos medibles, diagrama de bloques y lista de materiales |
| Diseño | En 02–06, antes de construir | Esquemático, cálculos y plano o boceto revisados |
| Construcción | Subsistemas en fabricación o programación | Cada subsistema probado por separado |
| Pruebas | Integrado y en verificación (07) | Requerimientos verificados con mediciones |
| Completado | Documentado en 08 | Ficha final, evidencias y lecciones aprendidas |
| Pausado / Descartado | Detenido, con el motivo registrado | — |

**Regla clave:** no se construye nada sin diseño, ni se integra nada sin haber probado cada parte por separado. Así es más fácil encontrar las fallas.

---

## 5. Convenciones

- **ID de proyecto:** `MP-001`, `MP-002`… Es único y nunca se reutiliza, aunque el proyecto se descarte.
- **Carpetas de proyecto:** dentro de cada sección que participe, se crea una carpeta `MP-001_Nombre-Corto/`.
- **Nombres de archivo:** `MP-001_descripcion_v01.ext`. Nunca se sobrescribe una versión que funcionó; se crea `v02`.
- **Sin tildes, sin ñ y sin espacios** en carpetas y archivos, para evitar problemas con Arduino IDE, Git, Python y los programas CAD.
- **Fechas** en formato ISO: `AAAA-MM-DD`.
- **Fuente única de verdad:** el estado oficial de cada proyecto está en `00_.../REGISTRO_de_Proyectos.md`.

---

## 6. Uso junto con Claude

Esta carpeta se acompaña del Proyecto **"MP Corporation"** en Claude.

- Abrir un chat por sección y por proyecto, con un título que lleve prefijo. Por ejemplo: `[03] MP-003 Puente H` o `[01] Banco de ideas`.
- Al iniciar un chat, indicar la sección y el ID del proyecto.
- Los resultados importantes de cada chat se guardan en la carpeta de la sección correspondiente.

---

## 7. Estado

- **Creado:** 2026-11-20
- **Fase actual:** estructuración
- **Siguiente paso:** elegir el primer proyecto del banco (`01_Fase_Preliminar/BANCO_de_Proyectos.md`) y abrir su ficha a partir de la plantilla de 00.
