# Capítulo 3. Respuestas y knowledge

En este capítulo veremos con más detalle cómo usa tu chatbot las **variables** para arrojar respuestas más precisas. Para hacer esto, _Sylvia_ deberá usar su **knowledge** en los **events** de su **corpus**.

## Información del knowledge al corpus

El chatbot toma información directamente del knowledge para responder de forma precisa a las solicitudes de los usuarios. Esto lo hace siguiendo los [paths (rutas)](../concepts/path.md) de la ontology que son descritas por las variables en los events del corpus. Es por esto que, la forma en que diseñes tu [knowledge y ontology](../concepts/ontology.md) determina la manera como tu chatbot accede a sus datos.

El chatbot va a buscar las respuestas en un lugar que el usuario le haya dado anteriormente en la pregunta. Tomemos de nuevo el ejemplo del scenario 1 events 3 y 4 en el corpus de _Sylvia_. La pregunta del usuario: _"Cuál es el precio de la lasaña?"_. El chatbot buscará la información en un sitio que él ya conoce ```restaurant.sell_several.dish```. En el event de **id** 1 y **sub id** 3, podemos ver, por ejemplo, que la palabra _lasaña_ corresponde a la property (propiedad) **name**. Pero para la respuesta que tenemos; _El precio de nuestra lasaña es 18,50_ no podremos usar la misma property.

| _name_ | type | description | _Price_ |
| - | - | - | - |
| Desayuno americano | Desayuno | Panqueques con mantequilla y jarabe de arce, tocino frito y huevos fritos. | 22,00 |
| Sándwich | Desayuno | Puedes elegir 3 de estos rellenos para sándwiches: queso, jamón y queso, ensalada de jamón, salchicha, queso y cebolla, mayonesa de huevo, mayonesa de atún o ensalada de pollo.| 12,00 |
| ***Lasaña*** | Almuerzo | Un perfecto equilibrio entre capas de queso, fideos y salsa boloñesa casera.| ***18,50*** |
**Tab. 1:** _Properties "name" y "price" en el vertex "dish"_.

Como podemos ver, el precio está contenido en otra property, en este caso 'price (precio)'. La información de esta property varía de una instance a otra (es decir, los precios varían de un plato a otro). Por eso, es más provechoso usar otra variable para dar respuesta a la pregunta _"¿Cuál es el precio de la lasaña?"_. Así podemos lograr que _Sylvia_ acceda a la información alojada en la property **price** de cualquier instance del vertice 'dish'.

Ahora veamos cómo configurar una variable para la respuesta: _El precio de nuestra lasaña es 15,00_.

## Paso a paso: crea una variable para configurar la respuesta del chatbot usando información del knowledge

1. Ubícate en la columna **event_message** correspondiente al scenario 1, event 4 del corpus de _Sylvia_. Recuerda que la parte del scenario que no necesitas cambiar por variables debe quedar escrita en lenguaje natural (en un idioma como inglés, español, etc). Las palabras del mensaje que vamos a sustituir por variables podemos sustituirlas, por ahora, por un par de corchetes. Prueba escribiendo: *El precio de la [ ] es [ ]*. En los espacios dentro de los corchetes es dónde escribiremos las variables.

2. Ahora vamos a escribir las **variables** que irán en cada uno de los dos corchetes. En el primer corchete ubicaremos la variable que refiere al plato por el que se está preguntando. Prueba copiar la misma ruta que usaste para la pregunta en el capítulo anterior de este tutorial: ```[variable|restaurant.sell_several.dish.name]```.

3. Para el segundo corchete, vamos a crear una variable que indique la ruta hacia el **knowledge** comenzando por el **entry point** y que termine en la **property** de la **ontology** donde hemos añadido los datos de los precios de los platos. Si observas la ontology de _Sylvia_ podrás notar que este path recorre los siguientes puntos: entry_point (**restaurant**) + edge (**sell_several**) + vertice (**dish**) + property (**price**). Prueba escribiendo en este segundo corchete: ```[variable|restaurant.sell_several.dish.price]```.

    Eso es todo. Tus variables para este event deben verse así:

    | id | sub_id | scenery_type | event_message                                                                                                       |
    |----|--------|--------------|---------------------------------------------------------------------------------------------------------------------|
    | 1  | 3      | Conversation | ¿Cuál es el precio de la ```[variable\|restaurant.sell_several.dish.name]```?                                             |
    | 1  | 4      | Conversation | El precio de la ```[variable\|restaurant.sell_several_dish.name] es de [variable\|restaurant.sell_several_dish.price]```. |
    **Tab. 2:** _Variables en los events 3 y 4 del escenario 1_.

Bastante simple, ¿no? Ahora puedes establecer variables para todos los events (solicitudes de usuario y respuestas de tu chatbot) en el corpus siguiendo estos sencillos pasos.

# ¿Qué aprendiste en este capítulo?

Aprendiste cómo logra el chatbot acceder al knowledge cuando usas una variable. También creaste paso apaso una variable para una event de respuesta en el corpus de _Sylvia_. ¡Ahora _Sylvia_ puede responder a las preguntas usando los recursos alojados en su knowledge!

## ¿Qué sigue?

Ahora que sabes cómo construir las variables de tu chatbot, estamos listos para ver cómo estas pueden ayudar a _Sylvia_ a manejar el contexto en las conversaciones con los usuarios.

Nos vemos en el próximo capítulo sobre [Variables y el Scope](variables_and_scope.md)
