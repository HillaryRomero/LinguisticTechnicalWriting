# Widget de desambiguación

## Descripción general

>  NOTA: El texto que se presenta a continuación contiene algunos términos lingüísitcos que son necesarios para la explicación de la herramienta. Se recomienda la lectura del glosario ubicado al final del capítulo antes de hacer la lectura del texto.


El **widget de desambiguación** es una herramienta que permite la comprensión del lenguaje natural a través de la identificación del significado de una palabra en un contexto determinado. El objetivo de esta herramineta es acceder al conocimiento base, a las definiciones de los lemmas o palabras lexicalizadas en el proceso de lexicalización, para determinar en qué sentido se utiliza la palabra.

La ambigüedad se da cuando una palabra es susceptible a dos o más significados e interpretaciones, así pues, una misma palabra se puede entender de diversas maneras. Tomando en cuenta lo anterior, es posible que las palabras provenientes de un corpus o de un diccionario terminológico, luego de ser incorporadas al diccionario del paquete Mammut, puedan tener más de un significado o función. En estos casos, el desarrollador deberá desambiguar dichas palabras con la finalidad de identificar la utilidad o función de la misma en relación a un contexto.


A través de la herramienta **widget de desambiguación** el desarrollador accederá a todas las entradas de las palabras o lemmas que presenten ambigüedad. El desarrollador podrá desambiguar:

1. Lemmas como: sustantivos, adjetivos, verbos y adverbios. En este caso el desarrollador podrá utilizar la herramienta para desambiguar una palabra con múltiples entradas al lexicón. Esto con la finalidad de identificar el significado adecuado de una palabra dentro del corpus y lexicón mismo.
> (Ver ejemplo de esto en el apartado **funcionamiento**).

2. Lemmas funcionales como: preposiciones, artículos, pronombres, conjunciones. En este caso el desarrollador accederá a la herramienta para escoger el esquema prototípico que identifique la función desempeñada por el elemento funcional en un contexto.
> (Ver ejemplo de esto en el apartado **funcionamiento**).


## Entrada del widget

El **widget de desambiguación** es una herramienta que funciona dentro de un entorno llamado [Jupyter Notebook](cuadernos_jupyter.md)

Para que la herramienta **widget de desambiguación** funcione correctamente dentro de un entorno Jupyter Notebook debe estar declarada en una celda de texto de la siguiente manera:

`package.show_disambiguation_widget()`

Posterior a este paso, será posible utilizar la herramienta de lexicalización en un Jupyter Notebook.


## Funcionamiento

Dado que una palabra puede tener varios significados, la desambiaguación es una etapa en la que el desarrollador puede seleccionar el significado de una palabra que tenga más sentido en un contexto determinado

Identificar el significado de las palabras pertenecientes a un [evento](../concepts/events.md) es esencial en el proceso de entrenamiento de un sistema para la comprensión del lenguaje. Por lo tanto, la herramienta **widget de desambiguación** permitirá que el desarrollador determine cuál de los significados de una palabra es el adecuado en un contexto dado.


Para iniciar el proceso de desambiguación a través de la herramienta **widget de desambiguación** es necesario llenar estos campos:

| Campo  | Descripción |
| ------ | ----------- |
| Select corpus  | Campo para seleccionar el corpus a analizar.|
| All events    | Campo donde se reflejan los eventos que forman parte del corpus seleccionado anteriormente.|
| Select one token  | Campo donde se seleciona el elemento a desambiguar.|


Luego de correr la herramienta **wigget de anotación** en el entorno [Jupyter Notebook](cuadernos_jupyter.md) y seleccionar la información pertienente en los campos descritos anterioemente como: **select corpus**, **all events**
se desplegará el **widget de desambiguación** el cual reflejará de la siguiente manera las palabras que conforman el evento seleccionado:  

| Campo  | Descripción |
| ------ | ----------- |
| Lexical | Palabras que forman parte del evento seleccionado y que SÍ están lexicalizadas en el corpus.|
| Funtionals    | Palabras funcionales que forman parte del evento seleccionado.|
| None  |Palabras que forman parte del evento seleccionado y que NO están lexicalizadas.|


Para efectos de este ejemplo, el [corpus](../concepts/corpus.md) utilizado almacena dos [eventos](../concepts/events.md) que tienen un lemma en común:

`Wisly trabaja en Jogwards`

`Wisly estudia en Jogwards`

Sin embargo, cada lemma `Wisly` fue definido dos veces por el desarrollador en el lexicón puesto que cada uno de estos lemmas hacen referencia a un personaje distinto. El primer `Wisly` hace referencia a un `Wisly` padre, y el siguiente hace referencia a un `Wisly` hijo. En este caso, o para efectos del desambiguador, el contexto es lo que permitirá diferenciar a un `Wisly` de otro.

Ahora, para completar el proceso de desambiguación, el desarrollador deberá seleccionar el token `Wisly` (lemma ambiguo del evento) y asignarle la opción que le permita establecer una distinción o romper la ambiguedad entre ambos lemmas.

Por lo tanto, la desambiguación se verá de la siguiente manera:

Finalmente, luego de desambiguar los lemmas, el desarrollador deberá guardar la anotación para que el corpus almacene la data desambiguada.


## Almacenamiento de la data:

Las desambiguaciones creadas a través del **widget de desambiguación** se almacenan en el documento de hojas de calculo del paquete Mammut. En este caso, la data desambiguada se guarda específicamente en la hoja de cálculo de un [corpus](../concepts/corpus.md) denominada **desambiguation** que almacena las desambiguaciones hechas para un corpus.  

Luego de terminar el proceso de desambiguación, el documento de hojas de calculo almacena todas las palabras desambiguadas por el desarrollador y esta información pasa a formar parte de la data de entrenamiento del chatbot.


## Glosario

- **Lemma**: Entrada de diccionario compuesta por un conjunto de caracteres relacionado con un concepto o significado. Cada uno de las palabras que el lexicón almacena.

- **Lexicón**: Es el almacén o diccionario del léxico.

- **Cláusulas**: Conjunto de palabras que, formando sentido completo, encierran una sola oración o varias íntimamente relacionadas entre sí.

- **Capas de Anotación**: Cada una de las diferentes dimensiones creadas para anotar una información espcífica en cada una de las cláusulas.

- **Esquema prototípico**: Guía que representa los casos modelo.

- **Elemento funcional**: Elementos que no pueden ser definidos en el lexicón. Por ejemplo:  preposiciones, artículos, pronombres, conjunciones.
