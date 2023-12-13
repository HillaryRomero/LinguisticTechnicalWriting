# Vertices (Vértices)

## Definición

La información del knowledge es ordenada en clases o núcleos por medio de los **vertices**, estos son elementos centrales del **knowledge** y alrededor de ellos se construyen las relaciones de la [ontology](ontology.md). La estructura interna de los vertices está constituida por subtipos de la clase o núcleo que represente el vertex (véase [instances](instances.md)).

Los **vertices e instances** tienen la función de almacenar información dentro del knowledge del bot a manera de memoria a largo plazo. Esta información será accesible para el bot en sus operaciones con los usuarios (véase [knowledge y ontology](ontology.md)).

Los vertices representan para el sistema núcleos de información del knowledge y la ontology, típicamente estos mantienen un vínculo dependiente con el [entry point](entry_point.md); por ejemplo: productos, servicios, direcciones, etc. Generalmente, los **vertices** tiene la función de alojar la información referente a conceptos del dominio de la empresa o institución.

> **Nota:** El [corpus](corpus.md) de un Mammut package provee pistas de los elementos que formarán parte del knowledge; de esta manera, el desarrollador decide el núcleo de información o vertex que englobará tales elementos.

Conceptos relacionados: [corpus M](corpusM.md), [edges](edges.md), [property](properties.md), [instance](instances.md), [knowledge y ontology](ontology.md), [meta](meta.md), [entry point](entry_point.md).

## Formato general

La sheet del **mammut package** destinado para cualquier otro vertex que no sea el [entry point](entry_point.md) tiene un formato horizontal que dispone las properties en las columnas y las instances en las filas.

La información almacenada en los sheets de los vertices particulares se refiere a los conceptos del dominio de la empresa. Las properties del vertex son elegidas arbitrariamente por quién desarrolla el knowledge del bot (para saber más véase [property](properties.md)).

> **Nota:** La única property obligatoria para definir la estructura interna de los vertices es el **id**.

## Ejemplo

| id  | hidden |      name       |  description  |  price      |
| --- | ------ | --------------- | ------------- | ----------- |
| V_1 |        | varita de cedro | objeto mágico | 40 galeones |
| V_2 |        | varita de olmo  | objeto mágico | 45 galeones |
| V_3 |        | varita de sauco | objeto mágico | 50 galeones |

## Tipos de vertex según la presencia de datos

Las properties pueden ser diseñadas para alojar lo que el bot sabe o para alojar lo que el bot quiere saber. Según sea el caso, los vertices tendrán dos modalidades: **source vertex** o **sink vertex** (véase[**sink**](sink.md)).

> **Nota**: Esto es definido en la columna "sink" del sheet vertices de la [ontology](ontology.md) individualmente para cada property del vertex.

### Source vertex

Un source vertex es uno cuyas properties definidas son del tipo **source**, por lo tanto, el developer las debe llenar con datos.

### Sink vertex

Un sink vertex es uno cuyas properties son definidas para atrapar información en la conversación; por lo tanto, el developer no tendrá que llenarlas con datos. En un vertex de este tipo pueden coexistir properties **sink** con properties **source**.

> **Nota:** en un **sink vertex** que tenga todas sus properties tipo **sink** el único dato autogenerado será el **id** de la instancia. Este dato será generado del nombre del vertex más un número consecutivo.

## Sheet "vertices"

Todos los elementos (properties y edges) que formen parte de cada vértice, se declaran de forma vertical en un sheet llamado **vertices**. (véase [ontology](ontology.md))

|  Campo  |  Descripción  | 
| ------- | ------------- | 
| __name__ | Campo para agregar el nombre del vertex (entry point u otro) | 
| __element_type__ | Campo para especificar el tipo del elemento que se añade en esa fila: PROPERTY o EDGE. | 
| __property_predicate__ | En esta columna se añade un edge que plantee la relación semántica entre un vertex y una property definida. Si se está declarando un edge, esta columna queda vacía. | Obligatoria en las **properties**. |
| __element_name__ | Esta columna aloja el nombre de la property o edge que se está añadiendo. | Obligatorio. |
| __edge_head__	| Esta columna contiene el nombre del vertice de llegada cuando se declara un edge que enlaza dos vertices. | Obligatorio en los edges. |
| __optional__ |	Esta columna se llena con una equis "x" en los elementos que se quieran dejar opcionales. | Opcional. |
| __default_property__ | Esta columna se llena con una equis "x" en una sola fila del vertex, ya que solo puede haber un valor por defecto para cada vertex. | Opcional. |
| __entry_point__	| Esta columna se llena con una equis "x" en todos los elementos definidos del vertex que funcione como entry point. En las demás filas se deja en blanco. | Obligatorio en el vertex entry point |
| __reverse_predicate__ | Esta columna se llena con el nombre de un edge que indique la relación semántica inversa del edge declarado en la columna **property_predicate**.| Obligatorio |
| __sink__ | Esta columna se llena con una equis "x" en los elementos que se quieran definir como sink. | Opcional. |

## Ejemplo 

| name | element_type | property_predicate | element_name | edge_head | optional | default_property | entry_point | reverse_predicate | sink |
| ---- | ------------ | ------------------ | ------------ | --------- | -------- | ---------------- | ----------- | ----------------- | ---- |
| store | PROPERTY | has_one | id |  |  |  |  x | of_one |  | 
| store | PROPERTY | has_one | name |  |  |  |  x | of_one |  | 
| store | PROPERTY | has_one | description |  |  |  |  x | of_one |  | 
| store | PROPERTY | has_one | opening_hours |  |  |  |  x | of_one |  | 
| store | PROPERTY | has_one | contact |  |  |  |  x | of_one |  | 
| store | EDGE |  | sell_several | wand |  |  |  x | of_one |  | 
| wand | PROPERTY | has_one | id |  |  |  |  x | of_one |  | 
| wand | PROPERTY | has_one | name |  |  |  |  x | of_one |  | 
| wand | PROPERTY | has_one | description |  |  |  |  x | of_one |  | 