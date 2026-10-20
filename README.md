# Port Log - Sprint 3

## Objetivo

Aplicar conocimientos de bases de datos relacionales (SQLAlchemy), versionado
de datos (DVC) y busqueda por similitud visual (ChromaDB) para profesionalizar
el sistema portuario.

## Introduccion y contexto

El sistema ha crecido en volumen y complejidad. El equipo de desarrollo
portuario necesita:

1. **Persistencia estructurada**: pasar de CSVs a una base de datos
   relacional con ORM.
2. **Auditoria de cambios**: poder rastrear que version del dataset se uso en
   cada analisis.
3. **Identificacion visual de buques**: dado que el OCR no siempre funciona
   bien, el sistema debe poder identificar un buque por similitud visual de
   su imagen, sin depender del texto.

## Versionado de datos

Los archivos binarios y el dataset procesado final se versionan con DVC,
usando un bucket de Supabase como almacenamiento S3. Para descargarlos:
`dvc pull -r publico`.

## Estructura del proyecto

```
port_log
├── data
│   ├── interim
│   │   ├── imgs    (imagenes preprocesadas del Sprint 2)
│   │   └── plots   (graficos del Sprint 1, versionados con DVC)
│   ├── processed   (dataset final, base relacional y base vectorial, con DVC)
│   └── raw
│       └── imgs    (imagenes originales en plates y completes, con DVC)
└── reports         (resumenes y conclusiones)
```
