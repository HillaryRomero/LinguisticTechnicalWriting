# Palabra (desde el punto de vista tradicional - es)

### MODELO DE POS

El propósito de este documento es describir un modelo de formalización lingüística para POS (*Parts Of Speech*) tradicionales o clásicas.
  
El modelo está compuesto de etiquetas (*tags*) y features (*características*) asociadas a cada etiqueta. Se trata de un modelo con base en las clases de palabras tradicionales, que puede utilizarse para enriquecer un corpus con información sintáctica y morfológica relacionada con las palabras que lo componen.

Este modelo ha sido elaborado para tratar con las categorías tradicionales del inglés y el español, pero también ha sido concebido para ser lo más universal posible. En este sentido, incorpora categorías diseñadas para el proyecto [Universal Dependencies](https://universaldependencies.org) de la Universidad de Stanford.

En la última parte de este documento se presentan tablas con la especificación completa del modelo.


## CLASES DE PALABRA (PARTS OF SPEECH)

Las *clases de palabras tradicionales* son un sistema de clasificación bastante conocido en gramática tradicional. Se trata de una categorización que se ha ido desarrollando durante siglos y que combina criterios sintácticos, morfológicos y semánticos para proponer una teoría de uso de las palabras de diversas lenguas.

Esta clasificación comprende los siguientes tipos o clases de palabras:

- Noun (Sustantivo)
- Adjective (Adjetivo)
- Article (Artículo)
- Adverb (Adverbio)
- Auxilary (Auxiliar)
- Conjunction (Conjunción)
- Preposition (Preposición)
- Pronoun (Pronombre)
- Verb (Verbo)
- Discourse Marker (Marcador Discursivo)

A continuación se presenta y describe en detalle cada clase de palabra y los features (*características*) asociados a estas.


### NOUN (Sustantivo)

**El Noun es una clase de palabra que se utiliza para denotar una entidad. Las entidades denotadas pueden ser de cualquier índole (material o inmaterial, real o inventada, animada o inanimada, humana o animal), demás de acciones o resultados de estas.**


#### GENDER (género)

A continuación se presentan los valores relativos al feature GENDER.

##### Masculine (masculino)

Pueden ir acompañados por un Article o Adjective masculino. En algunas lenguas presentan un caso particular.

Ejemplo: _El **perro** de mi **vecino** nuevo_

##### Femenine (femenino)

Pueden ir acompañados por un Article o Adjective femenino. En algunas lenguas presentan un caso particular.

Ejemplo: _La **gata** de mi hermana_

##### Neuter (neutro)

Estos Nouns forman un tercer género junto con Femenine y Masculine. No se trata de una indistinción de género, sino de un género de derecho propio. En algunas lenguas presentan un caso particular y pueden ir acompañados de un Article o Adjective neutro. 

En algunas lenguas, el Neuter Noun es reconocido porque puede ser sustituido por un Pronoun neutro.


#### NUMBER (número)

#### Singular (singular)

Indica que el Noun se refiere a una unidad, o a lo que colectivamente se entiende como una, ejemplo, una _persona_, un _animal_, o una _cosa_.

Ejemplo: _Mi **casa** es azul_

#### Plural (plural)

Indica que el Noun se refiere a una agrupación de unidades. En español se expresa mediante los morfemas *–s* y *–es*.

Ejemplos: _Esas **casas** son azules_; _Ya tengo el presupuesto para los **carteles**_


#### ANIMACY (animación)

##### Animate (animado)

Designan personas, animales o seres considerados vivientes; también se utiliza para denotar organismos o entidades capaces de moverse a voluntad.

Ejemplos: _Los **obreros** trabajan mucho_; _Los **animales** merecen ser protegidos por el **hombre**_; _Los **robots** son el futuro_

##### Inanimate (inanimado)

Designan entidades carentes de vida o movimiento voluntario.

Ejemplos: _Compré muchas **flores**_; _La **mesa** de mi casa es grande_


#### COMMONNESS (especificidad)

##### Common (común)

Designan entidades de forma general a partir de sus propiedades características. Se trata de Nouns que denotan clasificando (si decimos que algo es un *perro* es que lo estamos clasificando como tal).

Ejemplos: _Existen cinco **continentes**_; _Los **escultores** son artistas_

##### Proper (propio)

Identifican a un elemento de entre los demás de su clase. Se trata de una designación que busca individualizar un ente en particular.

Ejemplos: _Visité un país en **Europa**_; _Leí sobre **Miguel Ángel**, un famoso escultor italiano_


#### COUNTABILITY (contabilidad)

Indica si el Noun designa entidades contables o no contables (materia).

##### Countable (contable)

Denotan sustantivos que pueden flexionarse en singular y plural, estos a su vez aceptan artículos indeterminados. Se trata de entidades que pueden ser contadas.

Ejemplos: _*Un chef* me dió su recomendación_; _Compré unas (dos, tres) *manzanas*_

##### Uncountable (incontable)

Sustantivos incontables, también llamados sustantivos de materia (*mass noun*). En algunos casos, pueden referirse a un conjunto de elementos no contable y no es posible anteponerles un articulo indeterminado.

Ejemplo: _El lugar estaba abarrotado de *gente*_; _Al café le faltaba *azúcar*_


#### GROUNDING (referencialidad)

El Grounding se utiliza para indicar si lo referido por el Noun tiene una referencia específica recuperable del discurso; sirve en particular para señalar si la referencialidad puede indicarse por medio de un Article.

##### Explicit Article (artículo explícito)

Se utiliza para indicar que el Noun está acompañado por un Article.

Ejemplo: _El **niño** juega con una **pelota** en su casa_

##### Zero Article (artículo cero)

El sustantivo no está acompañado de un artículo explícito, aunque podría estarlo. No se usa en sustantivos que por su naturaleza, o por estar acompañados de algún otro determinante, no pueden presentar un Article.

Ejemplo: _Comer es **placer** que enamora a todos_


### ADJECTIVE (Adjetivo)

El Adjetive acompaña al Noun añadiendo al mismo una cualidad o delimitando su extensión. Designa generalmente estados (durables o transitorios) relacionados a una entidad (codificada como Noun) y también relaciona al Noun con variables situacionales o discursivas.

En español es una palabra que incide sobre el Noun y que concuerda en género y número con este. Puede ser simple o compuesto, en cuyo caso es su núcleo el que concuerda en género y número con el Noun sobre el cual incide.


#### GENDER (género)

Los Adjectives pueden presentar variación de género, en español puede ser masculino o femenino. A veces el Gender es observable en la flexión de la palabra, no obstante, hay Adjectives que no muestran marcas externas de género porque son invariables, pero esta se puede deducir del Gender del Noun que el Adjective está modificando.

##### Masculine (masculino)

Se reconoce en general en la flexión de la palabra por el uso del morfema masculino (*-o*). Algunas veces no se muestran marcas pero se se puede por el género del Noun el Adjective está modificando.

Ejemplo: _el carro **blanco** de mi hermano_; _el niño **triste** se la pasa llorando_

##### Femenine (femenino)

Se reconoce en general en la flexión de la palabra por el uso del morfema femenino (*-a*). En ocasiones no se muestra marcas pero se se puede por el género del Noun el Adjective está modificando.

Ejemplo: _la gata *negra* de mi hermana*, *la casa **grande** de mi abuela_

##### Non-gender (sin género)

Algunas veces el Adjective no presenta información respecto al Gender. Este caso se da en algunas lenguas como el inglés.


#### NUMBER (número)

Los Adjectives presentan variación de número para concordar con el Noun. Puede ser Singular o Plural. En español el número normalmente se explicita en la terminación del Adjective.

##### Singular (singular)

Acompaña (de forma directa o indirecta) a un Singular Noun. En muchas lenguas se caracteriza por no llevar marca alguna de plural.

Ejemplo: _*Mi* camisa *roja* es *bonita*_

##### Plural (plural)

Acompaña (de forma directa o indirecta) a un Plural Noun. En español se expresa mediante el morfemas *–s* para las palabras que generalmente terminan en vocal átona, y *–es* para las que acaban en consonante.

Ejemplos: _Me encantan los marcadores **dorados**_; _**Estas** mesas son **elegantísimas**_

##### Non-number (sin número)

En algunas lenguas a veces el adjetivo no presenta información respecto al Number, bien porque queda indeterminado, o bien porque el Noun al que acompaña no presenta variación de Number.


#### Clasificación según la clase deíctica (Deictic Class)

A continuación se presenta una serie de features que definen clases de Adjective relacionadas con la deixis del Noun. Se trata de Adjectives que contribuyen a especificar la situación discursiva de un Noun más que definir alguna característica independiente del contexto.

##### Demostrative (demostrativo)

Un Demostrative Adjective se utiliza para señalar la distacia relativa (metafórica o literal) que hay entre lo designado por el Noun y algún participante del discurso (*este*, *esas*, *aquellos*). Esta distancia puede referirse al espacio a al tiempo. Este uso se formaliza apropiadamente con el modelo DEICTICS.

Ejemplo: _**Aquellos** ojos negros iluminaron mi camino_

##### Indeterminate (indeterminado)

Transmite imprecisión, pero no en cuanto a la cantidad de entidades sino en cuanto a la identidad del Noun al que acompaña (*algún, cada, cierto, cualquier, otro, semejante, sendos, tal*).

Ejemplo: _Hemos recibido **algunos** informes_

##### Possessive (posesivo)

Establece una relación entre un individuo del discurso y la entidad representada por el Noun al que acompaña (*mi, tus, nuestros*). Así pues, en _Esta es **mi** casa_, el Possessive *mi* indica que existe una relación entre *yo* y la entidad referida por el Noun *casa*.

Ejemplo: _¿Cuál es **tu** película favorita?_

En español este Adjective flexiona en número, género y persona.

Persona | Possessive Adjectives
--- | ---
1era persona | mi(s), mío(s), mía(s), nuestro(s), nuestra(s)
2da persona | tu(s), tuyo(s), tuya(s), suyo(s), suya(s)
3era persona | su(s), suyo(s), suya(s)

En el caso de este Adjective, la persona gramatical (Person) se anota como 1, 2 o 3. En el resto de tipos de Adjectives la persona se establece con el feature **non-person**.

##### Relative (relativo)

Este Adjective cumple una doble función: modificar al Noun al que acompaña y representar a ese Noun dentro de una cláusula subordinada. En español hay sólo dos Relative Adjectives *cuyo* y *cuanto*.

Ejemplo: _En un lugar, **cuyo** nombre no quiero recordar_

##### Quantitative (cuantitativo)

Indica una cantidad inexacta relacionada con el Noun. Se usa para expresar cantidades o identidades de forma vaga o imprecisa, por carencia de información o por alguna otra razón.

Ejemplos: _Te debo **varios** reportes; quiero a **pocas** personas; vinieron **demasiados** invitados a comer_

##### Numeral (numeral)

Indica el número exacto de una cantidad relacionada con el Noun, sus múltiplos, su división o su lugar en una escala (*uno, triple, mitad, cuarto*).

Ejemplos: _Sírvame **dos** raciones de espaguetti_; _Sírvame **triple** ración de pescado por favor_; _Llegó a la meta en **cuarto** lugar_; _¡Se comió casi **media** torta!_; _El **quintuple** asesinato de ayer_

##### Non-deictic (no-deíctico)

Se seleccionará este feature cuando la información que está aportando el Adjective no es de tipo deíctica, es decir, que no pertenece a ninguno de estos subtipos: cuantitative, demostrative, exclamative, indeterminate, possessive, numeral, o relative.


#### Clasificación según la clase semántica del Adjective (Semantic Class)

La clase semántica en los Adjectives incorpora los Qualifying Adjectives (adjetivos calificativos).

##### Qualifying Adjective (Adjetivo Calificativo)

Designan cualidades, concuerdan con el Noun y lo modifican (*estrecha*; *frondoso*), además restringe la extensión del Noun (_gatos **negros**_) y también destaca, pondera o evalúa un rasgo de su significado como en los epítetos. En otras palabras, expresa cualidades del Noun.

Ejemplo: _Tenía el rostro **ceniciento**_

##### Non-semantic (no-semántico)

Se seleccionariá este feature cuando la información que está aportando el Adjective no es de tipo semántica, es decir, que no pertenece al subtipos Qualifying.


#### Clasificación según la modalidad (Modal Class)

Un Adjective de la clase modal no supone cualidades del Noun, sino que cambia la modalidad de la cláusula de forma directa o indirecta.

##### Exclamative Adjective (Adjetivo Exclamativo)

Acompaña al Noun para crear junto a él una oración de tipo exclamativo.

Ejemplo: _¡**Qué** calor!_

##### Interrogative Adjective (Adjetivo Interrogativo)

Formula preguntas sobre la identidad (*qué, cuál*) o la cantidad (*cuánto*) de un determinada entidad del discurso, es decir, construye preguntas con el propósito de solicitar una identificación del Noun.

Ejemplo: _¿**Cuántas** travesuras hiciste hoy?_


#### Clasificación según el grado (Degree)

Estos features codifican el grado del Adjective.

##### Comparative Degree (grado comparativo)

Los Adjectives pueden presentarse en grado comparativo si:

- Si se ponen dos términos en relación de superioridad al agregar 'más', 'más... que' o 'mayor... que'.
  Ejemplo: _Clara es más **rápida** que María_

- Si se ponen dos términos en relación de igualdad al agregar 'tan...como'.
  Ejemplo: _María es tan **linda** como Carolina_

- Si ponen dos términos en relación de inferioridad al agregar 'menos', 'menos... que'.
  Ejemplo: _José es menos **alto** que Pedro_.

##### Superlative Degree (grado superlativo)

Los Adjectives pueden presentarse en grado superlativo. El grado superlativo de un adjetivo denota un nivel muy alto de la cualidad que describe.  

- Superlativo relativo: designa una persona o cosa que posee cierta propiedad en mayor o menor grado que otra. Este se construye con un artículo determinado + más/menos + adjetivo.
  Ejemplo: _Emile es la corredora más **rápida**_

- Superlativo absoluto: describe un grado muy alto de una cualidad sin establecer ninguna comparación. Este se construye al agregarse sufijos (*-ísimo* o *-érrimo*) o prefijos (*requete-*, *re-*, *super-*.
  Ejemplo: _Manuel es **rapidísimo**_

##### Non-degree (no-grado)

Los Adjectives que no presentan ni grado comparativo, ni superlativo se codifican como **non-degree**, lo que corresponde en gramática tradicional a un 'grado positivo'.

Ejemplos: _Mi tía es [jóven]_.


### ARTICLE (Artículo)

El Article es una clase de palabra de naturaleza gramatical que permite tanto delimitar la denotación del grupo nominal del que forma parte, como informar de su referencia. En efecto, el Article especifica si lo designado por ese segmento constituye o no información conocida o nombrada, y además sirve para indicar si el Noun debe entederse como la totalidad de un conjunto o una parte de dicho conjunto.

El Article en español es una palabra que siempre antecede a un Noun. Forma parte de una clase cerrada de palabras que determinan al Noun, y concuerdan con este en género y número.

#### DEFINITENESS (definición)

En este feature, el Article se clasifica con los valores **Definite** (Definido) o **Indefinite** (Indefinido).

#### Definite (definido)

Expresa que el elemento mencionado a continuación es identificable por los interlocutores o que la entidad referida por el Noun se considera un todo.

Ejemplo: _Hoy he recibido **la** carta_

A continuación se presenta una lista de los Articles con el feature Definite.

Género               | Número   | Ejemplos
-------------------- | -------- | ---
masculino            | singular | _**el** niño_; _**el** que venga temprano gana_
masculino ("neutro") | singular | _**lo** bueno_; _eso es **lo** que me faltaba_
masculino            | plural   | _**los** niños_; _**los** que vengan hoy ganarán_
femenino             | plural   | _**la** torta_; _**la** que vino hace rato me gritó_
femenino             | plural   | _**las** tortas_; _**las** que vengan hoy serán recibidas_

#### Indefinite (indefinido)

Introduce entidades nuevas al discurso, casi siempre no conocidas por el oyente. La entidad referida por el Noun es una unidad o una parte de un todo mayor.

Ejemplo: _Hoy he recibido **un** paquete_

A continuación se presenta una lista de los Articles con el feature Indefinite.

Género      | Número   | Ejemplos
----------- | -------- | ---
masculino   | singular |  _**un** niño_
masculino   | plural   |  _**unos** niños_
femenino    | singular |  _**una** torta_
femenino    | plural   |  _**unas** tortas_

### ARTICLE CONCRETENESS (concretitud)

#### Article Abstract (abstracto)

En español, el Article _lo_ (que las gramáticas denominan "Neutral Article") es una palabra cuya principal función es sustantivar un Adjective manteniendo los aspectos abstractos del mismo. Este Article se clasifica como **Abstract**.

##### Article Concrete (concreto)

El resto de los Articles (_el, la, los, las, un, una, unos, unas_) se codifica con el valor **concrete**.

### Nota sobre las palabras *al* y *del*

En la contracción _del_ se considerará '_de_' como preposición y '_l_' como artículo, de igual modo la contracción '_al_'; '_a_' será la preposición y '_l_' el Article.

#### ARTICLE NUMBER (Número)

Los Articles asimilan el número del Noun al que están modificando, estos pueden flexionar en singular y plural.

##### Article Singular (singular)

Ejemplos: _**Una** camisa roja y grande_; _**La** silla es marrón_

##### Article Plural (plural)

Ejemplos: _Escuché **unos** pájaros_; _Tengo el presupuesto para **los** bolsos_

#### ARTICLE GENDER (Género)

Los Articles asimilan el género del sustantivo al que están acompañando.

##### Article Masculine (masculino)

Ejemplo: _**el** cantante viene a la fiesta_

##### Article Femenine (femenino)

Ejemplo: _**la** gata negra de mi hermana es bonita_


### ADVERB (Adverbio)

Clase de palabra que suele codificar el modo, tiempo o lugar en que se realiza una acción. También se encarga de agregar o gradar la información denotada por un Adjective u otro Adverb.

En español el Adverb constituye una clase de palabra muy heterogénea. Desde el punto de vista morfológico, carece de flexión. Se aproxima en este sentido a las Prepositions, Conjunctions e interjecciones. Desde el punto de vista sintáctico el Adverb puede ser: núcleo del sintagma adverbial, complemento circunstancial del Verb, cuantificador, grado o complemento del Adjective, cuantificador de otro Adverb, modificador de Adverbs y de proposiciones.

#### Clasificación según la clase semántica del Adverb (Semantic Class)

Se trata de Adverbs cuyo significado no depende de la situación discursiva particular que se esté llevando a cabo en un momento determinado. En este sentido, realizan una calificación similar a la del Qualifying Adjective, pero sobre Verbs o Adjectives.

##### Mode Adverb (Adverbio de modo o manera)

Indica la manera, el modo o la forma en que se realiza un proceso.

Ejemplo: _El violín suena **bien**_

##### Qualify Adverb (Adverbio calificativo)

Designa cualidades al elemento que está siendo modificado (generalmente un Verbo). A diferencia del Adjective no presenta flexión en género ni en número.

Ejemplos: _Las golondrinas vuelan **bajo**_; _Estas espinacas saben **raro**_; _Ella canta **bonito** y en varios idiomas_

##### Non-Semantic Adverb (no-semántico)

Los Adverbs que no sean de Mode o Qualify serán considerados como **non-semantic**.


#### Clasificación según la clase deíctica del Adverb (Deictic Class)

Son Adverbs cuyo significado está parcialmente determinado con respecto a la situación discursiva particular que se esté llevando a cabo en un momento dado.

##### Cuantitative Adverb (cuantitativo)

Expresan cantidad, grado o intensificación. Son los únicos Adverbs que pueden modificar al Adjective y a otro Adverb.

Ejemplos: _**bastante** liso; no come **mucho**; gritó **a todo pulmón**_

##### Demostrative Adverb (demostrativo)

Es un subtipo de los locativos que indican una localización espacial que suele ser imprecisa y relativa a la situación discursiva de los intelocutores (_aquí_, _allí_, _allá_, _acá_, _ahí_).

Ejemplos: _**ahí** se ve una ventana_; _el café queda **allá**_

Indican lugares donde ocurre la acción verbal. Se trata de una palabra invariante sin Preposition que indica un lugar.

##### Locative Adverb (locativo)

Se considerarán como Locatives todos los Adverbs que indiquen una locación (exceptuando los Demostrative Adverbs).

Pueden expresar ubicación, destino o término. Estos suelen admitir un complemento (como si fuesen una Preposition).

Ejemplo: _estoy **detrás** de la pared]_

Pueden expresar dirección (también admiten complementos).

Ejemplo: _Se escondió **debajo** de la cama_

##### Relative Adverb (relativo)

El Relative Adverb recoge una referencia textual anterior. Generalmente retoma un lugar o modo dicho con anterioridad.

Algunos Adverbs relativos: _cuando, cuanto, como, donde_.

Ejemplos: _lo encontré **donde** lo dejaste_; _lo hice **como** me dijiste_

##### Temporal Adverbs (temporal)

El Temporal Adverb codifica tiempo. Puede establecer una referencia temporal, de duración, de frecuencia y aspectual. Este Adverb responde a interrogativos como: _¿Cuándo? ¿Cuánto (tiempo)? ¿Cada cuánto (tiempo)?_, etc.

A continucación se presentan ejemplos de este feature.

- De uso referencial: responde a la pregunta *¿cuándo?*.

Ejemplos: _**ayer** no pude venir_; _**hoy** voy a comprar algunas cosas_; _**actualmente** sigo sin trabajo_, _**recientemente** he visto muchas películas_

- De duración: responde a la pregunta *¿cuánto (tiempo)?*.

Ejemplos: _**brevemente** me perdi_; _el tan **largamente** esperdo té_; _**siempre** lo he esperado_

- De frecuencia: responde a la pregunta *¿cáda cuanto (tiempo)?*.

Ejemplos: _**habitualmente** me levanto a las seis_; _**nunca** compro pimentones verdes_, _**semanalmente** voy al cine_; _**siempre** almuerzo tarde_

##### Non-deictic Adverb (no-deíctico)

Se selecciona este feature cuando la información que está aportando el Adverb no es de tipo deíctica, es decir, que no se clasifica con ninguno de los features anteriormente vistos.


#### Clasificación según la clase modal del Adverb (Modal Class)

Se trata de Adverbs que cambian la modalidad de la cláusula (afirmación, negación, expresión exclamativa o interrogativa).

##### Positive Adverb (afirmativo)

Este feature se utiliza para marcar un Adverb que tiene como función reafirmar un valor afirmativo o positivo. Algunos de estos Adverbs en español son: *sí, también, claro, efectivamente, cierto*.

Ejemplo: _Claro que voy a ir a tu cumpleaños_

##### Negative Adverb (negativo)

Este valor se utiliza en Adverbs que codifican una negación de lo dicho en la cláusula. Algunos de los más frecuentes en español son: *no, tampoco, nunca, jamás, nada*.

Ejemplo: _Jamás comeré berenjenas_

##### Possibility Adverb (de duda o posibilidad)

Se trata de Adverbs que modalizan la cláusula para indicar duda, incertidumbre, probabilidad, posibilidad, etc. Los más comunes en español son: *quizá(s), acaso, igual, probablemente, posiblemente*.

Ejemplos: _quizás venga mañana_; _probablemente no vea esa película con mi familia_

##### Interrogative Adverb (interrogativo)

Los Adverbs usados en cláusulas interrogativas y exclamativas son *cuándo, cómo, cuánto, cómo, qué tan* y *dónde* (las formas relativas son idénticas a estas pero se escriben sin tilde).

Ejemplos: _¿**cuándo** puedo pasar a buscarlo?_; _¿**cuánto** cuesta eso?_; _¿**dónde** puedo buscar los donuts?_

##### Exclamative Adverbs (exclamativos)

Constituyen formas usadas en oraciones exclamativas, estas son: *cuándo*, *cómo*, *cuánto* y *dónde*. Tienen como propósito cambiar la modalidad de una cláusula para hacerla exclamativa.

Ejemplo: _¡cómo fastidias!_

##### Non-modal Adverb (no-modal)

Se seleccionará este feature cuando la información que está aportando el Adverb no es de tipo modal, es decir, cuando no tiene los features: *positive, negative, interrogative, posibility* y *exclamative*.


#### Clasificación según el grado del Adverb (Degree)

Los grados del Adverb permiten establecer comparaciones entre el modo de darse la acción del verbo. Se trata de una comparación con otra acción o con un grupo generalizado de ellas.

##### Comparative Adverb (comparativo)

Este feature atribuye una intensidad comparativamente mayor, menor o igual a la propiedad denotada por el adverbio, en relación con esa misma propiedad en otra cualidad o proceso.

Ejemplo: _Clara corre **mejor** que Carolina_

##### Superlative Adverb (superlativo)

El Superlative Adverb denota una propiedad en su máxima intensidad.

Ejemplo: _Sara corre **rapidísimo**_


### AUXILIARY (Auxiliar)

Un Auxiliary es una palabra funcional que acompaña al Verb en una perífrasis verbal y expresa las distinciones gramaticales no indicadas por el Verb (como la persona, el número, el tiempo, el modo, el aspecto, la voz o la evidencia). El Auxiliary amplía la morfología y la semántica del Verb añadiendo información diversa dependiendo de la gramática particular de cada idoma. A menudo su forma se corresponde con un Verb que también puede tener usos no auxiliares.

El Auxiliary presenta los mismos features de aspect, person, tense y modal que los Verbs.

A continuación algunos ejemplos de usos de Auxiliary en español.

- Verb _ser_ como marca de la voz pasiva: _la sentencia **fue** publicada_.

- Verb _estar_ en construcciones progresivas: _mis hijos **están** estudiando inglés_.

- Construcciones con preposiciones en medio: _**hay** que estudiar_, _**iba** a decir_, _**debes** de conocerle_.

- Usos modales: _no **puedo** entrar_; _**iremos** considerando cada caso particular_; _**llevo** escritas diez páginas_.


### CONJUNCTION (Conjunción)

La Conjunction puede enlazar elementos **sintácticamente equivalentes** dentro de una misma cláusula, o unir dos cláusulas. Sirve como enlace entre dos o más elementos que tienen la misma jerarquía sintáctica.

Una caracterización más detallada de las relaciones que puede establecer esta palabra puede encontrase en el modelo CONJUNCTIONS.

#### Conjunciones simples

Son aquellas formadas por una sola palabra. Se presentan las más comunes del español a continuación.

Conjunction | Ejemplo
--- | ---
bien|_Hará el viaje **bien** en avión, **bien** en barco_.
luego|_Estás poniendo muchas dificultades, **luego** no piensas venir a la fiesta_.
mas|_Es fea **mas** inteligente_.
mientras|_**Mientras** tú vas al cine, yo termino el trabajo_.
ni|_María no trajo el pan **ni** el queso_.
o/u|_Puedes venirte conmigo **o** irte por tu cuenta_.
pero|_Vete temprano a casa, **pero** mañana no llegues tarde_.
que|_Necesita **que** lo ayuden_.
si|_**Si** llegas tarde no podrás entra a la sala_.
sino|_No compro vegetales **sino** frutas_.
y/e|_Él es buen mozo **y** con dinero_.
ya|_No necesito tu ayuda **ya** resolví sola_.

#### Conjunciones compuestas

Son aquellas formadas por dos o más palabras. Se presentan las más comunes a continuación.

Conjunction | Ejemplo
--- | ---
aunque|_Terminé todo el trabajo  **aunque** me sentía mal_.
a fin de que|_Le dio dinero **a fin de que** pudiera terminar los estudios_.
así que|_Estoy trabajando, **así que** no puedo ayudarte_.
cada vez que|_Traes el mismo bolso **cada vez que** te veo_.
como si|_Siempre que viajamos actúas **como si** no quisieras venir_.
con que|_Me conformo **con que** llegues temprano_.
con tal de|_Él todo lo acepta **con tal de** mantener a su familia_.
con tal de que|_Hará lo que sea **con tal de que** su hijo se gradúe de la universidad_.
de manera que|_Es tarde, **de manera que** me voy a casa_.
en tanto que|_Sus padres trabajarán **en tanto que** él no termine sus estudios_.
hasta que|_Acamparemos **hasta que** amanezca_.
mientras que|_María actuó como testigo **mientras que** su marido evadió sus responsabilidades_.
para que|_Hizo la tarea **para que** su mamá se la corrigiera en la noche_.
porque|_Traje el libro **porque** Ana me lo pidió_.
pues|_Era inevitable el resultado, **pues** nunca siguió consejos_.
puesto que|_Se quedó en silencio **puesto** que no quería discutir_.
si bien|_Manuel vendrá a la fiesta **si bien** tú se lo pides_.
una vez que|_Te daré la carta **una vez que** termines de contarme_.
ya que|_No compres las entradas **ya que** no tienes tiempo_.
ya sea|_Lo puedes hacer **ya sea** en la mañana, **ya sea** en la tarde_.


### PREPOSITION (Preposición)

Una Preposition establece un nexo entre dos elementos, donde el primero es conocido como elemento inicial y el segundo como término. Es una palabra invariable en género y número que sirve para indicar la función sintáctica o semántica del término que introduce.

Una caracterización más detallada de las posibles relaciones que puede establecer una Preposition puede encontrarse en el modelo PREPOSITIONS.

#### Preposiciones simples

A continuación se presentan algunas Prepositions simples del español como ejemplo.

Preposition | Ejemplo
--- | ---
a|_Tu ayuda les fue útil **a** los voluntarios_.
ante|_Estaba parado **ante** un gran público_.
bajo|_Mi padre traía el paquete **bajo** el brazo_.
con|_El niño juega **con** la perra_.
contra|_Los defensores luchan **contra** las injusticias_.
de|_Todos salieron **de** la sala_.
desde|_Vino corriendo **desde** el jardín_.
durante|_La niña durmió **durante** toda la noche_.
en|_Los libros están **en** la mesa_.
entre|_El jefe tiene que decidir **entre** dos propuestas_.
hacia|_Los niños corrieron **hacia** sus padres_.
hasta|_Mis terrenos llegan **hasta** esa cerca_.
mediante|_Luis consiguió las entradas **mediante** un amigo_.
para|_La maestra tajo dulces **para** todos los niños_.
por|_Los invitados llegan mañana **por** la tarde_.
pro|_Don Roque es **pro** italiano_.
según|_Hicimos la torta **según** la receta_.
sin|_La cantante dejó **sin** palabras al público_.
sobre|_Siempre deja la ropa **sobre** la cama_.
tras|_El perro corre **tras** el gato_.
versus|_El juego es niñas **versus** niños_.
vía|_Las imágenes se reciben **vía** satélite_.

#### Preposiciones compuestas

A continuación se presentan algunas Prepositions compuestas del español como ejemplo.

Formadas por la anteposición de un Adverb | Ejemplo
--- | ---
arriba de|_Yo vi un plato **arriba de** la nevera_.
fuera de|_María estaba **fuera de** su casa_.
encima de|_Mi madre deja las llaves **encima de** la mesa_.
delante de|_Práctico mis discursos **delante de** un espejo_.
debajo de|_Estaba escondido **debajo de** los árboles_.
detrás de|_El gato estaba **detrás de** la casa_.
después de|_Manuel logró graduarse **después de** tantos años_.
además de|_Le dio muchos consejos **además de** algunas advertencias_.

Formadas por un Noun y una Preposition| Ejemplo
--- | ---
a causa de|_Marcos se molestó **a causa de** tus mentiras_.
con arreglo a|*Debes actuar **con arreglo a** la ley.
en virtud de|_Luis busca una solución **en virtud del** beneficio colectivo_.
con objeto de|_Trajo muchos dulces **con objeto de** repartirlos_.
gracias a|_Conseguimos la habitación **gracias a** mi actitud_.
por culpa de|_Nos perdimos **por culpa de** tu necedad_.
a sabiendas de|_Ella acepto el trabajo **a sabiendas del** horario_.
con base en|_Argumentó su postura **con base en** la investigación de su profesor_.
de acuerdo con|_Actué **de acuerdo con** lo que dijiste_.
en relación con|*Tengo una respuesta **en relación con** su petición_.
en vías de|_Es un país **en vías de** desarrollo_.
a este lado de... y al otro lado de...|_Los campos son iguales ***a este lado del** río **y al otro lado del** puente_.

Formadas por la anteposición de un Adjective | Ejemplo
--- | ---
conforme a|_Hicimos el proyecto **conforme a** tus especificaciones_.
debido a |_Llegué tarde al trabajo  **debido al** tráfico_.
referente a|_Tengo el informe **referente a** tu proyecto_.

Formadas por varias Prepositions | Ejemplo
--- | ---
en contra de|_Salió del hospital **en contra de** las indicaciones médicas_.
tras de|_Tengo dos semanas **tras de** ti para hacer el trabajo_.

El caso de la contracción *del*, se considerará *de* como preposition y *l* como Article. Igualmente, con *al* la *a* será la Preposition y *l* un Article.


### PRONOUN (Pronombre)

Esta clase de palabra señala, remite a algo o lo representa sin emplear su nombre. Los Pronouns remiten a un referente ya mencionado o conocido.

Ejemplo: _María viene esta tarde, **ella** traerá galletas_

A continuación se presentan los features y los valores que estos pueden tomar para caracterizar a esta categoría.

#### Pronoun Gender (género)

Los Pronouns en español presentan variación de género, en español puede ser masculine o feminine. A veces el Gender es observable en la flexión de la palabra, no obstante, hay Pronouns que no muestran marcas externas de Gender porque son invariables, pero esta se puede deducir del Noun del referente al que esta sustituyendo o de los adyacentes que lo acompañen.

##### Masculine Pronoun (masculino)

En español se reconoce en la flexión de la palabra con el uso del morfema masculino (*-o*), algunas veces no se muestran marcas pero se puede deducir del Noun del referente al que esta sustituyendo, o de los adyacentes que lo acompañan.

Ejemplo: _**él** se la pasa llorando_

##### Feminine Pronoun (femenino)

Se reconoce en la flexión de la palabra con el uso del morfema femenino (*-a*), algunas veces no se muestran marcas pero se puede deducir del Noun del referente al que esta sustituyendo, o de los adyacentes que lo acompañan.

Ejemplo: _**esa** es de mi hermana_; _hay dos casas rojos. La más **grande** es de mi abuela_

##### Neuter Pronoun (femenino)

Algunos Pronouns presentan un Neuter Gender. En español algunos Personal y Demostrative Pronouns se presentan en neutro.

Ejemplos: _**Ese** no te conviene_; _No creo en **ello**_

##### Non-gender Pronoun (no-género)

Algunas veces el pronoun no presenta información respecto al Gender.

Ejemplo: _¿**Qué** comida compramos?_

Los Interrogative y Exclamative Pronouns que no presentan flexión respecto al Gender se consideran como Non-gender, aún cuando el Noun que modifique tenga su género marcado.

#### Pronoun Number (número)

Los Pronouns presentan variación de número, pueden ser singulares o plurales. El número normalmente se explicita en la terminación del Pronoun.

##### Singular Pronoun (singular)

Término no marcado, por lo que se indica con el morfema cero (Ø). Este, indica una unidad.

Ejemplo: _La **mia** es más bonita_

##### Plural Pronoun (plural)

En español se expresa mediante los morfemas *–s* para las palabras que acaban en vocal átona, y con *–es* para las que acaban en consonante. Este indica una agrupación de varios elementos.

Ejemplos: _En la mañana puedo escuchar**los**_; _**Ellos** me quieren, pero no me soportan_

##### Non-number Pronoun (no-número)

Algunas veces el Pronoun no está presentando información respecto al número.

Ejemplo: _¿**Qué** (comida) compramos?_; _¿**Qué** (cosas) vamos a comprar en el centro comercial?_


#### Clasificación según la clase deíctica del Pronoun (Deictic Class)

Los pronombres son clases deícticas por naturaleza ya que su significado está totalmente determinado con respecto a la situación discursiva particular que se esté llevando a cabo en un momento dado. La siguente clasificación se basa en distinciones tradicionales en gramática. 

Para una visión más exhaustiva de la semántica del Pronoun se puede consultar el modelo DEICTICS.

##### Personal Pronoun (personal)

Los Personal Pronoun pueden cumplir la función de sujeto, complemento directo y complemento indirecto (precedidos o no por una Preposition).

Ejemplo: _Cuando los empresarios entraron el presidente **los** saludó_

Los Personal Pronoun flexionan en número, persona y caso, algunos flexionan también en género. Por ejemplo, *le* es un Personal Pronoun de 3era persona, masculino, singular, en caso acusativo. La palabra *yo*, en cambio, es un Personal Pronoun de 1era persona singular, sin género (non-gender), en caso nominativo (nom).

##### Possessive Pronoun (posesivo)

Se trata de los mismos Possessive Adjectives, pero sustantivados por un Article: _el carro mío_ --> _el mío_. Los Possessive Pronoun del español son los siguientes.

Persona | Possessive Pronoun
--- | ---
1era persona | mío(s), mía(s), nuestro(s), nuestra(s).
2da persona | tuyo(s), tuya(s), suyo(s), suya(s).
3era persona | suyo(s), suya(s).

Ejemplo: _Mi amiga no ha llegado, la **tuya** sí_; _Estos son los **nuestros**_

##### Indeterminate Pronoun (indeterminado)

Implican que una entidad es desconocida o imprecisa por falta de información, o por alguna otra razón.

Ejemplos: _Te llamó **alguien**; podría ser **cualquiera**; es **algo** muy inesperado_

##### Quantitative Pronoun (cuantitativo)

Se usan para expresar cantidades o identidades de forma vaga o imprecisa, por la carencia de información o alguna por otra razón.

Ejemplos: _Te debo **varios**; quiero a **pocos**; vinieron **demasiados** a comer_

##### Relative Pronoun (relativo)

Los Relative Pronoun son los que se utilizan para conectar o relacionar (de ahí su nombre) dos o más ideas que en realidad se podrían expresar en forma de oraciones independientes y son los siguientes: *que, el cual (los cuales, las cuales), quien, cuyo, donde, cuanto, como, cuando*.

Ejemplo: _Yo prefiero el vestido **que** es largo._

La forma de distinguir este Pronoun es que sustituye a otro elemento (por lo general inmediatamente anterior) y a veces es conmutable por otro relativo: _el niño del **que** te hablé_ --> _el niño d**el cual** te hablé_ --> _el niño de **quien** te hablé_. La elección del feature Gender en los Relative Pronouns se determinará en relación al género del Noun del referente que está sustituyendo, o de los elementos que lo estén acompañando.

##### Demostrative Pronoun (demostrativo)

Se utilizan para medir la proximidad (cercanía o lejanía) de un referente con respecto a sus intelocutores, es decir, se toma en cuenta la proximidad entre el hablante, el referente y el oyente. Los Demostrative Pronoun se pueden referir tanto a entidades concretas y físicas como a relaciones abstractas; no miden solo espacio, sino también tiempo.

Ejemplo: _Trae **esa** de allá_; _**Eso** que me dijiste el otro día me alegró mucho_

Estos son los Demostrative Pronoun, ordenados según su grado de distancia respecto al hablante.

Grado de distancia | masc , sing  | fem, sing | neu, sing | masc, plu | fem, plu
------------------ | ------------ | ----------| --------- | --------- | -------
Distancia corta al destinador | _**este**_ | _**esta**_ | _**esto**_ | _**estos**_ | _**estas**_
Distancia corta al destinatario | _**ese**_ | _**esa**_ | _**eso**_ | _**esos**_ | _**esas**_
Distancia lejana a los interlocutores | _**aquel**_ | _**aquella**_ | _**aquello**_ | _**aquellos**_ | _**aquellas**_

##### Numeral Pronoun (numeral)

Indica el número exacto de una cantidad relacionada con el Noun, sus múltiplos, su división o su lugar en una escala (*uno, triple, mitad, cuarto*). A diferencia del adjetivo numeral, el pronombre no va acompañado de un Noun.

Ejemplos: _Sírvame **dos** (raciones de comida)_; _Sírvame **triple**_; _Llegó a la meta de **cuarto**_

##### Non-deictic Pronoun (no-deíctico)

Se selecciona este feature si el Pronoun, aun siendo deíctico, tiene alguna otra función paralela que puede ser importante también, como en el caso del Modal Pronoun.

#### Clasificación según el caso del Pronoun (case)

El caso es una variación de la forma de una palabra para indicar la categoría sintáctica de la misma dentro de una cláusula, en particular, en el nivel de la cláusula como intercambio (Exchange). En español, flexionan en caso sólo los Personal Pronouns y los Possesive Pronouns.

##### Nominative (nominativo)

Es el caso utilizado para indicar que la palabra funciona como Subject.

Ejemplo: _**Yo** tengo hambre_

##### Accusative (acusativo)

Caso que generalmente no va acompañado de Preposition y que identifica un Complement (por lo general al objeto **directo**). Puede llevar la preposición *a* cuando es humano y está definido.

Ejemplo: _**Lo** voy a enviar_

##### Dative (dativo)

Caso que generalmente va acompañado de la preposición *a* y que identifica un Complement (por lo general al objeto **indirecto**).

Ejemplo: _**Te** lo dejo en la mesa_

##### Ablative (ablativo)

Es un caso que indica que un Pronoun funciona como un Adjunct. En español va antecedido de una Preposition o la incorpora directamente en su forma morfológica (*conmigo, contigo, consigo*)

Ejemplo: _Lo llevo **conmigo**_; _Lo guardo para **mí**_

##### Non-case Pronoun (no-caso)

Se considerará como non-case aquel Pronoun que no flexione en según el caso. En español equivale a decir que los Pronouns distintos a los Personal o Possesive serán clasificados con este feature.


#### Clasificación según la persona del Pronoun (Person)

Pronoun Person indica si el Pronoun se refiere a algún elemento de la situación comunicativa (destinador, destinatario u otro).

##### Pronoun First Person (primera persona)

Se utiliza cuando el Pronoun se refiere al destinador (emisor del mensaje).

Ejemplo: _Eso es **mío**_

##### Pronoun Second Person (segunda persona)

Se utiliza cuando el Pronoun designa al destinatario (receptor del mensaje).

Ejemplo: _El más chiquito es **tuyo**_

##### Pronoun Third Persona (tercera persona)

Se utiliza cuando la referencia del Pronoun no coincide con el destinador ni con el destinatario. Esta tercera persona se manifiesta también cuando no interesa la referencia Pronoun o cuando esta no se puede puntualizar en la realidad.

Ejemplo: _Nosotros tenemos el nuestro, ella debe buscar el **suyo**_

##### Pronoun Non-person (nonperson)

Se considerará como non-person a todos los Pronouns que no aportan información sobre la persona gramatical.

#### Clasificación según su clase modal (Modal)

Estos features están relacionados más con la modalidad de la cláusula que con la forma en que se establece una referencia con un Noun.

##### Interrogative Pronoun (interrogativo)

Designa entidades cuya identidad o cantidad están por precisar; indica también la modalidad interrogativa de la cláusula, de tal manera que establece una solicitud de información precisa al destinatario.

Ejemplo: _¿**Qué** va a comprar?_; _¿**Quién** te llamó?_

##### Negative Pronoun (negativo)

Indican o refuerzan la modalidad negativa de la cláusula, resaltando a su vez la identidad imprecisa del elemento.

Ejemplos: _hoy no vino **nadie**_; _no me apetece **nada**_; _no me agradó **ninguno**_

##### Positive Pronoun (positivo)

Se usa como 'feature por defecto' de un Pronoun en esta categoría, cuando la modalidad de la cláusula es *afirmativa* y *aseverativa*.

Ejemplo: _**Alguien** me llamó a las 3 de la madrugada_

##### Exclamative Pronoun (exclamativo)

Se utilizan para convertir la modalidad de una claúsula en exclamativa además de sustituir a alguna entidad general de la situación discursiva.

Ejemplo: _¡**Quién** te viera tan guapo!_

##### Non-modal Pronoun (no-modal)

Utilizado para casos en los que el Pronoun no indica modalidad.


### Verb (Verbo)

El Verb es una clase de palabra que se utiliza para denotar un proceso o una acción, dicho proceso configura el resto de las posibilidades sintácticas y semánticas de la cláusula. El Verb funciona como núcleo de varios niveles de análisis (Exchange, Message y Representation). 

En español es una palabra morfológicamente compleja debido a que posee un amplio sistema de conjugación. Además, su sistema morfológico puede ser ampliado utilizando uno o vario Auxiliaries.


#### Clasificación según el número del Verb (Number)

Los Verbs presentan variación de número, en español pueden ser singulares o plurales. El número en el Verb indica parcialmente la concordancia con el Subject, en otras palabras, el Number contribuye a identificar el Subject de un Verb.

##### Singular Verb (singular)

El Singular en un Verb indica que el Subject es una unidad.

Ejemplos: _Mi casa **es** más bonita_; _Yo **canto** solo en la ducha_

##### Plural Verb (plural)

Señala la concordancia con un sujeto que refiere a un conjunto o agrupación de personas o cosas.

Ejemplos: _Nosotros **cantamos** en la noche_; _Los carros **son** rápidos_

##### Non-number Verb (no-número)

Algunas veces el Verb no aporta información respecto al número, sobre todo cuando es un verbo no personal (Participle, Gerund, Infinitive).

Ejemplo: _Vamos a **ir** a clases_

#### Clasificación según la persona del Verb (Person)

Person indica que el Verb tiene como Subject al destinador (First Person), al destinatario (Second Person) o alguna otra entidad del discurso (Third Person). Person junto con Number contribuyen a identificar el Subject, incluso cuando no ha sido nombrado.

##### First Person Verb (primera persona)

Señala que el Subject del Verb es el destinador del discurso. Puede incluir entidades adicionales al destinador cuando está en plural.

Ejemplos: _(Yo) **Camino** hasta mi casa_; _Nosotros siempre **llegamos** a tiempo_

##### Second Person Verb (segunda persona)

Indica que el Subject del Verb es el destinatario o los destinatarios del discurso.

Ejemplos: _**Corres** sin rumbo_; _**Hablásteis** mucho ese día_

##### Third Person Verb

El Verb tiene como Subject uno o varios elementos de los cuales ninguno es el destinador, o el destinatario. También se utiliza cuando el Verb no tiene Subject (impersonal) o cuando el Subject es una entidad desconocida.

Ejemplos: _Sueña con irse lejos_; _Se **venden** helados_; _Por allí **viene** alguien_

##### Non-person Verb (no-persona)

Algunas veces el Verb no aporta información respecto a la persona, cuando es un verbo no personal (Participle, Gerund, Infinitive).

Ejemplo: _**Cantar** canciones de amor bajo la lluvia_


#### Clasificación del Verb según el modo (Mood)

El Mood del Verb contribuye a identificar la función general de la cláusula: solicitudes, mandatos, expresar seguridad e inseguridad, etc.

##### Imperative Verb (imperativo)

Se trata de un Mood que se utiliza para dar órdenes o solicitudes de forma directa y rápida. En español solamente se presenta en segunda persona: ¡*Entra*! ¡*Entrad*! Por otro lado, en las oraciones negativas el imperativo se sustituye por el subjuntivo.

Ejemplo: _**Venga** por aquí, señor alcalde_

##### Subjunctive Verb (subjuntivo)

Hace que la modalidad de la cláusula exprese deseo, intención, inseguridad, necesidad, temor o valoración. Suele estar subordinado a otro Verb que hace explícita dicha modalidad, aunque a veces puede prescindir de él debido a que la modalidad se puede deducir de la situación discursiva.

Ejemplos: _Espero que **venga**_; _¡Ojalá me **gane** la lotería!_; _Dios, ¡que le **guste** el regalo!_

##### Indicative Verb (indicativo)

Se trata del Mood por defecto, no implica ninguna modalidad en particular y puede utilizarse para expresar diversas modalidades de cláusula. Como no tiene un sentido específico, la modalidad debe ser construida en la cláusula a partir de elementos externos al Verb.

Ejemplos: _El director [vendrá]_; _¡Tú **haces* lo que yo te diga!_; _¿Qué te **gustaría** hacer hoy?_

##### Modal not apply (modal no aplica)

Algunas veces, aunque la cláusula presente un Mood, el Verbo no especifica por sí mismo información respecto al modo, sobre todo cuando es un verbo no personal (Participle, Gerund, Infinitive).

Ejemplo: _¡A **cantar** hoy!_


#### Clasificación del Verb según el tiempo gramatical (Tense)

El Tense del Verb se corresponde con las formas de conjugación que gramaticalizan las informaciones temporales. Desde el punto de vista temporal hay dos clases: absolutos y relativos. Los _absolutos_ están orientados directamente con el momento de la enunciación, los tiempos _relativos_ en cambio tienen como punto de referencia un tiempo absoluto o algún otro tiempo relativo.

El Tense es una categoría compleja, por un lado distingue entre tiempos relativos y absolutos, por el otro establece una diferencia entre tiempos primarios y secundarios.

A continución se presenta una tabla con los valores que puede tomar el feature class Tense para el Verb **en español** y ejemplos de los mismos. Esta tabla indica también los valores absoluto-relativo para cada tiempo. Cabe destacar que cada idioma en particular tiene su propia nomenclatura para el Tense debido a que se trata de un sistema complejo de features que se mezclan entre sí de formas complejas.

Mood | Valor del Tense | Ejemplos | Relatividad
---- | ----- | -------- | ---------------
indicativo | presente | _canto, bebo, vivo_ | absoluto
indicativo | pretérito | _canté, bebí, viví_ | absoluto
indicativo | copretérito | _cantaba, bebía, vivía_ | relativo
indicativo | postpretérito | _cantaría, bebería, viviría_ | relativo
indicativo | futuro | _cantaré, beberé, viviré_ | absoluto
indicativo | antepresente | _he cantad, he vivido_,  | relativo
indicativo | antepretérito | _hube cantado_ | relativo
indicativo | antecopretérito | _había cantado_ | relativo
indicativo | antepospretérito | _habría cantado_ | relativo
indicativo | antefuturo | _habré cantado_ | relativo
subjuntivo | presente | _cante, beba, viva_ | relativo
subjuntivo | pretérito | _cantara/cantase, bebiera/bebiese_ | relativo
subjuntivo | antepresente | _haya cantado_ | relativo
subjuntivo | antepretérito |  _hubiera/hubiese cantado_ | relativo

Los valores del Tense, además de distinguir entre absolutos y relativos, también distinguen entre Primary Tense y Secondary Tense. Se presenta esta clasificación a continuación.

##### Primary Tense (tiempo primario)

Indica si el proceso denotado por el Verb ocurre: simultáneamente al acto de habla (present), antes del acto de habla, o si se da posteriormente a dicho acto (fut). Se trata de una distinción básica temporal.

Ejemplos: _dice_ (presente); _dijo_ (pretérito); _dirá_ (futuro)

##### Secondary Tense (tiempo secundario)

Señala si el tiempo es absoluto o relativo. Un Verb en tiempo absoluto no se apoya en ningún otro tiempo, mientras que un Verb en tiempo relativo define parcialmente su temporalidad a partir de otro Verb.

Ejemplo de tiempo secundario absoluto: _yo lo **dije**_

Ejemplo de tiempo secundario relativo: _yo lo **decía** porque..._

Los dos ejemplos anteriores están en un tiempo primario pasado o pretérito. Sin embargo, _dije_ es un tiempo absoluto, mientras que _decía_ es un tiempo pasado que requiere de otro Verb o de otra marca temporal para definirse completamente.

##### No Tense (no tiempo)

Algunas veces el Verb no aporta información respecto al tiempo, sobre todo cuando es un Verb no personal (Participle, Gerund, Infinitive).

Ejemplo: _Hay que saber **vivir*_


#### Clasificación del Verb según el aspecto (Aspect)

El Verbal Aspect nos permite saber si las acciones surgen, se terminan o se repiten, pero también si se perciben en su integridad o se muestran únicamente en un punto de su desarrollo. El aspecto verbal afecta al tiempo interno de la situación, este puede ser: habitual, iterative, puntual, prospective, progressive, perfect o imperfect.

##### Habitual (habitual)

Se trata de un proceso que se lleva a cabo comunmente. Por lo general, el aspecto habitual se usa en verbos en presente simple.

Ejemplo: _¿(normalmente) A qué hora **abre** el restaurant?_

##### Iterative (iterativo)

Este valor del Aspect del Verb se usa para indicar que el proceso se realiza en acciones cortas repetidas durante un período breve de tiempo. El aspecto iterativo no es común en verbos en tiempo presente.

Ejemplo: _Sara **lee y lee** esa carta_

Entendemos que en este enunciado _leer_ es una acción corta que sucede de forma repetida durante un largo período de tiempo.

##### Puntual (puntual)

Este aspecto indica que la acción se realiza en el momento en el que se está hablando.

Ejemplo: _¿(en este momento) Cuánto **cuestan** las empanadas?_

##### Prospective (prospectivo)

Este Aspect expresa que la acción se está proyectando hacia un instante futuro (absoluto o relativo), este puede ser usado con verbos en distintos tiempos siempre que estos indiquen que la acción se realiza en dicho futuro.

Ejemplo: _Me **fui**_ (Usado en el sentido de *me voy a ir*)

##### Progressive (progresivo)

Progressive indica que la acción está en progreso. Se trata de una duración relativamente extensa comparada con la puntual.

Ejemplo: _El restaurant está **buscando** nuevos empleados_

##### Perfect

Este Aspect implica que la acción ha finalizado o que se "siente" como una acción terminada o terminable.

Ejemplo: _Ayer el restaurant **abrió** tarde_

##### Imperfect

Este Aspect se usa cuando se especifica que la acción no terminó o no es posible concluirla. Generalmente está relacionado con el Tense relativo.

Ejemplo: _El restaurant **ofrecía** un menú ejecutivo_

##### No Aspect (no aspecto)

Algunas veces el Verb no aporta información respecto al aspecto, sobre todo cuando es un verbo no personal (Participle, Gerund, Infinitive).

#### Aspect y Tense

A continuación se presenta una lista de ejemplos clasificados según el Aspect y el Tense. El Tense se presenta con su nombre tradicional en español.

Mood | Tense | Aspect | Example 
---- | ----- | ------ | -------
indicativo | presente | puntual | _Luis **llegó** a Caracas_
indicativo | presente | habitual | _Arturo **canta** los domingos_
indicativo | presente | progresivo | _Estate quieto, Carlos, no seas bruto; me **haces** daño_
indicativo | presente | prospectivo | _Nosotros nos **quedamos** el próximo verano en Vetusta_
indicativo | pretérito | perfecto | _José leyó 'Guerra y paz' el mes pasado_
indicativo | copretérito | imperfecto | _El libro **costaba** tres euros_
indicativo | copretérito | prospectivo | _¿A qué hora **empezaba** la película esta noche?_
indicativo | copretérito | puntual | _Si se enteraban los demás, yo **estaba** perdido_
indicativo | copretérito | habitual | _Todos los días **se acostaba** temprano_
indicativo | copretérito | progresivo | _Todos los mecánicos **llegaban** a bordo en aquel momento_
indicativo | postpretérito | prospectivo | _Me prometió que **lamaría**_
indicativo | futuro | imperfecto | _Luis **trabajará** ahora en la empresa de su padre_
indicativo | antepresente | perfecto | _**Ha muerto** hace dos meses_
indicativo | antepresente | imperfecto | _Siempre **he vivido** aquí_
indicativo | antepresente | prospectivo | _Mañana a estas horas, ya **han terminado** ustedes_
indicativo | antepresente | continuo | _Conozco todas sus tretas Las **han empleado** durante un siglo_
indicativo | antepretérito | perfecto | _Algunos invitados se marcharon cuando **hubo terminado** la cena_
indicativo | antecopretérito | perfecto | _Yo te ví allí Te **habías levantado**_
indicativo | antecopretérito | habitual | _A esta hora, los viernes Eugenio había salido del trabajo_
indicativo | antepospretérito | perfecto | _Afirmaron que cuando llegara el invierno **habrían recogido** la cosecha_
indicativo | antefuturo | perfecto | _Cuando el invierno llegue, **habré recogido** toda la cosecha_
subjuntivo | presente | puntual | _Es indispensable que **digas** la verdad_
subjuntivo | pretérito | imperfecto | _Durante todo el tiempo que **estuviesen** allí, todos se llamarían por su apellido_ 
subjuntivo | antepresente | prospectivo | _No creo que **haya teminado** el próximo lunes_
subjuntivo | antepretérito |  perfecto | _No creí que José **hubiese/hubiera** llegado_
subjuntivo | antepretérito | prospectivo | _Si en el plazo de diez días no se **hubiere presentado**_


#### Formas no personales (finiteness)

Son las formas que el Verb toma cuando no codifica Person, Tense, Aspect o Mood. El Verb en estos casos sigue siendo una acción o proceso que admite Complements, pero que ha perdido buena parte de su morfología verbal. En este sentido, un Finiteness Verb **debe seguir siendo un Verb**, y no funcionar como otro tipo de palabra derivada (Noun, Adjective o Adverb); para seguir siendo considerado tal, el Verb debe ir acompañado, por lo menos, de un Complement o un Adjunct.

##### Gerund (gerundio)

Se trata de un Verb que funciona de manera similar a un Adverb (modificando directamente a otro Verb); en español usa las terminaciones *-ando*, *-iendo*. Se usa para agregar una cláusula subordinada que funciona como Adjuct de otro Verb, generalmente para expresar acciones simultáneas.

Ejemplo: _Salió de la estancia [**dando** un fuerte portazo]_

##### Infinitive (infinitivo)

El Infinitive es un Verb que ejerce funciones de Noun, pero que al mismo tiempo es núcleo verbal de su propia cláusula. En español termina en *-ar*, *-er*, o *-ir*. La cláusula que tiene como núcleo un Infinitive funciona como un Noun, así que, esta puede ir en lugar de cualquier Noun de la clásula principal, siempre y cuando este denote una acción o proceso.

Ejemplo: _Me gustaría [**cantar** de manera profesional]_

##### Participle (participio)

Es un Verb que funciona como núcleo de una cláusula subordinada de rol similar al Adjective. Se utiliza sobre todo para construir otros Tense de la clásula o para proporcionar una cualidad de un Noun al cual se subordina.

Ejemplo: _Compré una computadora [**fabricada** en china] y [**diseñada** en California]_; _He **ido** de viaje a Madrid_


### DISCOURSE MARKER (Marcador discursivo)

Los Discourse Markers son unidades que tienen como función guiar las inferencias que se realizan en la estructura del texto y en el devenir del discurso.

Se trata de formas invariables y gramaticalizadas que no tienen contenido léxico-semántico, y que funcionan fuera del ámbito de la clásula, ya que, como se especificó arriba, guian la lectura del texto o las suposiciones del discurso.


### Lista de Códigos de T-POS

**Lista de códigos y POS:**

| Código    | POS                          | Equivalencia en español |
| --------- | ---------------------------- | ----------------------- |
| NOUN      | Noun                         | Sustantivo              |
| ADJ       | Adjective                    | Adjetivo                |
| ART       | Article                      | Artículo                |
| ADV       | Adverb                       | Adverbio                |
| CONJ      | Conjunction                  | Conjunción              |
| CONJ\_SEG | Conjunction seg              | Conjunción segmentado   |
| INT       | Interjection                 | Interjección            |
| PREP      | Preposition                  | Preposición             |
| PRON      | Pronoun                      | Pronombre               |
| AUX       | Auxilar                      | Auxilar                 |
| VERB      | Verb                         | Verbo                   |
| VERB\_SEG | Verb seg                     | Verbo segmentado        |
| MARKER    | Discourse Marker / Connector | Marcador discursivo     |

**Lista de POS y códigos:**

| POS              | Código    |
| ---------------- | --------- |
| Adjective        | ADJ       |
| Adverb           | ADV       |
| Article          | ART       |
| Auxiliar         | AUX       |
| Conjunction      | CONJ      |
| Conjunction seg  | CONJ\_SEG |
| Discourse Marker | MARKER    |
| Interjection     | INT       |
| Noun             | NOUN      |
| Preposition      | PREP      |
| Pronoun          | PRON      |
| Verb             | VERB      |
| Verb seg         | VERB\_SEG |

**Lista de Features por POS**

**Lista por POS:**

| POS  | Feature       | Value            | Característica                  |
| ---- | ------------- | ---------------- | ------------------------------- |
| NOUN | gender        | masc             | masculino                       |
| NOUN | gender        | fem              | femenino                        |
| NOUN | gender        | neut             | neutro                          |
| NOUN | gender        | non-gender       | sin género asignable            |
| NOUN | number        | sing             | singular                        |
| NOUN | number        | plu              | plural                          |
| NOUN | number        | non-number       | sin número asignable            |
| NOUN | commonness    | common           | común                           |
| NOUN | commonness    | propn            | propio                          |
| NOUN | animacy       | anim             | animado                         |
| NOUN | animacy       | inam             | inanimado                       |
| NOUN | countability  | count            | contable                        |
| NOUN | countability  | uncount          | incontable                      |
| —–   | ————-         | ————             | ————-                           |
| ADJ  | gender        | masc             | masculino                       |
| ADJ  | gender        | fem              | femenino                        |
| ADJ  | gender        | neut             | neutro                          |
| ADJ  | gender        | non-gender       | sin género asignable            |
| ADJ  | number        | sing             | singular                        |
| ADJ  | number        | plu              | plural                          |
| ADJ  | number        | non-number       | sin número asignable            |
| ADJ  | semanticClass | calif            | calificativo                    |
| ADJ  | semanticClass | non-semantic     | no semántico                    |
| ADJ  | degree        | cmp              | comparativo                     |
| ADJ  | degree        | sup              | superlativo                     |
| ADJ  | degree        | non-degree       | sin grado asignable             |
| ADJ  | deicticClass  | poss             | posesivo                        |
| ADJ  | deicticClass  | demos            | demostrativo                    |
| ADJ  | deicticClass  | excl             | exlamativo                      |
| ADJ  | deicticClass  | num              | numeral                         |
| ADJ  | deicticClass  | cuant            | cuantitativo                    |
| ADJ  | deicticClass  | indet            | indeterminado                   |
| ADJ  | deicticClass  | rel              | relativo                        |
| ADJ  | deicticClass  | non-deictic      | no deíctico                     |
| ADJ  | modalClass    | interrog         | interrogativo                   |
| ADJ  | modalClass    | non-modal        | no modal                        |
| ADJ  | person        | 1                | primera                         |
| ADJ  | person        | 2                | segunda                         |
| ADJ  | person        | 3                | tercera                         |
| ADJ  | person        | not-person       | sin persona asignable           |
| —–   | ————-         | ————             | ————-                           |
| ART  | definiteness  | indefinite       | indefinido                      |
| ART  | definiteness  | definite         | definido                        |
| ART  | concreteness  | concrete         | concreto                        |
| ART  | concreteness  | abstract         | abstracto                       |
| ART  | gender        | masc             | masculino                       |
| ART  | gender        | fem              | femenino                        |
| ART  | gender        | neut             | neutro                          |
| ART  | gender        | non-gender       | sin género asignable            |
| ART  | number        | sing             | singular                        |
| ART  | number        | plu              | plural                          |
| ART  | number        | non-number       | sin número asignable            |
| —–   | ————-         | ————             | ————                            |
| PRON | gender        | masc             | masculino                       |
| PRON | gender        | fem              | femenino                        |
| PRON | gender        | neut             | neutro                          |
| PRON | gender        | non-gender       | sin género asignable            |
| PRON | number        | sing             | singular                        |
| PRON | number        | plu              | plural                          |
| PRON | number        | non-number       | sin número asignable            |
| PRON | deicticClass  | prs              | personal                        |
| PRON | deicticClass  | poss             | posesivo                        |
| PRON | deicticClass  | demos            | demostrativo                    |
| PRON | deicticClass  | excl             | exlamativo                      |
| PRON | deicticClass  | num              | numeral                         |
| PRON | deicticClass  | cuant            | cuantitativo                    |
| PRON | deicticClass  | indet            | indeterminado                   |
| PRON | deicticClass  | rel              | relativo                        |
| PRON | deicticClass  | non-deictic      | no deíctico                     |
| PRON | modalClass    | interrog         | interrogativo                   |
| PRON | modalClass    | neg              | negativo                        |
| PRON | modalClass    | positive         | positivo                        |
| PRON | modalClass    | non-modal        | no modal                        |
| PRON | person        | 1                | primera                         |
| PRON | person        | 2                | segunda                         |
| PRON | person        | 3                | tercera                         |
| PRON | person        | not-person       | sin persona asignable           |
| PRON | case          | nom              | nominativo, caso sujeto         |
| PRON | case          | acc              | acusativo / oblicuo, caso átono |
| PRON | case          | dat              | dativo / oblicuo, caso átono    |
| PRON | case          | abl              | ablativo, caso con preposición  |
| PRON | case          | not-case         | sin caso asignable              |
| —–   | ————-         | ————             | ————-                           |
| VERB | person        | 1                | primera                         |
| VERB | person        | 2                | segunda                         |
| VERB | person        | 3                | tercera                         |
| VERB | person        | not-person       | sin persona asignable           |
| VERB | number        | sing             | singular                        |
| VERB | number        | plu              | plural                          |
| VERB | number        | non-number       | sin número asignable            |
| VERB | aspect        | perf             | perfecto                        |
| VERB | aspect        | imp              | imperfecto                      |
| VERB | aspect        | prog             | progresivo                      |
| VERB | aspect        | habitual         | habitual                        |
| VERB | aspect        | iter             | reiterativo                     |
| VERB | aspect        | puntual          | puntual                         |
| VERB | aspect        | prosp            | prospectivo                     |
| VERB | aspect        | aspect-not-apply | sin aspecto asignable           |
| VERB | moodtype      | ind              | indicativo                      |
| VERB | moodtype      | sub              | subjuntivo                      |
| VERB | moodtype      | imp              | imperativo                      |
| VERB | moodtype      | Not-Apply        | sin modo aplicable              |
| VERB | finiteness    | inf              | infinitivo                      |
| VERB | finiteness    | ger              | gerundio                        |
| VERB | finiteness    | part             | participio                      |
| VERB | finiteness    | finite-verb      | verbo finito                    |
| VERB | tense         | pre              | presente                        |
| VERB | tense         | pas              | pretérito                       |
| VERB | tense         | cop              | co-pretérito                    |
| VERB | tense         | posp             | pospretérito                    |
| VERB | tense         | fut              | futuro                          |
| VERB | tense         | antepre          | antepresente                    |
| VERB | tense         | antepas          | antepretérito                   |
| VERB | tense         | antefut          | antefuturo                      |
| —–   | ————-         | ————             | ————-                           |
| ADV  | degree        | cmp              | comparativo                     |
| ADV  | degree        | sup              | superlativo                     |
| ADV  | degree        | non-degree       | sin grado asignable             |
| ADV  | deicticClass  | cuant            | cuantitativo (de cantidad)      |
| ADV  | deicticClass  | demo s           | demostrativo                    |
| ADV  | deicticClass  | loc              | locativo (de lugar)             |
| ADV  | deicticClass  | temp             | temporal (de tiempo)            |
| ADV  | deicticClass  | excl             | exclamantivo                    |
| ADV  | deicticClass  | rel              | relativo                        |
| ADV  | semanticClass | mode             | modo o manera                   |
| ADV  | semanticClass | qulify           | calificativo                    |
| ADV  | semanticClass | non-semantic     | no semántico                    |
| ADV  | modalClass    | interrog         | interrogativo                   |
| ADV  | modalClass    | pos              | positivo, afirmativo            |
| ADV  | modalClass    | neg              | negativo                        |
| ADV  | modalClass    | posib            | duda, probabilidad, posiblidad  |
| ADV  | modalClass    | non-modal        | no modal                        |
| —–   | ————-         | ————             | ————-                           |
| AUX  | aspect        | perf             | perfecto                        |
| AUX  | aspect        | imp              | imperfecto                      |
| AUX  | aspect        | prog             | progresivo                      |
| AUX  | aspect        | habitual         | habitual                        |
| AUX  | aspect        | iter             | reiterativo                     |
| AUX  | aspect        | puntual          | puntual                         |
| AUX  | aspect        | prosp            | prospectivo                     |
| AUX  | moodtype      | ind              | indicativo                      |
| AUX  | moodtype      | sub              | subjuntivo                      |
| AUX  | moodtype      | imp              | imperativo                      |
| AUX  | moodtype      | Not-Apply        | sin modo aplicable              |
| AUX  | person        | 1                | primera                         |
| AUX  | person        | 2                | segunda                         |
| AUX  | person        | 3                | tercera                         |
| AUX  | person        | not-person       | sin persona asignable           |

**Lista por Característica:**

| Característica                  | POS  | Feature       | Value            |
| ------------------------------- | ---- | ------------- | ---------------- |
| ablativo, caso con preposición  | PRON | case          | abl              |
| abstracto                       | ART  | concreteness  | abstract         |
| acusativo / oblicuo, caso átono | PRON | case          | acc              |
| animado                         | NOUN | animacy       | anim             |
| antefuturo                      | VERB | tense         | antefut          |
| antepresente                    | VERB | tense         | antepre          |
| antepretérito                   | VERB | tense         | antepas          |
| calificativo                    | ADJ  | semanticClass | calif            |
| calificativo                    | ADV  | semanticClass | qulify           |
| co-pretérito                    | VERB | tense         | cop              |
| comparativo                     | ADJ  | degree        | cmp              |
| comparativo                     | ADV  | degree        | cmp              |
| común                           | NOUN | commonness    | common           |
| concreto                        | ART  | concreteness  | concrete         |
| contable                        | NOUN | countability  | count            |
| cuantitativo (de cantidad)      | ADJ  | deicticClass  | cuant            |
| cuantitativo (de cantidad)      | PRON | deicticClass  | cuant            |
| cuantitativo (de cantidad)      | ADV  | deicticClass  | cuant            |
| dativo / oblicuo, caso átono    | PRON | case          | dat              |
| definido                        | ART  | definiteness  | definite         |
| demostrativo                    | ADJ  | deicticClass  | demos            |
| demostrativo                    | PRON | deicticClass  | demos            |
| demostrativo                    | ADV  | deicticClass  | demos            |
| duda, probabilidad, posiblidad  | ADV  | modalClass    | posib            |
| exclamantivo                    | ADV  | deicticClass  | excl             |
| exlamativo                      | ADJ  | deicticClass  | excl             |
| exlamativo                      | PRON | deicticClass  | excl             |
| femenino                        | NOUN | gender        | fem              |
| femenino                        | ADJ  | gender        | fem              |
| femenino                        | ART  | gender        | fem              |
| femenino                        | PRON | gender        | fem              |
| futuro                          | VERB | tense         | fut              |
| gerundio                        | VERB | finiteness    | ger              |
| habitual                        | VERB | aspect        | habitual         |
| habitual                        | AUX  | aspect        | habitual         |
| imperfecto                      | VERB | aspect        | imp              |
| imperfecto                      | AUX  | aspect        | imp              |
| inanimado                       | NOUN | animacy       | inam             |
| incontable                      | NOUN | countability  | uncount          |
| indefinido                      | ART  | definiteness  | indefinite       |
| indeterminado                   | ADJ  | deicticClass  | indet            |
| indeterminado                   | PRON | deicticClass  | indet            |
| indicativo                      | VERB | moodtype      | ind              |
| indicativo                      | AUX  | moodtype      | ind              |
| infinitivo                      | VERB | finiteness    | inf              |
| interrogativo                   | ADJ  | modalClass    | interrog         |
| interrogativo                   | PRON | modalClass    | interrog         |
| interrogativo                   | ADV  | modalClass    | interrog         |
| locativo (de lugar)             | ADV  | deicticClass  | loc              |
| masculino                       | NOUN | gender        | masc             |
| masculino                       | ADJ  | gender        | masc             |
| masculino                       | ART  | gender        | masc             |
| masculino                       | PRON | gender        | masc             |
| modo o manera                   | ADV  | semanticClass | mode             |
| negativo                        | PRON | modalClass    | neg              |
| negativo                        | ADV  | modalClass    | neg              |
| neutro                          | NOUN | gender        | neut             |
| neutro                          | ADJ  | gender        | neut             |
| neutro                          | ART  | gender        | neut             |
| neutro                          | PRON | gender        | neut             |
| no deíctico                     | ADJ  | deicticClass  | non-deictic      |
| no deíctico                     | PRON | deicticClass  | non-deictic      |
| no modal                        | ADJ  | modalClass    | non-modal        |
| no modal                        | PRON | modalClass    | non-modal        |
| no modal                        | ADV  | modalClass    | non-modal        |
| no semántico                    | ADJ  | semanticClass | non-semantic     |
| no semántico                    | ADV  | semanticClass | non-semantic     |
| nominativo, caso sujeto         | PRON | case          | nom              |
| numeral                         | ADJ  | deicticClass  | num              |
| numeral                         | PRON | deicticClass  | num              |
| participio                      | VERB | finiteness    | part             |
| perfecto                        | VERB | aspect        | perf             |
| perfecto                        | AUX  | aspect        | perf             |
| personal                        | PRON | deicticClass  | prs              |
| plural                          | NOUN | number        | plu              |
| plural                          | ADJ  | number        | plu              |
| plural                          | ART  | number        | plu              |
| plural                          | PRON | number        | plu              |
| plural                          | VERB | number        | plu              |
| posesivo                        | ADJ  | deicticClass  | poss             |
| posesivo                        | PRON | deicticClass  | poss             |
| positivo, afirmativo            | PRON | modalClass    | positive         |
| positivo, afirmativo            | ADV  | modalClass    | pos              |
| pospretérito                    | VERB | tense         | posp             |
| presente                        | VERB | tense         | pre              |
| pretérito                       | VERB | tense         | pas              |
| primera                         | ADJ  | person        | 1                |
| primera                         | PRON | person        | 1                |
| primera                         | VERB | person        | 1                |
| primera                         | AUX  | person        | 1                |
| progresivo                      | VERB | aspect        | prog             |
| subjuntivo                      | VERB | moodtype      | sub              |
| imperativo                      | VERB | moodtype      | imp              |
| progresivo                      | AUX  | aspect        | prog             |
| subjuntivo                      | AUX  | moodtype      | sub              |
| imperativo                      | AUX  | moodtype      | imp              |
| propio                          | NOUN | commonness    | propn            |
| prospectivo                     | VERB | aspect        | prosp            |
| prospectivo                     | AUX  | aspect        | prosp            |
| puntual                         | VERB | aspect        | puntual          |
| puntual                         | AUX  | aspect        | puntual          |
| reiterativo                     | VERB | aspect        | iter             |
| reiterativo                     | AUX  | aspect        | iter             |
| relativo                        | ADJ  | deicticClass  | rel              |
| relativo                        | PRON | deicticClass  | rel              |
| relativo                        | ADV  | deicticClass  | rel              |
| segunda                         | ADJ  | person        | 2                |
| segunda                         | PRON | person        | 2                |
| segunda                         | VERB | person        | 2                |
| segunda                         | AUX  | person        | 2                |
| sin aspecto asignable           | VERB | aspect        | aspect-not-apply |
| sin caso asignable              | PRON | case          | not-case         |
| sin género asignable            | NOUN | gender        | non-gender       |
| sin género asignable            | ADJ  | gender        | non-gender       |
| sin género asignable            | ART  | gender        | non-gender       |
| sin género asignable            | PRON | gender        | non-gender       |
| sin grado asignable             | ADJ  | degree        | non-degree       |
| sin grado asignable             | ADV  | degree        | non-degree       |
| sin modo aplicable              | VERB | moodtype      | Not-Apply        |
| sin modo aplicable              | AUX  | moodtype      | Not-Apply        |
| sin número asignable            | NOUN | number        | non-number       |
| sin número asignable            | ADJ  | number        | non-number       |
| sin número asignable            | ART  | number        | non-number       |
| sin número asignable            | PRON | number        | non-number       |
| sin número asignable            | VERB | number        | non-number       |
| sin persona asignable           | ADJ  | person        | not-person       |
| sin persona asignable           | PRON | person        | not-person       |
| sin persona asignable           | VERB | person        | not-person       |
| singular                        | NOUN | number        | sing             |
| singular                        | ADJ  | number        | sing             |
| singular                        | ART  | number        | sing             |
| singular                        | PRON | number        | sing             |
| singular                        | VERB | number        | sing             |
| superlativo                     | ADJ  | degree        | sup              |
| superlativo                     | ADV  | degree        | sup              |
| temporal (de tiempo)            | ADV  | deicticClass  | temp             |
| tercera                         | ADJ  | person        | 3                |
| tercera                         | PRON | person        | 3                |
| tercera                         | VERB | person        | 3                |
| tercera                         | AUX  | person        | 3                |
| verbo finito                    | VERB | finiteness    | finite-verb      |
