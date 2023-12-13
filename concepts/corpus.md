# Corpus

## Definición

Un **corpus** es una colección de conversaciones prototípicas representativas de la comunicación entre diversos agentes (típicamente entre un bot y uno o más usuarios humanos). Un corpus puede ampliarse o no por medio de otra estructura denominada [corpus extension](extension.md) (o corpus extendido). Un corpus también puede relacionarse por medio de [variables](variables.md) a un **knowledge** para ampliar su capacidad expresiva.

Un corpus es una estructura de datos utilizada para configurar posibles [scenarios](scenario.md) por los cuales puede discurrir una conversación.

> Nota: un bot en su versión más simple se compone, en primera instancia, de uno o varios corpora.

Un **corpus** es un medio para que el bot generalice conversaciones, responda correctamente y sepa donde se puede usar la información proveniente del knowledge. Como tal, el corpus es un componente central de un bot de Mammut.

Conceptos relacionados: [corpus extension](extension.md), [corpus N](corpusN.md), [corpus M](corpusM.md), [scenario](scenario.md), [event](events.md).

## Formato general

Un corpus es una sheet de un *Mammut package*. Los nombres de las columnas se encuentran en la fila 2.

Cada fila de la sheet se corresponde con un **event**. La estructura de esta sheet es la siguiente:

| Campo | Descripción | Obligatoriedad |
| ----  | ----------  | -------------- |
| __id__ | Identificador de un **scenario**. Los valores válidos son de tipo entero. Enteros iguales se corresponden a un mismo scenario. | Obligatorio. |
| __sub_id__ | Identificador de un **event**. Los valores válidos son de tipo entero, y estos deben ser consecutivos, de menor a mayor, uno a uno, empezando en 1 cuando forman parte de un mismo scenario. La numeración se reinicia para el siguiente scenario. Los valores consecutivos del **sub_id** se corresponden con la secuencia prototípica en la que se presentan las partes integrantes de una conversación (por ejemplo, primero un saludo, segundo una pregunta, etc.) | Obligatorio. |
| __scenario_type__ | Tiene tres valores posibles: **Conversation**, **Monologue** y **Dialogue** para cada tipo de scenario. Más información en [scenario](scenario.md). | Obligatorio. |
| __event_message__ | Mensaje que determina al **event**. Los valores válidos son de tipo cadena de caracteres. En el caso del corpus M, las variables tendrán un formato específico. | Obligatorio. |
| __hidden__ | Ignora un event específico. Se marca con una "x" para esconder el event. Se deja vacío este valor para que el event sea tomado en cuenta por el framework. | Opcional. |
| __source__ | Origen de los events que recibe o genera el bot. Es una cadena de caracteres. La cadena de caracteres "Mammut" se reserva para los events iniciados por el bot. Cualquier otra cadena será interpretada como el nombre genérico de otro agente. | Obligatorio. |
| __regional_seting__ | Especifíca el idioma en que está escrito el event. En esta columna se usan los códigos “es” (para un corpus en español) o “en” (para un corpus en inglés) según sea el caso. | Obligatorio |
| __complexity__ | Identificador del grado de complejidad de un event. Los valores válidos son números de tipo entero. | Opcional. |

## Ejemplo

| id | sub_id | scenario_type | event_message | hidden | field | source | regional_settings |
| - | - | - | - | - | - | - | - |
1 | 1 | Conversation | Hola! |  |  | Carla | es |
1 | 2 | Conversation | Hola! Bienvenido a la tienda de varitas y calderos del señor Jollivanders. ¿En qué puedo ayudarte? |  |  | Mammut | es |
2 | 1 | Conversation | ¿Qué varitas venden? |  |  | Carla | es |
2 | 2 | Conversation | Vendemos varitas de madera de cedro, de olmo, de sauco. |  |  | Mammut | es |
2 | 3 | Conversation | ¿Cuál es el precio de la varita de sauco? |  |  | Carla  | es |
2 | 4 | Conversation | La varita de sauco cuesta 50 galeones. |  |  | Mammut | es |
2 | 5 | Conversation | La quiero |  |  | Carla | es |

## Tipos de corpus

### Corpus N

Corpus compuesto únicamente de scenarios en lenguaje natural. Véase [Corpus N](corpusN.md).

### Corpus M

Corpus compuesto por scenarios que, además de lenguaje natural, permiten usar un lenguaje formal (Mammut Markdown) para conectar el corpus a una ontology (ontología). Véase [Corpus M](corpusM.md).
