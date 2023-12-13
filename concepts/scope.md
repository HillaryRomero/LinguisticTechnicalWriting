# Scope (contexto de conversación)

## Definición

El **conversation scope** (o simplemente "scope") constituye los datos que el bot obtiene de una conversación determinada y que le ayudan a manejarla . El scope permite al bot contextualizar una conversación en tiempo real. Esta _contextualización_ se logra cuando un bot reconoce una instance que es parte de su **knowledge**.

> **Nota:** la forma como un bot reconoce las instances se da por medio de las transformaciones que hace de las [variables](variables.md) de los corpus M. La contextualización se logra con la adjudicación de un **valor** (una instance) del knowledge a una variable mammut.

El scope se vincula con los [paths](path.md) de la ontology del bot, esto significa que la primera información que necesita estar contextualizada es la del **entry point**. Para asegurar el manejo del contexto, las instances en el scope son guardadas en la memoria del bot durante el tiempo de una conversación.

> **Nota:** el 'tiempo de una conversación' es configurado en el package con las properties **conversationduration** y **conversationtimeout**.

Las instances en scope se usan para enriquecer la funcionalidad del bot y para proporcionar una experiencia más personalizada. De esta manera, el scope ayuda a que el bot pueda responder a sus usuarios, ya que el bot usa las instances contextualizadas para arrojar respuestas más precisas. Por lo tanto, el bot proveerá eficientemente a los usuarios la información que atiendan sus necesidades.

Cuando un usuario pregunta sobre un producto específico de una tienda, el scope permite que el bot proporcione información de dicho producto sin que el usuario tenga que repetir el nombre del mismo. Por otro lado, también evita que el bot confunda los productos disponibles en la tienda. Gracias al scope, el bot se mantendrá atento y consciente de lo que el usuario le está solicitando en los mensajes.

El scope no sólo se puede adquirir a través de los mensajes que envía el usuario, también es posible configurar algunas instances **por defecto**. Esto hace posible que el bot asuma el valor de algunas variables cuando los usuarios no provean datos. Esta configuración se hará en otro sheet del package llamada [default assumptions](default.md).

Conceptos relacionados: [variables](variables.md), [corpusM](corpusM.md), [knowledge](ontology.md), [defaults assumptions](default.md).

## ¿Cómo funciona?

El scope o contexto de un bot requiere seguir un orden específico. Este orden es el de algún **path** de su knowledge, siempre partiendo desde el **entry point**, y pasando por cada vertex hasta terminar en la property donde se encuentra la información que el bot requiere.

> **Nota:** las diversas rutas (paths) del knowledge se trazan considerando modelos de conversaciones, de manera que estas puedan servir al bot como representaciones eficientes de una conversación con un usuario.

El bot en una conversación va recorriendo paulatinamente un path de la ontology, eso le permite ir guardando el valor particular de los vertices que conoce.

## Ejemplo

El bot maneja el contexto de la conversación siguiendo los pasos que su programador le ha enseñado en la **ontology**. Por ejemplo, en una conversación donde se quiera saber el precio de un producto en una tienda, se debe tener contextualizado dos instances: 

tienda (vertex) -> nombre de la tienda (instance)
producto (vertex) -> nombre del producto  (instance)

De esta manera, será necesario que el usuario le diga al bot de qué tienda quiere la información (es posible que el bot maneje información sobre varias tiendas) y cómo se llama el producto del cual se solicita el precio. Veamos el siguiente escenario de un corpus:

| id | sub_id | scenario_type | event_message | hidden | field | lambda_condition | ui_event | action | source | regional_settings | complexity
| - | - | - | - | - | - | - | - | - | - | - | - |
2 | 1 | Conversation | ¿Cuál es el precio de la [`variable\|tienda.sell_several.varita.name`] en [`variable\|tienda.name`]? |  |  |  |  |  | Carla | es |
2 | 2 | Conversation | La [`variable\|tienda.sell_several.varita.name`] cuesta [`variable\|tienda.sell_several.varita.price`]. |  |  |  |  |  | Mammut | es |
2 | 3 | Conversation | La quiero. |  |  |  |  |  | Carla | es |
2 | 4 | Conversation | De inmediato. Dame tu correo electrónico para concluir tu petición. |  |  |  |  |  | Mammut | es |

En la primera pregunta "*¿Cuál es el precio de la [`variable\|tienda.sell_several.varita.name`] en [`variable\|tienda.name`]?*" el usuario está dando el valor de las dos variables que nos interesan: [`variable\|tienda.name`] y [`variable\|tienda.sell_several.varita.name`]. Esta información ahora está contextualizada y guardada en la memoria de corto plazo del bot. Por ello en la siguiente interacción del usuario "*La quiero*", no es necesario que este repita el nombre de la tienda o el nombre del producto.
