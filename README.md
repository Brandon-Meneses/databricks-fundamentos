# Databricks Fundamentos

Actividades prácticas del grupo de estudio **Fundamentos de Databricks** (Blur Consulting), desarrolladas en **Databricks Free Edition** con cómputo serverless.

## Herramientas

- Databricks Free Edition (serverless)
- Unity Catalog (catálogos, esquemas, tablas Delta, volúmenes, etiquetas y permisos)
- SQL y PySpark

## Contenido

| Actividad | Tema | Qué se practica |
|---|---|---|
| [Actividad 1](actividad-1-medallion-gobierno/) | Arquitectura Medallion y gobierno de datos | Capas Bronze, Silver y Gold, reglas de calidad, cuarentena, contrato de datos, comentarios, etiquetas y permisos |
| [Actividad 2](actividad-2-pyspark/) | PySpark sobre `samples.tpch` | `groupBy`, `agg`, `filter`, `join`, `orderBy` y funciones de `pyspark.sql.functions` |

## Estructura

```
databricks-fundamentos/
├── README.md
├── actividad-1-medallion-gobierno/
│   ├── README.md
│   ├── (notebook .ipynb)
│   └── (documentación .pdf)
└── actividad-2-pyspark/
    ├── README.md
    ├── (notebook .ipynb)
    └── (evidencias .pdf)
```

## Cómo reproducir

1. Crear una cuenta en Databricks Free Edition.
2. Importar el notebook de la actividad (*Workspace → Import*).
3. Conectarlo al cómputo serverless y ejecutar las celdas en orden.

> La Actividad 1 incluye una sección final de limpieza que borra los esquemas y el volumen creados. Ejecútala solo al terminar.
