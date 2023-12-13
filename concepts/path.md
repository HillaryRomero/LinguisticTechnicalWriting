# Rutas

## Definición

Un **path** indica un transverse en el knowledge que un bot sigue para buscar una información determinada. El path se construye con todos los [vertices](vertices.md) y [edges](edges.md) por los que el bot debe pasar para encontrar una [property](properties.md). El path está limitado a la estructura de la **ontology**.

Conceptos relacionados: [variable](variables.md), [knowledge](ontology.md), [ontology](ontology.md), [vertex](vertices.md), [edge](edges.md), [property](properties.md).

## Formato general

Un path siempre empieza desde el vertex [entry point](entry_point.md) y sigue un camino de la ontology hasta el vertex donde se encuentra la información a la que se está haciendo referencia. Para escribirlo, se debe separar sus componentes por medio de puntos ".", agregando los vertices y edges uno a uno. El path termina la property del **knowledge** que se esté refiriendo.

Los paths suelen tener el siguiente formato: `vertice.edge.vertice.edge.(...)vertice.property`.

> **Nota:** si un path no termina en una property, se asumirá que la property a la que está refiriendo es aquella que ha sido marcada como "default" en el sheet de vertices (véase [ontology](ontology.md)).

## Ejemplo

`tienda.sell_several.varita.name`

> **Nota:** en este ejemplo, el punto de entrada es **tienda**; seguidamente se encuentra el edge **sell_several** que lo une con otro vertex, **varita**. Por último, se incluye la property **name** que denota el lugar específico al cual debe llegar el bot para encontrar la información.
