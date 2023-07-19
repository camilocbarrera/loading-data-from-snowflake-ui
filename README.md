# ¿Cómo cargar datos desde Snowflake UI?

Este tutorial tiene como objetivo demostrar de manera gráfica cómo cargar datos utilizando la nueva interfaz de Snowflake a través de diferentes formatos, como CSV.



## Tutorial de carga de datos en Snowflake

[![Tutorial de carga de datos en Snowflake](https://www.youtube.com/watch?v=ID_DEL_VIDEO)](https://www.youtube.com/watch?v=ID_DEL_VIDEO)


## Muestra de archivos CSV

## Creación de Objetos
```sql
-- creación de base de datos
CREATE OR REPLACE DATABASE analytics;

-- creación de warehouse
CREATE OR REPLACE SCHEMA analytics.warehouse;


-- table definition fct_tasks
CREATE OR REPLACE TABLE fct_tasks
(
     parent                    VARCHAR,
     task_id                   VARCHAR,
     parent_task_id            VARCHAR,
     is_parent                 BOOLEAN,
     depth                     VARCHAR(9),
     _equipo_id                NUMBER,
     user_assignes_initials    VARCHAR,
     date_closed               TIMESTAMPNTZ,
     date_done                 TIMESTAMPNTZ,
     date_created              TIMESTAMPNTZ,
     date_updated              TIMESTAMPNTZ,
     archived                  BOOLEAN,
     folder                    VARIANT,
     product_id                VARCHAR(32),
     folder_name               VARCHAR,
     time_estimate             NUMBER,
     time_spent_in_miliseconds NUMBER
);


-- table definition dim_equipos
CREATE OR REPLACE TABLE dim_equipos
(
     _equipo_id    NUMBER,
     nombre_equipo VARCHAR(15)
);

-- table definition dim_prodcuts
CREATE OR REPLACE TABLE dim_prodcuts
(
     product_id   VARCHAR(32),
     product_name VARCHAR
);


-- table definition type_config
CREATE OR REPLACE TABLE type_config
(
     id          VARCHAR(32),
     type_config VARIANT
);

```