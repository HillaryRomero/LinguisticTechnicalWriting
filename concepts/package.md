# Mammut package (paquete mammut)

## Definición

Un **mammut package** (o simplemente "package") constituye una colección de datos que tienen toda la información necesaria para preparar un bot. Los datos del Mammut Package se estructuran en un "package data" y estos se introducen por medio de un archivo presentation y un archivo spreadsheet.

> **Nota:** tanto el archivo presentation como el spreadsheet se instancian por medio de _Google Slides_ y _Google Sheets_ respectivamente. Más información en el documento [package data](package_data.md).

Conceptos relacionados: [package data](package_data.md), [corpus](corpus), [ontology](ontology), [knowledge](ontology).

## Formato general

Las partes que conforman al package son las siguientes:

| Parte del package | Descripción | Obligatoriedad |
| ----------------- | ----------- | -------------- |
| Corpus | Un corpus es una colección de interacciones que llamamos [scenarios](scenario.md). Estos son conversaciones prototípicas entre diversos agentes (Véase [corpus](corpus.md)). | Obligatorio. |
| Knowledge | Un knowledge es el conjunto de valores o datos que un agente (bot) necesita saber para interactuar en un ambiente o situación (Véase [knowledge](ontology.md)). | Obligatorio para corpus M. |
| Ontology | Una ontology es la estructura semántica que permite organizar el knowledge (Véase [ontology](ontology.md)).  | Obligatorio para corpus M. |
| Configuración del bot | La configuración del bot es la vinculación de las diferentes partes de un *mammut package* a través de la presentation. Esta permite adjudicar parámetros para el funcionamiento del bot (Véase [configuration](bot_configuration.md). | Obligatorio. | 
| Herramientas de comprensión del lenguaje. | Estas son herramientas que ayudarán al bot a la comprensión e interpretación del lenguaje natural. | Opcional. |
