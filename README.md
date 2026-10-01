# Port Log - Sprint 2

## Objetivo

Aplicar conocimientos de tratamiento de imagenes y programacion limpia sobre el
contexto del sistema portuario.

## Introduccion y contexto

Los radares ubicados en los accesos a los muelles capturan evidencia
fotografica de las infracciones de velocidad. Las camaras asociadas toman
fotografias de la zona de proa donde esta pintada la matricula del buque. En
algunos casos el sistema recorta automaticamente la zona de matricula
(`plates`); en otros, entrega la imagen completa (`completes`).

El sistema presenta las siguientes limitaciones:

- No todas las infracciones tienen imagen asociada.
- No todas las imagenes corresponden a una infraccion real (falsos positivos
  del radar).
- Puede haber errores de deteccion optica: imagenes borrosas, nocturnas o
  tomadas a gran distancia.

El objetivo del sprint es responder: **que infracciones tienen evidencia visual
valida?**

## Estructura del proyecto

```
port_log
├── data
│   ├── interim
│   │   ├── imgs    (imagenes preprocesadas: gris, ecualizada, blur y canny)
│   │   └── plots   (graficos exportados en el Sprint 1)
│   ├── processed   (dataset de infracciones con evidencia visual)
│   └── raw
│       └── imgs    (imagenes originales de los radares)
└── reports         (resumenes y conclusiones de cada sprint)
```
