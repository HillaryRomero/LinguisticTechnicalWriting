# Event (evento)

## Definición

Un **event** constituye cada uno de los mensajes emitidos consecutivamente por un agente en un channel. Estos mensajes pueden ser texto, imagen o cualquier recurso que provea información. Así pues, cualquier pregunta o respuesta que forme parte de una conversación entre un usuario y un bot son ejemplos de **events**.

Ninguno de los events que forman parte de un [scenario](scenario.md) puede omitirse, ni la secuencia cronológica que hay entre ellos se puede romper, dado que cada **event** agrega gradualmente información al contexto de la conversación. Esta información es necesaria para que el bot pueda interpretar adecuadamente los mensajes que recibe.

> **Nota:** un **event** puede ser emitido bien por un usuario o por un bot Mammut.

Dado que son parte de un corpus, los **events** deben ser seleccionados como ejemplos prototípicos de una conversación, pues ellos serán parte de los datos que se usarán para la preparación de los bots.

Un conjunto de events forman un **scenario** y, a su vez, un conjunto de scenarios forman un **corpus**. Por lo tanto, los events se almacenarán también en el **corpus**.

En tal sentido, en el **corpus**, dentro de un mismo scenario (pregunta + respuesta) una petición hecha por un usuario es un **event**; también lo es la respuesta que el bot proporciona a tal petición.

Conceptos relacionados: [corpus](corpus.md), [corpus N](corpusN.md), [corpus M](corpusM.md), [scenario](scenario.md).

## Formato general

Para efectos de un corpus, cada uno de los events que forman parte de un mismo scenario serán identificados a través del **sub-id**. El sub-id se utilizará también para organizar cronológicamente todos los events que deben ser diferentes entre sí y deben mantener una secuencia.

Es posible observar en un corpus que el código del **id** será el mismo para todos los events de un scenario (por ejemplo: 2), pero para diferenciar cada uno de los events se usará un sub_id distinto (por ejemplo: sub_id "1" para la pregunta y sub_id "2" para la respuesta).

La estructura de los events en el corpus es la siguiente:

| Campo | Descripción | Obligatoriedad |
| ----  | ----------  | -------------- |
| __id__ | Identificador de un **scenario**. Los valores válidos son de tipo entero. Enteros iguales se corresponden a un mismo scenario. | Obligatorio. |
| __sub_id__ | Identificador de un **event**. Los valores válidos son de tipo entero, y estos deben ser consecutivos, de menor a mayor, uno a uno, empezando en "1" cuando forman parte de un mismo scenario. La numeración se reinicia para el siguiente scenario. Los valores consecutivos del sub_id se corresponden con la secuencia prototípica en la que se presentan las partes de una conversación (por ejemplo, primero un saludo, segundo una pregunta, etc.). | Obligatorio. |

## Ejemplo

| id | sub_id | scenario_type | event_message | hidden | field | source | regional_settings |
| -- | -- | -- | -- | -- | -- | -- | -- |
2 | 1 | Conversation | ¿Qué varitas venden? |  |  | Carla | es |
2 | 2 | Conversation | Vendemos varitas de madera de cedro, de olmo, de sauco. |  |  | Mammut | es |
