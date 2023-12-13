# Default scenario (escenario por defecto)

## Definición

Un **default scenario** (o simplemente "default") es una configuración de una instance que se incorporará por defecto en el **scope** de una conversación. Esta es una herramienta que ayuda al bot a solventar conversaciones en momentos donde el usuario no le provea la contextualización necesaria (véase [scope](scope.md)). Los llamamos **default scenarios** porque permiten que el bot asuma el valor de una [variable](variables.md), en aquellos momentos cuando el usuario no lo dé explícitamente.

Los defaults están condicionados a una de estas situaciones: [channel](channels.md), **subchannel** o los datos que ya están en **scope** (véase [condition](condition.md)). Por eso, además de enseñarle al bot qué [instance](instances.md) debe incluir en el scope de la conversación, también le especificamos bajo qué condición serán válidos estos datos.

> **Nota:** no hay incoveniente si en el package se define un default condicionado a un channel con el que no existe (aún) integración. Esta configuración empezará a ser válida en el momento en que la integración con dicho channel se haga.

Las instances por defecto pueden ser agregadas a los distintos **vertices** de un [path](path.md) de la **ontology** desde un Mammut package. De esta manera, un bot estará preparado para diversas situaciones utilizando el mismo package.

Conceptos relacionados: [scope](scope.md), [variables](variables.md), [condition](condition.md), [ontology](ontology.md).

## Formato general

**Defaults** es una sheet del **Mammut package**. Los nombres de las columnas de esta sheet se encuentran en la fila #2 y, a partir de allí, cada fila contiene la información correspondiente al dato por defecto de un solo vertex, partiendo del **entry point**.

La estructura de la sheet defaults es la siguiente:

 |  Campo  |  Descripción  | Obligatoriedad |
 |  ----   |  ----------   | -------------- |
 |  **variable**  |  Columna en la que se agrega la variable mammut a la que se le vincularán datos por defecto. Esta debe culminar en un vertex, no en una property.  | Obligatorio. |
 |  **ontology_id**  |  Columna en la que se agrega el **id** de la instance que se asumirá por defecto. Esta instance debe ser parte del último vertex que se puso en el campo de variable. | Obligatorio |
 |  **lambda_lexical_form**  |  Columna en la que se agrega una condición que se debe cumplir para asumir los datos del campo variable y ontology_id como verdaderos. (Véase [condition](condition.md) | Obligatorio |

> **Nota:** la información que se aporta en el campo **lambda_lexical_form** determina el **canal**, **sub_canal** o la información en **scope** para el cual aplica la definición. Esta especificación permite que se configuren diversos datos para los posibles canales o sub canales por los cuales el bot va a interactuar.

## Ejemplo

| variable | ontology_id | lambda_lexical_form |
| -- | -- | -- |
| tienda | JS_1 | 1 == 1 |
| tienda.sell_several.varita | V_1 | base_closure.channel == "Slack" |
