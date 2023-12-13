# Knowledge commit

## Definición

Un **knowledge commit** es un action del corpus que permite guardar en el knowledge del bot datos que han sido capturados en tiempo de conversación con un usuario. 

> **Nota**: El knowledge commit se hace cuando se haya agregado en el conversation scope toda la información que se necesita acerca de un vértice.

Este action es el que permite confirmar un conjunto de cambios provisionales dados en el tiempo de conversación y guardarlos de forma permanente. Es decir, con este action se consolida la data atrapada en el knowledge del bot.

Conceptos relacionados: [corpusM](corpusM), [sink](sink.md), [property](properties.md).

## Formato general

Un knowledge commit se incorporará en la columna **action** del corpus de un event que tenga como source al agente bot (_Mammut_). Este action se agrega de la siguiente manera: **knowledge_commit(path)**. En especifico, este path se refiere al transverse del vertex donde se guardará los datos que han sido capturados en los eventos anteriores a la invocacion del action. 

## Ejemplo

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
1 | 1 | Conversation | Hola! |  |  |  |  |  | Carla | es |
1 | 2 | Conversation | Hola! Bienvenido a la tienda de varitas y calderos del señor Jollivanders. ¿En qué puedo ayudarte? |  |  |  |  |  | Mammut | es |
2 | 1 | Conversation | ¿Cuál es el precio de la [`variable\|tienda.sell_several.varita.name`] en [`variable\|tienda.name`]? |  |  |  |  |  | Carla | es |
2 | 2 | Conversation | La [`variable\|tienda.sell_several.varita.name`] cuesta [`variable\|tienda.sell_several.varita.price`]. |  |  |  |  |  | Mammut | es |
2 | 3 | Conversation | Quiero comprar una de [`variable|store.manage.user_data.order`] |  |  |  |  |  | Carla | es |
2 | 4 | Conversation | De inmediato. Dame tu correo electrónico para concluir tu petición. |  |  |  |  |  | Mammut | es |
2 | 5 | Conversation | Mi correo es [`variable|store.manage.user_data.email`] |  |  |  |  |  | Carla | es |
2 | 6 | Conversation | Tu compra sera procesada. Con el email [`variable|store.manage.user_data.email`]. |  |  |  |  | **knowledge_commit(store.manage.user_data)** | Mammut | es |
