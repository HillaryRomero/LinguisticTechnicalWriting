# Mammut Markdown

## Definición

**Mammut Markdown** es un lenguaje de marcado que puede usarse en un [package](package.md). Cada **event** de un [corpusM](corpusM.md) es un documento en Mammut Markdown. Esta extensión usa como base las marcas de Markdown y permite añadir en un mismo [event](events.md) la mezcla de información con distintos formatos (énfasis, listas, imágenes, listas jerárquicas, listas no jerárquicas, etc.). Además de estas marcas, añade otras marcas que especifican información adicional sobre la estructura o la forma en que un documento tiene que ser presentado. Por ejemplo, si se esta definiendo una lista de elementos con Mammut Markdown, se puede especificar si la lista va a ser enviada al usuario horizontal o verticalmente.

> **Nota**: Mammut Markdown es una extensión que incide en la presentación de los mensajes que un bot enviará. Con este formato se implementan mejoras en los mensajes que el bot reconoce y genera en una interacción con los usuarios.

Las marcas que se añaden con esta extensión denotan transformaciones de la forma del texto que dependen de la conversación en curso. Mammut markdown facilita las transformaciones a través de una [variable](variables.md), que asume su forma en los mensajes generados o reconocidos desde [knowledge](ontology.md). Estos datos de salida toman su forma dependiendo de la [instance](instances.md) pertinente en la conversación en curso. Mammut Markdown permite crear un events que pueden tomar forma en innumerables mensajes concretos. Los [packages](package.md) que se crean con Mammut Markdown se pueden renderizar de distinta forma según el [channel](channels.md) por donde se comuniquen los usuarios.

Conceptos relacionados: [event](events.md), [corpus M](corpusM.md), [scope](scope.md).



## Tipo de marcas

**Mammut Markdown** permite crear events en los corpusM con los siguientes recursos:

### Texto

Para incluir texto, se debe escribir directamente como se quiere mostrar el ```texto``` sin ninguna marca especial.

**Ejemplo:**

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
| 1 | 1 | Conversation | Hola, Sylvia |  |  |  |  |  | Carla | es |
| 1 | 2 | Conversation | Hola! ¿Cómo puedo ayudarte hoy? |  |  |  |  |  | Mammut | es |

### Dividir un event en varios mensajes

Para dividir un event en varios mensajes, crea párrafos en una misma celda. Usa una o más líneas en blanco para separar un event en varios mensajes.

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
| 2 | 1 | Conversation | Hola, Sylvia |  |  |  |  |  | Carla | es |
| 2 | 2 | Conversation | Hola! |  |  |  |  |  | | |
| | | | | | | | | |
| | | | ¿Cómo puedo ayudarte hoy?|  |  |  |  |  | Mammut | es |

### Énfasis

Para agregar énfasis en un texto puedes poner el texto en **negrita** o _cursiva_. Usa el texto entre dos asteriscos ```**texto**``` para poner el texto en negrita. Usa el texto entre un asterisco ```*texto*``` para poner el texto en cursiva.

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
| 1 | 1 | Conversation | Hola, Sylvia |  |  |  |  |  | Carla | es |
| 1 | 2 | Conversation | _Hola!_ ¿Cómo puedo ayudarte **hoy**? |  |  |  |  |  | Mammut | es |

### Texto desde el knowledge

Para incluir texto desde el knowledge, puedes usar una **variable**. La variable es un elemento que se transforma en datos con formato de texto, imagen, video, o audio. La variable asume su valor dependiendo del scope de cada conversación. Esta sigue la forma ```[variable|vértice.edge.vértice[...].property]``` para describir el lugar del knowledge donde buscará los datos (Véase [variable](variables.md)).

**Ejemplo**

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
2 | 1 | Conversation | ¿Cuál es el precio de [variable\|tienda.sell_several.varita.name] en [variable\|tienda.name]? |  |  |  |  |  | Carla | es |
2 | 2 | Conversation | [variable\|tienda.sell_several.varita.name] cuesta [variable\|tienda.sell_several.varita.price] |  |  |  |  |  | Mammut | es |


### Sintaxis alterna: Imagen desde el knowlegde

Para incluir imágenes que ya sean parte del knowledge, puedes usar una [variable](variables.md). Sin embargo, también se permite agregar una imagen desde el knowledge a través de una sintaxis alterna. Para lograrlo se debe seguir la siguiente forma ```[image|id_del_archivo]```. De esta manera, se describe el lugar donde buscará la imagen (Véase [variable](variables.md)).

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
4 | 1 | Conversation | Muéstrame una imagen de las instalaciones. |  |  |  |  |  | Carla | es |
4 | 2 | Conversation | [image\|1FbcfdFsPCQO-bEwvhLGxMLLo_klpeAVV] |  |  |  |  |  | Mammut | es |


### Botón

Un botón es un elemento en el chat que provoca alguna acción. Para incluir botones, se debe indicar entre doble llaves el id ```{{número}}``` de la acción previamente definida que se quiere añadir al evento.

> **Nota**: Estas acciones se definen en el *variables_sheet* del package.

**Ejemplo**

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
2 | 5 | Conversation | Quiero la [variable\|tienda.sell_several.varita.name]  |  |  |  |  |  | Carla | es |
2 | 6 | Conversation | De inmediato {{2}}  |  |  |  |  |  | Mammut | es |


### Listas

Para incluir listas, se ofrece la opción de definir secciones que componen la lista de mensajes. Se usa el símbolo ```##``` para todos los elementos de la lista enumerada. Y se usa el símbolo ```*``` para todos los elementos de una lista no enumerada.

**Ejemplo**

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
5 | 1 | Conversation | ¿Cuál es el procedimiento para realizar compras? |  |  |  |  |  | Carla | es |
5 | 2 | Conversation | Selecciona el producto que quieras. | |  | | | | Mammut | es |
| | | | ## Envía un mensaje por nuestro _Dobibot_ con el nombre de la varita diciendo que la quieres comprar |  |  |  |  |  |  |  |
| | | | ## Ofrece tu correo electrónico para procesar la compra |  |  |  |  |  |  | |
| | | | ## Completa los datos para completar la compra |  |  |  |  |  |  |  |


### Jerarquía de secciones

Para crear una jerarquía de secciones se usa el símbolo ```#```. En esta **#** es el nivel más alto, **##** el segundo nivel, **###** el tercero, y así sucesivamente. Esto permite crear events complejos que denoten una jerarquía entre los elementos que lo componen.

**Ejemplo**

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
2 | 1 | Conversation | ¿Cuál es el precio de las varitas en [variable\|tienda.name]? |  |  |  |  |  | Carla | es |
2 | 2 | Conversation | # En [variable\|tienda.name] ofrecemos | |  | |  | | Mammut | es |
| | | | ## [variable\|tienda.sell_several.varita.name] cuesta [variable\|tienda.sell_several.varita.price] |  |  |  |  | |  |

> **Nota**: Esta jerarquía puede estar motivada por la [ontology](ontology.md) lo cual permitirá que suman su valor al mismo tiempo desde varios vertices del knowledge.


### Tags de estilos en una lista

Las listas que se construyen en los events pueden ser formateadas con tags de estilos. De esta manera, se identificarán valores esenciales tales como la orientación del mensaje (vertical u horizontal), la presencia o ausencia de un mensaje introductorio y también la posiblidad de resaltar uno de los elementos del event.

> **Nota**: Si la lista no contiene tags de estilos, esta se asumirá como una lista horizontal.

| Tag | Descripción |
| - | - |
| `<SimpleCarrousel>` | Carrusel de uno o mas elementos sin mensaje introductorio |
| `<Carrousel>` | Carrusel de uno o mas elementos con mensaje introductorio |
| `<SimpleLargeList>` | Lista de uno o mas elementos, resaltando el primero de ellos, sin mensaje introductorio |
| `<LargeList>` | Lista de uno o mas elementos, resaltando el primero de ellos, con mensaje introductorio |
| `<SimpleCompactList>` | Lista de uno o mas elementos, sin mensaje introductorio |
| `<CompactList>` | Lista de uno o mas elementos, con mensaje introductorio |

**Ejemplo**

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
2 | 1 | Conversation | ¿Cuál es el precio de las varitas en [variable\|tienda.name]? |  |  |  |  |  | Carla | es |
2 | 2 | Conversation | \<Carrousel> | |  | |  | | Mammut | es |
| |  |  | # En [variable\|tienda.name] ofrecemos | |  | |  | |  |  |
| | | | ## [variable\|tienda.sell_several.varita.name] cuesta [variable\|tienda.sell_several.varita.price] |  |  |  |  | |  |
