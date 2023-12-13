# Corpus M

## Definición

El **corpus M** es un tipo de [corpus](corpus.md) que se compone de scenarios en lenguaje natural y lenguaje formal para preparar a un bot de Mammut. Esta mezcla es posible gracias a [Mammut Markdown](mammut_markdown.md). Los [scenarios](scenario.md) se pueden conectar con una [ontology](ontology.md) para ampliar la funcionalidad de los bots.

En los ejemplos de interacción dispuestos en el corpus, es decir, de los **events** o **scenarios** es posible usar [variables](variables.md) para sustituir elementos que sean parte del knowledge.

> **Nota:** la capacidad de respuesta del bot es más eficiente y precisa gracias al uso de mammut markdown en los corpus M.

El uso de un **corpus M** permite que un bot de Mammut pueda manejar el contexto en una conversación. Esto es posible porque un bot con un **corpus M** usa una memoria de la conversación vinculada al knowledge. Esta memoria almacena información sobre la conversación, que será utilizada por el bot de Mammut en futuras interacciones para responder los mensajes enviados por los usuarios (Véase [scope](scope.md)).

El **corpus M** se almacena en una sheet. La información dispuesta en el corpus M provee casos representativos en lenguaje natural y formal, así como información necesaria para la preparación del bot.

Conceptos relacionados: [corpus](corpus.md), [corpus extension](extension.md), [scenario](scenario.md), [event](events.md), [variable](variables.md) [knowledge](ontology.md), [ontology](ontology.md), [scope](scope.md).

## Formato general

Un **corpus M** es una sheet de un mammut package. Cada fila de la sheet se corresponde con un **event**. Los nombres que corresponden a cada una de las columnas se encuentran en la fila #2.

La estructura de esta sheet es la siguiente:

| Campo | Descripción | Obligatoriedad |
| ----  | ----------  | -------------- |
| __id__ | Identificador de un **scenario**. Los valores válidos son de tipo entero. Enteros iguales se corresponden a un mismo scenario. | Obligatorio. |
| __sub_id__ | Identificador de un **event**. Los valores válidos son de tipo entero, y estos deben ser consecutivos, de menor a mayor, uno a uno, empezando en 1 cuando forman parte de un mismo scenario. La numeración se reinicia para el siguiente scenario. Los valores consecutivos del **sub_id** se corresponden con la secuencia prototípica en la que se presentan las partes integrantes de una conversación (por ejemplo, primero un saludo, segundo una pregunta, etc.) | Obligatorio. |
| __scenario_type__ | Tiene tres valores posibles: **Conversation**, **Monologue** y **Dialogue** para cada tipo de scenario. (Véase [scenario](scenario.md)). | Obligatorio. |
| __event_message__ | Mensaje que determina al **event**. Los valores válidos son de tipo cadena de caracteres. En el caso del corpus M, las variables tendrán un formato específico. | Obligatorio. |
| __hidden__ | Ignora un event específico. Se marca con una "x" para esconder el event. Se deja vacío este valor para que el event sea tomado en cuenta por el framework. | Opcional. |
| __field__ | Indica una palabra vinculada al tema del event. | Opcional. |
| __lambda_condition__ | Condición necesarias para que el bot envíe una respuesta determinada al usuario, dependiendo de la información que se encuentre en el scope. | Opcional. |
| __ui_event__ | Función escrita en código informático que permite al bot percibir ciertas acciones llevadas a cabo por un agente en la interfaz de usuario. | Opcional. |
| __action__ | Acción programática predefinida en código que se ejecuta automáticamente en un event asociado. Esta columna permite programar acciones determinadas que el bot puede llevar a cabo (dependiendo de los intereses del programador) cuando tiene lugar un event determinado. | Opcional. |
| __source__ | Origen de los events que recibe o genera el bot. Es una cadena de caracteres. La cadena de caracteres "Mammut" se reserva para los events iniciados por el bot. Cualquier otra cadena será interpretada como el nombre genérico de otro agente. | Obligatorio. |
| __regional_seting__ | Especifíca el idioma en que está escrito el event. En esta columna se usan los códigos **“es”** (para un corpus en español) o **“en”** (para un corpus en inglés) según sea el caso. | Obligatorio. |
| __complexity__ | Identificador del grado de complejidad de un event. Los valores válidos son números de tipo entero. | Opcional. |


## Ejemplo

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
1 | 1 | Conversation | Hola! |  |  |  |  |  | Carla | es |
1 | 2 | Conversation | Hola! Bienvenido a la tienda de varitas y calderos del señor Jollivanders. ¿En qué puedo ayudarte? |  |  |  |  |  | Mammut | es |
2 | 1 | Conversation | ¿Cuál es el precio de la [`variable\|tienda.sell_several.varita.name`] en [`variable\|tienda.name`]? |  |  |  |  |  | Carla | es |
2 | 2 | Conversation | La [`variable\|tienda.sell_several.varita.name`] cuesta [`variable\|tienda.sell_several.varita.price`]. |  |  |  |  |  | Mammut | es |
2 | 3 | Conversation | La quiero. |  |  |  |  |  | Carla | es |
2 | 4 | Conversation | De inmediato. Dame tu correo electrónico para concluir tu petición. |  |  |  |  |  | Mammut | es |
3 | 1 | Conversation | ¿En [`variable\|tienda.name`] cuál es el precio del [`variable\|tienda.send_several.caldero.name`]? |  |  |  |  |  | Carla | es |
3 | 2 | Conversation | El [`variable\|tienda.send_several.caldero.name`] cuesta [`variable\|tienda.send_several.caldero.price`]. |  |  |  |  |  | Mammut | es |
3 | 3 | Conversation | Quiero el [`variable\|tienda.send_several.caldero.name`].  |  |  |  |  |  | Carla | es |
3 | 4 | Conversation | De inmediato. Dame tu correo electrónico para concluir tu petición. |  |  |  |  |  | Mammut | es |
