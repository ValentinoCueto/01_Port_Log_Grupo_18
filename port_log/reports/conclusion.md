# Conclusión - Sprint 1

## Calidad del dataset heredado

De los 1500 registros originales quedaron 447 infracciones.
Se descartaron 313 registros (20.9%)
por errores de calidad (nulos en columnas críticas y outliers) y
740 (49.3%) porque no eran
infracciones de velocidad.

Los errores más frecuentes fueron fechas y horas en distintos formatos o con
valores imposibles (por ejemplo 32/13/2021 o 26:42:00), matrículas y muelles
con símbolos y mayúsculas/minúsculas mezcladas, y valores nulos o fuera de
rango en tonelaje y velocidad.

## Patrones de infracción

- Turnos: el turno con más infracciones es Tarde
  (124).
- Muelles: la cantidad de infracciones es pareja entre muelles. El de mayor
  exceso promedio es MUELLED (3.22 nudos).
- Tipo de carga: las que más infracciones acumulan son
  TRIGO (69) y
  CONTENEDORES (68).

## Impacto de incorporar los datos sin limpieza

Si se cargaran los datos sin limpiar, el nuevo sistema tendría fechas y horas
imposibles, el mismo buque registrado con distintas matrículas (por ejemplo
"EVER-GLORY" y "ever glory!!") y valores extremos que distorsionarían las
estadísticas. Esto llevaría a tomar decisiones con información incorrecta.

## Propuesta de mejora

Validar los datos al momento de cargarlos: fechas con calendario, horas en
formato de 24hs, matrículas y muelles elegidos desde una lista predefinida, y
campos numéricos obligatorios con rangos permitidos.
