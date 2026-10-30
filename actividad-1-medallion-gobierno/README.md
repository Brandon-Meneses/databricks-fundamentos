# Actividad 1 · Del dato crudo al dato de negocio

Construcción de las capas **Bronze, Silver y Gold** en Unity Catalog con un dataset de 3 201 películas (`movies.json` de vega-datasets), y gobierno de datos sobre ellas.

## Arquitectura

```
internet → volumen (aterrizaje)
              │
   ┌──────────┼───────────────┐
cine_bronze   cine_silver     cine_gold
tal como      limpio, con     agregados para
llegó         contrato        el negocio
```

- **Bronze:** el JSON tal cual llegó, más metadatos de ingesta (`_archivo_origen`, `_ingestado_en`).
- **Silver:** tipos correctos, nombres de negocio, reglas de calidad, tabla de cuarentena y contrato (`NOT NULL`, `CHECK`, clave primaria informativa).
- **Gold:** una tabla por pregunta de negocio.

## Ejercicios resueltos (sección 9)

1. **`peliculas_rentables` (Gold):** top 50 por retorno (taquilla mundial ÷ presupuesto), solo películas con más de 10 000 votos en IMDB. Usa `try_divide`, `WHERE`, `ORDER BY` y `LIMIT`.
2. **Nueva regla de calidad:** rechazar películas sin género **y** sin director (`genero IS NULL AND director IS NULL`). Pasan **162 filas más** a cuarentena: de 18 a 180. Silver baja de 3 183 a 3 021 y la reconciliación sigue cuadrando (180 + 3 021 = 3 201).
3. **Gobierno de la tabla nueva:** `COMMENT` de tabla y columnas, `SET TAGS` y `GRANT SELECT` de lectura.

También se responde la pregunta sin código: quién debe decidir qué hacer con las filas en cuarentena. Es una decisión del dueño del dato, no del equipo técnico.

## Archivos

- Notebook con el desarrollo y las salidas de ejecución (`.ipynb`).
- Documento PDF con las consultas, los resultados y la justificación de cada decisión.

## Conceptos practicados

Medallion, perfilado de datos, funciones `try_*`, cuarentena de filas rechazadas, contratos de datos, `information_schema`, etiquetas, mínimo privilegio y `DESCRIBE HISTORY`.
