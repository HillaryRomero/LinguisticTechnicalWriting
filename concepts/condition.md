# Condición

## Definición

Una **condition** es una expresión que puede ser verdadera (True) o falsa (False). Una condition es una estructura que permite determinar un comportamiento del bot. Algunos de los comportamientos que una condition puede determinar en un bot son la inclusión de instancias por defecto en el scope (véase [defaults](default.md)) o la construcción de dos opciones de respuestas en el corpus. 

> **Nota:** Si la condition se cumple (True), el comportamiento definido es ejecutado. Si la condition no se cumple (False), el comportamiento definido no es ejecutado.

Esta estructura típicamente actúa sobre el [scope](scope.md) en las conversaciones entre el bot y los usuarios humanos. De esta manera, usando una condition se puede verificar la veracidad de alguna información del conversation scope. Por ejemplo, una **condition** puede acceder a evaluar el [**channel**](channels.md) por el cual se está comunicando un usuario, el bot con el cual se esté comunicando o la información que se encuentre guardada en el **scope** de una conversación. 

Conceptos relacionados: [scope](scope.md), [channel](channels.md), [default scenario](default.md), [corpusM](corpusM.md).

## Formato general

Una condition se crea a partir de una expresión válida en [Mammut Markdown](mammut_markdown.md). Esta se escribe siguiendo el formato de una expresión booleana o expresión lógica.

| Expresión | Significado |
| --------- | ----------- |
| True | siempre será cierto |
| a == b  | ¿a es igual a b? |
| a != b  | ¿a es distinto de b? |
| a < b   | ¿a es menor que b? |
| a <= b  | ¿a es menor o igual que b? |
| a > b   | ¿a es mayor que b |
| a >= b  | ¿a es mayor o igual que b? |
| a and b | El resultado es True solamente si a es True y b es True. De lo contrario el resultado es False |
| a or b  | El resultado es True si a es True o b es True. De lo contrario el resultado es False |
| not a     | El resultado es True si a es False. De lo contrario el resultado es False |
| path.in_scope | Hay una instancia del path descrito en scope |
| path.not_in_scope | No hay una instancia del path descrito en scope |
| path.with_ambiguity | Hay una ambigüedad sobre la instancia en scope |

En una expresión booleana de Mammut Markdown **a** y **b** pueden asumir un valor literal o un valor variable. En una condition, un **valor literal** puede ser un número, un string o un boolean. En cambio, un **valor variable** es definido como un valor que puede cambiar durante la ejecución. Algunos valores variables que se pueden usar para expresar las conditions son los que se ofrecen en la siguiente tabla. 

| variable | valor |
| - | - |
| base_closure.channel | Channel ID |
| base_closure.sub_channel | Sub channel ID |
| base_closure.room_id | Room ID |
| base_closure.mammut_id | Mammut bot ID |

> **Nota:** Al scope se accede través del ```base_closure```. (véase [scope](scope)). El channel ID o el sub channel ID varía en cada channel (véase [channel](channels.md)). 

## Ejemplo

Una condition es una expresión que se incluye en una columna identificada con **lambda_condition** del [mammut package](package.md). Esta columna aparece en las tablas *scenario defaults*, *corpus* y *properties*. 

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
| 2 | 3 | Conversation | La quiero. |  |  |  |  |  | Carla | es |
| 2 | 4 | Conversation | Por supuesto! |  |  | **tienda.sell_several.varita.in_scope**  |  |  | Mammut | es |
| 2 | 4 | Conversation | Necesito saber el nombre de la varita que te interesa. ¿Podrías darme su nombre en el siguiente mensaje? |  |  | **tienda.sell_several.varita.not_in_scope** |  |  | Mammut | es |
| 2 | 5 | Conversation | [variable\|tienda.sell_several.varita.name] |  |  |   |  |  | Carla | es |
| 2 | 6 | Conversation | Listo, ya agregamos el pedido. |  |  |   |  |  | Carla | es |

> Nota: Este ejemplo de condition está en el sheet *corpus*. Como puedes observar, la condición permite solicitar el valor de ```[variable\|tienda.sell_several.varita.name]``` en los casos donde no se encuentre en scope (```not_in_scope```). Al mismo tiempo que permite manejar la conversación cuando sí se encuentre el valor en scope (```in_scope```).
