## Nombre
lm.patch_corearea --  Devuelve el área interior del polígono que está más allá de la profundidad especificada del borde del perímetro del polígono, dividido por 10.000 (unidades: Hectáreas).

## Synopsis

```sql
float p_corearea(geometry geom);

geometry p_corearea(geometry geom, float radius_buffer);
```

```tex
\[CORE= a_{ij}^{c}\left ( \frac{1}{10.000} \right )\]
```

## Descripción

Esta fórmula también se puede calcular en formato ráster.

Descripción más elaborada, con ejemplos de uso en la literatura científica. ¿En qué casos ha sido útil (significaba algo)?


## Ejemplos (autocontenidos)


```sql
WITH  patches (geom,categ) AS (VALUES
                               (ST_GeomFromText('POLYGON((0 0,0 1,1 1,1 0,0 0))',25830),'Urbano'))

SELECT lm.p_corearea(geom) As p_corearea FROM patches;
```

## Referencias

1. Mcgarigal, K. (2015). Fragstats.Help.4.2, (April), 1–182. [https://www.umass.edu/landeco/research/fragstats/documents/fragstats.help.4.2.pdf](https://www.umass.edu/landeco/research/fragstats/documents/fragstats.help.4.2.pdf)
