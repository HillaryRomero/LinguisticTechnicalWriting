# Capítulo 1. Introducción

En esta primera sección aprenderemos sobre las **variables Mammut**: qué son y cómo funcionan.

Actualmente el [package de ejemplo _Sylvia_](https://docs.google.com/spreadsheets/d/1J4S7VAzvGqTQ9_PFzgb37VxDlWVHB-Egvpjz7okbPXo/edit?usp=sharing) tiene un [corpus N](../concepts/corpusN.md) (aún sin variables). Los **scenarios** del **corpus**, deben incluir una variedad de posibles interacciones de las que aprenderá cómo responder a las necesidades de sus usuarios.  En el corpus, _Sylvia_ debe abarcar la mayor cantidad de preguntas o peticiones sobre los vertices (vértices): **dish**, **drink** o **restaurant**. Toda esta información que _Sylvia_ necesita para atender, ya se encuentra alojada en su [knowledge](../concepts/ontology.md).

Ahora bien, ¿cómo puede _Sylvia_ acceder a dicha información para responder a sus usuarios durante una conversación? y ¿cómo sabe en qué platillo, de todos los del menú, está interesado el usuario? Además, ¿cómo puede saber _Sylvia_ de qué item está hablando el usuario sin necesidad de que este se lo repita en cada mensaje?, ¿cómo puede estar al tanto de lo que ocurre en las interacciones? La respuesta a estas preguntas es que lo hace a través de las **variables**.

## ¿Qué son las variables?

Las **variables** Mammut son símbolos susceptibles a tomar distintos valores. Para mantener las cosas simples, podemos pensar que las variables funcionan como palabras abstractas. Estas tienen la posibilidad de transformarse en texto, imágenes, videos u otros tipos de contenido dentro de un corpus M. Las variables toman su contenido directamente desde el **knowledge** (base de conocimiento) de un chatbot. En este sentido, son como palabras generales que pueden sustituir a otras palabras específicas, permitiendo flexibilidad para identificar información conocida por el bot de un **event** (evento) a otro.

> **Nota:** existen diferentes tipos de transformaciones para las variables Mammut, dependiendo del formato de los datos que se vayan a sustituir. Si queremos sustituir una unidad de información en formato de texto, podemos usar la transformación ```[variable]```; ahora, si queremos sustituir una imagen, un video o un audio en el knowledge, podemos indicarlo, escribiendo ```[variable_image]```, ```[variable_video]```, o ```[variable_audio]``` según sea el caso. Puedes ver esto con detalle en el artículo de [variables](../concepts/variables.md). **Para los propósitos de este tutorial, usaremos las variables para sustituir información en formato de ***texto***.**

### ¿Cómo funcionan?

Estas variables Mammut se agregan al corpus como piezas de código que se escriben en los events. Su propósito es reemplazar elementos de información variable que el chatbot pueda reconocer en las conversaciones como parte de su knowledge. Esto es posible porque se traza un **path** (ruta) a través de la **ontology** (ontología) que el chatbot podrá seguir para encontrar la información que necesita.

Por ejemplo, uno de los usos de las variables es **generalizar los events de un corpus**. En este sentido, un event como: _"¿Cuál es el precio de la lasaña?"_ podría usar una variable que sustituya la palabra "_lasaña_" por cualquiera de las opciones incluídas en el vertex 'dish'; **instances** (instancias) como *lasagna*, *sándwich*, *ensalada griega*, etc. De esta manera, el bot será capaz de entender cuando un usuario pregunta de la misma forma por platillos distintos sin necesidad de programar events diferentes para cada uno de estos. 

_Sylvia_ también podría usar una variable para **buscar la respuesta adecuada a esta solicitud** directamente en su knowledge base. En este caso, solo habría que agregar una variable al event de respuesta con el [path](../concepts/path.md) hacia el lugar del knowledge en la que se encuentra la información del *precio de la lasaña*. 

Además, las variables ayudan al bot a **identificar la información que conoce (almacenada en su lnowledge) en los eventos del corpus** para que así pueda almacenarla en su memoria a corto plazo y usarla a lo largo de la conversación. De esta manera, _Sylvia_ puede estar al tanto de los pedidos de sus usuarios para darles información pertinente sin necesidad de que estos deban repetirle varias veces la misma información.

## Entonces, ¿cómo podemos mejorar un corpus usando las variables?

Teniendo en cuenta lo explicado anteriormente, las variables Mammut pueden ayudarnos a mejorar un corpus M al permitirnos:

1. Generalizar los **events** del **corpus** para que un mismo event cubra una mayor cantidad de solicitudes relacionadas a items intercambiables alojados en el **knowledge**.

2. Darle al chatbot acceso a una base de datos (knowlege) para que pueda identificar la información conocida en los mensajes que recibe al tiempo que usa esta información para dar respuestas precisas a los usuarios.

3. Programar información sobre el contexto de modo que el chatbot esté al tanto de lo que ocurre en la conversación y de las necesidades del usuario.

    > **Nota:** en los próximos capítulos del tutorial veremos con más detalle cada una de estas funciones.

## ¿Qué aprendimos en esta sección?

En este primer capítulo, aprendimos sobre las limitaciones de un corpus sin variables. También aprendimos qué son las variables Mammut y cómo pueden ayudarnos a mejorar las capacidades de conversación de un chatbot Mammut.

## ¿Qué sigue?

En el próximo capítulo de este tutorial, aprenderemos paso a paso cómo utilizar las variables Mammut para ampliar el alcance de los events en el corpus de _Sylvia_.

[Paso a paso 1: generalizando events](event_generalization.md)
