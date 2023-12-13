# Corpus Extension

## Definición

El **corpus extension** (o simplemente "extension") complementa el corpus con paráfrasis de los [events](events.md) que tienen como fuente a usuarios de un bot. El extension permite alojar las diferentes formas en las que cada uno de estos events puede ser expresado por diversos usuarios. De esta manera se le proporciona al bot la información necesaria para comprender un mismo mensaje, aun cuando este sea escrito de muchas formas distintas. 

> **Nota:** el **extension** es un herramienta para que los corpus N y M tengan más ejemplos representativos de mensajes emitidos por usuarios. Por lo tanto, el extension amplía las capacidades de un corpus dado, proveyendo una mayor cantidad de datos que serán usados por los bots para generalizar conversaciones y aprender cómo responder correctamente los mensajes recibidos.

El corpus extension no debe usarse para añadir paráfrasis de las respuestas que serán emitidas por el bot. La función del extension se limita a alojar los mensajes que el bot podría recibir en las conversaciones, es decir, de los events del corpus que tengan como fuente a los usuarios.

**Conceptos relacionados:** [corpus](corpus.md), [corpus N](corpusN.md), [corpus M](corpusM.md), [event](events.md), [scenario](scenario.md).

## Formato general

El corpus extension es una sheet de un **package** de Mammut. Los nombres de las columnas del **extension** se encuentran en la fila 2. Cada fila de la sheet se corresponde con una paráfrasis de un event del corpus; estas se escriben en lenguaje natural.

La estructura de esta sheet es la siguiente:

| Campo | Descripción | Obligatoriedad |
| ----  | ----------  | -------------- |
| __id__ | Identificador de un scenario. Los valores válidos son de tipo entero, en este sentido, enteros iguales se corresponden a un mismo scenario. El **id** de las paráfrasis usado en el corpus_extension debe ser idéntico al id del scenario del corpus que está parafraseando. | Obligatorio. |
| __sub_id__ | Identificador de un event. Los valores válidos son de tipo entero. El **sub_id** de las paráfrasis usado en el corpus_extension debe ser idéntico al sub_id del event del corpus que está parafraseando. | Obligatorio. |
| __event_message__ | Mensaje que determina la paráfrasis de un event. Los valores válidos son de tipo 'cadena de caracteres'. En el caso del corpus M, las variables deben estar escritas de acuerdo con la sintaxis de este tipo de datos. | Obligatorio. |
| __hidden__ | Función que ignora una paráfrasis específica. Se marca con una "x" para esconder la paráfrasis. Se deja este valor vacío para que la paráfrasis sea tomada en cuenta por el framework. | Opcional. |
| __source__ | Origen de los events que recibe el bot. Es una cadena de caracteres. Los events parafraseados deben ser siempre mensajes que tengan como fuente a un usuario de un bot. | Obligatorio. |
| __regional_setting__ | Especifica el idioma en el que está escrito el event. En esta columna se usan los códigos "es" (español) o "en" (inglés) según sea el caso. El **regional_setting** de una paráfrasis debe coincidir con el regional_setting del event del corpus que se está parafraseando. | Obligatorio. |

## Ejemplo

| id | sub_id | event_message | hidden | source | regional_settings |
| -- | -- | -- | -- | -- | -- |
1 | 1 | hey! |  | Carla | es |
1 | 1 | oye |  | Carla | es |
1 | 1 | ola |  | Carla | es |
2 | 1 | Cuál es el precio de las [`variable\|tienda.sell_several.varita.name`] en [`variable?\|tienda.name`]? |  | Carla | es |
2 | 1 | En [`variable\|tienda.name`] cuánto valen las [`variable\|tienda.sell_several.varita.name`]? |  | Carla | es |
2 | 3 | Compro la [`variable\|tienda.sell_several.varita.name`] |  | Carla | es |
2 | 3 | Dame la [`variable\|tienda.sell_several.varita.name`] |  | Carla | es |
