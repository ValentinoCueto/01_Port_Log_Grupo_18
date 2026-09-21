[Ejercicio 03]
- Normalizacion de fechas de ingreso/egreso a formato YYYY-MM-DD (invalidas -> 1900-01-01).
- Normalizacion de horas de ingreso/egreso a formato de 24hs (invalidas -> 00:00).
- Calculo de la columna duracion_horas.
- Normalizacion de matriculas y muelles.
- Eliminacion de filas con nulos en columnas criticas (matricula, velocidad_ingreso, tonelaje_declarado).
- Deteccion y eliminacion de outliers en tonelaje_declarado y velocidad_ingreso (metodo IQR).
- Calculo de exceso_velocidad_real y exceso_velocidad (con 5% de tolerancia) y eliminacion de filas sin infraccion.
- Exportacion del dataset limpio a data/interim y del resumen estadistico a reports/summary_sprint1.csv.

[Ejercicio 02]
- Descarga del dataset raw en port_log/data/raw/port_movements.csv.
- Analisis de tipos de datos y de columnas que requieren conversion.
- Conteo de valores nulos y calculo de completitud por columna.

[Ejercicio 01]
- Inicializacion del repositorio sobre la rama Sprint_1.
- Creacion de la estructura de directorios de port_log.
- Alta del README.md con el objetivo y el contexto del sprint.

