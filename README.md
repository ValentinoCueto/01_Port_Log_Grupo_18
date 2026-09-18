# Port Log - Sprint 1

## Objetivo

Aplicar conocimientos de versionado, organizacion y analisis exploratorio de datos con
pandas sobre un dataset real de operaciones portuarias.

## Introduccion y contexto

El Puerto Fluvial de Rosario es uno de los complejos portuarios mas importantes de
America del Sur y el principal punto de exportacion de granos y derivados de la
Argentina. Diariamente ingresan y egresan decenas de buques de distintas banderas con
cargas de diverso tipo.

El sistema de registro de movimientos portuarios fue migrado recientemente desde un
sistema heredado de los anios '90. Ese sistema acumulo durante decadas inconsistencias
de formato en fechas, matriculas de buques y valores numericos fuera de rango,
generando registros que no pueden incorporarse directamente al nuevo sistema.

Nuestro equipo fue contratado para analizar y depurar los datos del sistema antiguo.

## Estructura del proyecto

```
port_log
├── data
│   ├── interim     (datasets procesados en pasos intermedios)
│   │   └── plots   (graficos exportados)
│   ├── processed   (datasets finales para otra aplicacion)
│   └── raw         (datasets en crudo)
└── reports         (resumenes estadisticos generados)
```
