# Instances del conocimiento

## Definición

El knowledge del bot se ordena en nociones generales (vertices) que engloban conceptos específicos (instances). Las **instances** son unidades de información específica que forman parte de un núcleo de información o [vertex](vertices.md). En este sentido, las instances funcionan como subtipos de una noción general. Por ejemplo, si el vertex refiere a la noción **producto**, entonces las instances representarán los conceptos que puedan formar parte de la categoría 'producto' en el knowledge.

Un vertex puede contener diferentes instances; estas instances cumplen con las [properties](properties.md) que el programador decide que definan al **vertex**. Además, estas instances se diferencian entre sí dado que poseen diferentes valores en las properties. Por ejemplo, el vertex **producto** tiene tres properties, **id**, **name** y **price**, todas las instances tendrán estas properties pero con diferente valor.  

Conceptos relacionados: [vertices](vertices.md), [properties](properties.md), [knowledge y ontology](ontology.md).

## Formato general

### Instances en el entry point

El formato de las instances depende del **vertex** del que forman parte. Las instances en el sheet del **entry point** refieren a información sobre la empresa o empresas que formarán parte del knowledge del bot. Cada instance representará una institución diferente con datos particulares en las properties.

Las instances en el entry point se dispondrán en columnas diferentes, son constituidas por distintos valores para cada fila de properties. Las instances se incluyen a partir de la columna B, mientras que las properties se añadirán en la columna A.

> **Nota:** la única property obligatoria para cada instance es el **id**.

#### Ejemplo

| A             | **B**                          |
| ------------- | ------------------------------ |
| id            | **JS_1**                       |
| name          | **Jollivander Shop**           |
| description   | **Tienda para magos y brujos** |
| opening_hours | **Mo-Su 11:00-18:00**          |
| contact       | **Jollivandershop@hedwid.com** |
| especialidad  | **varitas y calderos mágicos** |

### Instances en los vertices particulares

En un vertex distinto al entry point, las instances refieren a información referente a conceptos del dominio de la empresa, por ejemplo: tipos de productos, tipos de servicios, diferentes direcciones, etc; cada uno de estos tipos representará una **instance** diferente con datos particulares en las properties.

Las instances en la sheet de cualquier vertex distinto al entry point se dispondrán en filas diferentes y son constituidas por distintos valores para cada columna de properties. Estas se incluyen a partir de la fila 3, mientras que las properties se añadirán en la fila 2.

> **Nota:** la única property obligatoria para cada instancia es el **id**.

#### Ejemplo

| id  | hidden |     name        | description   |   price     |
| --- | ------ | --------------- | ------------- | ----------- |
| V_1 |        | varita de cedro | objeto mágico | 40 galeones |
| V_2 |        | varita de olmo  | objeto mágico | 45 galeones |
| V_3 |        | varita de sauco | objeto mágico | 50 galeones |
