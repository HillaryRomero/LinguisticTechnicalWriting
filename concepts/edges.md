# Edges (Aristas) y relaciones

## Definición

El **edge** es un elemento que crea un vínculo entre los vértices y properties del knowledge. Un edge describe la relación semántica que existe entre dos vertices del knowledge o también la relación semántica entre un vértice y una property. La estructura de la [ontology](ontology.md) es dada a partir de las relaciones establecidas por los **edges**.

Este elemento tiene una semejanza funcional con los verbos, las conjunciones o las preposiciones en el lenguaje natural, ya que estos unen unos elementos a otros a través de relaciones semánticas.

Conceptos relacionados: [vertices](vertices.md), [properties](properties.md), [variables](variables.md), [knowledge y ontology](ontology.md).

## Formato general

En la fila 2 del sheet **edge** se ubican los nombres de Todos los edges utilizados en la ontology. Cada fila se corresponde con un **edge**. Su estructura es la siguiente:

|  Campo  |  Descripción  | Obligatoriedad |
| ------- | ------------- | -------------- |
| __name__    | Esta columna se llena con el nombre o enunciado del edge, que puede ser una cadena de caracteres (letras, números, underscore, etc.).| Obligatorio |
| __multiplicity__ | Esta columna determina si el enlace podrá unirse a varias entidades (ONE2MANY) o si solo se puede unir a una sola entidad (ONE2ONE), sea una property o un vertex. | Obligatorio |

## Ejemplo

|      name       | multiplicity |
| --------------- | ------------ |
|  sell_several   |   ONE2MANY   |
|      is_one     |   ONE2ONE    |
|      of_one     |   ONE2ONE    |
|     has_one     |   ONE2ONE    |
| sell_in_several |   ONE2MANY   |
|   has_several   |   ONE2MANY   |
|  send_several   |   ONE2MANY   |
| send_in_several |   ONE2MANY   |
