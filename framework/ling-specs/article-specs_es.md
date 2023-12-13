# Artículo (es)

## MODELO DE ARTÍCULOS<a name="id50"></a>

Este documento tiene como propósito fundamental determinar qué significa y cómo se usa cada feature (*característica*) relacionado con la formalización de artículos (ARTICLES).

El modelo ARTICLES (*artículos*) se trata de un modelado cognitivo que pretende organizar y analizar la funcionalidad de los artículos en el discurso, a través de unos features que se encargan de codificar las relaciones de estos en el espacio. El modelo abarca una serie de parámetros que permite analizarlos y ubicarlos en el contexto.

A continuación se explica cada feature (*característica*) utilizado en este modelo.

## ARTÍCULOS (ARTICLES)<a name="id1"></a>

El **artículo** es un elemento que sirve para delimitar la extensión significativa y los límites de referencialidad del grupo nominal del que forma parte, y que ayuda, por lo tanto, a presentar su referente o a identificarlo en el contexto. Una de las funciones del artículo, por ejemplo, es la nominalización (_el verde_, _el morado_).

En español el artículo tiene como propósito indicar la totalidad/parcialidad de la referencia de un sustantivo en el texto, la situación discursiva o en el léxico (Givón, 2005) -por extensión, la idea de totalidad puede reinterpretarse, en alguno casos, como límites definidos de la referencia-. Ahora bien, esta totalidad se puede interpretar de forma distinta en dimensiones semánticas diferentes, con lo cual la totalidad/parcialidad (límites claros/difusos) adquirirá una interpretación relativa en cada una de esas dimensiones.

## TYPE<a name="id2"></a>

Existen dos clases de artículo: el indefinido y el definido. Los artículos definidos o indefinidos dotan al sustantivo que acompañan de matices semánticos de acuerdo con las dimensiones que se manifiesten en su uso. Estas dimensiones se presentarán en casos en los que el artículo denote tanto una idea de totalidad, como de parcialidad.

#### Indefinite<a name="id3"></a>

El artículo **indefinite** se usa para presentar entidades nuevas en el discurso, es decir, cuando no se ha dado información previa de estas entidades.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Indefinte | _Hoy he recibido **una** carta_|

#### Definite<a name="id4"></a>
El artículo **definite**  permite hacer referencia a una entidad que se supone identificable por el oyente.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Definte | _Hoy he recibido **la** carta._ |

#### Zero<a name="id5"></a>
En ciertos sintagmas nominales el artículo está ausente, esta ausencia es denominada artículo **zero**. La ausencia de artículo o artículo zero se presenta cuando a este le sigue una "categoría nominal". Las categorías nominales son construcciones en las que el sustantivo no presenta ningún tipo de determinación, por lo tanto, con ellas el artículo se puede omitir.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Zero | _Hoy he recibido **Ø** cartas._ |

El artículo **zero** indica, generalmente, una indeterminación con respecto a un total. Por lo general, este caso sin artículo va con participates prototípicamente no humanos.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Zero | _Tengo **Ø** peluches en mi habitación._ |

Además del artículo **zero**, existen grupos nominales que no pueden llevar artículo. Los grupos nominales que no van precedidos por un elemento que sirve para delimitar su extensión significativa, suelen tener como núcleo sustantivos no contables en singular o contables en plural, como en estos casos:


| Ejemplos |
| --------- |
|_Compran **oro**_ |
|_Compré **mesas**_|
|_Conocí **gente**_|
|_¿Bebes **agua** fría?_|
|_Ha caído **agua** en el patio_|

Ahora bien, es posible encontrar casos con sustantivos contables en singular en locuciones verbales como:

| Ejemplos |
| --------- |
|_No tener **corazón**_ |
|_No pegar **ojo**_|
|_Hacer **frente**_|
|_Sentar **cabeza**_|
|_Tomar **nota**_|
|_Dar **parte**_ |
|_Formar **parte**_|
|_Dar **lugar**_|
|_Tener **lugar**_|

Asimismo, se omitirá el artículo en grupos nominales conformados por nombres de personas, países y ciudades, días de la semana y estaciones del año como atributos, meses del año, vocativos, etc.

| Ejemplos |
| --------- |
|_**Antonio** es simpático,vive en **América** pero nació en **Italia**._|
|_Hoy es **lunes** y mañana es **martes**._|
|_Estamos en **primavera**._|
|_En **junio** iré a Nigeria y en **julio** a Francia._|
|_**Señor Pérez**, no se siente todavía, por favor. Entiendo lo que usted quiere decirme, **caballero**._|

En español estos grupos nominales que no pueden llevar artículo no solo carecen de valor referencial sino que también carecen de valor cuantificador; de manera que, por lo general, se rechaza la idea de que pueda operar un elemento como el ‘artículo cero’ (o ‘artículo Ø’). Según esta visión, la falta de valor cuantificador de estos grupos nominales se relaciona (y justifica) con la idea de que “denotan entidades no delimitadas o amorfas” (Laca, 1999: 904) porque "carecen de la posibilidad de designar colecciones 'cerradas' de elementos o bien grupos de elementos concebibles como unidad" (Laca, 1996: 243-244).


## TOTALITY<a name="id6"></a>
Este feature **totality** está relacionado con el concepto de límite. La totalidad que manejamos es la de un conjunto. Supondremos que un sustantivo se entiende como totalidad o como conjunto completo cuando el sustantivo se interpreta como el grupo completo de elementos en una determinada dimensión semántica, es decir, cuando el sustantivo no deja espacios para otros subgrupos. Esta totalidad incluye un elemento que sea pensado como único en una dimensión.

#### Total<a name="id7"></a>
El value (*valor*) **total** indica que el sustantivo que acompaña al artículo definido es interpretado como un elemento o conjunto único que no convive con otros elementos o conjuntos iguales.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Total | _**El** borrador que estaba buscando._ |

#### Parcial<a name="id8"></a>
El value **parcial** indica que el sustantivo que acompaña al artículo indefinido es interpretado como un elemento que puede ser equivalente a otros posibles.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Parcial | _Necesito **un** borrador._ (cualquiera) |


## STATE<a name="id9"></a>
El feature **state** está relacionado con la activación de los participantes en el discurso. Los artículos acompañan a estos participantes como elementos de una narración, ya sea que hayan sido introducidos por primera vez o se hayan mencionado anteriormente en el texto.


#### Inactive<a name="id10"></a>
El value **inactive** señala que los elementos nuevos en el discurso son introducidos a través del artículo indefinido debido a que indican que es un elemento entre otros posibles.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Inactive| _Había una vez, **una** princesa que estaba condenada a vivir en una torre._|


#### Active<a name="id11"></a>
El value **active** indica que un elemento antes mencionado suele estar acompañado por el artículo definido pues ya se ha establecido como elemento foco del discurso, por lo tanto, es este y no otro.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Active| _Y así, **la** princesa fue rescatada por el príncipe._|

Los participantes nuevos introducidos en un *discurso* pueden hacerlo con un artículo definido si son considerados como una totalidad en otras dimensiones.

La ausencia de artículos supone información no activada (excepto con nombres propios, que están indeterminados en este sentido).

## CONCRETENESS<a name="id12"></a>
El feature **concreteness** está relacionado con la abstracción discursiva. Dicha abstracción diferencia la interpretación referencial de un sustantivo de su uso como conceptualización.

Entendemos la abstracción discursiva como un efecto de sentido derivado del hecho de interpretar un sustantivo como una conceptualización, en vez de como referencia a un objeto concreto. La abstracción discursiva de un sustantivo supone, entonces, interpretarlo como una generalidad, en la que los rasgos centrales o comunes del sustantivo se hacen más relevantes que los periféricos o que los detalles semánticos del mismo.

La abstracción producto del artículo es independiente de la cualidad abstracta/concreta del sustantivo al que modifica. Por ejemplo, el sustantivo *clase obrera* es abstracto por naturaleza, así que, cuando se dice *la clase obrera* se entenderá en el modelo como no-abstracto ya que lo que se está estudiando no es la naturaleza abstracta/concreta de este, sino los efectos semánticos y pragmáticos del artículo sobre el sustantivo.


#### Abstract<a name="id13"></a>
El value **abstract** indica que, por medio del artículo, el sustantivo es percibido como una conceptualización más que como una referencia a un elemento concreto. En este caso privan más los rasgos generales y centrales, que los particulares y periféricos que los diferencian de otros.


| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Abstract| _**La** familia es el pilar de la sociedad._|


#### Concrete<a name="id14"></a>
El value **concrete** indica que, por medio del artículo, el sustantivo direcciona al referente concreto del mismo.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Concrete| _Esta cena es importante para **la** familia._|

En varios casos, la ausencia del artículo indica también un sentido abstracto, como en *Ella toca ∅ piano* / *Ella toca el piano*. El artículo indefinido, en cambio, limita el sustantivo a un elemento concreto: *Ella toca un piano*.

En el caso de los adjetivos calificativos, el artículo lo sustantiva y mantiene el sentido abstracto de la cualidad (_lo bonito, lo delicado, lo fantástico_), mientras que el definido concretiza al calificativo (_el bonito, la delicada, el fantástico_).


## COUNTABILITY<a name="id15"></a>

El sentido de totalidad proporcionado por el artículo definido, y el de parcialidad dado por el indefinido, interactúan de forma dinámica con los values (*valores*) contable/no-contable del sustantivo.

Hay que especificar que este rasgo depende del elemento léxico como tal, es decir, no depende de su entrada en el lexicón sino de una acepción en particular. Por ejemplo, *masa* como sustancia no es contable, pero *masa* como ingrediente preparado para una empanada sí lo es. Por ejemplo: *pásame las dos masas que están sobre la mesa*.

Si un sustantivo es contable y plural, el artículo definido indicará una totalidad de límites claros. Por ejemplo: *pásame los lápices* indica la totalidad de "los lápices", o una aproximación bastante cercana a la de totalidad, así pues, _los lápices_ se refiere a "todos los lápices" (o casi todos), que podrían ser el referente del sustantivo en una situación dada. Lo mismo sucede si el sustantivo lleva un contador: *pásame los tres lápices*, que refiere a que se desean *los tres lápices* (ni uno más, ni uno menos).

#### Countable<a name="id16"></a>
El value **countable** sirve para indicar que el sustantivo es contable.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Countable| _Para la salsa necesito **unos** 3 tomates._|

#### Uncountable<a name="id17"></a>
El value **uncountable** sirve para señalar que el sustantivo no es contable.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| TYPE | Uncountable| _**El** sol sale por la mañana._|


## DETERMINATION<a name="id18"></a>

Por medio del feature **determination** se indica que el sustantivo que acompaña al artículo puede, o no, sufrir una determinación externa además de la que le provee el artículo mismo; es decir, el feature indica que se está proporcionando información que contribuye al sentido del sustantivo mismo.

El sustantivo puede determinarse por medio de un complemento preposicional *el libro de Pedro*, oraciones relativas *el libro que te presté ayer*, adjetivos demostrativos o posesivos *el libro ese; el libro tuyo*, por medio de una construcción atributiva *el libro que busco fue el que te presté*, entre otras posibilidades.

#### Determiner<a name="id19"></a>
El value **determiner** señala que el sustantivo que el artículo (definido o no) acompaña, sufre una determinación externa que puede realizarse por medio de complementos preposicionales, oraciones subordinadas relativas, adjetivos posesivos o demostrativos pospuestos, construcciones atributivas, etc.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| DETERMINATION | Determiner | _Te veo en **el** cumpleaños de Juan._|

#### Undeterminer<a name="id20"></a>
El value **undeterminer** apunta a que el sustantivo no está determinado externamente por medio de una atribución o complemento.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| DETERMINATION | Undeterminer | _Te veo en **la** fiesta._|


## NUMBER<a name="id21"></a>
Por medio del feature **number** se indica que el artículo, junto con el sustantivo que acompaña, coinciden en número y que este puede señalar varios elementos o un único elemento.

#### Singular<a name="id22"></a>
El value **singular** apunta a que el sustantivo denota un solo elemento.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| NUMBER | Singular | _**El** joven faltó a clases._|

#### Plural<a name="id23"></a>
El value **plural** indica que el sustantivo que acompaña al artículo denota un conjunto de elementos formado por dos o mas de ellos.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| NUMBER | Plural | _**Los** jóvenes ya estaban en el salón_|

## POS<a name="id24"></a>

EL feature **POS** se refiere al tipo de palabra que le sigue al artículo; es decir, la clase de palabra a la que pertenece la misma antes de unirse al artículo que la nominaliza. Estas palabras pueden ser verbos, adjectivos, sustantivos, adverbios, etc,* estos servirán como los values del feature POS.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| POS | VERB | _No hay nada como **el** comer._|
| POS | ADJ  | _**Lo** bello es sublime._ |
| POS | NOM  | _**El** carro se estrelló._ |

## COMMONNESS<a name="id25"></a>

El feature **commonness** refiere a que el sustantivo que acompaña al artículo es un elemento particular y único, o es uno entre tantos.

#### Proper<a name="id26"></a>
Con el value **proper** se indica que el sustantivo que acompaña al artículo está identificada como una entidad única, y diferencia esta del resto.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| COMMONNESS | Proper | _María fue al gimnasio._|

#### Common<a name="id27"></a>
Con el value **common** se indica que el sustantivo que acompaña al artículo refiere a entidades de una cierta clase o especie, sin tomar en cuenta sus particularidades o especificidades.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| COMMONNESS | Common | _**Las** pelotas rebotan._|


## GENDER<a name="id28"></a>

Por medio del feature **gender** se indica que el artículo junto con el sustantivo que acompaña, coinciden en género y que este puede variar entre el femenino y el masculino.

#### Femenine<a name="id29"></a>
El value **femenine** apunta a que el género del sustantivo es femenino.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| GENDER | Femenine | _**Las** manzanas son rojas._|

#### Masculine<a name="id30"></a>
El value **masculine** apunta a que el género del sustantivo es masculino.

| Class     | Value | Ejemplo |
| --------- | ----- | ------- |
| GENDER | Masculine | _**Los** limones son ácidos._|
