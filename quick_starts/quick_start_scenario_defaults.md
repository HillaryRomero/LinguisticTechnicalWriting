# Guía de inicio rápido: ¿cómo incorporar instances al default?

Esta guía de inicio rápido describe los pasos para que tu bot pueda responder con información configurada por defecto. Por medio de los [default scenarios](../concepts/default.md) podrás configurar instancias por defecto al [scope](../concepts/scope.md) de un bot.  A través de los default scenarios tu bot podrá responder de manera eficiente cuando un usuario no provea toda la información necesaria.

Supongamos que un usuario hace preguntas como: "_¿cuáles son los horarios?_" o "_¿cuál es el precio de una familiar?_. Para responder a estas preguntas el bot necesita información previa que le permita identificar la 'tienda' a la cual el usuario hace referencia o el 'platillo' del menú que le interesa. En estos casos, la información que necesita el bot para entender la petición está ausente.

Si un usuario no provee datos específicos en sus preguntas esto representa un inconveniente para el bot. Por esta razón, crearemos **default scenarios**. Estos nos servirán para incorporar información al scope de nuestro bot en los casos donde el usuario no especifique algún dato; por ejemplo, el nombre de la tienda o el nombre del platillo.

## Requisitos previos

* Instalación del _Mammmut Services_ (MS).

* Crea el **spreadsheet** de un bot con un **corpus M**. Puedes hacer una copia del spreadsheet de [_Sylvia_](https://docs.google.com/spreadsheets/d/1PipFFyOWTcou9yYm3Uyc_bcNmnzh7kmKHdqR2jKgkyc/edit?usp=sharing). _Sylvia_ es un bot que atiende a los usuarios de _Mammut Restaurant_.

* Integra tu bot con [dos o más **canales**](channels_connection_es.md). En esta guía utilizaremos a *Sylvia* que es un bot que hemos integrado con tres canales; *SMS*, *Whatsapp* y *Slack*.


## Lecturas previas

Antes de comenzar te recomendamos leer los siguientes artículos:

* Artículo de [scope](../concepts/scope.md).
* Artículo de [variable](../concepts/variables.md).
* Artículo de [default scenarios](../concepts/default.md).
* Guía rápida de [solicitud de contexto a un usuario](quick_start_lambda_condition.md).

## Default scenarios

 Los **default scenarios** incorporan al **scope** la instancia que el usuario ha dejado ausente al momento de emitir una petición, de esta manera, el bot solventa la necesidad de contexto.

> **Nota:** el [scope](../concepts/scope.md) de una conversación se va creando a medida de que el bot reconoce una instance que es parte de su **knowledge** en el tiempo de la conversación. Con los **default scenarios** se podrán incluir instancias al scope cuando el usuario no las exprese.

Los **default scenarios** pueden ser condicionados a un canal por donde se comunique nuestro bot a través de una expresión de [condition](../concepts/condition.md). Por ejemplo,  si el 73% de los usuarios que escriben por el canal _WhatsApp_ están interesados en la **lasaña**, entonces podemos condicionar este **scenario default** con el nombre del plato, únicamente cuando los usuarios se comuniquen por dicho canal.

> **Nota:** un escenario por defecto crea una condición relacionada al canal, sub-canal o la información en scope para contextualizar a un bot cuando este no tenga la información necesaria.

Las conditions determinan el comportamiento del bot. Este comportamiento se basa en si se cumple o no una condition. En caso de que la condition se cumpla, la información configurada por defecto se incorporará al scope. De lo contrario, si la condition no se cumple, el scope no sufrirá cambios. Por ejemplo, si el usuario se comunica por un canal diferente a _WhatsApp_, la condition no se cumplirá y, por lo tanto, el default scenario tampoco aplicará.

## ¿Cómo incorporar instances al scope por medio de los scenarios default?

1. Para comenzar, **entra al spreadsheet de un package y abre el sheet defaults**.

2. **Especifica una variable:** La variable debe señalar el lugar del knowledge donde se buscará la información por defecto para cuando no exista valor en el scope.

    * En el sheet de **defaults** de _[Sylvia](https://docs.google.com/spreadsheets/d/1PipFFyOWTcou9yYm3Uyc_bcNmnzh7kmKHdqR2jKgkyc/edit#gid=390039748)_ escribimos en la columna 'variable' el **path** del knowledge: ```restaurant```

       > **Nota:** recuerda que estas configuraciones deben seguir la lógica del **scope**, así que el primer vertice que se configurará será el **entry point**. Luego, puedes seguir configurando los demás vertices del knowledge ('dish', por ejemplo) siguiendo el mismo proceso.

3. **Indica el id de la [instance](../concepts/instances.md) que queremos definir:** Esta instance debe formar parte del **vertex** dispuesto en el campo 'variable'.

      * En el campo **ontology_id** escribimos _KR_1_. Esta es la identificación de la instance _Mammut Restaurant_ del entry point.

4. **Crea la condición que se debe cumplir para que los datos anteriormente definidos sean válidos:** Este campo debemos llenarlo con una [**condition**](../concepts/condition.md).

      * En este caso, en el campo **lambda_lexical_form** escribimos **True** para indicar que la condición siempre será válida.

Al terminar estos pasos, tu instance incorporada a los default scenarios se verá así:

| variable | ontology_id | lambda_lexical_form |
| -------- | ----------- | ------------------- |
| ```restaurant``` | KR_1 | ```True``` |

## ¿Cómo condicionar un default scenario a un canal en especifico?

Ahora, si deseas configurar otro default scenario y condicionarlo a un canal específico:

1.  **Ubícate en la fila siguiente del sheet defaults**

2.  **Llena el campo 'variable' con un path del knowledge:** Escribe en el campo **variable** el path del knowledge: ```restaurant.sell_several.dish```.

3. **Llena el campo ontology_id:** Para llenar este campo **ontology_id** escribe _KP_3_ (lasaña).

4. **Llena el campo lambda_lexical_form:** Especifica en el campo **lambda_lexical_form** la condición que se debe cumplir para que los datos anteriormente definidos sean válidos.
Utiliza una expresión de [condition](../concepts/condition.md) para llenar este campo. En este caso emplea una expresión de igualdad ( a **==** b) para indicar que la información definida será válida solo cuando el **channel** sea igual a "_Whatsapp_".

      * Primero, idica en 'a' el elemento al que atenderá la condición. Escribe ```base_closure.channel```.
      * Después, separado por un espacio, escribe el signo que determina la expresión. En este caso, el signo será ```==```.
      * Finalmente, define 'b'. En esta caso 'b' será _"Whatsapp"_.

Al terminar estos pasos, tu sheet **defaults** se verá así:

| variable | ontology_id | lambda_lexical_form |
| -------- | ----------- | ------------------- |
| ```restaurant``` | KR_1 | ```True``` |
| ```restaurant.sell_several.dish``` | KP_3 | ```base_closure.channel == "Whastapp"``` |

El cuadro anterior indica lo siguiente:
Cuando un usuario se comunique por cualquiera de los canales con los que está integrada _Sylvia_ la variable ```[variable|restaurant.name]``` tendrá el valor **Mammut Restaurant**. Y cuando un usuario se comunique por _Whatsapp_ la variable ```[variable|restaurant.sell_several.dish.name]``` tendrá el valor de **lasaña**.

Finalmente, al terminar esta guía rápida puedes verificar lo que hiciste [aquí](https://docs.google.com/spreadsheets/d/1T_n57sue6n4HBMy5zCJg69gLYQXFR-LMWUHBRxijsN8/edit#gid=390039748).

## Resumen
En esta guía rápida seguiste los pasos para incorporar instances al scope de tu bot a través de los **default scenarios**. Estos scenarios permitirán al bot responder de manera más eficiente. Además, pudiste condicionar los **scenarios defaults** a un canal en especifico. Este proceso lo hiciste en 3 etapas: 1) Especificaste un path a un dato guardado en el knowledge de tu bot; 2) Indicaste el id de la instance que querías definir; 3) Creaste una condición para que los datos definidos fuesen válidos. De esta manera, lograste aumentar la efectividad de tu bot para que pueda responder la mayor cantidad de events.

## Lecturas recomendadas

* Guía rápida de [solicitud de contexto a un usuario](quick_start_lambda_condition.md).
