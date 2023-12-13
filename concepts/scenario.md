# Scenario (escenario)

## Definición

El **scenario** es un conjunto de interacciones que forman parte de un mismo contexto. Es decir, son una sucesión de [events](events.md) en secuencia cronológica; así pues, entendemos que dos o más events que funcionan juntos se organizan en un scenario. Cada nueva secuencia cronológica de events formará parte de un nuevo scenario.

Los events que forman parte de un mismo scenario deben estar dispuestos en orden cronológico -tal y como sucederían en una conversación. El bot va a usar este orden para aprender las secuencias lógicas de las conversaciones. Cada secuencia de events que forme parte de un contexto distinto, debe constituir un scenario diferente.

> **Nota:** un **scenario** está compuesto por una o varias solicitudes de un usuario, y por las respuestas a estas solicitudes. Es posible imaginar los scenarios como partes de una conversación o diálogo.

Ahora bien, así como un scenario está formado por un conjunto de events, un conjunto de scenarios constituyen un corpus. Entonces, los scenarios se almacenarán también en la sheet denominada **corpus N** o **corpus M** según corresponda. La información dispuesta en el corpus N o M provee casos representativos en lenguaje natural o formal, así como información necesaria para la preparación del bot.

Conceptos relacionados: [corpus](corpus.md), [corpus N](corpusN.md), [corpus M](corpusM.md), [event](events.md).

## Formato general

Para efectos del **corpus N** y el **corpus M**, las interacciones que forman parte de un mismo scenario se identificarán con el mismo **id**.

| Campo | Descripción |
| ----  | ----------  |
| __id__ | Identificador de un **scenario**. Los valores válidos son de tipo entero, donde, enteros iguales se corresponden a un mismo scenario. Este campo es **obligatorio**. |

### Ejemplo

Como se puede ver en este ejemplo, ambos events pertenecen a un mismo scenario y son identificados con el número 1.

| id | sub_id | scenario_type | event_message | hidden | field | source | regional_settings |
| - | - | - | - | - | - | - | - |
1 | 1 | Conversation | Hola! |  |  | Carla | es |
1 | 2 | Conversation | Hola! Bienvenido a la tienda de varitas y calderos del señor Jollivanders. ¿En qué puedo ayudarte? |  |  | Mammut | es |

## Tipos de scenario

Los mensajes que reciba el bot podrán tener cualquier identificación que los diferencie de los mensajes que envía. Por ejemplo, los mensajes que recibe el bot pueden tener como identificador el nombre de un usuario (José, María, Juan o Pedro), mientras que los mensajes que envía el bot tendrán siempre como source: "Mammut". A este identificador se le denomina **source**.

Entonces, dado el número de sources en un scenario, estos podrán ser:

- **Conversation**: es un scenario con dos **fuentes** distintas.

    | id | sub_id | scenario_type | event_message | hidden | field | source | regional_settings |
     - | - | - | - | - | - | - | - |
    1 | 1 | Conversation | Hola! |  |  | Carla | es |
    1 | 2 | Conversation | Hola! Bienvenido a la tienda de varitas y calderos del señor Jollivanders. ¿En qué puedo ayudarte? |  |  | Mammut | es |

- **Monologue**: es un scenario que tiene una sola **fuente**. Por ejemplo, un saludo que se le programa al bot, pero que no se espera que sea respondido por el usuario.

    | id | sub_id | scenario_type | event_message | hidden | field | source | regional_settings |
    | - | - | - | - | - | - | - | - |
    1 | 1 | Monologue | Hola! |  |  | Mammut | es |

- **Dialogue**: es un tipo de scenario que incluye tres o más **sources** en los events que lo componen.

    | id | sub_id | scenario_type | event_message | hidden | field | source | regional_settings |
    | - | - | - | - | - | - | - | - |
    2 | 1 | Dialogue | ¿Qué varitas venden? |  |  | Carla | es |
    2 | 2 | Dialogue | Vendemos varitas de madera de cedro, de olmo, de sauco. |  |  | Mammut | es |
    2 | 3 | Dialogue | ¿Y cuál es el precio de la varita de sauco? |  |  | Maria  | es |
