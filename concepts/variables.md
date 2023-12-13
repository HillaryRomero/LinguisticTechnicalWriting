# Variables

## Definición

Una **variable mammut** (o simplemente "variable") es una herramienta de **Mammut markdown** que construye una unidad susceptible a tomar distintos valores. Estas tienen la posibilidad de transformarse en texto, imágenes, videos u otros tipos de contenido. Las variables representan un dato que el bot sabe o que el bot quiere saber, por lo tanto, toman su valor directamente desde una property del [knowledge](ontology.md).

Una variable permite hacer referencias a un [path](path.md) del knowledge que el bot deberá seguir. La variable ayuda al bot para reconocer algún dato, o para arrojarlo según se trate de una solicitud o respuesta hacia el usuario. Una variable también puede representar a un valor que el bot quiere saber y que será atrapado en la conversación (véase [sink](sink.md)).

> **Nota:** las variables permiten al bot resolver una mayor cantidad de peticiones, ya que estas toman su valor directamente al momento de una conversación.

Una variable es el medio para sumar datos al **conversation scope**. Las transformaciones de variables realizadas en una conversación, son guardadas en una memoria para así dar respuestas más correctas al usuario.

Conceptos relacionados: [corpus M](corpusM.md), [knowledge](ontology.md), [path](path.md), [conversation scope](scope.md).

## Formato general

La variable es una secuencia escrita entre corchetes que consta de dos partes divididas por una barra vertical (**|**): en primer lugar se encuentra el tipo de **transformación** y en segundo lugar una **función**.

**Estructura:** ```[Tipo_de_transformación|función]```

> **Nota:** la **transformación** especifica el tipo de contenido que la variable tomará luego de la transformación.

El identificador que se usa para cada tipo de transformación depende de la naturaleza del contenido referido en la función:

- **[variable]** = transformación de texto (admiten properties del tipo String, GeoLocation, Boolean, Integer, Long, Double, LocalDate, LocalTime, ZonedDateTime o StringToLower),
- **[variable_image]** = transformación de imagen (admiten properties del tipo GAttachment o Attachment),
- **[variable_video]** = transformación de video (admiten properties del tipo GAttachment o Attachment),
- **[variable_sound]** = transformación de audio (admiten properties del tipo GAttachment o Attachment).

> **Nota:** el tipo de transformación **[variable_image]** tiene una variación que nos permite incorporar imagenes directamente desde el corpus, sin necesidad de hacer referencia a una **función**. Esto se logra sustituyendo la función directamente por el id de la imagen que se quiera incorporar.
>> La **función** es la parte de la variable que especifica un [path](path.md) donde se debe buscar la información.

## Ejemplos

* Ejemplo de una variable con una transformación de texto:

    `[variable|tienda.sell_several.varita.name]`

* Ejemplo de una variable con una transformación en imágen:

    `[variable_image|tienda.sell_several.varita.image]`

* Ejemplo de una variable con una transformación en imagen, usando un atajo directo desde Google Drive:

    `[image|1FbcfdFsPCQO-bEwvhLGxMLLo_klpeAVV]`

A continuación se observa un ejemplo de un **corpusM** con variables Mammut:

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
1 | 1 | Conversation | Hola! |  |  |  |  |  | Carla | es |
1 | 2 | Conversation | Hola! Bienvenido a la tienda de varitas y calderos del señor Jollivanders. ¿En qué puedo ayudarte? |  |  |  |  |  | Mammut | es |
2 | 1 | Conversation | ¿Cuál es el precio de la ```[variable\|tienda.sell_several.varita.name]``` en ```[variable\|tienda.name]```? |  |  |  |  |  | Carla | es |
2 | 2 | Conversation | La ```[variable\|tienda.sell_several.varita.name]``` cuesta ```[variable\|tienda.sell_several.varita.price]```. |  |  |  |  |  | Mammut | es |
2 | 3 | Conversation | Quiero la ```[variable\|tienda.sell_several.varita.name]``` |  |  |  |  |  | Carla | es |
2 | 4 | Conversation | De inmediato. Dame tu correo electrónico para concluir tu petición. |  |  |  |  |  | Mammut | es |
3 | 1 | Conversation | ¿Puedes enviarme una imagen de ```[variable\|tienda.sell_several.varita.name]``` |  |  |  |  |  | Carla | es |
3 | 2 | Conversation | ```[variable_image\|tienda.sell_several.varita.image]``` |  |  |  |  |  | Mammut | es |
