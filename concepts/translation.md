# Translations

## Definición

Las **knowledge translations** (o simplemente "translations") permiten la expresión de un dato en un idioma que ha sido escrito originalmente en otro. Esta es una herramienta que permite traducir las [instances](instances.md) del **knowledge** de un bot, lo cual hace posible preparar al bot para que pueda comunicarse en diferentes idiomas utilizando una única ontology. 

> **Nota:** las **translations** facilitan la preparación de un bot en varios idiomas usando una sheet de un package de Mammut.

Las translations permiten traducir unicamente los datos del knowledge que requieran ser traducidos, es decir, toda la información que varíe de un idioma a otro y que, por lo tanto, deba estar disponible en las diferentes lenguas habladas por los usuarios del bot. En el caso de que un bot preparado con un corpus multilingüe tenga instances del knowledge que no requieran traducción (como nombres propios, números, cifras o símbolos), estas se enviarán a los usuarios en el idioma original del knowledge.

Conceptos relacionados: [knowledge](ontology.md), [vertex](vertices.md), [instance](instances.md), [property](properties.md).

## Formato general

Las translations se guardan en una sheet de un package de Mammut. Cada fila de la sheet **translations** corresponde a la traducción de un dato de una instance determinada.

La estructura de esta sheet es la siguiente:

| Campo | Descripción | Obligatoriedad |
| ----  | ----------  | -------------- |
| __vertex_name__ | Columna en la que se escribe el nombre de la sheet que contiene el vertex a traducir. | Obligatorio. |
| __vertex_id__ | Columna en la que se escribe el id de la instance a traducir. | Obligatorio. |
| __property__ | Columna en la que se escribe el nombre de la property a traducir, para una instance determinada. | Obligatorio. |
| __language__ | Idioma de la traducción, siguiendo la convención ISO 639-1 (**en** para inglés y **es** para español). | Obligatorio. |
| __translation__ | Columna que contiene la traducción de los diferentes valores de cada instance del knowledge. | Obligatorio. |

## Ejemplos

1. Vertex en el knowledge:

    | id | JS_1 |
    | ---- | ---- |
    | name | Jollivander Shop
    | description | Tienda para magos y brujos
    | opening_hours | Mo-Su 11:00-18:00
    | contact | Jollivandershop@hedwid.com
    | especialidad | varitas y calderos mágicos
    | sell_several | varita
    | send_several | caldero

2. Traducción de algunas instances en el **translations**:

    | vertex_name | vertex_id | property | language | translation |
    | ---- | ---- | ---- | ---- | ---- |
    | tienda | JS_1 | description | en | Shop for wizards and sorcerers |
    | tienda | JS_1 | especialidad | en | magic wands and cauldrons |

