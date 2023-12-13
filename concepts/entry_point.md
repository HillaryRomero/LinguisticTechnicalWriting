# Entry point (Punto de entrada)

## Definición

El **entry point** es un [vertex](vertices.md) que representa para el sistema el punto de inicio de la **ontology** y el **knowledge**; los demás vertices están relacionados con él jerárquicamente. Generalmente, el entrypoint tiene la función de alojar la información referente a la empresa o institución de las cuales el bot tiene dominio. Las instances del entry point contendrán datos particulares sobre dicha empresa o institución.

Conceptos relacionados: [corpus M](corpusM.md), [edges](edges.md), [property](properties.md), [instance](instances.md), [knowledge y ontology](ontology.md), [meta](meta.md), [entry point](entry_point.md).

## Formato general

El entry point es una sheet del **mammut package** que posee un formato vertical. En este sheet se disponen, a partir de la fila 2, las properties en la columna A y las instances en la columna B.

Las properties del entry point se refieren a la empresa, por ejemplo su nombre, contacto, email, ubicación u horario.

En el entry point también se incluirán los nombres de los vertices que estan relacionados con el entry point (columna B), así como el nombre del edge correspondiente (columna A) (para saber mas véase [edges](edges.md)).

> **Nota:** La única property obligatoria para definir la estructura interna de los vertices es el **id**.

## Ejemplo

| A             | B                          |
| ------------- | -------------------------- |
| id            | JS_1                       |
| name          | Jollivander Shop           |
| description   | Tienda para magos y brujos |
| opening_hours | Mo-Su 11:00-18:00          |
| contact       | Jollivandershop@hedwid.com |
| especialidad  | varitas y calderos mágicos |
| sell_several  | varita                     |
| send_several  | caldero                    |
