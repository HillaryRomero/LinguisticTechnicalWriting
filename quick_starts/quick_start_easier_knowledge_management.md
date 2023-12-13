# Guía rápida: maneja fácilmente los valores del knowledge

Esta guía rápida te ofrecerá una forma sencilla de manejar el valor de una **property** de una [instance](../concepts/instances.md) usando cuadros de texto en un **mammut package**.

El **knowledge** de los chatbots mammut se construye, mayormente, en tablas de un **spreadsheet**. Sin embargo, el formato de las tablas puede ser incómodo para cuando se necesiten especificar valores de texto que sean extensos. Por ejemplo, piensa en un texto como el siguiente:

_Puedes elegir 3 de estos rellenos para sándwiches: queso, jamón y queso, ensalada de jamón, salchicha, queso y cebolla, mayonesa de huevo, mayonesa de atún o ensalada de pollo._

Esta es la descripción de uno de los platillos de un restaurant. En esta guía aprenderás una manera de incorporar valores largos en un cuadro de texto de la presentation.

## Antes de comenzar

* Lee los [conceptos básicos](../concepts/basic_concepts_corpus_m-es.md).

## Requisitos previos

* Instalación de _Mammut Services_ (MS).

* Crea un **package mammut** con un [**corpus M**](../concepts/corpusM.md) y un [**knowledge**](../concepts/ontology.md). 

Para seguir esta guía rápida, puedes a utilizar el package de _Sylvia_, un chatbot que atiende a los usuarios de _Mammut Restaurant_. Su package cuenta con un corpus M y un knowledge de donde obtiene los datos que le permiten atender a los clientes; los platos de los restaurantes y las bebidas con las que se pueden acompañar estos platos en las dos locaciones de la cadena.
   * Spreadsheet: desde tu cuenta Google, haz una copia del **spreadsheet** de [Sylvia](https://docs.google.com/spreadsheets/d/12u_dE-b7zu8u2JzevBuYJCUyyOke0vRWmCBECWXPsus/edit?usp=sharing).
   * Presentation: desde tu cuenta Google, haz una copia de la **presentation** de [Sylvia](https://docs.google.com/presentation/d/1NDj6a3CLo7-zOP9PGgut_sDSCWFbKYPW2KHbCRyBTrs/edit?usp=sharing)

## Maneja fácilmente los valores del knowledge

Un cuadro de texto es un lugar mucho más cómodo para incorporar párrafos largos. Esto facilita la incorporación del valor de una property del knowledge. Para hacerlo, simplemente debes agregar los textos extensos en un cuadro de texto de la presentation sin identificación alguna. Es necesario, además, sustituir el contenido de la celda correspondiente en el sheet del vertex, por una referencia a su ubicación en la presentation.

La referencia incluye el número de lámina, el tipo de elemento en la presentation (text o image), y las primeras palabras (mínimo las tres primeras palabras) que forman parte del texto escrito en el cuadro de texto, usando el formato: _slide|#pagina-tipo-Contenido inicial_ como en el siguiente ejemplo:

`slide|1-text-Puedes elegir 3 de estos`

A continuación, observemos cómo poner partes del **knowledge** en la **presentation**.

1. En tu [presentation](https://docs.google.com/presentation/d/1NDj6a3CLo7-zOP9PGgut_sDSCWFbKYPW2KHbCRyBTrs/edit?usp=sharing) crea un nuevo cuadro de texto donde vas a colocar el valor del knowledge, sin ninguna identficación particular.

    * En el cuadro de texto introduce exactamente el texto que estaría en la celda:

        `Puedes elegir 3 de estos rellenos para sándwiches: queso, jamón y queso, ensalada de jamón, salchicha, queso y cebolla, mayonesa de huevo, mayonesa de atún o ensalada de pollo.`

2. En tu [spreadsheet](https://docs.google.com/spreadsheets/d/1PipFFyOWTcou9yYm3Uyc_bcNmnzh7kmKHdqR2jKgkyc/edit#gid=1353852089)  busca el lugar del knowledge donde se encuentra la property e instance que estamos llenando.

    1. Ubica en el **sheet** del **vertex**, "dish", por ejemplo.
    2. Identifica la columna donde está la property "description".
    3. Identifica la instance a la que corresponde el texto "KP_2".  

3. En la celda del knowledge que te interesa sustituir o rellenar, debes sustituir o llenar la celda donde debería estar la descripción con la referencia de la presentation.

    1. Escribe "`slide`" y separa con una barra vertical.
    2. Escribe el número de lámina de la presentation donde está el cuadro de texto, por ejemplo, _1_.
    3. Separa con un guión "-" y sin dejar espacios, agrega _text_ (este el tipo de elemento).
    4. Por último, especifica el pedazo inicial del cuadro de texto que te interesa referenciar. Puedes probar con las primeras cuatro o cinco palabras, ejemplo: _Puedes elegir 3 de estos_.

El texto debería quedar así: ``slide|1-text-Puedes elegir 3 de estos``

Esta posibilidad puede ser útil para las partes del knowledge que puedan ser muy largas. Eso facilita el manejo de contenido que podría resultar complejo del knowledge.

Puedes verificar lo que hiciste con los siguientes archivos

* [Archivo de verficación del spreadsheet](https://docs.google.com/spreadsheets/d/1-b5SU2BOtTRKJXnzn3QZQLkqH6dwYN0Q6r91kvt7FGU/edit#gid=1353852089)
* [Archivo de verificación de la presentation](https://docs.google.com/presentation/d/1OrcDOKDBUnNXqUNuqIddhTmHcJoMeiojs3PbXmu6j-A/edit?usp=sharing)
