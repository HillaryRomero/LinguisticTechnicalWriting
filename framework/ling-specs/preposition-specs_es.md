# Preposición (es)

## MODELO DE PREPOSICIONES<a name="id1"></a>

Este documento tiene como propósito fundamental describir cada feature relacionado con el modelado de preposiciones PREPOSITIONS.

El modelo PREPOSITIONS (*preposiciones*) se trata de un modelado de inspiración cognitiva que busca formalizar las funciones de las proposiciones en el discurso a través de features (*características*) que se encargan de codificar las relaciones de estas en el espacio. El modelo abarca una serie de parámetros que permite analizarlas y ubicarlas en el contexto.

Las preposiciones se entienden como palabras que establecen relaciones entre diversas partes del discurso. En este sentido, las preposiciones se acercan más a los verbos que a los sustantivos, dado que al ser palabras relacionales adquieren sentido solamente cuando sus argumentos (valencias) son satisfechos. A este respecto, el modelado de preposiciones que describimos en estas páginas debe clasificar cada preposición en su uso y en contexto; esta clasificación se consigue a partir de valores discretos que se asignan a features. 

Los features escogidos para este modelo han sido aquellos que varias teorías gramaticales y lingüísticas de corte cognitivista han utilizado durante años para estudiar esta clase de palabras.

A continuación se explica cada feature (*característica*) utilizado en este modelo.


## TRAJECTOR (Elemento de foco):<a name="id3"></a>

La clasificación de preposiciones se basa en la premisa básica de que, en las relaciones entre los términos de una preposición, siempre habrá un Trajector (*elemento de foco*) que se individualiza a partir de un Landmark (_elemento de fondo o background_) . El trajector (Tr) es entonces un elemento prominente en la relación, en la gran mayoría de los casos se trata del argumento o término que se encuentra a la izquierda de la preposición.

| Class     | Tag   | Ejemplo |
| --------- | ----- | ------- |
| TRAJECTOR | Tr    | _(El libro) **en** la mesa._ |

En el ejemplo anterior, el _(libro)_ es un objeto individual que se destaca sobre _[la mesa]_ que le funciona como fondo.

> _NOTA: para efectos de resaltar el elemento **trajector** en este instructivo, se pondrá dicho elemento entre paréntesis **()**._

#### Tr Movil<a name="id4"></a>

En términos prácticos, se encuentra casi siempre como el primer argumento o término de la preposición. Es un trayector que, relativamente hablando, es móvil, o que cambia de tamaño o altera su forma. En algunos casos, el trayector no se concibe como móvil o fijo extrictamente hablando, sino como una diferenciación entre trayectores particulares y trayectores generales (conjuntos). Si el trayector es más particular que general, se entenderá, metafóficamente, como un trayector móvil.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| TRAJECTOR | Movil | _(El niño) camina **por** el parque._ |
| TRAJECTOR | Movil | _(El niño) **del** grupo._ |


#### Tr Fijo<a name="id5"></a>

En términos prácticos, se encuentra casi siempre en el primer argumento o término de la preposición. Elemento que, relativamente hablando, se percibe como fijo o como punto de referencia, y que denota también un volumen estable. En el caso de que no opere la distinción literal de móvil/fijo, sino la de "conjuntos", se trataría de un conjunto o agrupación, y por lo tanto, tendría el valor fijo.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| TRAJECTOR | Fijo | _(El enchufe) está detrás **del** mostrador._ |
| TRAJECTOR | Fijo | _(Los niños) **de** mi casa._ |


## LANDMARK<a name="id6"></a>

El Landmark (LM) es un elemento (o conjunto de elementos) de fondo sobre el cual se destaca el trayector. El Landmark suele ampliar la información sobre el trayector de forma directa o indirecta. Este fondo suele ser de dimensión espacial o temporal.

| Class     | Tag   | Ejemplo |
| --------- | ----- | ------- |
| LANDMARK  | LM    | _El libro **en** la mesa._ |
| LANDMARK  | LM    | _Nos veremos **en** julio._ |

> _NOTA: para efectos de resaltar el elemento **landmark** en este instructivo, se pondrá dicho elemento entre llaves **[]**._

#### LM Movil<a name="id7"></a>

En términos prácticos, casi siempre es el segundo argumento de la preposición. Elemento que, relativamente hablando, es móvil, o que cambia de tamaño o altera su forma. En algunos casos, el LM no se concibe como móvil o fijo extrictamente hablando, sino como una diferenciación entre fondos particulares y fondos generales (conjuntos). Si el LM es más particular que general, se entenderá, metafóficamente, como un 'Landmark móvil'.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| LANDMARK | Movil | _El niño camina **por** [el parque]._ |


#### LM Fijo<a name="id8"></a>

En términos prácticos, casi siempre es el segundo argumento de la preposición. Elemento que, relativamente hablando, se percibe como fijo o como punto de referencia, este denota también un volumen estable. Desde el punto de vista de los conjuntos, se trataría casi siempre de una agrupación de elementos con respecto al trayector. En este sentido, en *un vaso de **agua*** el LM *agua* se entiende como fijo, no porque no pueda moverse, sino porque se entiende como una *masa* o un _conjunto_.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| LANDMARK | Fijo | _El niño está detrás **del** [mostrador]._ |


## DIMENSION<a name="id9"></a>

El feature **dimension** está relacionado con las cualidades del Trajector y el Landmark en torno a un dominio conceptual, ya sea temporal, espacial, social, etc. y corresponde dominios conceptuales metafóricos básicos y generales. Cabe destacar que se trata de tipos de relaciones entre el Tr y el LM.

#### Espacio<a name="id10"></a>

El value (*valor*) **espacio** en el feature **dimension** indica que el Tr y el LM se encuentran relacionados por un vínculo espacial; generalmente este vínculo supone que el Tr ocupa un espacio en un lugar denotado por el LM.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| DIMENSION | Espacio | _(El niño) camina **por** [el parque]._ |


#### Tiempo<a name="id11"></a>

El value **tiempo** indica que el Tr es una entidad física o abstracta, y que el LM es una dimensión temporal en la que se encuentra o se mueve dicho Tr.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| DIMENSION | Tiempo | _(El paquete) llega **en** [la tarde]._|


#### Espacio metafórico<a name="id12"></a>

El value **espacio metafórico** establece que el Tr y el LM se presentan como entidades espaciales, sin tomarse de manera literal; en otras palabras, se trata de un espacio físico solo de manera metafórica. Por lo tanto, el LM no es un espacio o entidad real.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| DIMENSION | Espacio metafórico | _(El niño) pasó **a** [primer grado]._|


#### Transacción<a name="id13"></a>

El value **transacción** establece que el Tr es una entidad (física o inmaterial) y el LM es una entidad social (persona, compañía, institución, etc.).

| Class     | Value-Type| Ejemplo |
| --------- | ----- | ------- |
| DIMENSION | Transacción | _(Lo compré) **para** [ti]._|

#### Circunstancia<a name="id14"></a>

El value **circunstancia** supone que el Tr es una entidad concreta o abstracta (una acción) y el LM es una circunstancia derivada de la acción (destino, causa, consecuencia).

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| DIMENSION | Circunstancia | _(Lo hice) **por** [tu beneficio]._|

#### Medida<a name="id15"></a>

El value **medida** indica que el Tr es una entidad (física o inmaterial) y el LM es una escala (cuantitativa, ordinal o cualitativa). Puede tratarse de una medida de longitud del LM, del volumen del Tr, etc. En otras palabras, el LM se usa para medir algo con respecto al Tr.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| DIMENSION | Medida | _(Tu pueblo) está **a** [veinte kilometros]._|

#### Instrumento<a name="id16"></a>

El value **instrumento** implica que el LM es un instrumento que opera sobre el Tr para cambiar su forma, volumen, trayectoria, alterarlo, etc. Puede ser también un medio con el cual el Tr se desplaza.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| DIMENSION | Instrumento | _Cortó (la carne) **con** [un cuchillo]._|

#### Conjunto<a name="id17"></a>

El value **conjunto** indica que el LM y/o el Tr son conjuntos de elementos o entidades de dichos conjuntos. Puede implicar también, que el Tr y el LM son entidades individuales que guardan una relación entre sí de identidad o pertenencia. En este sentido, se pueden formalizar relaciones conjunto-conjunto, conjunto-entidad y entidad-entidad.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| DIMENSION | Conjunto | _(Varios) **de** [estos niños] me hicieron bullying._ |


## DIRECTIONALITY<a name="id18"></a>

Este feature establece el tipo de relación entre el Tr y el LM para cada clase de espacio metafórico.

El feature **directionality** está asociado a la idea de dirección o de posición relativa. Este feature se utiliza para formalizar las posibles relaciones espaciales entre el Tr y el LM, dichas relaciones pueden ser literales, pero en la gran mayoría de los casos serán relaciones espaciales metafóricas. En este sentido, el LM se concibe como un "espacio" sobre el cual se desplaza o se ubica el Tr.

El value-type que se utiliza en el modelo especifica también el subtipo de direccionalidad (1D, 2D, 3D). Este value-type se trata más de un criterio de organización de los values de este feature, que de un feature de derecho propio.

#### Directionality  = <a name="id19"></a>

El value **directionality =** se utiliza para indicar que hay una comparación. Se trata de la vinculación de dos dimensiones metafóricas, en la que el Tr de una se pone en relación al LM de la otra. También puede comparar dos conjuntos de Tr y LM que compartan la misma dimensión.

Tipo de direccionalidad: direccionalidad_1D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality =  | _**Para** [la edad que tiene], se ve  (joven)._|

#### Directionality  > <a name="id20"></a>

El value **directionality >** indica que la distancia entre el Tr y el LM se acorta en el tiempo. En otras palabras, que el Tr se acerca al LM.

Tipo de direccionalidad: direccionalidad_1D_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality > | _(Yo) voy llegando **a** [mi casa]._|

#### Directionality  < <a name="id21"></a>

El value **directionality <** indica que la distancia entre el Tr y el LM se alarga, es decir, el Tr se aleja del LM.

Tipo de direccionalidad: direccionalidad_1D_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality < | _(Yo) voy saliendo **de** [mi casa]._|

#### Directionality  -- <a name="id22"></a>

El value **directionality --** indica que el Tr se mantiene a una distancia constante del LM. El Tr se mantiene fijo con respecto al LM en cuanto a la distancia.

Tipo de direccionalidad: direccionalidad_1D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality -- | _(Pedro) está **con** [Juan]._|


#### Directionality  <> <a name="id23"></a>

El value **directionality <>** indica que la distancia entre el Tr y el LM fluctúa. En otras palabras, el Tr se acerca y se aleja simultáneamente del LM.

Tipo de direccionalidad: direccionalidad_1D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality <> | _(El precio de las zanahorias) está más o menos **a** [5 $] el kilo_. |


#### Directionality  # <a name="id24"></a>

El value **directionality #** indica que hay una permutación o sustitución. El Tr es reemplazado por el LM.

Tipo de direccionalidad: direccionalidad_1D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality # | _Cambio (peras) **por** [manzanas]._|


#### Directionality  → <a name="id26"></a>

El value **directionality  -->** el Tr está a un lado del LM, a una distancia constante. En este caso, la preposición indica detalladamente si se trata de una posición arriba/abajo o izquierda/derecha.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality → | (No existe este tipo de preposición en español) |

#### Directionality  -> <a name="id27"></a>

El value **directionality ->** indica que la distancia entre el Tr y el LM se acorta desde un lateral (izquierda o derecha).

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality -> | (No existe este tipo de preposición en español) |


#### Directionality  <- <a name="id28"></a>

El value **directionality <-** indica que  la distancia entre el Tr y el LM se aleja desde un lateral (izquierda o derecha).

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality <- | (No existe este tipo de preposición en español) |


#### Directionality  <-> <a name="id29"></a>

El value **directionality <->** indica que la distancia entre el Tr y el LM fluctúa (se acerca y se aleja simultáneamente) desde un lateral.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality <-> | (No existe este tipo de preposición en español) |


#### Directionality  ^ <a name="id30"></a>

El value **directionality ^** indica que el Tr está arriba del LM a distancia constante. Puede haber, o no, contacto entre el Tr y LM.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   | Directionality ^ | _(Las estrellas) están **sobre** [nosotros]._|


#### Directionality  ^> <a name="id31"></a>

El value **directionality ^>** indica que la distancia entre el Tr y el LM se acorta desde arriba.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality ^> | (No existe este tipo de preposición en español) |


#### Directionality  <^ <a name="id32"></a>

El value **directionality <^** indica que la distancia entre el Tr y el LM se alarga desde arriba, es decir, el Tr se distancia del LM en dirección hacia arriba.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality <^ | _Subió (el impuesto) **sobre** [las importaciones]._ |

#### Directionality  v <a name="id33"></a>

El value **directionality v** indica que el Tr está debajo del LM a una distancia constante.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality v | _(Los diamantes) están **bajo** [nosotros]._ |


#### Directionality  v> <a name="id34"></a>

El value **directionality v>** sirve para indicar que la distancia entre el Tr y el LM se acorta desde abajo. El Tr se acerca al LM desde abajo.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality v> | _(Yo) subí **hasta** [el tercer piso]._ |


#### Directionality  <|> <a name="id35"></a>

El value **directionality <|>** sirve para indicar que el Tr se mueve de izquierda a derecha o de arriba a abajo por un lateral del LM.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality <|> | _(Las piezas) se mueven **sobre** [la mesa]._ |


#### Directionality  >|< <a name="id36"></a>

El value **directionality >|<** indica que el Tr se mueve entre dos partes diferenciadas del LM o que el Tr se mueve dentro de la estructura del LM. Esto quiere decir que el Tr atraviesa, de alguna manera, al LM, muchas veces traspasándolo por completo.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality  >l< | _(Él) actuó **contra** [su voluntad]._|


#### Directionality  -><- <a name="id37"></a>

El value **directionality -><-** indica que el Tr se mantiene a una distancia constante de dos partes diferenciadas del LM, o que el Tr está fijo entre las partes que integran el LM.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality -><- | _(Ella) se escondió **entre** [los carros]._ |


#### Directionality  o <a name="id38"></a>

El value **directionality o** indica que el Tr se mueve o se encuentra alrededor de una figura plana que constituye el LM. En otras palabras, el Tr rodea u orbita alrededor o dentro del LM.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality o | _(Los niños) se mueven **por** [el bosque]._ |


#### Directionality  u <a name="id39"></a>

El value **directionality u** indica que el LM es una figura plana que contiene al Tr, y a su vez señala la pertenencia de una entidad a un conjunto. Se trata, entonces, de una relación en la que el Tr es un contenido y el LM su contenedor; este contenedor se concibe, por motivos de simplicidad, como una figura plana.

Tipo de direccionalidad: direccionalidad_2D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality u| _(Yo) vivo **en** [Mérida]._ |


#### Directionality  !> <a name="id40"></a>

El value **directionality !>** indica que el Tr se acerca al LM desde atrás. Este "atrás" es relativo, puede ser la parte trasera de algo, o puede que el Tr se encuentre entre el sujeto perceptivo y el LM.

Tipo de direccionalidad: direccionalidad_3D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality !> | _(Yo) voy **tras** [él]._ |


#### Directionality  ¡> <a name="id41"></a>

El value **directionality ¡>**  indica que el Tr se acerca al LM desde delante. Este "delante" es relativo, puede ser la parte delantera de algo, o puede que el LM se encuentre entre el sujeto perceptivo y el Tr.

Tipo de direccionalidad: direccionalidad_3D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality ¡>| (No existe este tipo de preposición en español) |


#### Directionality  <! <a name="id42"></a>

El value **directionality <!** indica que  el Tr se aleja del LM desde la parte trasera del LM.

Tipo de direccionalidad: direccionalidad_3D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality <!| (No existe este tipo de preposición en español) |


#### Directionality  <¡ <a name="id43"></a>

El value **directionality <¡** indica que el Tr se aleja del LM desde la parte frontal del LM.

Tipo de direccionalidad: direccionalidad_3D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality <¡| (No existe este tipo de preposición en español) |


#### Directionality  -! <a name="id44"></a>

El value **directionality -!** indica que el Tr se mantiene a una distancia constante detrás del LM. Este "detrás" es relativo, puede ser la parte trasera de algo, o puede que el Tr se encuentre entre el sujeto perceptivo y el LM.

Tipo de direccionalidad: direccionalidad_3D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality -!| _(La ventana) da **a** [la calle].|

En el ejemplo anterior, la (ventana) es el Tr, que se encuentra entre el sujeto perceptivo y la [calle] [LM].


#### Directionality  -¡ <a name="id45"></a>

El value **directionality -¡** sirve para indicar que el Tr se mantiene a una distancia constante delante del LM. Este "delante" es relativo; puede ser la parte delantera de algo, o puede que el LM se encuentre entre el sujeto perceptivo y el Tr.

Tipo de direccionalidad: direccionalidad_3D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality -¡| _(Una montaña) se encuentra **ante** [el pistolero]._ |

En el ejemplo anterior el (pistolero) (Tr) está delante de la [montaña] [LM].


#### Directionality  !o <a name="id46"></a>

El value **directionality !o** sirve para indicar que el Tr se mueve o se encuentra alrededor del volumen del LM. En este caso, y a diferencia del **directionality o**, el LM se concibe no como una figura plana, sino como un volumen.

Tipo de direccionalidad: direccionalidad_3D

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality !o| (No existe este tipo de preposición en español) |


#### Directionality  !u <a name="id47"></a>

El value **directionality !u** indica que el LM es un volumen que contiene al Tr. El Tr sería un contenido de ese volumen. Se usa, sobre todo, para metáforas de tipo conjunto.

Tipo de direccionalidad: direccionalidad_3D


| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| DIRECTIONALITY   |Directionality !u| _(Un vaso) **con** [agua]._ |


## VOLUME <a name="id48"></a>

El feature **volume** está relacionado con las cualidades del Trajector y el Landmark en torno a la extensión que ocupa un objeto en el espacio. De esto se desprenden valores que especifican: si el Tr se topa con algún tipo de límite, si hay contacto con el LM, o si el Tr debe atravesar al LM.


#### Limite+ <a name="id49"></a>

El value **limite+** indica que el LM es un límite para el movimiento del Tr. Aunque este límite podría ser traspasado, la preposición indica que se espera que no lo sea.

| Class      | Value Type | Ejemplo               |
| ---------- | ----------- | --------------------- |
| VOLUME  |Limite+| _(Voy) **hasta** [Barquisimeto]._ |


#### Limite- <a name="id50"></a>

El value **limite-** indica que el LM no es necesariamente un límite para el movimiento del Tr, y que este último podría ir más allá de los límites del LM.


| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| VOLUME  |Limite-| _(Voy) **para** [Barquisimeto]._ |


#### Contacto+ <a name="id51"></a>

El value **contacto+** indica que el Tr en reposo mantiene un contacto con el LM. El Tr mantiene un contacto físico o psicológico con el LM.

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| VOLUME  |Contacto+| _(El libro) está **en** [la mesa]._|


#### Contacto- <a name="id52"></a>

El value **contacto-** indica que el Tr en reposo no mantiene un contacto con el LM. El Tr no mantiene un contacto físico o psicológico con el LM.

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| VOLUME  |Contacto-| _(Un niño) flotó **sobre** [mi]._|


#### Medio+ <a name="id53"></a>

El value **medio+** indica que el LM es un espacio que debe atravesar el Tr para llegar a su destino. El LM se concibe como un medio que sirve para que el Tr se desplace.

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| VOLUME  |Medio+| _Envié (el paquete) **por** [correo]._|


#### Medio- <a name="id54"></a>

El value **medio-** indica que el LM es un espacio dentro del cual se encuentra el Tr en posición de reposo.

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| VOLUME  |Medio-| (El paquete) está **en** [el correo]._|


#### Ninguno <a name="id55"></a>

Este value tiene la finalidad de hacer explícita la categoría "vacía" que ocurre en algunos prototipos donde _ninguno_ de los valores disponibles en el modelo aplican para el caso modelado.

| Class      | Value Type | Ejemplo               |
| ---------- | ---------- | --------------------- |
| VOLUME  |Ninguno| _Venezuela está llena de (gente joven) **con** [ganas de divertirse]._|

## SUBJECTIVATION<a name="id56"></a>

El feature **subjectivation** está asociado con la perspectiva del usuario en torno a la relación entre Tr y el LM. Incorpora nociones de evidencialidad, distinción clara entre el Tr y LM, información nueva o conocida, finalidad, etc. Se trata de factores subjetivos relacionados con la relación entre el Tr y LM.

#### Evidencial+<a name="id57"></a>

El value **evidencial+** señala que hay evidencia perceptiva de la posición del Tr. El sujeto perceptivo observa con sus propios sentidos la relación entre el Tr y LM.

| Class     | Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Evidencial+ | _(La joven) estaba parada **ante** [el cuadro]._|


#### Evidencial- <a name="id58"></a>

El value **evidencial-** señala que no hay evidencia perceptiva de la posición del Tr con respecto al LM. Es especialmente útil para indicar que la relación entre el Tr y LM no es totalmente constatable a través de los sentidos (se trata sobre todo de un supuesto).

| Class     |Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Evidencial- | _Él (se asustó) **ante** [mis preguntas]._|

#### Union+ <a name="id59"></a>

El value **union+** señala que, desde la perspectiva del usuario, el Tr y el LM forman una unidad, o van camino a hacerlo.

| Class     | Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Union+ | _El acero (se convirtió) **en** [una espada]._|

#### Union- <a name="id60"></a>

El value **union-** señala que, desde la perspectiva del usuario, el Tr y el LM forman dos unidades distintas, o van camino a hacerlo.

| Class     |Value-Type | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Union- | (Batman) **versus** [Superman]._ |

#### Determinado+ <a name="id61"></a>

El value **determinado+** señala que el LM debe ser información conocida.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Determinado+ | (No existe este tipo de preposición en español) |

#### Determinado- <a name="id62"></a>

El value **determinado-** señala que el LM debe ser información nueva.

| Class     | Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Determinado- | (No existe este tipo de preposición en español) |

#### Manera+ <a name="id63"></a>

El value **manera+** señala que el LM es una manera en la que el Tr se produce o realiza algo.

| Class     | Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Manera+ | _Ella envió (el contacto) **vía** [fax]._ |

#### Sentido+ <a name="id64"></a>

El value **sentido+** señala que el LM proporciona un sentido (en analogía con un vector) espacial o metafórico. El sentido es subjetivo y depende del punto de vista del emisor.

| Class     | Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Sentido+ | _Pedro le grita (cosas) **a** [Juan]._ |

#### Benefactivo+ <a name="id65"></a>

El value **benefactivo+** señala que el LM se entiende como el benefactivo.

| Class     | Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Benefactivo+ | _Tú (dámelo) **a** [mí]._|

#### Adversativo+ <a name="id66"></a>

El value **adversativo+** señala que el LM se entiende como una consecuencia del movimiento del Tr. Esta consecuencia es un argumento adverso hacia la posición de uno de los interlocutores.

| Class     | Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Adversativo+ | _**Hasta** [Eva] piensa como (tú)._ |

#### Finalidad+ <a name="id67"></a>

El value **finalidad+** señala que el LM se entiende como una finalidad.

| Class     | Value-Type | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Finalidad+ | _(Fácil) **de** [usar]; (facilidad) **de** [uso]._ |

#### Finalidad- <a name="id68"></a>

El value **finalidad-** señala que el LM no es una finalidad (se usa para distinguir algunos casos en los que se esperaría una finalidad que al final no se cumple).

| Class     | Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Finalidad- | _**Para** [él] todo (está mal)._ |

#### Ninguno <a name="id69"></a>

Ingrese este value para hacer explícita la categoría "vacía" que ocurre en algunos prototipos.

| Class     | Value-Type  | Ejemplo |
| --------- | ----- | ------- |
| SUBJECTIVATION | Ninguno | _(Yo) trabajo de 9 **a** [1]_
