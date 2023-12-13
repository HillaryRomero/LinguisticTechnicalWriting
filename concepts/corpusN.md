# Corpus N

## Definición

Un **corpus N** es un tipo de [corpus](corpus.md) que se compone únicamente de [scenarios](scenario.md) en lenguaje natural. El corpus normal o natural (N) es un tipo de corpus básico que está conformado por peticiones y respuestas creadas por el desarrollador. Este tipo de corpus es sencillo y rápido de construir, sin embargo, el bot de Mammut podrá responder únicamente a los [events](events.md) dispuestos en él.

El corpus N se almacena en una sheet del *Mammut package*. La información dispuesta en el corpus N contiene ejemplos representativos de conversaciones escritas en lenguaje natural, así como información necesaria para la preparación del bot.

> **Nota:** el **corpus N** es un conjunto de interacciones simples que conforman a un bot de Mammut para que este pueda comunicarse con un usuario. El corpus N se considera un subconjunto del **corpus M**.

Conceptos relacionados: [corpus](corpus.md), [corpus extension](extension.md), [scenario](scenario.md), [event](corpus.md).

## Formato general

Un **corpus N** es una sheet de un *Mammut package*. El corpus N está compuesto por **scenarios** y **events**. Cada fila de la sheet se corresponde con un event. Los nombres que corresponden a cada una de las columnas se encuentran en la fila #2: id, sub_id, scenario_type, event_message, hidden field, source, regional_settings, complexity.

La estructura de este sheet es la siguiente:

| Campo | Descripción | Obligatoriedad |
| ----  | ----------  | -------------- |
| __id__ | Identificador de un **scenario**. Los valores válidos son de tipo entero. Enteros iguales se corresponden a un mismo scenario. | Obligatorio. |
| __sub_id__ | Identificador de un **event**. Los valores válidos son de tipo entero, y estos deben ser consecutivos, de menor a mayor, uno a uno, empezando en 1 cuando forman parte de un mismo scenario. La numeración se reinicia para el siguiente scenario. Los valores consecutivos del **sub_id** se corresponden con la secuencia prototípica en la que se presentan las partes integrantes de una conversación (por ejemplo, primero un saludo, segundo una pregunta, etc.) | Obligatorio. |
| __scenario_type__ | Tiene tres valores posibles: *Conversation*, *Monologue* y *Dialogue* para cada tipo de scenario. (Véase [scenario](scenario.md)). | Obligatorio. |
| __event_message__ | Mensaje que determina al **event**. Los valores válidos son de tipo cadena de caracteres. En el caso del corpus M, las variables tendrán un formato específico. | Obligatorio. |
| __hidden__ | Ignora un event específico. Se marca con una "x" para esconder el event. Se deja vacío este valor para que el event sea tomado en cuenta por el framework. | Opcional. |
| __field__ | Indica una palabra vinculada al tema del event. | Opcional. |
| __source__ | Origen de los events que recibe o genera el bot. Es una cadena de caracteres. La cadena de caracteres "Mammut" se reserva para los events iniciados por el bot. Cualquier otra cadena será interpretada como el nombre genérico de otro agente. | Obligatorio. |
| __regional_seting__ | Especifíca el idioma en que está escrito el event. En esta columna se usan los códigos **“es”** (para un corpus en español) o **“en”** (para un corpus en inglés) según sea el caso. | Obligatorio |
| __complexity__ | Identificador del grado de complejidad de un event. Los valores válidos son números de tipo entero. | Opcional. |

## Ejemplo

Como se puede apreciar en la siguiente imagen, el **corpus N** está conformado por intervenciones (petición/respuesta) que sirven como modelos conversacionales al bot de Mammut:

| id | sub_id | scenario_type | event_message | hidden | field | source | regional_settings |
| - | - | - | - | - | - | - | - |
1 | 1 | Conversation | Hola! |  |  | Carla | es |
1 | 2 | Conversation | Hola! Bienvenido a la tienda de varitas y calderos del señor Jollivanders. ¿En qué puedo ayudarte? |  |  | Mammut | es |
2 | 1 | Conversation | ¿Qué varitas venden? |  |  | Carla | es |
2 | 2 | Conversation | Vendemos varitas de madera de cedro, de olmo, de sauco. |  |  | Mammut | es |
2 | 3 | Conversation | ¿Cuál es el precio de la varita de sauco? |  |  | Carla  | es |
2 | 4 | Conversation | La varita de sauco cuesta 50 galeones. |  |  | Mammut | es |
2 | 5 | Conversation | La quiero |  |  | Carla | es |
