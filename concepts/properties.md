# Properties (Propiedades)

## Definición

Una **property** es un atributo que puede adjudicarse a las instances de un [vertex](vertices.md). Las properties sirven para describir aspectos, características o parámetros pertenecientes a los vertices que componen la **ontology**. Estas representan los atributos de los vertices ya que cumplen la misma función que tienen los 'adjetivos' en las lenguas, es decir, describir, especificar o complementar a los núcleos (vertices).

Una **property** es una característica asociada a las instances en un vertex. Cada property se relaciona con su respectivo vertex a través de un edge. Las properties **no** pueden relacionarse a otras properties por medio de edges. Las properties también pueden tener properties y agregar complejidad a la ontology.

> **Nota:** las **properties** sirven para describir aspectos, características o información de los vertices, de modo que son obligatorias. Las properties no son atributos fijos, si no que dependen de las necesidades de cada corpus. Por ejemplo, en el **entry point** de una ontology para una tienda, las properties podrían ser: **id**, **name**, **description**, **opening_hours**, **telephone**, **email**, etc.

Conceptos relacionados: [corpus](corpus.md), [vertex](vertices.md), [instance](instances.md), [edge](edges.md), [knowledge](ontology.md), [ontology](ontology.md).

## Formato general

Las properties se agregan de forma vertical (en la primera columna) en el sheet que funciona como entry point de la ontology. En el resto de los vertices particulares, estas se disponen de forma horizontal (en la segunda fila del sheet).

> **Nota:** es importante saber que las **properties** tienen restricciones en cuanto a los nombres que las definen. Estas solo deben tener como nombre un grupo nominal o adjetivo.

## Ejemplo

En los vertices particulares, las **properties** se verían así:

| id | hidden | name | description | price |
| ---- | ------ | ---- | ----------- | ----- |
| __V_1__ |     | varita de cedro | objeto mágico | 40 galeones

## Tipos de properties

Dependiendo de la naturaleza de la información en una **property**, podremos elegir uno de los siguientes tipos:

- **String** (cadena): en properties de este tipo podremos agregar una cadena de caracteres alfanuméricos. Por ejemplo, una property como: **name** o **description** sería de tipo String.

- **Boolean** (booleano): este tipo de property es un dato lógico o booleano que puede representar valores binarios, normalmente del tipo FALSE y TRUE. Por ejemplo, la property **hidden** sería un Boolean.

- **GAttachment** (GAdjunto): property que permite adjuntar un archivo como dato. Por ejemplo, la property **image** sería un GAttachment.

- **Integer**: tipo de property con números pertenecientes al conjunto de los enteros (sin decimales). Por ejemplo: '1'.

- **Long**: en properties de este tipo también podremos agregar números enteros, solo que más grandes que los anteriores (el valor que se puede guardar es mayor).

- **Double**: este tipo de property comprende números con decimales, punto flotantes, o pertenecientes al conjunto de los racionales. Por ejemplo: 1.2, 1.234, 1.23455.

- **LocalDate**: property que permite agregar la fecha en un formato simple, sin tiempo ni zona horaria, siguiendo el formato YYYY-MM-DD, como en: **2007-12-03**.

- **LocalTime**: en properties de este tipo podemos agregar la hora en un formato simple, sin fecha ni zona horaria, siguiendo el formato HH:MM:SS, como en: **10:15:33**.

- **ZonedDateTime**: es un tipo de property que comprende un texto que especifica una fecha, tiempo y zona horaria. En primer lugar tenemos la fecha con formato: YYYY-MM-DD. Luego tenemos el tiempo en formato militar (00-24hrs), seguida de la forma THH:MM:SS. Por último, se agrega la zona horaria UTC. Por ejemplo: **2007-12-03T10:15:30+01:00**. En este ejemplo, tenemos la fecha: 2007-12-03, luego la hora: T10:15:30, y por último la zona horaria +01:00.

- **StringToLower**: es una cadena de caracteres (texto) que se llevará a minúsculas. Por ejemplo, la property **id** sería de tipo StringToLower.

## Tipos de cardinality

La cardinality puede ser 'SINGLE', 'SET' o 'LIST'.

- **Single** (única): es una property que se puede describir en su totalidad con un solo valor. Por ejemplo, una property que represente la cuenta de Instagram de una tienda. En principio se asume que, con un valor dado, la property está completa: "@tiendita".

- **Set** (conjunto): es una property que debe ser descrita con distintos valores al mismo tiempo. Por ejemplo, los métodos de pago que acepta una institución. Esta property puede ser descrita por un conjunto de palabras: {efectivo, punto de venta, transferencia}.

- **List** (lista): es una property que se describe con una lista de valores que no deben ser distintos entre sí.

## Tipos de una property según la presencia de datos

Las properties pueden ser diseñadas para alojar lo que el bot sabe o para alojar lo que el bot quiere saber. Según sea el caso, las properties tendrán dos modalidades: **source properties** o **sink properties**. (véase[**sink**](sink.md)). 

> **Nota**: El tipo de property es definido individualmente para cada property en la columna "sink" de la [ontology](ontology.md).

### Source properties

Cuando el feature **sink** está inactivo, las **properties** presentan la modalidad **source**. En esta modalidad las properties son atributos que contienen datos precargados en el knowledge del bot. Es decir, _son datos que el bot sabe_, que forman parte de una instancia del knowledge y que el bot puede utilizar en una conversación para responder las preguntas de los usuarios.

### Sink properties

Por otro lado, cuando el feature está activo, las **properties** tienen la modalidad **sink**. Las **sink properties** son properties _vacías_ que pueden ser llenadas con datos suministrados por los usuarios durante una conversación. Las properties de tipo **sink** representan _lo que el bot quiere saber_; una vez el bot recoja esta información de la conversación, estos datos pueden ser utilizados dentro de la misma.

## Sheet "properties"

Las properties usadas en el package se declaran de forma vertical en un sheet llamado **properties**. (véase [ontology](ontology.md))

|     Campo     |  Descripción  |
| ------------- | ------------- |
| __name__          | Campo para agregar el enunciado o nombre de la property declarada. |
| __property_type__ | Campo que indica el tipo de información en la property. |
| __cardinality__   | Campo para indicar el número de valores necesarios para describir una property. |
| __properties__    | Campo para adjudicar properties a otras properties. |
| __range__         | Campo para limitar los posibles valores y tipos de una property. |
| __lambda_lexical_form__ | Campo para determinar otras formas de escribir una property en el Knowledge. |

### Ejemplo

En el sheet **properties** de un corpus, las properties se verán de esta manera:

| name | property type | cardinality | properties | range | lambda_lexical_form |
| ---- | ------------- | ----------- | ---------- | ----- | ------------------- |
| __id__ | StringToUpper | SINGLE |  |  |  |
| __name__ | String | SINGLE |  |  |  |
| __description__ | String | SINGLE |  |  |  |
| __opening_hours__ | OpeningHours | SINGLE |  |  |  |
| __contact__ | String | SINGLE |  |  |  |
