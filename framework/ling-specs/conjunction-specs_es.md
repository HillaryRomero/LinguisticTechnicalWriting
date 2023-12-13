# Conjunción (es)

## MODELO DE CONJUNCIONES<a name="id50"></a>

Este documento tiene como propósito fundamental determinar qué significa, y cómo se usa, cada feature (característica) relacionado con la anotación requerida para el modelo de CONJUNCTIONS.

El modelo CONJUNCTIONS (*conjunciones*) se trata de un modelado discursivo que pretende organizar y analizar la funcionalidad de las conjunciones en el discurso a través de unos features (*características*) que se encargan de codificar las relaciones que estos elementos establecen de forma más o menos lógica entre los dos elementos conectados por dichas conjunciones. El modelo abarca una serie de parámetros que permite analizarlas y ubicarlas en el contexto. Decimos que las conjunciones son una palabra de enlaces lógicos no en el sentido estricto del término "lógica", sino en relación con una lógica más discursiva que formal. No se trata de un modelado de tipo cognitivo (de inspiración espacial o metafórica) sino de uno funcional inspirado en la *Gramática sistémico-funcional* de Michael Halliday y Christian Matthiessen.

Este modelado contempla, entre otras, relaciones espacio-temporales, de causa, consecuencia, condicionales y discursivas.


## ELEMENTOS BÁSICOS DEL MODELO<a name="id1"></a>

#### CONJUNCTION<a name="id70"></a>

Elemento lingüístico de enlace. Establece un vínculo gramatical o discursivo entre dos elementos: uno previo (**Elemento A**) y uno posterior (**Elemento B**). En las uniones hechas con conjunciones, tanto el Elemento A como el Elemento B tienen el mismo estátus gramatical (el estátus discursivo puede y suele variar).


#### ELEMENTO A A<a name="id2"></a>

El **elemento A** es aquel que se encuentra antes de una conjunción, puede ser una palabra, una frase, una cláusula o un párrafo.

| Sheet      | Elemento | Ejemplo               |
| ---------- | ---------- | --------------------- |
| GLOSARY  |Elemento A| _(Pintura para suelos) **o** paredes._ |

> _NOTA: para efectos de resaltar el **Elemento A** en este instructivo, se pondrá dicho elemento entre paréntesis **()**._



#### ELEMENTO B<a name="id3"></a>

El **elemento B** es aquel que se encuentra después de una conjunción, puede ser una palabra, una frase, una cláusula o un párrafo.

| Sheet      | Elemento | Ejemplo               |
| ---------- | ---------- | --------------------- |
| GLOSARY  |Elemento B| _Él es bonito **y** [con dinero]._ |

> _NOTA: para efectos de resaltar el **Elemento B** en este instructivo, se pondrá dicho elemento entre llaves **[]**._


### CONMMUTATION<a name="id4"></a>

La **commutation** es un procedimiento mediante el cual se sustituye una unidad por otra para discernir si tal cambio entraña una diferencia de significado o no. En el caso del modelo conjunctions, la conmutación se utiliza para indicar que una conjunción puede ser sustituida por otra para un uso en particular. Aunque en algunos casos una conjunción puede ser cambiada por otra sin que esto afecte mayormente el significado del enunciado, el registro en el que estas conjunciones se usa puede que sea distinto para cada una de ellas.


| Ejemplo     |
| ---------- |
|_(La casa es horrible), **pero** [tiene una excelente ubicación]._|
|_(La casa es horrible), **mas** [tiene una excelente ubicación]._|

| Ejemplo     |
| ---------- |
|_(Dos) **y** [dos son cuatro]._|
|_(Dos) **más** [dos son cuatro]._|

En los ejemplos anteriores es posible notar que el hecho de sustituir una conjunción por otra no compromete el sentido y el significado del enunciado. En el caso de *pero/mas* se trata de una diferencia de registro (*mas* es muy formal o literaria); en el caso de *y/más*, la primera es más genérica, mientras la segunda es más específica y clara.


### OVERLAP<a name="id5"></a>

Un **overlap** se da cuando dos usos de una misma conjunción actúan de manera simultánea. Se trata de un caso en el que dos interpretaciones de una conjunción pueden neutralizar sus distinciones, o en la que conviven dos interpretaciones diferentes.

Situación en la que una misma conjunción puede ser analizada como perteneciente a dos tipos, sub-tipos y sub sub-tipos distintos.

| Ejemplo                     | Explicación                           |
| --------------------------- | ------------------------------------- |
| _(Trabaja todo el día) **y** [acabarás enfermo]._ | En este caso la conjunción *y* puede interpretarse de dos maneras: como **causal specific result** o **conditional positive**.


A continuación se explica cada feature (*característica*) utilizada en este modelo.

## TYPE<a name="id6"></a>

Para efectos del modelo de CONJUNCTIONS, el feature **type** señala los tres tipos de expansión que pueden darse con el uso de las conjunciones.

Este feature se realiza con los siguientes values (*valores*): elaboration, extension y enhancement.

#### Elaboration<a name="id7"></a>

El value **elaboration** indica que el Elemento B elabora o reitera lo dicho en el Elemento A, es decir, el Elemento B proporciona o añade alguna caracterización al Elemento A con el propósito de especificar el mensaje, describirlo, o reforzarlo. En otras palabras, no se introduce un nuevo elemento al discurso, sino que se refuerza lo dicho anteriormente. En tal sentido, se re-elabora, clarifica, refina o amplía información (comentario, atributos, etc.) del discurso previo.

El type **elaboration** contiene los siguientes subtypes: appositive y clarifying. Estos values se explicarán en el feature **subtype**.

| Class | Value | Ejemplo |
| ----- | ----- | ------- |
| TYPE  | Elaboration | _(El protagonista), **o** [el personaje principal de la fábula, es Hércules]._ |

#### Extension<a name="id8"></a>

El value **extension** indica que el Elemento B extiende lo dicho en el Elemento A. A diferencia del value elaboration, el Elemento B amplía el significado del Elemento A añadiendo algo nuevo, en lugar de repetir la tesis del Elemento A con diferentes palabras.

El type **extension** contiene los siguientes subtypes: additive y varying. Estos values se explicarán en el feature **subtype**.

| Class | Value | Ejemplo |
| ----- | ----- | ------- |
| TYPE  | Extension | _(Ellos salieron al cine) **y** [a comer algo]._ |

#### Enhancement<a name="id9"></a>

El value **enhancement** indica que el Elemento B mejora, incrementa o amplifica lo dicho por el Elemento A. Así pues, el Elemento B agrega información referente al Elemento A con cualificaciones relativas a especificaciones de tiempo, lugar, causa, condiciones, etc. Se trata de ampliaciones a manera de circunstanciales, sobre todo de causalidad y temporalidad.


El type **enhancement** contiene los siguientes subtypes: spatio temporal, manner, causal conditional y matter*. Estos values se explicarán en el feature **subtype**.

| Class | Value | Ejemplo |
| ----- | ----- | ------- |
| TYPE  | Enhancement | _(No pude ir) **porque** [se me hizo tarde]._ |


## SUBTYPE<a name="id10"></a>

El feature **subtype** incluye subtipos de los values expuestos en el feature **type**.

#### Appositive<a name="id11"></a>

El value **appositive** es un subtype del type **elaboration** y refiere a que el Elemento B presenta de nuevo o replantea lo dicho en el Elemento A. Este replanteamiento se consigue por exposición (explicación con otras palabras, similar a lo introducido por un *es decir* u *en otras palabras*) o por ejemplificación. No se trata de una aclaratoria, sino de agregar un ejemplo o una pequeña explicación sobre lo dicho.

Este value tiene dos sub-subtypes: appositive expository y exemplifying.


#### Clarifying<a name="id12"></a>

El value **clarifying** es un subtype del type **elaboration** e indica que el Elemento B aclara información sobre lo dicho en el Elemento A. Aquí el Elemento A es clarificado para los propósitos del discurso. Esta aclaratoria, a diferencia del Appositive, puede resumir (_resumiendo, en conclusión_), particularizar *en particular*, auto-corregir *o sea*, o reconstruir lo dicho en el Elemento A. El Elemento B entonces reconstruye y re-elabora lo dicho anteriormente para que el discurso previo se aprecie con más claridad.

Este value tiene como sub-subtypes: corrective, distractive, dismissive, particularizing, resumptive, summative y verifactive.


#### Additive<a name="id13"></a>

El value **additive** es un subtype del type **extension** e indica que el Elemento B agrega nueva información sobre lo dicho en el Elemento A. Esta adición puede ser positiva (con la conjunción *y*), negativa (conjunción *ni*), o adversativa (conjunción *pero*).

Este value tiene como sub-subtypes: additive positive, negative o adversative.


#### Varying<a name="id14"></a>

El value **varying** es un subtype del type **extension** e indica que el Elemento B presenta una alternativa o variedad de lo planteado en el Elemento A. Esta alternativa puede ser una sustitución de un argumento (con la conjunción *en cambio*), la presentación de una excepción (*excepto*), o la adición de diversas opciones nuevas (conjunción *o*).

Este value incluye los sub-subtypes: replacive, subtractive y alternative.


#### Spatio temporal<a name="id15"></a>

El value **spatio temporal** es un subtype del type **enhancement** e indica que el Elemento B agrega información espacio-temporal con respecto al Elemento A. Se trata de una referencia con respecto a un lugar o tiempo. Este espacio-tiempo puede ser metafórico también con respecto al discurso.

Se subdividen en dos tipos de referencia: simples y complejas. Las simples establecen relaciones temporales sencillas (como lo *primero*, lo *último*, lo *previo*, etc.). Las complejas se basan en los usos de las simples, pero agregando algún aspecto semántico: algo que sucede *al mismo tiempo*, o que ocurre *hasta un momento* para terminar luego, entre otras relaciones semejantes.

Este value incluye los sub-subtypes: simple following, simple fimultaneous, simple preceding, simple conclusive, complex immediate, complex interrupted, complex repetitive, complex specific, complex durative, complex terminal, y complex punctiliar.


#### Manner<a name="id16"></a>

El value **manner** es un subtype del type **enhancement** e indica que el Elemento B especifica la manera en que se produce el Elemento A, o lo dicho sobre este último, utilizando como procedimiento general la comparación: (*así pues*, *de tal manera*).

Este value incluye los siguientes sub-subtypes: comparative positive, comparative negative y reference to means.

#### Causal Conditional<a name="id17"></a>

El value **causal conditional** es un subtype del type **enhancement** e indica que el Elemento B agrega una causa (*porque*), condición (*en ese caso*), resultado (*como consecuencia*), razón (*por esa razón*) o propósito (*con ese objetivo en mente*) respecto al Elemento A.

Este value incluye los siguientes sub-subtypes: causal general, causal specific result, causal specific reason, causal specific purpose, conditional positive, conditional negative y concessive.

#### Matter<a name="id18"></a>

El value **matter** es un subtype del type **enhancement** e indica que el Elemento B se refiere a un asunto mencionado previamente en el Elemento A.

Este value incluye los siguientes sub-subtypes: matter positive y negative.


## SUB-SUBTYPE<a name="id19"></a>

El feature de tipo **sub-subtype** incluye values más específicos que los expuestos en el feature subtype. Se trata de los features distintivos de este modelo, ya que los anteriormente expuestos (type y sub-type) son utilizados sobre todo con el propósito de organizar macro-valores.

Los ejemplos se presentarán al final de los features relacionados para que pueda apreciarse mejor el contraste.


#### Expository<a name="id20"></a>

El value **expository** es un sub-subtype del value **appositive**, el cual indica que el Elemento B re-presenta o reitera lo dicho en el Elemento A por medio de una explicación o exposición.


#### Exemplifying<a name="id21"></a>

El value **exemplifying** es un sub-subtype del value **appositive**, el cual indica que el Elemento B re-presenta o reitera lo dicho en el Elemento A por medio de un ejemplo.

| SUBTYPE | SUB-SUBTYPE | Ejemplo |
| ----- | ----- | ------- |
| Appositive  | Expository | _(Pedro reprobó el examen de conductor), **es decir**, [que no podrá conducir su automóvil]._ |
| Appositive  | Exemplifying | _(Los colores pueden tener diferentes significados); **por ejemplo**, [el blanco es el color de las bodas en algunas culturas y de los funerales en otras]._ |

#### Corrective<a name="id22"></a>

El value **corrective** es un sub-subtype del value **clarifying**, el mismo que indica que el Elemento B rectifica o reformula lo dicho en el Elemento A.

#### Distractive<a name="id23"></a>

El value **distractive** es un sub-subtype del value **clarifying**, el mismo que indica el inicio de un nuevo tema parcialmente relacionado o no con el Elemento B, cambiando el foco de atención de lo dicho en el Elemento A.

#### Dismissive<a name="id24"></a>

El value **dismissive** es un sub-subtype del value **clarifying**, el cual indica que el Elemento B se usa para desestimar o descartar lo dicho en el Elemento A (generalmente se descarta lo dicho por el otro interlocutor).

#### Particularizing<a name="id25"></a>

El value **particularizing** es un sub-subtype del value **clarifying**, el cual indica que el Elemento B particulariza lo dicho en el Elemento A; es decir, resalta un aspecto implícito o explícito de lo dicho en el Elemento A.

#### Resumptive<a name="id26"></a>

El value **resumptive** es un sub-subtype del value **clarifying**, el mismo que indica que el Elemento B reanuda o retoma lo dicho en el Elemento A.

#### Summative<a name="id27"></a>

El value **summative** es un sub-subtype del value **clarifying**, el cual indica que el Elemento B resume o construye una conclusión a partir de lo dicho en el Elemento A.

#### Verificative<a name="id28"></a>

El value **verificative** es un sub-subtype del value **clarifying**, el cual indica que el Elemento B proporciona evidencia sobre lo dicho en el Elemento A.


| SUBTYPE | SUB-SUBTYPE | Ejemplo |
| ----- | ----- | ------- |
| Clarifying  | Corrective | _(Mañana iremos a trotar a las 4), **o más bien** [a las 5 de la tarde]._ |
| Clarifying  | Distractive |  _(Es lamentable lo que está ocurriendo). **Entonces**, [¿me decías que perdió el conocimiento?]_ |
| Clarifying | Dismissive | _(La culpa es de ella) -dicho por el interlocutor A-. **Dejando eso de lado,** [¿no te parece mejor que vayamos saliendo?] -dicho por el interlocutor B-_ |
| Clarifying | Particularizing | _(El ejercicio del poder en Gran Bretaña), **específicamente**, [en Inglaterra, no puede ser entendido a menos que sea reconocido como tal]._ |
| Clarifying | Resumptive | _(La madre era una compañera de Amadeo, trabajadora y buena gente… Bueno), **para no desviarnos del punto**, [le contaré la aventura de aquél día]._ |
| Clarifying | Summative | _(Hoy fuimos al banco, al mercado, a la universidad, etc). **O sea**, [hicimos las diligencias]._ |
| Clarifying | Verificative | _(Me dieron un golpe terrible). **De hecho** [aquí se puede ver el moretón]._ |

#### Positive<a name="id29"></a>

El value **positive** es un sub-subtype del value **additive**, el cual indica que el Elemento B agrega información sobre lo dicho en el Elemento A de forma positiva.

#### Negative<a name="id30"></a>

El value **negative** es un sub-subtype del value **additive**, el cual indica que el Elemento B agrega información sobre lo dicho en el Elemento A de forma negativa.

#### Adversative<a name="id31"></a>

El value **adversative** es un sub-subtype del value **additive**, el cual indica que la información que se agrega en el Elemento B contrasta con, o se opone a, lo dicho en el Elemento A.

| SUBTYPE | SUB-SUBTYPE | Ejemplo |
| ----- | ----- | ------- |
| Additive  | Positive | _(La casa es bella). **Además**, [tiene una excelente ubicación]._ |
| Additive  | Negative | _(Eso no, Sancho; que el necio en su casa) **ni** [en la ajena sabe nada]._ |
| Additive | Adversative | _(La idea es buena), **pero** [no se puede llevar a la práctica]._ |

#### Replacive<a name="id32"></a>

El value **replacive** es un sub-subtype del value **varying**, el cual indica que el Elemento B sustituye o reemplaza al Elemento A.

#### Substractive<a name="id33"></a>

El value **substractive** es un sub-subtype del value **varying**, el cual indica que el Elemento B expresa una excepción a algo dicho en el Elemento A.

#### Alternative<a name="id34"></a>

El value **alternative** es un sub-subtype del value **varying**, el cual indica que el Elemento B señala una alternativa al Elemento A.

| SUBTYPE | SUB-SUBTYPE | Ejemplo |
| ------- | ----- | ------- |
| Varying | Replacive |  _(Teníamos planeado ir de vacaciones); **en cambio** [decidimos quedarnos en casa]._ |
| Varying | Substractive | _(Es amable), **excepto** [cuando se le lleva la contraria]._ |
| Varying | Alternative | _(Debes decidir si te vas) **o** [te quedas]._ |

#### Simple Following<a name="id35"></a>

El value **simple following** es un sub-subtype del value **spatio temporal**, el cual indica que los Elementos A y B están unidos por una secuencia temporal o espacial en el discurso. Incluye correlativos como *primero*, *segundo*, *entonces*, *luego*, etc.

#### Simple simultaneous<a name="id36"></a>

El value **simple simultaneous** es un sub-subtype del value **spatio temporal**, el cual indica que los Elementos A y B se presentan como eventos que tienen lugar al mismo tiempo en el discurso.

#### Simple preceding<a name="id37"></a>

El value **simple preceding** es un sub-subtype del value **spatio temporal**, en el cual la conjunción indica que el Elemento B tuvo lugar anteriormente (es anterior, previo) al Elemento A.

#### Simple conclusive<a name="id38"></a>

El value **simple conclusive** es un sub-subtype del value **spatio temporal** el cual indica que el Elemento B que sigue a la conjunción es el último de una sucesión de eventos. De manera que, posterior al Elemento B, no se percibe más información de dicha secuencia.

| SUBTYPE | SUB-SUBTYPE | Ejemplo |
| ------- | ----- | ------- |
| Spatio temporal | Simple following | _(Si está lloviendo), **entonces** [no podemos hacer el picnic]._ |
| Spatio temporal | Simple simultaneous |  _(Atacaron el banco de España) **mientras** [derrocaban al gobierno]._ |
| Spatio temporal | Simple preceding | _[El niño vive ahora con su padre]. **Anteriormente**, (estaba bajo la protección de su madre)._ |
| Spatio temporal | Simple conlcusive | _**Finalmente**, [es importante conocer la fuente del la información antes de compartirlar en redes sociales]._ |


#### Complex immediate<a name="id39"></a>

 El value **complex immediate** es un sub-subtype del value **spatio temporal** en el cual la conjunción indica que el Elemento B es un evento que tiene lugar en un tiempo muy cercano (inmediato) a lo dicho en el Elemento A.

#### Complex interrupted<a name="id40"></a>

El value **complex interrupted** es un sub-subtype del value **spatio temporal** en el cual la conjunción indica que el evento descrito en el Elemento B tiene lugar un corto tiempo (no inmediato) después del evento del Elemento A.

#### Complex repetitive<a name="id41"></a>

El value **complex repetitive** es un sub-subtype del value **spatio temporal** el cual indica que la conjunción une un Elemento A que se repite en el tiempo y un Elemento B que es parte de esta repetición, pero que se lleva a cabo de una manera distinta.

#### Complex specific<a name="id42"></a>

El value **complex specific** es un sub-subtype del value **spatio temporal** el cual permite indicar que por medio de la conjunción el hablante une una secuencia de eventos, indicando que el evento narrado en el Elemento B se inició en un momento puntual, pero no se sabe en qué momento finalizará.

#### Complex durative<a name="id43"></a>

El value **complex durative** es un sub-subtype del value **spatio temporal** el cual permite indicar que los eventos A y B suceden al mismo tiempo, pero que lo expuesto por el Elemento B aporta o agrega más información sobre lo descrito en esos hechos simultáneos. En otras palabras, lo dicho en el Elemento B supone algo que sucedió durante lo expuesto por el Elemento A, agregando información muy relevante.

#### Complex terminal<a name="id44"></a>

El value **complex terminal** es un sub-subtype del value **spatio temporal** el cual permite indicar que con esta conjunción el hablante muestra que el Elemento B es un límite temporal a lo dicho por el Elemento A.

#### Complex punctiliar<a name="id45"></a>

El value **complex punctiliar** es un sub-subtype del value **spatio temporal** el cual indica que la conjunción contrasta a un Elemento A con un Elemento B, y el Elemento B tiene lugar en un momento puntual.


| SUBTYPE | SUB-SUBTYPE | Ejemplo |
| ------- | ----- | ------- |
| Spatio temporal |  Complex immediate |  _[Yo estudié] **una vez** (terminado el almuerzo)._ |
| Spatio temporal | Complex interrupted | _(Él amaba la poesía), **luego** [empezó a escribir sus propios poemas]._ |
| Spatio temporal | Complex repetitive | _(En un principio los estudiantes dijeron que salieron mal por culpa del profesor). **Tiempo después** [rectificaron y asumieron que fue por no haber estudiado]._ |
| Spatio temporal |Complex specific | _(Yo me fui a acostar) **y** [ellos se quedaron echando cuentos]._
| Spatio temporal |Complex durative | _**Mientras** (te sigas portando mal), [continuarás castigado]._ |
| Spatio temporal |Complex terminal| _(Cuando iba a despegar el avión me puse nerviosa), **anteriormente** [no me había pasado]._|
| Spatio temporal |Complex punctiliar |_(Yo solía ir a gimnasio en las mañanas), **pero** [ahora no lo hago]._ |


#### Comparative positive<a name="id46"></a>

El value **comparative positive** es un sub-subtype del value **spatio temporal**  el cual indica que el Elemento B se compara con el Elemento A de forma positiva.

#### Comparative negative<a name="id47"></a>

El value **comparative negative** es un sub-subtype del value **spatio temporal**  el cual indica que el Elemento B se compara con el Elemento A de forma negativa.

#### Reference to means<a name="id48"></a>

El value **reference to means** es un sub-subtype del value **spatio temporal**  el cual indica que el Elemento B hace referencia a un producto logrado a partir de los medios mencionados en el Elemento A.


| SUBTYPE | SUB-SUBTYPE | Ejemplo |
| ------- | ----- | ------- |
| Manner | Comparative positive |_[Ella es tan inteligente] **como** (su madre)._|
| Manner | Comparative negative| _[No me agradan las personas amargadas] **como** (tú)._|
| Manner | Reference to means |_(Empezó a llover). **Entonces** [tendremos que llevar paraguas]._ |


#### Causal general<a name="id49"></a>

El value **causal general** es un sub-subtype del value **Spatio temporal** el cual indica que el Elemento A es el causante del Elemento B.

#### Causal specific result<a name="id50"></a>

El value **causal specific result** es un sub-subtype del value **spatio temporal** el cual indica que el Elemento B es el resultado de lo mencionado en el Elemento A. La conjunción introduce el resultado.

#### Causal specific reason<a name="id51"></a>

El value **causal specific reason** es un sub-subtype del value **spatio temporal** el cual indica que el Elemento B especifica las razones que dieron origen al Elemento A. La conjunción introduce la causa.

#### Causal specific purpose<a name="id52"></a>

El value **causal specific purpose** es un sub-subtype del value **spatio temporal**  el cual señala que el Elemento A indica un propósito del Elemento B.

#### Conditional positive<a name="id53"></a>

El value **conditional positive** es un sub-subtype del value **spatio temporal** el cual señala que el Elemento A es una condición para que el Elemento B tenga lugar. Esta condición se expresa de forma positiva.

#### Conditional negative<a name="id54"></a>

El value **conditional negative** es un sub-subtype del value **spatio temporal** el cual indica que el Elemento A expresa una condición para que el Elemento B tenga lugar. Esta condición se expresa de forma negativa.

#### Concessive<a name="id55"></a>

El value **concessive** es un sub-subtype del value **spatio temporal** donde la conjunción hace que el Elemento B no sea excluído de lo propuesto en el Elemento A.


| SUBTYPE | SUB-SUBTYPE | Ejemplo |
| ------- | ----- | ------- |
| Causal conditional |Causal general |  |
| Causal conditional  | Causal specific result| _(Vamos tan despacio) **que** [no llegaremos a tiempo]._|
| Causal conditional  | Causal specific reason | _(Vete ahora mismo), **que** [llegarás tarde]._|
| Causal conditional  | Causal specific purpose |_(Acércate), **para** [te vea bien]._|
| Causal conditional  | Conditional positive |_(Llegarás a tiempo), **si** [sales ahora]._|
| Causal conditional  | Conditional negative |_(Yo iría a clases) **si no** [estuviese lloviendo tan fuerte]._|
| Causal conditional  | Concessive | _(Siempre quiso tener una casa en ese país), **aun** [sabiendo que iba de paso]._|


#### Matter Positive<a name="id56"></a>

El value **matter positive** es un sub-subtype del value **spatio temporal** el cual indica que el Elemento B se refiere de forma positiva a un asunto que ha sido mencionado previamente en el texto.

#### Matter Negative<a name="id57"></a>

El value **matter negative** es un sub-subtype del valor **spatio temporal** el cual indica que el Elemento B se refiere de forma negativa a un asunto que ha sido mencionado previamente en el texto.

| SUBTYPE | SUB-SUBTYPE | Ejemplo |
| ------- | ----- | ------- |
| Matter | Positive | _(Esto es matemáticas). *Acá* [no valen las interpretaciones subjetivas]._|
| Matter  | Negative|_(Esto es matemáticas). *Pero* [hablaremos tambíen sobre otros temas]._  |
