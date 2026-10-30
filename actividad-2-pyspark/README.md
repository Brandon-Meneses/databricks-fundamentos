# Actividad 2 · PySpark con `samples.tpch`

Seis preguntas de negocio resueltas con la API de DataFrames de PySpark sobre las tablas `orders`, `customer` y `nation` del catálogo de ejemplo `samples.tpch`.

## Preguntas

| # | Pregunta | Técnicas |
|---|---|---|
| 1 | Pedidos y monto total por estado | `groupBy`, `count`, `sum` |
| 2 | Pedidos y monto total por año | `withColumn`, `F.year`, `groupBy`, `orderBy` |
| 3 | Pedidos finalizados con monto mayor a 100 000 | `filter` con `&`, `agg(F.count)` |
| 4 | Clientes por segmento de mercado | `groupBy`, `count`, `F.desc` |
| 5 | Top 5 países con más clientes | `join` con `nation`, `groupBy`, `limit` |
| 6 | Ticket promedio por segmento | `join` con `customer`, `F.avg`, `F.round` |

## Relaciones entre tablas

- `orders.o_custkey` → `customer.c_custkey`
- `customer.c_nationkey` → `nation.n_nationkey`

## Archivos

- Notebook con las soluciones (`.ipynb`).
- PDF con el enunciado, el código y la captura del resultado de cada ejercicio.

## Cómo ejecutarlo

Importar el notebook en Databricks Free Edition, conectarlo al cómputo serverless y ejecutar las celdas en orden. `samples.tpch` ya viene disponible en el workspace.
