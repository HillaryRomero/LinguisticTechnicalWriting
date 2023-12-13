# Bot configuration (Configuración del bot)

## Definición

El **bot configuration** (o simplemente "configuration") es la organización y vinculación de las diferentes partes de un *Mammut package*. La configuration requiere de la especificación de ciertos parámetros que son obligatorios para la creación de un bot.

Conceptos relacionados: [package](package.md).

## Formato general

Cada parámetro del **bot configuration** es un cuadro de texto en una _presentation_ del *Mammut package*. Su estructura es **campo** -> **valor**.

| Campo | Descripción | Obligatoriedad |
| ----- | ----------- | -------------- |
| **Min conversation duration** | Campo donde se expresa el tiempo mínimo que dura una conversación. Se llena con una unidad de tiempo. Actualmente se soportan milisegundos (millis), segundos (s), minutos (min), horas (h) y días (d/day) | Obligatorio |
| **Conversation time out** | Campo donde se expresa el tiempo de culminación de conversación. Luego de terminado el **min conversation time out**, empieza a correr el **conversation time out**, si luego de haberse cumplido este período no ha llegado un nuevo mensaje, se da por culminada la conversación. | Obligatorio |
| **Think status** | Campo donde se configura el mensaje programado para responder a los usuarios en aquellos momentos en los que el bot no cuente con la información necesaria para contestar a un event. | Obligatorio |
| **Sheet-id** | Campo donde se pone la identificación del Google Spreadsheet del package. Este campo contiene el número de identificación obtenido de la URL del spreadsheet que se desea vincular con la presentation. | Obligatorio |

## Ejemplo

|   |
|-- |
| Sheet-id -> 1FojxJ09c4LLSzhLK7j_MTySRz4cxnOyNGuOjVBfdoeE |
| Min conversation duration -> 1h |
| Conversation time out -> 30min |
| Think status -> Antes de responderte, necesito consultar la respuesta con otro miembro de la empresa la respuesta. |
