# Oración (nivel: intercambio comunicativo - es)


## DIMENSIÓN EXCHANGE<a name="id50"></a>

El propósito de este instructivo es servir de herramienta para el anotado de la dimensión **exchange** para la Prueba Piloto de Mammut.
Este instructivo está diseñado para anotar todo elemento que aparezca en el nivel de **exchange** de un corpus mammut sin dejar residuos.

## MOOD<a name="id2"></a>

El **mood** está constituido por el Subject (Sujeto) y el Finite (Elemento Finito), es la parte de la cláusula que está sometida a cambios gramáticales mientras que el resto continúa intacto.

Ejemplos: _**Él fue** a clases en la mañana_;_**Él irá** a clases en la mañana_; _**Él va** a clases en la mañana._

>  NOTA: Debido a que en la mayoría de los casos del español la información del Finite y del Predicator están fucionadas en una misma palabra, y para los efectos de la anotación, la etiqueta Finite-predicator será enlazada tanto dentro del **mood**, como en el RESIDUE.

## MOOD TYPE (Tipos de Mood)<a name="id3"></a>
El feature **mood type** indica la actitud de quien emite el mensaje ante el mismo. Este puede tratarse de una orden (imperative), hechos no reales (subjunctive) o hechos materializados (indicative).

#### Imperative (Imperativo)<a name="id4"></a>
El value **imperative** se utiliza para indicar que se está exigiendo bienes y servicios. Según su estructura, en el español no tiene más formas propias que la segunda persona y generalmente el subject se mantiene tácito.

Ejemplos: _**Sal** de ahí_ ; _**Entra** al establecimiento._

#### Subjunctive (Subjuntivo)<a name="id5"></a>
El value **subjunctive** señala el carácter ficticio, no real, de lo que denota el significado del predicador. Puede expresar deseo, intención, inseguridad o necesidad. 

El Mood subjuntivo se desenvuelve en cuatro tiempos.

Ejemplos: _Tú quieres que **yo cante**_ ; _**Él hubiera comido** lo que cociné._

| Mood       | Tense         | Ejemplos                           |
| ---------- | ------------- | ---------------------------------- |
| subjuntivo | presente      | *cante, beba, viva*                |
| subjuntivo | pretérito     | *cantara/cantase, bebiera/bebiese* |
| subjuntivo | antepresente  | *haya cantado*                     |
| subjuntivo | antepretérito | *hubiera/hubiese cantado*          |

#### Indicative (Indicativo)<a name="id6"></a>
El value **indicative** designa la “no ficción” de lo denotado por el predicator, esto es, todo lo que el hablante estima real o cuya realidad o irrealidad no se cuestiona.

Ejemplos: _**Yo canto** en la ducha_; _**El lavará** la ropa_.

| Mood       | Tense            | Ejemplos                     |
| ---------- | ---------------- | ---------------------------- |
| indicativo | presente         | *canto, bebo, vivo*          |
| indicativo | pretérito        | *canté, bebí, viví*          |
| indicativo | copretérito      | *cantaba, bebía, vivía*      |
| indicativo | postpretérito    | *cantaría, bebería, viviría* |
| indicativo | futuro           | *cantaré, beberé, viviré*    |
| indicativo | antepresente     | *he cantad, he vivido*       |
| indicativo | antepretérito    | *hube cantado*               |
| indicativo | antecopretérito  | *había cantado*              |
| indicativo | antepospretérito | *habría cantado*             |
| indicativo | antefuturo       | *habré cantado*              |

## INFORMATION TYPE (Tipos de Información en el Mood)<a name="id7"></a>
El feature **information type** señala si se está dando una información (declaración) o si se está pidiendo (pregunta). Para este caso, la cláusula indicativa puede ser tanto declarativa como interrogativa.

| Interrogative      | Declarative         |
| ------------------ | ------------------- |
| ¿Te gusta el café? | Me encanta el café. |

#### Tipos de Mood Interrogativo<a name="id8"></a>
Las cláusulas interrogativas se dividen del tipo yes/no (InterrogativeNonWH) y las que contienen algún elemento WH (InterrogativeWH).

##### Cláusulas interrogativas de Polaridad (InterrogativeNonWH)<a name="id9"></a>
El value **interrogationNonWH** indica que la clausula interrogativa se basa en el caracter cierto o incierto de un hecho, por esta razón las respuestas obtenidas son del tipo **Si/no**.

Ejemplo: _¿Tienes sueño?; ¿Desean ordenar ahora?_

Estas oraciones, en el Español, tienen la misma estructura que una cláusula declarativa, su punto de diferenciación está en la entonación producida por el hablante.

##### Cláusulas interrogativas con elemento WH- (InterrogativeWH)<a name="id10"></a>
El value **interrogativeWH** indica que en la clausula interrogativa se encuentra un elemento **WH-** (Pronombre interrogativo) que tiene como función especificar la entidad que el interrogador desea saber; **como el Subject, Complement o Adjunct.**

Ejemplo: _¿**Qué** desean ordenar? ; ¿**Dónde** está ubicado el local?_

También pueden estar precedidos por una preposición. Ejemplo: _¿**De qué** está hecha esta hamburguesa? ; ¿**Hasta qué** hora trabajan?_.

> NOTA: En caso de que un **elemento WH-** se encuentre en posición de Adjunct o Complement (o sea, fuera del Mood, como en _“¿A qué hora abren?” o “¿Qué ofreces?”_, el MOOD seguirá portando la característica de (**interrogativeWH**) puesto que el MOOD es un elemento que afecta a toda la cláusula.

| Elementos Wh- |
| ------------- |
| Quién(es)     |
| Cuándo        |
| Dónde         |
| Cuánto        |
| Qué           |
| Cuál(es)      |
| Cómo          |

##  MOOD IMPERSONALITY (Tipos de Mood según la presencia del Subject)<a name="id11"></a>
El feature **mood impersonality** indica los tipos de Mood que pueden presentarse dependiendo de si en la clausula hay o no un subject.

#### Mood personal<a name="id12"></a>
El value **mood personal** se utiliza para indicar que hay presencia del Subject dentro de la cláusula; por lo tanto, se trata de un Mood en el cual el Finite constituyente puede conjugarse en todos los paradigmas de flexión de persona (1era, 2da y 3era persona) y número (singular y plural), principalmente.

Ejemplo: _Mañana **el cafetín abrirá** a las diez._

#### Mood Impersonal<a name="id13"></a>
El value **mood impersonal** se utiliza para indicar que el Mood carece de sujeto y que, por lo tanto, al no poder concordar con él, ha de conjugarse siempre en 3era persona del singular que es la persona por defecto.

Ejemplo: _**Hay** varios postres en el menú_.


## SUBJECT (Sujeto)<a name="id14"></a>
El **subject** es el elemento que hace referencia a aquello sobre lo cual una proposición o propuesta puede ser afirmada o negada; se trata de una entidad sobre la cual pesa la responsabilidad del funcionamiendo de la cláusula como evento interactivo. Una proposición es algo sobre lo cual se puede argumentar (afirmar, negar, dudar, contradecir, insistir, aceptar, arrepentirse, etc.)

Ejemplo: _**Roberto** lanzó la pelota._

En este caso 'Roberto' es el **subject**, ya que es la entidad de la que se afirma algo. La “verdad” del enunciado depende no de si alguien lanzó una pelota, sino de que haya sido precisamente 'Roberto' quien lo haya hecho. Desde el punto de vista de la estructura, el **subject** en español se caracteriza por ser un Nominal Group cuyo núcleo (simple o compuesto) concuerda en persona y número con el Verb y, de ser un pronombre personal, estará en 'caso nominativo'.

Por ejemplo, en *'Me sobran las propuestas'* el **subject** es *'las propuestas'* ya que el Verb está conjugado en tercera persona del plural. *'Me'* no podría ser el Subject, además, porque no está en caso nominativo.

| Definición                                                                                   | Ejemplo                                                                                                                                       |
| -------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Grupo nominal. Elemento con respecto al cual se dice, se pregunta, se pide o se ofrece algo. | _**Roberto** lanzó la pelota_.                                                                                                              |
| No marcado de una declarativa (corresponde al Theme)                                         | _**Yo** amo el chocolate. Amo el chocolate (tácito o implícito)._                                                                        |
| No marcado en una interrogativa Yes/No                                                       | ¿_**Roberto** lanzó la pelota? (grupo nominal que concuerda con el verbo en persona y número)_.                                             |
| No marcado en una interrogativa Wh-                                                          | _¿A quién ama **Romeo**? ¿**Quién** ama a Romeo? (Grupo nominal con respecto al cual se pregunta algo que no empiece con Preposition)_. |
| Voz pasiva: diferencia entre Subject y Actor.                                                | _**El libro** fue escrito por un famoso periodista y escritor. Subject: **El libro**. Actor: **un famoso periodista y escritor**._              |

#### Identificación

1.  El Subject concuerda con el Verb en persona y número.

 Ejemplo: _**Blanca llevó** el libro al colegio*_  

 Una vez localizado el Verb, se puede cambiar el número original para corroborar el Subject de la oración. Ejemplo: _**Ellas** llevaron el libro al colegio._

2.  El Subject no siempre precede al Verb, puede aparecer posterior al Verb de la oración.

 Ejemplo: _Me gusta **el chocolate**._

3.  En español, es posible que el Subject no aparezca en la oración. Puede existir un Subject tácito, también conocido como Subject omitido, Subject sobreentendido o Subject implícito. En estos casos, las formas verbales son las que van a determinar la persona y el número del Subject.

 Ejemplo: *Voy a la playa*

 (Subject= *YO*. El Subject aparece dentro del Verb “voy” = yo voy). En estos casos, el Subject debe ser repuesto antes del análisis por medio de una RESTITUCIÓN.

4.  En preguntas tales como _¿**Cuál** es el horario de Mammut Restaurant?_ el Subject se reconoce porque es el elemento que se puede sustituir por el Pronoun *ese*.

## SUBJECT PERSON<a name="id15"></a>

El feature **subject person** indica si el **subject** en cuestión es alguno de los participantes de la conversación o si se trata de un elemento externo que se referencia en la cláusula.

#### Interactant<a name="id16"></a>
El value **interactant** señala que el *subject* asume el rol de emisor o receptor dentro del intercambio comunicativo en la cláusula. La primera y segunda persona, singular y plurar, hacen referencia al ‘yo’ como emisor del mensaje y el ‘tú’ como el receptor de tal, por consiguiente se apunta como **interactant**.

Ejemplo: _¿Hasta qué hora trabajan **ustedes**?_: Subject Interactant. _**Yo** iré en la tarde_ : Subject Interactant.

#### Non Interactant<a name="id17"></a>
El value **non interactant** señala un elemento que está fuera del intercambio; por ende, es un Subject **Non Interactant**. En caso de que el *subject* sea un elemento WH, este portara el value **non interantant**.

Ejemplo: _**El postre** me gustó_: Subject Non-Interactant.


| Clase          | Ejemplo                                                                                | Característica                                                    |
| -------------- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Subject Wh     | ¿_**Quién** vende eso?; ¿**Cuál** es el mejor?; ¿**Qué** está pasando?_; | Subject con un Thing Wh                                           |
| Subject Wh     | _¿**Cuál** empanada me recomiendas?_; ¿**Qué** cosa está pasando?            | Subject con un Deictic Wh                                         |
| Subject Wh     | _Dime **qué** es eso_                                                           | El *qué* es el Subject Wh de la cláusula dependiente *qué es eso* |
| Subject Non Wh | _¿**Pedro** vendrá?; Me encantan **esas empanadas**                         | Subject que no tiene un elemento Wh                               |


## FINITE (Finito)<a name="id18"></a>

El **finite element** tiene como función hacer finita la proposición o propuesta; esto quiere decir que ancla la cláusula a un punto de referencia vinculado con el aquí y el ahora. De esta forma relaciona la proposición con el acto de habla como evento. Esta contextualización se da, sobre todo, con relación al momento de la enunciación (Primary Tense) y con el punto de vista del juicio del emisor (Modality).

El Finite en español se reconoce porque se trata siempre de un **verb conjugado**.

## TEMPORAL OPERATORS (Operadores temporales)<a name="id19"></a>

El feature **temporal operators** indica cuándo pasa lo que se dice del Subject. La expresión tiempo no se reduce a señalar si el hecho es “ahora”, “antes de ahora” o “después de ahora”, sino que a veces detalla si un hecho “pasado” es anterior a otro hecho ocurrido en el pasado, si un hecho “futuro” es anterior a otro hecho que ocurrirá en el futuro, o si el hecho es visto o no como algo durativo, todo esto se encuentra expresado en la misma conjugación verbal. En la anotación en español el Primary Tense dependerá de si el modo es indicativo, subjuntivo o imperativo.

Los tiempos del Primary Tense del Finite en el modo indicativo en español son diez en total: uno para expresar el *present*, cinco para señalar el *past* y cuatro para indicar el *future*.

En una oración que tenga un Verb pleno, la información del Finite se encuentra implícita dentro del Verb: Ejemplo: _Ella **jugaba** todas las noches bingo_. (**jugaba** es tanto Finite como Predicator (finite-predicator).

Los tiempos compuestos se construyen con la conjugación del Verb HABER como auxiliar, en estos casos _haber_ va a tener la función de Finite y el participio pasado del Verb que funcionará como Predicator. En el caso del tiempo compuesto, se anota solo el tiempo del Finite.

**Modo indicativo**

| Polaridad           | Antepresente      | Antepretérito      | Antecopretérito     | Antefuturo           | Antepospretérito     |
| ------------------- | ------------------ | ------------------- | --------------------- | --------------------- | --------------------- |
| positiva no marcada | *he* (cantado)    | *hube* (cantado)    | *había* (cantado)    | *habré* (cantado)   | *Habría* (cantado)    |
| positiva marcada    | *Sí he* (cantado) | *Sí hube* (cantado) | *Sí había* (cantado) | *Sí habré* (cantado) | *Sí habría* (cantado) |
| negativa marcada    | *No he* (cantado) | *No hube* (cantado) | *No había* (cantado) | *No habré* (cantado) | *No habría* (cantado) |

**Modo subjuntivo**

| Polaridad           | Antepresente        | Antecopretérito                       | Antefuturo             |
| ------------------- | ------------------- | ------------------------------------- | ---------------------- |
| positiva no marcada | *haya* (cantado)    | *hubiera* o *hubiese* (cantado)       | *hubiere* (cantado)    |
| positiva marcada    | *Sí haya* (cantado) | *Sí hubiera* o *Sí hubiese* (cantado) | *Sí hubiere* (cantado) |
| negativa marcada    | *No haya* (cantado) | *No hubiera* (cantado)                | *No hubiere* (cantado) |

La construcción del tiempo *Fúturo Perifrástico* usa como Auxiliar el Verb **ir** conjugado que será el **finite** combinado con una forma en infinitivo del *Predicator*. La Preposition **SÍ** se anota como parte del Predicator.

| Polaridad           | IR (Finite) + A | \+ Predicator (Infinitivo) |
| ------------------- | --------------- | -------------------------- |
| positiva no marcada | *voy a*         | *comer* …                  |
| positiva marcada    | *Sí iré a*      | *bailar* …                 |
| negativa marcada    | *No voy a*      | *cantar* ….                |

## POLAR OPERATORS (Operadores modales)<a name="id20"></a>

El feature **polar operator** es una característica del Finite que indica, dentro del mismo, la polaridad de la clausula; es decir, si la proposición es negativa o positiva, esto se expresa mediante un **modal adjunct**.

#### Positive (positiva)<a name="id21"></a>
El value **positive** indica que el Verb funciona como una afirmación.

Cuando el Modal Adjunct esté ausente, la polaridad será positiva. En estos casos, el feature **polar operators** se debe anotar como *finite Polar Positive*.

Ejemplo: _Ayer fui al cine_.

#### Negative (negativa)<a name="id22"></a>
El value **negative** indica que hay una negación en alguna parte de la cláusula que implica que la proposición es negativa (Modal Adjunct).

En estos casos, cuando haya algun **adverbio** que tenga forma negativa (Modal Adjunct) y que modifique al finite o finite-predicator, vamos a decir que su polaridad es negativa.

El *No*, al igual que *Nunca*, son Adverbios de Negación y, a su vez, Modal Adjuncts. En estos casos, el feature **polar operators** se debe anotar como *Finite Polar Negative*.

Ejemplos:

| ¿No           | tienen            | empandas   | en Mammut Restaurant? |
| ------------- | ----------------- | ---------- | --------------------- |
| Modal Adjunct | Finite/predicator | Complement | Adjunct               |

| En Mammut Restaurant | nunca         | hay               | empanadas. |
| -------------------- | ------------- | ----------------- | ---------- |
| Adjunct              | Modal Adjunct | Finite/predicator | Subject    |


## MODALITY TYPE (Tipo de Modalidad)<a name="id23"></a>

El feature **modality type** se encarga de interpretar los grados intermedios entre los polos negative y positive (*POLAR OPERATORS*).

#### Probability (probabilidad)<a name="id24"></a>
El value **probability** indica que la proposición es probable o posible.

#### Usuality (frecuencia)<a name="id25"></a>
El value **usuality** indica que la proposición es frecuente.

#### Obligation (obligación)<a name="id26"></a>
El value **obligation** señala que la proposición se presenta como algo necesario.

#### Inclination (inclinación)<a name="id27"></a>
 El value **inclination** indica que el hablante implica que desea que la proposición se cumpla.


## MODALITY VALUE<a name="id28"></a>

El feature **modality value** tiene estrecha relación con los *Modality Type*, ya sea si la probabilidad es alta, media o baja, y de igual manera con la frecuencia (usuality), obligación o inclinación.

  - **High** (alto)
  - **Medium** (medio)
  - **Low** (bajo)

Muchas de estas características se marcan fuera del Finite en muchos casos. Aun así, durante la anotación se marcarán como una característica dentro del Finite.

#### Modal Operators en Verbal Groups
Se pueden usar Modal Verbs dentro de Verbal Groups para marcar las características anteriores. El Modal Verb, como verbo conjugado, se anota como Finite. En la anotación no se incluye la negación dentro del Finite.

| Polaridad           | Poder                     | Deber                   | Querer                       | Saber                             | Necesitar                         | Soler                     |
| ------------------- | ------------------------- | ----------------------- | ---------------------------- | --------------------------------- | --------------------------------- | ------------------------- |
| positiva no marcada | *puedo*, *podría*…      | *debo*, *debía*…       | *quiero*, *quisiera*…      | *sé*, *sabía*…                    | *necesito*, *necesitaba*…        | *suelo*, *solía*…         |
| positiva marcada    | *Sí* *puedo*, *podría*… | *Sí* *debo*, *debía*…  | *Sí* *quiero*, *quisiera*… | *Sí* *sé*, *sabía*…               | *Sí* *necesito*, *necesitaba*…   | *Sí* *suelo*, *solía*…    |
| negativa marcada    | *no puedo*, *no podría*… | *no debo* , *no debía*… | *no quiero*, *no quisiera*… | *no sé*, *no sabía* …             | *no necesito* , *no necesitaba*… | *no suelo* , *no solía* . |
| Ejemplo             | *No pude entrar*         | *Debí empezar ayer*    | *Quisi era tenerte*         | *Ella sí sabía cocinar muy bien* | *Necesito hablar contigo*         | *No solías ignorarme*.   |

## RESIDUE<a name="id29"></a>
**El **residue** es un elemento que contiene todos los demás elementos que no van dentro del **mood**, como los Adjunct NO modales como los circunstanciales o conjunctivos, el predicator y los Complements.**

## PREDICATOR (Predicador)<a name="id30"></a>

El **predicator** [se encuentra fuera del Mood  Element](es%20parte%20del%20Residue). Se trata de un elemento que establece referencias temporales distintas al Primary Tense (incluyento o no a uno o varios Auxiliars), y especifica también la voz (activa, media o pasiva).

- Voz activa: *El perro mordió al gato*.
- Voz pasiva: *El gato fue mordido por el perro*.

El **predicator** (predicador) es el elemento del grupo verbal de la cláusula que contiene la acción verbal, pero que no necesariamente contiene al operador temporal ni modal (Finite), y que por sí mismo es Non-Finite en una perífrasis. Es el elemento del **residue** que está presente en todas las cláusulas, incluso en las Non-Finite.

**El predicator** son todos aquellos verbs de un verbal group que no son finite.

Ejemplo: _Ella **cantó** muy bonito; Ella ha estado **cantando** muy bonito._

Cuando el **predicador** está separado del Finite, como por ejemplo en _Ella ha estado **cantando** muy bonito._, se anotará como parte del **residue**; en caso contrario, de estar codificado junto con el Finite, como en: _Ella **cantó** muy bonito_, se anotará el *Finite-Predicator* como parte del MOOD.

| Casos                                                                                                       | Se identifica como  | Ejemplos                                                             |
| ----------------------------------------------------------------------------------------------------------- | ------------------- | -------------------------------------------------------------------- |
| Si el Predicator y el Finite están fusionados                                                               | Finite/Predicator   | _Yo **corro** todas las mañanas; ¿Cuál **es** el horario?_ |
| Si aparece solo el Verb “to be” o “to have” como Main Verb de la oración                                    | Finite/Predicator   | _Yo **soy** profesor ;  Él **tiene** una casa grande_.                                       |
| Si aparece un tiempo compuesto (el primer elemento verbal es Finite y el resto de los Verbs son Predicator) | Finite + Predicator | _Ellos están **leyendo**; Ellos han **estado leyendo**_.                                     |

## ADJUNCT (Adjunto)<a name="id31"></a>

Un **adjunct** es un elemento que no tiene el potencial para llegar a ser un Subject, es decir, que no puede ser elevado al estatus interpersonal de responsabilidad modal. Esto quiere decir que alrededor de los **adjuncts** no se puede construir una predicación (una afirmación, pregunta, negación, etc.).

Por ejemplo, en _ayer en mi casa yo hice el café_, 'ayer' y 'en mi casa' funcionan como **adjuncts**. Obsérvese que no funcionan ni pueden funcionar como Subjects dentro de la misma oración, mientras que 'yo' y 'el café'' sí pueden hacerlo: _yo hice un café_ (en la que se afirma algo sobre ese 'yo') y _el café fue hecho por mí_ (donde se afirma algo sobre 'el café'). En el caso de _el café fue hecho por mí_, la frase preposicional 'por mí'' es un **adjunct**, así que no puede ser elevada a la calidad de Subject, sin embargo, el elemento nominal 'mí' sí puede serlo.

Tanto en español como en inglés, el **adjunct** coincide muchas veces con lo que la tradición denomina *Circunstancial Complement.*

El Adjunct es realizado generalmente por un grupo Adverbial o una Preposicional Phrase. Los **adjuncts** pueden formar parte del Mood, del Residue, o estar fuera de la estructura del Mood.

### ADJUNCT TYPE<a name="id32"></a>

#### Modal Adjunct (Adjunto Modal)<a name="id33"></a>
El value **modal adjunct** expresa el juicio o actitud hacia el contexto del mensaje. Contribuye a construir el contexto intertextual de la oración; esto quiere decir que presenta la perspectiva del emisor acerca de cómo debe interpretarse lo dicho en la oración con respecto al receptor o a la situación comunicativa.

Ejemplo: _**Para ser honesto**, esta torta está horrible._ (el **modal adjunct** : 'para ser honesto' le indica al receptor que debe entender la oración como una confesión, que puede llegar a resultar incluso incómoda.)

Los Modal Adjuncts valoran subjetivamente la oración (no un hecho) en términos de probabilidad, opinión, deseabilidad, evaluación, etc.

Ejemplo: _**probablemente** no pueda venir_.

En esta oración se le asigna una probabilidad a toda la oración; de esa manera, el emisor indica que no está completamente seguro de que la oración que produjo sea verdadera o no. Este feature está intimamente relacionado con el feature *MODALITY TYPE* del **mood**.

| Algunos Modal Adjuncts                                                                                                                          |
| ----------------------------------------------------------------------------------------------------------------------------------------------- |
| *Probablemente, ciertamente, usualmente, algunas veces, ocasionalmente, obviamente, en mi opinión, a decir verdad, aparentemente, casualmente.* |

#### Conjunctive Adjunct (Adjunto Conjuntivo)<a name="id34"></a>
El value value **conjunctive adjunct** indica que dicho adjunto tiene la finalidad de mostrar una relación contextualizadora. Estos adjuntos relacionan la oración en la que aparecen con otra porción del texto (típicamente un texto anterior a la oración). Por lo tanto, establecen relaciones de cohesión con el resto del texto.

Ejemplo: _**En conclusión**, el calentamiento global es una realidad._

Se trata de Grupos Adverbiales o Preposicional Phrases que funcionan, a grandes rasgos, de la misma manera que las *Conjunctions*, pero estableciendo enlaces a nivel textual (como conectores oracionales o marcadores discursivos textuales).

Ejemplo: _**En otras palabras**, *se debe hacer lo correcto; en cualquier caso._

Suele ir fuera de la estructura del Mood (ni en el Mood ni en el Residue).

| Algunos Conjunctive Adjuncts                                                              |
| ----------------------------------------------------------------------------------------- |
| Por ejemplo, en otras palabras, por cierto, y, pronto, en este momento, sin embargo, etc. |

#### Circumstantial Adjunct (Adjunto Circunstancial)<a name="id35"></a>
El value **circumstantial adjunct** expresa circunstancias relacionadas con los procesos: tiempo, lugar, modo, causa, extensión, etc. Este forma parte siempre del Residue.

Ejemplo: _**ayer** me encontré con mi mejor amigo. ; nos movemos **hacia allá**._

Se reconoce porque no puede ser elevado a la función de Subject; si se trata de una Preposicional Phrase, el **circumstantial adjunct** solo podría ser elevado a Subject siempre y cuando desapareciera la Preposition. En la práctica, ninguna Preposicional Phrase funciona o puede llegar a funcionar como Subject.

Ejemplos: _¿**Por cuánto** vende la torta? ; lo hizo **porque se lo pedimos**._

| ¿**Por cuánto**        |    vende la torta?          |
| ---------------------- | --------------------------- |
| Adjunct Circumstantial | finite/predicator + Subject |
| RESIDUE                | MOOD                        |

## Complement (Complemento)<a name="id36"></a>

Un **complement** es un constituyente que tiene la posibilidad de constituirse como un Subject, su función es agregar información sobre el Subject o el Object. El **complement** puede estar desempeñando dos funciones, como Direct Complement o como Indirect Complement.

#### Direct Complement - Complemento Directo

Cuando este elemento está desempeñando la función de *Direct Complement* se reconoce al convertir la oración activa en pasiva (el DC de la oración activa pasa a ser el Subject de la oración pasiva).

Ejemplo: _El gato rompió **el florero** - **El florero** fue roto por el gato._

También, un método para reconocer el *Direct Complement* es sustituyendo el elemento por un Pronoun clítico.

Ejemplo: _El gato rompió **el florero** - El gato **lo** rompió._

O mediante una interrogación con _“¿Qué es lo + Verb en participio?”_ (la respuesta de la pregunta debe coincidir con el constituyente que se presume como *Direct Complement*).

Ejemplo: _Miguel compró **unas flores** - ¿Qué es lo comprado?: **unas flores**._

#### Indirect Complement - Complemento Indirecto

Cuando se trata de un *Indirect Complement*, se reconoce porque puede tratarse de un SN que está precedido por la Preposition *‘a’* y tiene un clítico *'le/s'* correferencial.

Ejemplo: _**A María le** gusta mucho bailar._

**El *Indirect Complement* también puede ser un Pronoun tónico que está precedido por la Preposition ‘a’ y aparece un clítico correferencial.**

Ejemplo: _Se lo dió **a él**_.

Cuando solo aparece un Pronoun átono en la oración, se debe agregar una fórmula: a mí, a ti, etc. que sea correferencial con el Pronoun átono, luego se sustituye dicho Pronoun por los clíticos le/les (que son los clíticos identificables con *Indirect Complement*).

Ejemplo: _**Te** lanzó la pelota - **Te** lanzó la pelota **a ti** // **Le** lanzó la pelota._

Cuando no aparece ningún Pronoun átono, sino un SN precedido por la Preposition 'a', se debe agregar un Pronoun clítico correferencial 'le/les', si la oración resultante es gramaticalmente correcta entonces se trata de un *Indirect Complement*.

Ejemplo: _Entregué el sobre **al vigilante** - **Le** entregué el sobre **al vigilante**_.

| Definición                                                                                                                    | Ejemplos                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Definición general: un Complement es cualquier elemento que tiene el potencial de convertirse en Subject de la oración. | _Él escribió **un libro**._ (El Complement se puede convertir en Subject de la siguiente manera: **un libro** fue escrito por él.) |
| Complement de Subject o de objeto: agrega información sobre el Subject o el Objet.                                      | _Él es **un buen escritor**. Ellos me vuelven **loco.**_                                                                             |

## MINOR Y MAJOR CLAUSES

Las **minor y major clauses** son tipos de oraciones clasificadas por la presencia o no de el elemento *MOOD*.

### Minor Clauses<a name="id37"></a>
El Mood es un elemento que no siempre va a estar presente en la cláusula, cuando esta carece de una estructura interna (Mood + Residue) recibe el nombre de **minor clause**. Este tipo de “cláusula” desempeña una función de habla menor como llamadas (en función de vocativo), saludos (¡bienvenidos! ¡adiós!), exclamaciones (¡auch! ¡si!) y alarmas (¡ayuda! ¡cuidado!); se destaca que estas construcciones tampoco tienen una estructura temática.

### Major Clauses<a name="id38"></a>
Por otro lado, y en la mayoría de los casos, el Mood va a estar presente junto con el Residue contruyendo una **major clause**, las cuales pueden ser del tipo indicativa (dar o exigir información), imperativa (exigir bienes y servicios) o subjuntiva (expresar subjetividad). También, si se habla de una cláusula del tipo indicativo, se desarrollará la información como declarativa (proporciona información) o interrogativa (exige información); y si es interrogativa, podrá ser del tipo interrogativo ‘sí / no’ o interrogativo con elemento ‘WH-’.

>NOTA: Al momento de anotar, las *major clauses* no se enlazan con entity alguna.

### FREEDOM<a name="id39"></a>
El feature **freedom** indica si la *major clause* en cuestión puede, o no, sostenerse por sí sola como una de sentido completo.

#### Free Clauses<a name="id40"></a>
El value **free** señala que la *major clause* presenta proposiciones o propuestas, son oraciones de sentido completo que no depende de otra para completar su sentido.

Ejemplos: _¿Tienen alguna especialidad?; Mañana iré al parque; ¿Dónde es la reunión?; Él ha estado jugando con su corazón_.

#### Bound Clauses<a name="id41"></a>
El value **bound** señala que la *major clause* está asistiendo o apoyando a la cláusula principal (free clause) pero que, por sí solas, no funcionan como una oración completa porque carecen de algunas funciones interactivas.

A su vez, estas oraciones ligadas pueden ser tanto *Finitas* (subject - finite) como *No Finitas*.

Ejemplos: _Me gusta **que el café lleve canela**_. Bound Clause Finite. _No sé **qué hacer**_. Bound Clause Non finite.

Las Bound Clauses pueden ser introducidas por la conjunción *‘que’* o un pronombre interrogativo.

Ejemplos: _Me molesta **que** hayas dicho eso ; Ella no recordaba **dónde** había dejado las llaves_.

Estas oraciones pueden cumplir diversas funciones sintácticas dentro de una cláusula principal, como por ejemplo Subject, Complement o Circumstantial.

Ejemplos: _Más vale **que me calle**_. Subject. _Él pensó **que el café tenía azucar**_. Complement. _Ella traerá las bebidas **cuando esté listo el almuerzo**_. Circumstantial.

Las **bound clauses**, a pesar de ser parte de una oración, poseen su propio MOOD; es así como una construcción compuesta puede contener el MOOD de la oración principal y el de la oración subordinada.

Ejemplo: _Me gustaría saber qué ofrecen ustedes_.

En este caso, el MOOD de la oración principal se caracteriza por ser *declarativo*, a pesar de contener una pregunta dentro. Esta particulariedad se reflejará en el MOOD de la Bound Clause que contendrá la característica de *interrogativo con particula WH-*.

| Me | gustaría | saber qué ofrecen ustedes |
| -- | -------- | ------------------------- |
| R  | MOOD (F) | MOOD (SUBJECT)            |

| Qué | ofrecen  | ustedes  |
| --- | -------- | -------- |
| R   | MOOD (F) | MOOD (S) |
