# Palabra (desde el punto de vista de su función - es)

## Introducción

A diferencia de lo que ocurre con las clásicas *Parts Of Speech* (T-POS), las Functional Parts Of Speech (F-POS) se basan únicamente en la interpretación actual de la función de la palabra en la cláusula. Por ejemplo, un Adjective (T-POS) es una palabra que modifica a un Noun, sin importar el tipo de modificación que haga; un Classifier, por otra parte, es un tipo de modificador de un Noun con una función y posición específicas. En este sentido, la clasificación de F-POS es más específica y está más relacionada con la función de un determinado constituyente que la categorización tradicional. Los F-POS se basan, desde el punto de vista gramatical, en una representación experiencial del la cláusula.

A continuación se presentan especificaciones F-POS para los constituyentes que forman parte del VERBAL GROUP y NOMINAL GROUP. Esta especificación es una versión simplificada de la presentada por Halliday y Matthiessen (2014).

## NOUN GROUP

El Noun Group es una expansión del sustantivo. Se trata de un compuesto hecho de palabras que tiene por núcleo un sustantivo. Desde la perspectiva funcional, el Noun Group codifica a uno de los participantes o entidades del discurso. El Noun Group es importante para identificar las entidades más relevantes del discurso, y para caracterizar las modificaciones y añadiduras que influyen en la interpretación de tales entidades.

### THING

El elemento denominado **Thing** es considerado el núcleo semántico del Noun Group y el único elemento obligatorio de dicho grupo. Puede ser instanciado por un Common Noun, un Proper Noun o un Pronoun. Se trata del centro del Noun Group, alrededor del cual “gira” el resto de las palabras de dicho grupo. El Thing corresponde a una palabra que se refiere, nombra o designa a seres vivos, objetos, ideas o conceptos.

#### Thing clasificado por Commonnes

| Features      | Ejemplos en español                                |
| ------------- | ---------------------------------------------------- |
| Common Noun   | _Ayer el **carro** nuevo se me dañó_                 |
| Proper Noun   | _Le dije a **Ana** que no me había convencido_       |
| Pronoun       | _Creo que **esto** no **me** funciona como debería_  |

#### Thing clasificado por Interrogative

El Thing puede ser clasificado con dos features: *Interrogative* y *Non-interrogative*.

| Features          | Ejemplos                                                                                               |
| ----------------- | ------------------------------------------------------------------------------------------------------ |
| Interrogative     | _**¿Qué** venden en esa tienda?_; _¿**Quién** llamó?_; _Me gustaría saber **qué** piensas sobre esto_  |
| Non-interrogative | _Venden muchas **cosas** en esa tienda_; _**Pedro** llamó_; _Me gustaría conocer **esto** mucho mejor_ |

### DEICTIC

El término *deixis* apunta a un forma de orientación o referencia con respecto al hablante. Partiendo de esto, se puede definir el **Deictic** como un elemento que indica si un subconjunto o parte del Thing está siendo determinado; dicho subconjunto o parte puede ser **specific** o **non-specific**. 

El Deictic es expresado típicamente por Articles, Demostrative Adjectives y Possessive Adjectives, y siempre se presenta antes del Thing. Estas palabras conectan al Thing con otra entidad o evento en el contexto de la oración, el texto o en la situación. El Deictic puede ser también **interrogative** si se trata de un adjetivo interrogativo que inquiere cuál es la ubicación discursiva del Thing, o puede ser **non-interrogative** en el caso de que no sea un interrogativo.

| Features          | Ejemplos                                                                        |
| ----------------- | ------------------------------------------------------------------------------- |
| Specific          | _**Mi** casa está ubicada frente al mar._; _Busco **el** teléfono rapidito._    |
| Non-specific      | _**Un** perro no es un juguete_; _Encontré **una** buena excusa.*_              |
| Interrogative     | _¿**Qué** cosa estás buscando?_; _¿De **cuál** Pedro estamos hablando_          |
| Non-interrogative | _**Las** cosas se están poniendo interesantes._; _**Esas** cosas no me gustan._ |

#### Deictic clasificado por Interrogative

El Deictic puede ser clasificado con dos features: **Interrogative** y **Non-interrogative**. Un Deictic **Interrogative** inquiere información sobre el Thing, es decir, hace que cualquier Thing se interprete como una solicitud de información.

#### Deictic clasificado por Specification

**Specific Deictic**

Se trata de Deictics que apuntan a una referencia específica o identificable a partir del contexto.

| Tipo / *Modo*                | *Non-interrogative* (Determinativo) | *Interrogative* (Interrogativo) |
| ---------------------------- | ----------------------------------- | ------------------------------- |
| Demonstrative (Demostrativo) | este; ese; aquel; el, lo            | cuál; qué                       |
| Possessive (Posesivos)       | mi; tu; su; nuestro(a); vuestro(a)  | de cuál; de qué                 |

**Non Specific Deictic**

Deictics cuya referencia es difusa.

| Tipo / Número         | Singular                            | Non-singular                          |
| --------------------- | ----------------------------------- | ------------------------------------- |
| Total positive        | cada                                | ambos; todos                          |
| Total negative        | ningún                              |                                       |
| Partial selective     | cualquier                           | algunos, algunas                      |
| Partial non-selective | un, una, unos, unas; cierto, cierta | **CERO morfológico** ciertos, ciertas |

### PRE-DEICTIC y POST-DEICTIC

El _Pre-Deictic_ especifica o hace más particular al Deictic, el _Post-Deictic_ en cambio, vincula el Thing con valores de una escala relacionada con probabilidad, frecuencia temporal, familiaridad, similitud con otra entidad, reporte discursivo (mencionado, nombrado), etc. Los Pre-Deictics y Post-Deictics son palabras que puede ir antes y después del Deictic (respectivamente), estos aportan mayor información deíctica a la ya agregada por el Deictic. Se trata generalmente de Adjectives que típicamente se encuentran delante o después del Deictic, pero antes del Thing.

| Pre-Deictic                                         | Deictic | Post-Deictic                                                                  |
| --------------------------------------------------- | ------- | ----------------------------------------------------------------------------- |
| toda, todas algunas de, ninguna de solo cada una de | la, las | otras, mismas, diferentes posibles, probales típicas especiales, particulares |
| solo                                                | un, una | tipo de, clase, de                                                            |

### NUMERATIVE

El Numerative proporciona el número o cantidad de elementos del subconjunto del Thing. Los Numerative tienden a ser Adjectives (simples o compuetos) o frases modificadoras que definen una característica numérica en el sustantivo. Se trata, en esencia, de una forma de contar (de manera exacta o aproximada) la cantidad de elementos de un conjunto.

#### Numerative clasificado por tipo de Quantity

Los elementos que funcionan como Numerative se subclasifican en **quantitative** y **ordinative**. El feature Quantitative implica la medición de una magnitud o el número de elementos de un conjunto. El feature Ordinative establece el orden de elementos en una lista, o la relación de sucesión entre ellos.

#### Numerative clasificado por tipo de Measure

Los Numeratives poseen una subcategoría compuesta por **Definite** e **Indefinite**. Si son Definite especifican un número exacto de algo, comprenden los números cardinales y ordinales. Si son Indefinite se refieren a un número inexacto. Por otra parte, los ordinativos si son definidos especifican un lugar exacto en un orden. Si son indefinidos se refieren a una posición inexacta en una escala.

| Numerative     | Definite                                   | Indefinite                                  |
| ---------------| ------------------------------------------ | ------------------------------------------- |
| Quantitative   | uno, dos, tres, etc.; un par de, etc.      | unos pocos, etc.; algunos (pocos, muchos), un número de, etc.; muchos, tantos, pocos, etc. |
| Ordinative     | primero, segundo, tercero, etc.; próximo, anterior, etc. | previo, siguiente, etc.       |

### QUANTIFIER

El Quantifier expresa una medida, definida o indefinida, del Thing en términos no del número de elementos de su conjunto, sino de la cantidad de una medida asociada; no se trata del número de elementos del Thing, sino de la cantidad o magnitud de una medida asociada a este.

Presenta los features **Definite** e **Indefinite** (tipo de Measure).

| Definite                                 | Indefinite                           |
| ---------------------------------------- | ----------------------------------------------- |
| tres gramos de, dos kilos de, etc.; cuarto de, mitad de, etc. | algunos gramos de, varios litros de, etc.; poco de, mucho de, demasiado de, etc. |

### EPITHET

El Epithet indica una **cualidad** relacionada con el Thing. No se trata de un clasificador, sino de la expresión de una **cualidad** objetiva o subjetiva. Corresponde a una expresión subjetiva o valorativa acerca del Thing (*maravilloso, fantástico, tonto*), o a una mención de una propiedad objetiva o definitoria del mismo (*viejo, grande, azul, rápido*). Suele ser denotado por un adjetivo calificativo. 

#### Epithet clasificado por el tipo Subjective

El Epithet puede expresar una propiedad “objetiva” del Thing, construida a partir de la representación de la experiencia del referente (**Experiential Epithet**) o la expresión de la actitud subjetiva del hablante hacia el Thing (**Interpersonal Epithet**). El Epithet puede incorporar la gradación por medio de un Adverb. Esta gradación se toma como parte misma del Epithet como se verá en los ejemplos de la próxima tabla.

Esta distinción es útil para extraer, por ejemplo, la valoración que hace un interlocutor de un producto o servicio.

| Características       | Ejemplos                                               |
| --------------------- | ------------------------------------------------------ |
| Experiential Epithet  | _Es un carro **rojo**_; _Es un carro **medio rojo**_; _Un televisor **muy muy muuuuy grande**_  |
| Interpersonal Epithet | _Es un carro **bonito**_; _Es un carro **muy bonito**_; _Una torta **demasiado deliciosa**_ |

### CLASSIFIER

El Classifier codifica una subclase del Thing. Los Classifiers incluyen clasificiones materiales, de escalas y alcances, propósitos y funciones, estados y rangos, orígenes, modos de operación o cualquier otra característica que puedar servir para clasificar un conjunto de cosas en un sistema de conjuntos más pequeños. Puede ser un Adjective o una Prepositional Phrase.

Algunos ejemplos:

| Thing    | Classifier  |
| -------- | ----------- |
| carro    | eléctrico   |
| espada   | de práctica |
| cuchillo | de cocina   |
| café     | con leche   |
| café     | negrito     |

#### Classifier clasificado por Interrogative

Si el Classifier es un adjetivo interrogativo que pregunta por un tipo o clase de Thing, presentará entonces el feature **Interrogative**; en caso contrario se clasifica como **Non-interrogative**. Se diferencia del Deictic interrogative en que este último no pregunta por una clase, sino por un Thing particular de la situación discursiva.

| Características   | Ejemplos                                                                                            |
| ----------------- | --------------------------------------------------------------------------------------------------- |
| Interrogative     | _¿**Qué** televisor compraste?_ (qué clase de televisor); _Dime **cuáles** empanadas te gustan más_ |
| Non-Interrogative | _huevos **de codorníz**_; _balón **de fútbol**_; _sintagma **nominal**_                             |

### QUALIFIER

El Qualifier, al igual que el Epithet, caracteriza al Thing. La diferencia está en que el Qualifier no supone una cualidad (rara vez es Adjective) sino que define un proceso en el cual el Thing participa de alguna manera; por ello, el Qualifier es una cláusula o Prepositional Phrase que modifica al Thing. Por ejemplo, *el niño **al cual le grité** salió corriendo* indica que se trata de un niño en particular, y que ese niño es el receptor de *gritar*. Igualmente, en *la torta **en la mesa** es mía* se interpreta como una torta en particular, que además fue puesta en la mesa por alguien.

El Qualifier determina a un Thing como un participante de un proceso o como elemento del modelo cognitivo de Prepositions.

Ejemplos: _el hombre **que mira desde la ventana**_; _la tienda **vista desde aquí**_; _las tortas **vendidas ayer**_; _el camino **de la ciencia**_

## VERBAL GROUP

El Verbal Group incorpora el proceso (Event) y, adicionalmente, toda la información relacionada con el Mood, Tense, Aspect, etc. Es particularmente importante para encontrar el proceso principal de una cláusula y de las alteraciones modales y temporales que se hacen sobre el mismo.

**Un Verbal Group es una extensión del Verb de la misma forma en que el Noun Group es una extensión del Noun. Es un constituyente que funciona como Finite más Predicator, o como Predicator solo si no hay Finite, y que se presenta en el Mood de la cláusula, y como proceso en el nivel Representation.**

El Verbal Group está compuesto, como mínimo, de un **Event** (que funciona como Predicator en el nivel Exchange): _Quiero dinero para **comprar** una cocina_. Por lo general, el Verbal Group tendrá también un Finite (equivalente al Finite del nivel Exchange). En español, muchas veces el Finite y el Event están unidos en una misma palabra: *Max **estornudó***. Si hay una preposición de enlace, esta se encuentra justo antes del Predicator (_Él **debería de** venir temprano_).

Además de Finite y Event, el Verbal Group puede llevar, de manera opcional, uno o varios Auxiliars entre el Finite y el Event. Por ejemplo: *Ella ha **estado** cantando toda la semana*. El Auxiliar siempre es un elemento que está entre un Finite y un Event. No se considerará como Auxiliar un Finite; en otras palabras, la palabra **he** en *he estado corriendo* no es un Auxiliar, sino un Finite.

| Ella       | comió          |
| ---------- | -------------- |
| Noun Group | Finite / Event |

| ¿Van a | vender | chocolates? |
| ------ | ------ | ----------- |
| Finite | Event  | Noun Group  |

| No       | habría | podido | haber | encontrado | una mejor amiga |
| -------- | ------ | ------ | ----- | ---------- | --------------- |
| Polarity | Finite | Aux    | Aux   | Event      | Noun Group      |

### FINITE VG

El Finine ubica la proposición en el aquí y en el ahora discursivo, relacionando el proceso con el destinador del mensaje (*speaker-now*) por medio de Tense y Mood.

Ejemplos: _**Estamos** cantando a todo pulmón_; _**Hemos** ido demasiado lejos_

### EVENT VG

El Event (*Predicator* en términos del modelo Exchange), es el elemento que contiene la carga léxica del **Verbal Group** y, por lo tanto, es el elemento que se clasifica como un tipo de Process en el nivel Representation. En español el Event suele condificarse en una única palabra junto al Finite.

Es importante señalar que en casos en el que el Finite y Event son palabras diferentes, el Event también puede añadir apectos de Tense a través del **SecondaryTense** expresando pasado, presente o futuro en relación con el **PrimaryTense**.

Ejemplos: _Estamos **cantando** a todo pulmón_; _Hemos **ido** demasiado lejos_

### FINITE-EVENT VG

En la mayoría de casos es frecuente encontrar al Event y al Finite fusionados en un único elemento del Verbal Group (Finite-Event) porque este elemento contiene tanto temporalidad y modalidad como la acción verbal.

Es así como en oraciones del tipo _Alejandra **toca** el saxofón_, el grupo verbal está conformado por un solo elemento en el que se codifican tanto el tiempo como el proceso (contenido léxico).

### AUXILIARY VG

Los Auxiliares suelen estar entre el Finite y el Event, y su única función es añadir contrastes temporales al verbal group. Sirven para construir relaciones temporales o modales más complejas que las conseguidas con la combinación de tan solo el Finite y el Event.

| Has    | estado    | comiendo |
| ------ | --------- | -------- |
| Finite | Auxiliary | Event    |

Ejemplos: _He **estado** cantando toda la tarde_; _Hemos **ido** trabajando en esto toda la semana_

### POLARITY VG

Polarity es un constituyente **explícito** que expresa si la proposición o propuesta es positiva o negativa. Es equivalente al Modal Adjunct del nivel _Exchange_.

Un VerbalGroup es de polaridad Positiva cuando el Verb funciona como una afirmación; para que se desempeñe como Negativa debe haber una negación en alguna parte de la cláusula que implica que la proposición es negativa.

Algunos Polarity VG en español:

| Positive | Negative |
| -------- | -------- |
| Sí       | No       |
| Tambíen  | Tampoco  |
| Siempre  | Nunca    |

Ejemplos: _Ayer **no** fui a clases_; _**Nunca** te veo en el curso_

## PREPOSITIONAL PHRASE

Las Prepositional Phrase tienen dos niveles de codificación como F-POS. En un primer nivel, toda la frase preposicional se anota como *Prepositional Phrase* y en el segundo nivel, se debe analizar cada elemento dentro de la frase, comenzando por la preposición (que se concebirá como **non-functional**) y luego cada elemento que le sigue se analiza individualmente como en el siguiente ejemplo:

| sobre                | la                   | mesa                 |
| -------------------- | -------------------- | -------------------- |
| Non-functional       | Deictic              | Thing                |
| Prepositional phrase | Prepositional phrase | Prepositional phrase |

## NON-FUNCTIONAL Interpretation (Interpretación No Funcional)

La Preposition dentro de la Prepositional Phrase, los Adverbs, y los Adjectives solos (que aparecen después de un Relational Process) no tienen interpretación en el nivel de análisis descrito en este documento. Por lo tanto, en la anotación les asignamos la etiqueta **Non-Functional Interpretation.**

| ¿Sandro restaurant* | es           | nuevo?   |
| ------------------- | ------------ | -------- |
| Thing               | Finite/Event | Non-F    |

## Lista de Códigos de F-POS

**Lista de códigos y F-POS:**

| Código               | F-POS           |
| -------------------- | --------------- |
| TH                   | Thing           |
| DT                   | Deictic         |
| PRD                  | Pre-Deictic     |
| POD                  | Post-Deictic    |
| NM                   | Numerative      |
| QN                   | Quantifier      |
| EP                   | Epithet         |
| CL                   | Classifier      |
| QL                   | Qualifier       |
| NounGroup            | NOMINAL GROUP   |
| VERBAL FINITE        | Finite VG       |
| VERBAL EVENT         | Event VG        |
| VERBAL FINITE-EVENT  | Finite-Event VG |
| VERBAL AUX           | Auxiliar VG     |
| VERBAL POLARITY      | Polarity VG     |
| VerbalGroup          | VERBAL GROUP    |

**Lista de F-POS y códigos:**

| F-POS           | Código               |
| --------------- | -------------------- |
| Classifier      | CL                   |
| Deictic         | DT                   |
| Epithet         | EP                   |
| Numerative      | NM                   |
| NOMINAL GROUP   | NounGroup            |
| Pre-Deictic     | PRD                  |
| Post-Deictic    | POD                  |
| Qualifier       | QL                   |
| Quantifier      | QN                   |
| Thing           | TH                   |
| Finite VG       | VERBAL FINITE        |
| Event VG        | VERBAL EVENT         |
| Finite-Event VG | VERBAL FINITE-EVENT  |
| Auxiliary VG    | VERBAL AUX           |
| Polarity VG     | VERBAL POLARITY      |
| VERBAL GROUP    | VerbalGroup          |

**Lista de Features**

**Lista por F-POS:**

| F-POS           | Feature                   | Value                                     |
| --------------- | ------------------------- | ----------------------------------------- |
| Thing           | wh-mode                   | non-interrogative                        |
| Thing           | wh-mode                   | interrogative                            |
| Deictic         | specification             | specific                                  |
| Deictic         | specification             | non-specific                             |
| Deictic         | wh-mode                   | non-interrogative                        |
| Deictic         | wh-mode                   | interrogative                            |
| Pre-Deictic     | (none)                    | (none)                                    |
| Post-Deictic    | (none)                    | (none)                                    |
| Numerative      | quantityType              | quantitative                             |
| Numerative      | quantityType              | ordinative                                |
| Numerative      | accuracyType              | definite                                  |
| Numerative      | accuracyType              | indefinite                                |
| Quantifier      | measureType               | definite                                  |
| Quantifier      | measureType               | indefinite                                |
| Epithet         | subjectiveType            | experiential                             |
| Epithet         | subjectiveType            | interpersonal                            |
| Classifier      | wh-mode                   | non-interrogative                        |
| Classifier      | wh-mode                   | interrogative                            |
| Qualifier       | (tipo)                    | (se anota en otro nivel)                  |
| Finite VG       | VerbalGroupSecondaryTense | VerbalGroupFiniteSecondaryTensePresent |
| Finite VG       | VerbalGroupSecondaryTense | VerbalGroupFiniteSecondaryTensePast    |
| Finite VG       | VerbalGroupSecondaryTense | VerbalGroupFiniteSecondaryTenseFuture  |
| Event VG        | VerbalGroupSecondaryTense | VerbalGroupFiniteSecondaryTensePresent |
| Event VG        | VerbalGroupSecondaryTense | VerbalGroupFiniteSecondaryTensePast    |
| Event VG        | VerbalGroupSecondaryTense | VerbalGroupFiniteSecondaryTenseFuture  |
| Finite-Event VG | VerbalGroupPrimaryTense   | VerbalGroupFiniteTensePresente         |
| Finite-Event VG | VerbalGroupPrimaryTense   | VerbalGroupFiniteTensePreterito        |
| Finite-Event VG | VerbalGroupPrimaryTense   | VerbalGroupFiniteTenseFuturo            |
| Finite-Event VG | VerbalGroupPrimaryTense   | VerbalGroupFiniteTenseCopreterito      |
| Finite-Event VG | VerbalGroupPrimaryTense   | VerbalGroupFiniteTensePostpreterito    |
| Auxiliar VG     | VerbalGroupSecondaryTense | VerbalGroupFiniteSecondaryTensePresent |
| Auxiliar VG     | VerbalGroupSecondaryTense | VerbalGroupFiniteSecondaryTensePast    |
| Auxiliar VG     | VerbalGroupSecondaryTense | VerbalGroupFiniteSecondaryTenseFuture  |
| Polarity VG     | VerbalGroupPolarity       | VerbalGroupPolarityPositive             |
| Polarity VG     | VerbalGroupPolarity       | VerbalGroupPolarityNegative             |
