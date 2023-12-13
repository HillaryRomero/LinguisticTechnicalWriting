# Meta

## Definición

El **meta** es un [vertex](vertices.md) singleton del **knowledge**, por ende, tiene una sola instance (instancia) que siempre se identifica con el **id** _KM_1_. Este es el único vertex de la [ontology](ontology.md) que se no se aloja en un spreadsheet del [package](package.md), si no que se encuentra en la presentation.

La función del **meta** es agregar datos a los que el bot puede acceder de forma más rápida, ya que este vertex es independiente del [scope](scope.md). En este sentido, el meta sirve para incluir la información que el bot sabe sobre sí mismo (como por ejemplo su nombre y sus funciones), o las respuestas a preguntas que este recibe con mucha frecuencia.

Conceptos relacionados: [knowledge](ontology.md), [package](package.md), [ontology](ontology.md), [vertex](vertices.md).

## Formato general

Dado que el vertex **meta** se aloja en la presentation, sus [properties](properties.md) se agregan, una a una, en distintos cuadros de texto de los slides. En todas las properties definidas en el meta, es obligatorio usar el prefijo "Meta" antes del nombre de la property. Cada property es separada de su valor usando los caracteres **"->"**, como se muestra a continuación:

| nombre de la propiedad | -> | valor |
| --- | --- | --- |
| MetaPropertyName | -> | Property Value |


## Ejemplo

En un cuadro de texto de la presentation se pone la información del vertex meta, tal como se observa en la siguiente tabla:  

| - |
| --- |
| MetaName -> Sylvia |
| MetaGreeting -> Hola! Cómo puedo ayudarte? |


> El nombre del vertex usado en las variables debe ser siempre "meta". Por ejemplo, si quisiéramos usar estas properties en una variable de un [corpus M](corpusM.md), se verían así: [`variable|meta.name`] y [`variable|meta.greeting`] respectivamente.