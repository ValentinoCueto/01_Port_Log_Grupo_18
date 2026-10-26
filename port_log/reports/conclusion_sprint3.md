# Conclusión integradora - Port Log

## Problema que resuelve el sistema

El sistema toma el registro heredado de movimientos del puerto, con errores
de carga, y lo convierte en información confiable y consultable. En el
Sprint 1 se limpiaron los datos y se detectaron 447
infracciones de velocidad. En el Sprint 2 se analizaron las fotos de los
radares mediante OCR: el 96.42% de los movimientos
tiene una imagen asociada. En el Sprint 3 los datos pasaron a una base
relacional, se versionaron con DVC y se agregó la identificación de buques
por imagen.

## Ventaja de la base vectorial frente al OCR

El OCR depende de leer cada carácter: un 0 en lugar de una O o un guion
leído incorrectamente pueden hacer que el matching falle. La base vectorial
compara la imagen completa por similitud, sin pasar por el texto, por lo
que puede identificar buques aun cuando la matrícula no se puede leer.
En la validación, la imagen 0001_complete_patente.jpg se identificó como CMAROSARIO (correcto, distancia 0.3384), sin depender de la lectura de la matrícula.

## Principales limitaciones

- Los datos de origen tienen inconsistencias: el código de buque no
  identifica al buque y algunos movimientos no tienen radar registrado.
- Las imágenes no tienen fecha ni radar, por lo que la asociación con los
  movimientos se realiza a partir del buque identificado, sin garantizar
  una correspondencia temporal exacta.
- Solo 16 de 20 buques tienen imagen
  complete con match (80.00% de cobertura vectorial), y
  cada uno con una sola imagen de referencia.
- Los recortes plate presentan limitaciones como consulta: en esta validación la imagen 0001_plate_patente.jpg se identificó como PILSANTA (correcto, distancia 0.4821), pero la base se construyó con imágenes complete, de composición muy distinta.
- La base relacional es SQLite local, pensada para pruebas.

## Cambios para producción en el Puerto de Rosario

- Usar una base PostgreSQL gestionada en lugar de SQLite, para tener acceso
  concurrente, backups y control de usuarios.
- Que las cámaras guarden fecha, hora y radar en cada foto, para vincular
  cada imagen con su movimiento exacto.
- Tomar las matrículas de un padrón oficial de buques.
- Cargar varias imágenes por buque en la base vectorial, de ambos tipos, y
  definir un umbral de distancia para derivar los casos dudosos a revisión.
- Automatizar la carga diaria del pipeline y etiquetar cada versión de los
  datos con DVC.
