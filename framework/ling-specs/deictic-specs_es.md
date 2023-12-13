# Deíctico (es)

## MODELO DE DEÍCTICOS<a name="id50"></a>

Este documento tiene como propósito fundamental determinar qué significa, y cómo se usa, cada feature (*característica*) relacionado con el modelo de DEICTICS. El modelo DEICTICS (*deícticos*) es un modelado discreto de formas léxicas cuyo significado depende de circunstancias espacio-temporales relacionadas con el proceso comunicativo. Incluye no solo elementos claramente referenciales (como pronombres), sino también otras clases de palabras cuyo sentido puede formalizarse por medio de aspectos contextuales (adverbios de lugar, cantidad, etc.), principios lógicos sencillos (por ejemplo los adjetivos de cantidad) o por asociación a otros sistemas simbólicos (adjetivos numerales). DEICTICS también puede utilizarse para formalizar el sentido de palabras relacionadas con el cuerpo humano y su relación con el espacio (izquierda, arriba, entre otras).

Este modelado fusiona aspectos formales-lógios y cognitivos. En este sentido, se configura como una serie de features que adquieren distintos values (*valores*) discretos en distintas semánticas diversas.

## DEICTICS<a name="id1"></a>

Los **deictics** son palabras que se interpretan en relación con la situación comunicativa. Se le llama deíctico al elemento que remite a algo ya mencionado (o por mencionar) o que solo adquiere contenido al contextualizarse. El modelo DEICTICS asume una perspectiva más amplia que la otorgada por la gramática tradicional a los deícticos; en este sentido, no se toma como deíctico solamente aquella palabra que hace referencia a otra de forma directa, sino a cualquier elemento cuyo value semántico depende fuertemente de la situación comunicativa. Se trata de elementos que solamente pueden ser definidos con mucha dificultad en un lexicón tradicional y cuya semántica depende de la dinámica conversacional.

Debido a que la significación de los deícticos depende del contexto, solamente es posible conocerla en función del hablante. La deixis, que se encarga de señalar una parte del discurso, siempre se desarrolla a partir de un punto de referencia que depende de quien se expresa.

A continuación se explica cada feature (*característica*) utilizado en este modelado.


## GROUNDED<a name="id3"></a>

El feature **grounded** indica en términos generales cuál es el punto de referencia del deíctico desde la perspectiva de uno de los interactuantes. Cada uno de los values ha sido determinado pensando en la posible comunicación entre seres humanos o entre un ser humano y un chatbot. En todo caso, la perspectiva será siempre del destinatario, sea una persona o un chatbot.

#### User<a name="id4"></a>
El valor **user** indica que desde la perspectiva del chatbot o del destinatario, el deíctico se entiende como parte del dominio del usuario (destinador).

|   Class    | Value Type | Ejemplo      |
| ---------- | ---------- | -------------|
|  GROUNDED  |    User    | _Él viene **conmigo**._ |


#### User-discourse<a name="id5"></a>
El value **user_discourse** indica que desde la perspectiva del chatbot o del destinatario, el deíctico se entiende como parte del *discurso* del usuario (destinador).

| Class      | Value Type         | Ejemplo             |
| ---------- | ------------------ | ------------------- |
|  GROUNDED  |  User-discourse  | _Quiero **estas** zapatillas._|


#### Chatbot<a name="id6"></a>
El value **chatbot** indica que desde la perspectiva del chatbot, el deíctico se entiende como parte del dominio del chatbot o del destinatario.

| Class      |   Value Type  | Ejemplo          |
| ---------- | ------------- | ---------------- |
|  GROUNDED  |  Chatbot  | _Necesito **sus** servicios._    |


#### Chatbot-business<a name="id7"></a>
El value **chatbot-business** indica que desde la perspectiva del chatbot o del destinatario, el deíctico se entiende como una entidad (_la empresa_, por ejemplo) a la que pertenece el chatbot o destinatario. Se trata de una mención al destinatario y a una organización a la que el chatbot o destinatario representan.

| Class      | Value Type  | Ejemplo   |
| ---------- | ----------- | --------- |
|  GROUNDED  |  Chatbot,business  | _Necesito los servicios que **ustedes** ofrecen._         |


#### Discourse-now<a name="id8"></a>
El value **discourse-now** indica que desde la perspectiva del chatbot o del destinatario, el deíctico se entiende como el tiempo del enunciado en relación con el tiempo de la enunciación. Este uso se utiliza para formalizar algunos adverbios temporales.

| Class      | Value Type     | Ejemplo      |
| ---------- | -------------- | ------------ |
|  GROUNDED  | Discourse-now  | _**Ayer** pregunté y estaban agotados._  |


#### Discourse-here<a name="id9"></a>
El value **discourse-here** indica que desde la perspectiva del chatbot o del destinatario, el deíctico se entiende como el lugar del enunciado en relación con el lugar de la enunciación. Se usa para formalizar adverbios de lugar.

| Class      | Value Type     | Ejemplo       |
| ---------- | -------------- | ------------- |
|  GROUNDED  | Discourse-here | _**Allá** hace frío._     |


#### Manner<a name="id10"></a>
El value **manner** indica que desde la perspectiva del chatbot o del destinatario, el deíctico se entiende como el calificador de una acción. Este uso se utiliza para formalizar algunos adverbios de modo.

| Class   | Value Type | Ejemplo       |
| ------- | ---------- | ------------- |
|  GROUNDED  |  Manner   | _Los precios subieron **considerablemente**._|


#### Body-position<a name="id11"></a>
El value **body-position** indica que desde la perspectiva del chatbot o del destinatario, el deíctico apunta a una posición o dirección con relación al chatbot o al usuario.

| Class      | Value Type     | Ejemplo   |
| ---------- | -------------- | --------- |
|  GROUNDED  | Body-position  | _Los baños están **arriba**._ |


## LOGICAL FORM<a name="id12"></a>

El feature **logical Form** indica la formalización de un acuerdo lógico entre el usuario (destinador) y el chatbot (o destinatario) cuando el deíctico no sugiere perspectivas diferentes del referente entre los interactuantes. Este acuerdo lógico es una aproximación "lógica" al significado del deíctico,es decir, no se trata de un significado fijo y exacto, sino de una aproximación relativa. Lo ideal es que esta aproximación lógica se realice por medio de conveciones que sean lo más claras posible. Eso no implica un lenguaje formal como tal, sino expresiones que pueden utilizar símbolos no lingüísticos para representar de manera informal dichas relaciones lógicas.

Ejemplo: pocas - 40>quantity>0 (aquí "pocas" se define como una cantidad menor al 40% pero superior al 0%). Se pueden utilizar signos lógicos, operadores matemáticos, etc. Cabe destacar que los símbolos o cantidades no son exactos en muchos casos, sino que se toman como aproximaciones formales solamente.

| Class       |   Value Type     | Ejemplo       |
| ----------- | ---------------- | ------------- |
|  LOGICAL FORM  | 40>quantity>0  | _Quedan **pocas** manzanas._|


## SPECIFICITY<a name="id13"></a>

El feature **specificity** indica si el significado/referencia es más o menos específico, o si es más o menos general. Se utiliza sobre todo para distinguir si un deíctico se refiere a un conjunto de elementos no necesariamente indetificables en un principio, o si bien establece una referencia a un conjunto definido compuesto de elementos cuya identidad se conoce de antemano.

#### Specific<a name="id14"></a>

El value **specific** refiere a un lugar, tiempo, elemento, o conjunto de elementos en particular. En otras palabras, el deíctico se refiere a un elemento claramente identificable.

|   Class   | Value Type |    Ejemplos     |
| --------- | ---------- | -------------- |
|   SPECIFICITY  |  Specific  | _**Esta** mañana desayuné en el patio;  **Estos** zapatos me quedan grandes._|


#### General<a name="id15"></a>

El value **general** refiere a un conjunto de elementos no necesariamente indetificables por separado, pero relacionados en un conjunto por algún factor. Este conjunto es una agrupación de elementos de los que se pueden conocer algunos sí, y otros no.

| Class    |   Value Type   |    Ejemplos     |
| -------- | -------------- | -------------- |
|   SPECIFICITY  |  General   | _Lo quiero **todo**; No tengo **muchas** cosas en mi escritorio._          |


## DISTANCE TYPE<a name="id16"></a>

El feature **Distance Type** indica el tipo de distancia metafórica que existe entre el usuario y lo referido por el deíctico/palabra. Esta distancia puede ser física o social.

#### Social<a name="id17"></a>

El value **social** indica que el deíctico refiere a una entidad *social* distinta o igual al usuario (PRO PERSONAL). Esta distancia se entiende como una "lejanía" o "asimetría" entre el grounded y lo denotado por el deíctico. Por ejemplo, las diferencias sociales entre el uso de "tú" y "usted" en algunas variedades del español indican una cercanía/lejanía de tipo social y no física.

|   Class    | Value Type |   Ejemplo     |
| ---------- | ---------- | ------------- |
|  DISTANCE TYPE |   Social   | _**Yo** estoy aquí; **Él** no vendrá._ |


#### Physical<a name="id18"></a>

El value **physical** indica que el deíctico indica una distancia física entre lo referido y el usuario (destinador).

|   Class     | Value Type |   Ejemplo     |
| ----------- | ---------- | ------------- |
|  DISTANCE TYPE |  Physical  | _**Este** zapato me aprieta; **Aquel** señor se fue sin pagar._   |


## DISTANCE FROM USER<a name="id19"></a>

El feature **distance from User** indica a qué distancia, social o física, está lo referido por el deíctico. Se trata de una distancia relativa en cada caso. Se proporcionan tres values: near, medium y far.

#### Near<a name="id20"></a>

El valor **near** indica que lo referido está relativamente cercana con respecto al usuario (destinador).

| Class   | Value Type | Ejemplo   |
| ------- | ---------- | ---------
|  DISTANCE FROM USER  |    Near    | _**Este** zapato me aprieta - (physical); **Mis** zapatos me aprietan - (social)._ |

#### Medium<a name="id21"></a>

El value **medium** indica que lo referido está a una distancia relativa media en relación con el usuario (destinador).

| Class       | Value Type | Ejemplo    |
| ----------- | ---------- | ---------- |
|  DISTANCE FROM USER |   Medium   | _**Ese** zapato me aprieta - (physical); **Tus** zapatos me aprietan - (social)._      |


#### Far<a name="id22"></a>

El valor **far** indica que lo referido está lejos del usuario (destinador).

| Class       | Value Type | Ejemplo    |
| ----------- | ---------- | ---------- |
|  DISTANCE FROM  USER |    Far     | _**Aquel** zapato me aprieta - (physical); El zapato de **él** me aprieta - (social)._ |


## SENTIMENT<a name="id23"></a>

El feature **sentiment** indica la polaridad en la interpretación del referente, lo dota de connotaciones positivas, negativas o neutras. El feature **sentiment** se incluye en el modelo de DEICTICS debido a que se requiere la comprensión del contexto situacional para adjudicar el value apropiado de esta categoría.

#### Positive<a name="id24"></a>

El value **positive** indica que el deíctico dota al referente de una polaridad positiva en el contexto de la situación discursiva.

| Class      | Value Type     | Ejemplo     |
| ---------- | -------------- | ----------- |
| SENTIMENT  |    Positive    | _Tienes **muchos** zapatos._  |


#### Negative<a name="id25"></a>

El value **negative** indica que el deíctico dota al referente de una polaridad negativa en el contexto situacional.

| Class      | Value Type     |   Ejemplo    |
| ---------- | -------------- | ------------ |
| SENTIMENT  |    Negative    | _Tienes **pocos** zapatos._ |

#### Neutral<a name="id26"></a>

El value **neutral** indica que el deíctico no dota al referente de una polaridad positiva o negativa, sino que evalúa muy discretamente al referente (polaridad neutra).

| Class      |  Value Type     |  Ejemplo    |
| ---------- | --------------- | ----------- |
| SENTIMENT  |     Neutral    | _Tienes **varios** zapatos._ |


## EMBODIMENT<a name="id27"></a>

El feature **embodiment** relaciona los modelos con dimensiones del lenguaje determinadas por la configuración del cuerpo humano y su interacción con el entorno.

#### Body<a name="id28"></a>

El value **body** indica que el deíctico determina un referente que es asociado con el cuerpo humano. Esta asociación puede ser con todo el cuerpo o con una parte de él.

|   Class    |   Value Type   |    Ejemplo     |
| ---------- | -------------- | -------------- |
| EMBODIMENT |      Body      | _**Yo** no hice nada._  |


#### Movement<a name="id29"></a>

El value **movement** indica que el deíctico está relacionado con la capacidad de movimiento del GROUNDED.

| Class      | Value Type     | Ejemplo        |
| ---------- | -------------- | -------------- |
| EMBODIMENT |    Movement    | _Voy al gimnasio **frecuentemente**._ |


#### Orientation<a name="id30"></a>

El value **orientation** indica que el deíctico determina una posición espacial o temporal con relación al GROUNDED.

| Class      | Value Type     | Ejemplo      |
| ---------- | -------------- | ------------ |
| EMBODIMENT |   Orientation  | _**Hoy** fui a trotar - (temporal);  **Ahí** estudié yo - (espacial)._       |


#### Object interaction<a name="id31"></a>

El value **object interaction** indica que el deíctico determina, directa o indirectamente, un objeto (generalmente físico) de la interacción comunicativa, y que puede ser manipulable por cualquiera de los interlocutores.

|   Class    |   Value Type     |    Ejemplo     |
| ---------- | ---------------- | -------------- |
| EMBODIMENT |   Object interaction    | _**Esto** está delicioso; **Mis** trabajos está sobre la mesa._


## ONTOLOGIC ANCHORS<a name="id32"></a>

Este feature se usa cuando se posee una upper ontology (*ontología superior*) que puede utilizarse para indicar la referencia del deíctico. El feature **ontology anchors** indica el nodo de información de la upper ontology al que apunta la palabra en cuestión.

#### Place<a name="id33"></a>

El value **place** indica que el deíctico está relacionado al vértice "place" de una upper ontology, puede ser una instancia temporal (place time) o espacial (place space).

| Class      | Value Type     | Ejemplo     |
| ---------- | -------------- | ----------- |
| ONTOLOGIC ANCHORS  |     Place      | **Mañana** voy al gimnasio - (_place-time_). **Ahí** está lo que me pediste - (_place-space_)|

#### Agent<a name="id34"></a>

El value **agent** indica que el deíctico está relacionado al vértice agent de una upper ontology.

|Class |    Value type     |       Definition         | Ejemplo |
|------| ----------------- | ------------------------ | ------- |
ONTOLOGIC ANCHORS| Agent interactant | Lo referido por el deíctico es el usuario. | _**Yo** voy al gimnasio._ |
ONTOLOGIC ANCHORS|  Agent chatbot    | Lo referido por el deíctico es el chatbot. | _**Tú** eres al que estaba buscando._ |
ONTOLOGIC ANCHORS| Agent social agent | Lo referido por el deíctico es una entidad social (_una institución_) que no está dentro de la interacción. | _**Eso** _(el local)_ estaba cerrado._
ONTOLOGIC ANCHORS| Agent physical agent | Lo referido por el deíctico es una entidad física (_sujeto concreto_) que no está dentro de la interacción. | _**Él** estuvo aquí._ |


#### Object<a name="id35"></a>

El value **object** indica que el deíctico está relacionado con el vértice "object" de una upper ontology, puede ser una instancia física (physica Object) o social (social object).


|Class|   Value type   | Definition | Ejemplo |
| ---| --------------- | ---------- | ------- |
ONTOLOGIC ANCHORS| Physical object | Lo referido por el deíctico es un producto. | _Quiero **estos** zapatos._ |
ONTOLOGIC ANCHORS| Social object   |  Lo referido por el deíctico es un servicio | _Quiero saber **cómo** funciona._ |



#### Social contextualization<a name="id36"></a>

El value **social contextualization** indica que el deíctico está relacionado al vértice social contextualization de una upper ontology y que este complementa una circunstancia.

| Class      | Value Type     | Ejemplo     |
| ---------- | -------------- | ----------- |
| ONTOLOGIC ANCHORS  |     Social contextualization     |  _**Frecuentemente** voy al gimnasio._



## REFERENCE TYPE<a name="id42"></a>

El feature **reference type** se encarga del señalamiento a una expresión del discurso o a un elemento de la puesta en escena del discurso; se refiere a elementos básicos de la comunicación, y a conceptos de tiempo y espacio. Por lo tanto, la _reference type_ indicará el tipo de referencialidad que exista entre una parte del *discurso* y el elemento deíctico.

#### Interlocutors<a name="id43"></a>

Es aquella expresión deíctica que se refiere al papel que desempeña un participante. Estas referencialidades pueden ser de primera, de segunda o de tercera persona. Algunos ejemplos de referencialidades de primera persona son los siguientes pronombres y determinantes *yo, nosotros, nuestro, mi, mío, míos*.


| Class      |  Value Type | Ejemplo    |
| ---------- | ----------- | ---------- |
| REFERENCE TYPE   | Interlocutors   | _**Yo** compro demasiadas cosas innecesarias._|


#### Location<a name="id44"></a>

La **reference location** o deixis de lugar es una expresión deíctica que sitúa a un participante en el espacio e indica cercanía o lejanía, como por ejemplo «aquí, allí, ahí».

| Class      |  Value Type | Ejemplo    |
| ---------- | ----------- | ---------- |
| REFERENCE TYPE   | Location   | _Yo nací **aquí** en Caracas._|


#### Time<a name="id45"></a>

La **reference time** o deixis de tiempo es un referente temporal en relación con un momento en particular que suele ser el instante en que se articula el mensaje.

| Class      |  Value Type | Ejemplo    |
| ---------- | ----------- | ---------- |
| REFERENCE TYPE   | Time | _**Hoy** es el examen de inglés._|


#### Other references<a name="id46"></a>

Sirve para identificar un elemento dentro del discurso que no forma parte ni de los interlocutores, ni de la referencia de un lugar, ni de un tiempo.

| Class      |  Value Type | Ejemplo    |
| ---------- | ----------- | ---------- |
| REFERENCE TYPE   | Other referents |_**Increíblemente** hoy saldré temprano del trabajo._|


## T-POS, F-POS, REPRESENTATION, EXCHANGE<a name="id37"></a>

Las columnas conformadas por los parámetros **T-POS, F-POS, representation, exchange** sirven para señalar qué elemento en la cláusula acompaña o funciona como referente de un deíctico específico. Se trata de referencias endofóricas directas, o de referencias indirectas a un elemento mencionado anteriormente por alguno de los interlocutores.

Cada una de estas columnas mencionadas no indican la función de ese deíctico en la cláusula, sino la del antecedente o acompañante del mismo (si lo hay). Por lo tanto, la clasificación dependerá de la función sintáctica del antecedente o la palabra relacionada.

La utilidad es que la información presente en las columnas, proporcione pistas que muestren cuál elemento de la cláusula podría ser el antecedente o elemento que acompañe al deíctico en el discurso previo.

## T-POS<a name="id38"></a>

#### Noun<a name="id39"></a>

El value **noun** indica que el deíctico (él) tiene como referente a un **noun** (Carlos).

| Class      | Value Type| Ejemplo  |
|------------| ------------------| ------------|
| T-POS      | Noun      | _**Carlos** es ingeniero de sistemas. **Él** trabaja en Microsoft._|


## F-POS<a name="id40"></a>

#### Thing<a name="id41"></a>

El value **thing** indica que el deíctico (su) acompaña a un **thing** (película).

| Class      | Value Type  |  Ejemplo       |
| ---------- | ----------- | -------------- |
| F-POS      | Thing     | _¿Cuál es **su** **película** favorita?_|


También el value **thing**, depende de cual sea el caso, serviría para indicar que el deíctico (que) tiene como referente a un **thing** (María).

| Class      | Value Type | Ejemplo       |
| ---------- | ---------- | ------------- |
| F-POS      | Thing     | _Yo me vine con **María** **que** maneja mejor._|


## REPRESENTATION<a name="id42"></a>

#### Actor<a name="id43"></a>

El value **actor** indica que el deíctico (ella) tiene como referente a un **actor** (la señora Ana).

| Class       | Value Type | Ejemplo         |
| ----------- | ---------- | --------------- |
| REPRESENTATION      | Actor      |  _**La señora Ana** lavó los baños. **Ella** los dejó impecables._|


#### Goal<a name="id44"></a>

El value **goal** indica que el deíctico (esos) tiene como referente a un **goal** (caramelos).

| Class   | Value Type | Ejemplo     |
| ------- | ---------- | ----------- |
| REPRESENTATION  | Goal | _Paula trajo **caramelos** para todos.**Esos** son los tuyos._|


#### Possessor<a name="id45"></a>

El value **possessor** indica que el deíctico (ella) tiene como referente a un **possessor** (Claudia).

| Class     | Value Type | Ejemplo        |
| --------- | ---------- | -------------- |
| REPRESENTATION      | Possessor  | _**Claudia** tiene muchos trabajos por corregir. **Ella** siempre está ocupada._|


#### Possessed<a name="id46"></a>

El value **possessed** indica que el deíctico (ese) tiene como referente a un **possessed** (punto de venta).

| Class   | Value Type | Ejemplo     |
| ------- | ---------- | ----------- |
| REPRESENTATION      | Possessed  | _El restaurante tiene **punto de venta**, pero **ese** siempre falla._|


#### Entity<a name="id47"></a>

El value **entity** indica que el deíctico (que) tiene como referente a un **entity** (el muchacho).

| Class     | Value Type | Ejemplo        |
| --------- | ---------- | -------------- |
| REPRESENTATION      | Entity     |  _**El muchacho** **que** tiene camisa blanca es el entrenador._  |


## EXCHANGE<a name="id48"></a>


#### Subject<a name="id49"></a>

El value **subject** indica que el deíctico (ese) tiene como referente a un **subject** (el sábado).

| Class      |  Value Type | Ejemplo    |
| ---------- | ----------- | ---------- |
| EXCHANGE   | Subject   | _**El sábado** es el día de compras. **Ese** es el mejor día del fin de semana._|


#### Complement<a name="id50"></a>

El value **complement** indica que el deíctico (esas) tiene como referente a un **complement** (manzanas verdes).

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| EXCHANGE   | Subject   | _Hoy compré **manzanas verdes.** **Esas** son mis favoritas._ |
