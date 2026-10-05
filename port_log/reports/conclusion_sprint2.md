# Conclusión - Sprint 2

## Infracciones validadas visualmente

De las 447 infracciones, 431
(96.4%) tienen una imagen cuya matrícula
coincide con la del registro. De las 100 imágenes,
3 no coincidieron con ninguna matrícula del dataset.

## Grupo más útil para el OCR

El grupo 'plates' tuvo la mayor tasa de match
(100.00%). En los recortes la matrícula ocupa
casi toda la imagen, mientras que en las imágenes completas es chica y está
rodeada de fondo oscuro con ruido que dificulta la lectura.

## Condiciones de captura

La condición que más afectó el matching fue la captura nocturna:
85.19% de match en la primera lectura, contra
97.73% en imágenes sin condiciones
adversas. El reintento sobre las imágenes preprocesadas recuperó la mayoría
de esos casos. Las 3 imágenes que siguieron sin match
son capturas amplias ('completes'), con poco contraste entre la matrícula y
el fondo, y en su mayoría borrosas.

## Mejoras propuestas

En la captura: iluminación infrarroja para las tomas nocturnas, cámaras más
rápidas para evitar imágenes movidas, y recorte automático de la matrícula.

En el algoritmo: recortar la zona de la matrícula antes del OCR, corregir
caracteres que el OCR confunde (0/O, 1/I, 4/A) y comparar las matrículas
de forma que un carácter de más no desplace todo el resto.
