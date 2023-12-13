# Package data

## Definición

Lo que llamamos **package data** es el conjunto de herramientas que nos permiten construir el mammut package.

Conceptos relacionados: [package](package.md).

## Formato general

El **package data** se aloja en dos archivos:

* Archivo presentation (se instancia por medio de _Google Slide_ o _Powerpoint_).

* Archivo spreadsheet (se instancia por medio de _Google Spreadsheet_ o _Excel_).

Los formatos del package data son los siguientes:

| Package data | Descripción | Obligatoriedad |
| ------------ | ----------- | -------------- |
| Corpus | El **main_corpus** es el sheet que aloja los ejemplos de conversaciones del bot (Véase [corpus](corpus.md)). Este corpus se puede ampliar con un sheet que aloje el **corpus_extension**, donde se incluyen las paráfrasis de los events del corpus que tienen como source  a los usuarios del bot (Véase [corpus_extension](extension.md)).| Obligatorio. |
| Knowledge | Cada vertex del knowledge conforma un sheet distinto. (Véase [knowledge](ontology.md) y [vertex](vertices.md)). Este knowledge puede traducirse con un sheet que aloje las **knowledge translations** (Véase [translations](translation.md))| Obligatorio para corpus M. |
| Ontology | La ontology se describe en tres sheets: **ontology_vertices** (sheet donde se enlazan mediante relaciones semánticas los vertices y las properties que definen la ontology), **ontology_edges** (sheet donde se definen los edges utilizados para enlazar los elementos de la ontology) y **ontology_properties** (sheet donde se definen las properties usadas). (Véase [ontology](ontology.md)) | Obligatorio en el corpus M. |
| Configuración del bot | La configuración establece parámetros para el funcionamiento del bot como el **min. conversation duration**, el **conversation time out** y el **think status**. Estos datos se alojan en el document. (Véase [configuration](bot_configuration.md) | Obligatorio |
| Herramientas de comprensión del lenguaje | Estas herramientas se disponen en distintos sheets: **dictionary** (sheet donde se dispone el lexicón del bot), y **f-annotation** (sheets que guardan las anotaciones del corpus). | Opcional. |
