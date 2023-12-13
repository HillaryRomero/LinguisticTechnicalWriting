# Conceptos básicos

## Índice

Letra|Conceptos
---|---
[C](#c)| [Channel](#channel); [Condition](#condition); [Corpus](#corpus); [Corpus extension](#corpus-extension); [Corpus N](#corpus-n); [Corpus M](#corpus-m); [Corpus map](#corpus-map)
[D](#d)| [Default](#default)
[E](#e)| [Edge](#edges); [Entry point](#entry-point); [Events](#events)
[I](#i)| [Instances](#instances); 
[K](#k)| [Knowledge](#knowledge)
[M](#m)| [Mammut markdown](#mammut-markdown); [Meta](#meta)
[O](#o)| [Ontology](#ontology)
[P](#p)| [Package](#package); [Path](#path); [Presentation](#presentation); [Properties](#properties)
[S](#s)| [Scenario](#scenario); [Scenario controller](#scenario-controller); [Scope](#scope); [Spreadsheet](#spreadsheet)
[T](#t)| [Translation](#translation)
[V](#v)| [Variables](#variables); [Vertices](#vertices)

## C

### Channel

Un [channel](channels.md) es el medio digital a través del cual un bot se comunica. Los channels pueden ser sitios web, aplicaciones móviles, clientes de mensajería instantánea, etc. Un bot desarrollado por Mammut se caracteriza por ser **multichannel**. De esta manera, los usuarios pueden comunicarse a través de cualquiera de las plataformas con las que esté integrado el bot.

### Condition

Una [condition](condition.md) es una expresión que, a través de una sentencia **conditional** (True o False), puede determinar si una instrucción es verdadera o falsa. Las conditions determinan un comportamiento del bot que es ejecutado o no dependiendo de su valor.

### Corpus

Un [corpus](corpus.md) es una colección de conversaciones prototípicas representativas de la comunicación entre diversos agentes (típicamente entre un bot y uno o más usuarios humanos). Los corpus pueden ser de dos tipos: [Corpus N](#corpus-n) y [Corpus M](#corpus-m).

#### Corpus extension

El [corpus extension](extension.md) (o simplemente "extension") complementa el corpus con paráfrasis de los [events](#events) que tienen como fuente a usuarios de un bot. El extension aloja las diferentes formas en las que cada uno de estos events puede ser expresado por diversos usuarios.

#### Corpus N

Un [corpus N](corpusN.md) es un tipo de corpus que se compone únicamente de [scenarios](#scenario) en lenguaje natural. El corpus N se almacena en un sheet del [Mammut package](#package).

#### Corpus M

El [corpus M](corpusM.md) es un tipo de corpus que se compone de scenarios en lenguaje natural y lenguaje formal para preparar a un bot de Mammut. Esta mezcla es posible gracias a [Mammut Markdown](#mammut_markdown). Los [scenarios](#scenario) se pueden conectar con una [ontology](#ontology) para ampliar la funcionalidad de los bots.

#### Corpus map

El [corpus map](corpus_map.md) es un mapa de cada uno de los [corpus](corpus.md) que pueden ser usados para preparar a un mismo bot. La función de este mapa es almacenar los nombres de las diferentes sheets de cada corpus y atribuir la función a dichas sheets para que el sistema pueda interpretar correctamente los datos que estas contienen.

## D

### Default

Un [default scenario](default.md) (o simplemente "default") es una configuración de una [instance](#instances) que se incorporará por defecto al **scope** de una conversación. Esta es una herramienta que ayuda al bot a solventar conversaciones en momentos donde el usuario no le provea la contextualización necesaria (véase [scope](#scope)).

## E

### Edges

El [edge](edges.md) es un elemento que crea un vínculo entre las entidades del [knowledge](#knowledge) ([vertices](#vertices) y [properties](#properties)). Estos tienen una semejanza funcional con los verbos, las conjunciones o las preposiciones en el lenguaje natural, ya que unen unos elementos a otros a través de relaciones semánticas.

### Entry point

Este tipo de [vertex](#vertices) representa para el sistema el punto de inicio de la [ontology](#ontology) y el [knowledge](#knowledge); los demás vertices están relacionados con él jerárquicamente. Generalmente, el entry point tiene la función de alojar la información referente a la empresa o institución de las cuales el bot tiene dominio.

### Events

Un [event](events.md) constituye cada uno de los mensajes emitidos consecutivamente por un agente en un [channel](#channel). Estos mensajes pueden ser texto, imagen o cualquier recurso que provea información. Así pues, cualquier pregunta o respuesta que forme parte de una conversación entre un usuario y un bot son ejemplos de **events**.

## I

### Instances

El [knowledge](#knowledge) del bot se ordena en nociones generales ([vertices](#vertices)) que engloban conceptos específicos (_instances_). Las [instances](instances.md) son unidades de información específica que forman parte de un núcleo de información o vertex. En este sentido, las instances funcionan como subtipos de una noción general.

## K

### Knowledge

El [knowledge](ontology.md) es una estructura de datos que contiene la información que un agente (bot) necesita saber para interactuar en un ambiente o situación. En el [package](#package), el [knowledge](#knowledge) está representado por el conjunto de valores (es decir, las [properties](#properties) e [instances](#instances)) contenidas en los [vertices](#vertices).

## M

### Mammut Markdown

El [mammut Markdown](mammut_markdown.md) es una extensión del lenguaje Markdown que facilita la creación de bots. Este puede usarse únicamente en los [corpus M](#corpus-m) de un [mammut package](#package). 

### Meta

El [meta](meta.md) es un [vertex](#vertices) singleton del [knowledge](#knowledge) por ende, tiene una sola [instance](#instances) (instancia) que siempre se identifica con el **id** _KM_1_. Este es el único vertex de la [ontology](#ontology) que no se aloja en un [spreadsheet](#spreadsheet) del [package](#package), si no que se encuentra en la [presentation](#presentation).

## O

### Ontology

La [ontology](ontology.md), es la estructura grafa establecida por las relaciones jerárquicas y semánticas entre [vertices](#vertices), [instances](#instances), [properties](#properties) y valores de un [knowledge](#knowledge). Consiste en un mecanismo que tiene la función de aumentar la eficiencia del léxico del bot a través de herramientas que faciliten la búsqueda de información en la memoria del bot (véase [variables](#variables), [path](#path)).

## P

### Package

Un [mammut package](package.md) (o simplemente "package") constituye una colección de datos que tienen toda la información necesaria para preparar un bot. Los datos del Mammut Package se estructuran en un "package data" y estos se introducen por medio de un archivo [presentation](#presentation) y un archivo [spreadsheet](#spreadsheet).

### Presentation

Parte del [package](#package) que se vincula con el [Spreadsheet](#spreadsheet).

### Path

Un [path](path.md) indica el recorrido que un bot debe seguir para buscar una información determinada en el [knowledge](#knowledge). El path debe incluir todos los [vertices](#vertices) y [edges](#edges) por los que el bot debe pasar para encontrar una [property](#properties) en un vertex dado, siguiendo el orden de la estructura de la [ontology](#ontology).

### Properties

Una [property](properties.md) es un atributo que puede adjudicarse a un [vertex](#vertices). Las properties sirven para describir aspectos, características o parámetros pertenecientes a los vertices que componen la [ontology](#ontology). Estas representan los atributos de los vertices ya que cumplen la misma función que tienen los 'adjetivos' en las lenguas, es decir, describir, especificar o complementar a los núcleos ([vertices](#vertices)).

## S

### Scenario

El [scenario](scenario.md) constituye un conjunto de interacciones que forman parte de un mismo contexto. Es decir, los scenarios son una sucesión de [events](#events) en secuencia cronológica; así pues, entendemos que dos o más events que funcionan juntos se organizan en un scenario. Cada nueva secuencia cronológica de events formará parte de un nuevo scenario.

### Scenario controller

El [scenario controller](scenery_controller.md) es una herramienta de Mammut donde se interpretan los [events](#events) que recibe un bot. El scenario controller maneja estructuras abstractas llamadas 'thoughts' (pensamientos), que aún no tienen el estatus de events.

### Scope

El [conversation scope](scope.md) (o simplemente "scope") constituye los datos que el bot obtiene de una conversación determinada y que le ayudan a manejarla . El scope permite al bot contextualizar una conversación en tiempo real, esta _contextualización_ se logra cuando un bot reconoce una [instance](#instances) que es parte de su [knowledge](#knowledge).

### Spreadsheet

Parte del [package](#package) que se vincula con la [presentation](#presentation).

## T

### Translations

Las [knowledge translations](translation.md) (o simplemente "translations") permiten la expresión de un dato en un idioma que ha sido escrito originalmente en otro. Esta es una herramienta que permite traducir las [instances](#instances) del [knowledge](#knowledge) de un bot, lo cual hace posible preparar al bot para que pueda comunicarse en diferentes idiomas utilizando una única [ontology](#ontology). 

## V

### Variables

Una [variable mammut](variables.md) (o simplemente "variable") es una herramienta de [Mammut markdown](#mammut-markdown) que construye una unidad susceptible a tomar distintos valores. Estas tienen la posibilidad de transformarse en texto, imágenes, videos u otros tipos de contenido. Las variables toman su valor directamente desde el [knowledge](#knowledge) de un bot.

### Vertices

La información del [knowledge](#knowledge) es ordenada en clases o núcleos por medio de los [vertices](vertices.md), estos son elementos centrales del knowledge y alrededor de ellos se construyen las relaciones de la [ontology](#ontology). La estructura interna de los vertices está constituida por subtipos de la clase o núcleo que represente el vertex (véase [instances](#instances)).


### Por definir

Corpus map
Aristas y relaciones
Framework
Eventos lambda
Log conversational
ReLog de issues
commit
pull request
commands
cluster
kubeflow
embedded
API
Data
simulator
widget
standard
Jupyter notebooks
quick start
Bot
compilation
IA
machine learning
deep learning
natural language processing NLP
feature
