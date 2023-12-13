# Package verification

## Verificación en la validación

Antes de empezar la preparación de tu chatbot deberías verificar las siguientes cosas:

| Sheet name | Verificación |
| ---------- | ------------ |
| corpus, corpus extension | Revisar que no haya ningún evento en el que esté vacío el campo **regional setting**. |
| corpus, corpus extension | Revisar que no haya ningún evento en el que esté vacío el campo **source**. |
| corpus, corpus extension | Revisar que no haya ninguna fila en blanco en medio de filas con datos. |
| corpus map | Revisar que los nombres dispuestos en el **corpus_map** correspondan a los nombres de los sheets. Estos deben ser identificos. |

Evita en tu package:

* Emojis.
* Dejar espacios entre las palabras que componen los nombres de los sheets o elemetos. Por ejemplo, poner “corpus Restaurant”, en vez de “corpus_restaurant” o poner "product description" en vez de "product_description".
* Usar el guión para separar palabras en los nombres de los sheets, debes usar underscore.

> **Nota**: Muchos de los problemas más comunes suceden por causa de error de tipeo en las definiciones de los elementos o en su uso. Por lo cual se recomienda ir definiendo en la ontología (es decir, ontology_vertex, ontology_edge y ontology_properties) los elementos que se vayan agregando al conocimiento en cada vértice (propiedades y edges).

## Verificación en el entrenamiento

### Leyenda de términos que aparecen en el notebook

A continuación presentamos una leyenda con porciones de los mensajes de error que arroja el compilador cuando la compilación no se ha logrado con éxito. Por medio de esta clasificación podemos identificar qué tipo de error está interrumpiendo la compilación.

 vertex_name | Nombre del vértice | |   
-|-|-
'vertex_id' | Id de una Instancia | |
Sufijo… 'ontology_edge' | edge | Esto aparece al final de una cadena de caracteres que es el nombre de un edge.
sufijo…’ontology_property’| propiedad | Esto aparece al final de una cadena de caracteres que es el nombre de una propiedad.
sufijo…’ontology_vertex’ | vértice | Esto aparece al final de una cadena de caracteres que es el nombre de un vértice.
'transverse'. | path |
Not found: value |  Datos no encontrados en el conocimiento. | 
Not found: type |  Datos no encontrados en la ontología. | 'base closure'