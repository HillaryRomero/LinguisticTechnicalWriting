# Corpus Map 

## Definición

El **corpus map** es un mapa de cada uno de los [corpus](corpus.md) que pueden ser usados para preparar a un mismo bot. La función de este mapa es almacenar los nombres de las diferentes sheets de cada corpus y atribuir la función a dichas sheets para que el sistema pueda interpretar correctamente los datos que estas contienen.

> **Nota:** un bot desarrollado por Mammut puede ser preparado usando varios corpora. El **corpus map** hace posible que el sistema identifique los vínculos que existen entre las partes de un mismo corpus, y que identifique los distintos corpora que se utilizarán en un solo bot.

El corpus map almacena el nombre de las sheets que guardan las opciones del corpus, especifica el idioma y el tipo de corpus. Si se trata de un **corpus M**, además, se deben listar las sheets que pertenecen a la ontology. De manera opcional, un corpus M puede incluir también la información de otras sheets, como la que guarda información sobre las variables, los scenario defaults y las translations del knowledge.

Conceptos relacionados: [corpus](corpus.md), [corpus extension](extension.md), [corpus N](corpusN.md), [corpus M](corpusM.md), [ontology](ontology.md), [property](properties.md), [edge](edges.md), [vertices](vertices.md), [variable](variables.md), [scenario default](default.md), [translation](translation.md).

## Formato general

El corpus map es una sheet del *Mammut package*. Los nombres de las columnas del **corpus map** se encuentran en la fila #2, y a partir de allí cada fila contiene la información correspondiente a un corpus distinto.

Los nombres de las sheets que se listan en las columnas del corpus map pueden contener cualquier serie de caracteres (letras, números, códigos, etc.).
Ahora, para que el sistema pueda reconocer estas sheets listadas, los nombres de estas sheets deben ser escritos en el corpus map de la misma manera como fueron escritos en el proceso de identificación de los sheets del *Mammut package*. Además, al nombrar los sheets no se admiten guiones "-" o espacios en blanco " "; estos se pueden sustituir por guiones bajos " _ " , por ejemplo:  *'entry_point'* en lugar de *'entry point'*.

La estructura de la hoja de cálculo **corpus_map** es la siguiente:

 |  Campo  |  Descripción  | Obligatoriedad |
 |  ----   |  ----------   | -------------- |
 |  __id__  |  Identificación de un corpus expresada con un número entero comenzando desde 1. El id debe ser distinto para cada corpus listado en el corpus map. | Obligatorio. |
 |  __main_sheet__  |  Columna en la que se agrega el nombre de la sheet en la que está contenido el [corpus](corpus.md). | Obligatorio.  |
 |  __extension_sheet__  |  Columna en la que se agrega el nombre de la sheet en la que está contenido el [corpus extension](extension). | Opcional. |
 |  __variable_sheet__  |  Columna en la que se agrega el nombre de la sheet que contiene los datos de las variables de un **corpus M**. | Opcional para corpus M. |
 |  __corpus_type__  |  Identifica el tipo de corpus. Para un corpus tipo Natural, esta columna se llena con una 'N' escrita en mayúscula, mientras que para un corpus tipo Mammut, se llena con una 'M'. | Obligatorio.  |
 |  __regional_setting__  |  Especifíca el idioma principal (idioma en el que está escrito el corpus original, sin traducir) del corpus. En esta columna se usan los códigos “es” (para un corpus en español) o “en” (para un corpus en inglés) según sea el caso. | Obligatorio.  |
 |  __annotable__  |  Esta columna se llena con una equis "x" solo para los corpus que se desee anotar. | Opcional.  |
 |  __ontology_instances__  |  Columna en la que se agrega el nombre de la sheet en la que está contenido el [vértice](vertices.md) **entry_point** de la ontology de un **corpus M**. | Obligatorio para corpus M. |
 |  __ontology_vertices__  |  Columna en la que se agrega el nombre de la sheet en la que está contenida la información de los vertices de la [ontology](ontology.md) de un **corpus M**. | Obligatorio para corpus M.  |
 |  __ontology_edges__  |  Columna en la que se agrega el nombre de la sheet en la que está contenida la información de los edges de la [ontology](ontology.md) de un **corpus M**. | Obligatorio para corpus M. |
 |  __ontology_properties__  |  Columna en la que se agrega el nombre de la sheet en la que está contenida la información de las properties de la [ontology](ontology.md) de un **corpus M**. | Obligatorio para corpus M.  |
 |  __scenario_defaults__  |  Columna en la que se agrega el nombre de la sheet que contiene la configuración de los **scenario_defaults** de un **corpus M**. | Opcional para corpus M. |
 |  __knowledge_translations__  |  Columna en la que se agrega el nombre de la sheet que contiene las [translations](translation.md) de las instances del **knowledge** de un **corpus M**. | Opcional para corpus M. |
 |  __hidden__  |  Esta columna se llena con una equis "x" solo para los corpus que se desee ocultar. | Opcional. |

## Ejemplo

| id | main_sheet | extension_sheet | variables_sheet | corpus_type | regional_settings | configuration_json | annotable | ontology_instances | ontology_vertices | ontology_defaults | ontology_edges | ontology_properties | scenario_defaults | knowledge_translations | hidden |
| - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - |
| 1 | corpus_jollivanders | corpus_jollivanders_extension | variables | M | es |  | x | tienda | vertices |  | edges | properties | defaults | translations |  |
| 2 | jollivanders_corpus_N | jollivanders_corpus_N_extension |  | N | es |  |  |  |  |  |  |  |  |  | x |
