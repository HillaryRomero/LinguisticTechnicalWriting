# Canal de Slack

Esta sección te guía hacia la integración de un Slack Workspace para tu bot. Para ello, tienes que integrar la plataforma de backend de Mammut en tu **aplicación Slack**.

Slack se puede integrar como un [canal de comunicación], lo que significa que puedes integrar tu bot para manejar las conversaciones en un espacio de trabajo de Slack. Incluso puedes integrar el bot para manejar tantos espacios de trabajo como quieras, especificando diferentes [bases de conocimiento] para cada uno de ellos.

![Mammut Slack conversation](img/mammut_slack_conversation.png)

El canal Slack también soporta la integración de Mammut para la [notificación y resolución de issues]. Puedes configurar tu bot para manejar problemas en las conversaciones en algún canal específico del espacio de trabajo. Esto significa que puedes monitorizar todos los reportes de issues del bot por medio de un canal específico de Slack.

![Mammut Slack conversation](img/mammut_slack_issues.png)

Puedes integrar la supervisión de issues con un espacio de trabajo de Slack. Allí recibirás todas las notificaciones de Issues que se produzcan en cualquier canal de conversación con el que esté integrado tu bot, ya sea desde Facebook Messenger, WhatsApp o en otro espacio de trabajo de Slack.

![Mammut Slack conversation](img/mammut_slack_issue_notifications.png)

Si no tienes una aplicación de Slack, o si ya tienes una aplicación y quieres integrarla con Mammut, lee la siguiente sección para obtener más información sobre cómo crear/configurar tu aplicación de Slack para la integración con Mammut.

+ [Crea tu aplicación Slack](#crea-tu-aplicación-slack).
+ [Integra tu Mammut a tu aplicación](#integra-tu-mammut-a-tu-aplicación)
+ [Integra la supervisión de Issues](#integra-la-supervisión-de-issues)
+ [Resumen](#resumen)

-----

## Crea tu aplicación Slack

1. Sigue la documentación de Slack para [crear tu aplicación](https://api.slack.com/authentication/basics#creating).

2. Dale los [scopes de permiso](https://api.slack.com/scopes) adecuados a tu aplicación. Los scopes requeridos son:
    - `users:write`
    - `users:read`
    - `chat:write`
    - `im:history`
    - `im:read`

3. Establece la URL de la API de Mammut de la implementación que estás usando para tu aplicación Slack en la [configuración de tus componentes interactivos](https://api.slack.com/interactivity/handling#setup). Debes proporcionar la URL de la API de Mammut y el endpoint de Slack en la ruta de la URL:

    `Mammut Slack API endpoint: https://api.mammut.io/channel/slack/events`

    > **Nota:** la URL de tu webhook puede ser diferente si estás usando un despliegue fuera de nuestra nube.
    > Utilízalo como tu _Request URL_ (URL de solicitud). Asegúrate de que tu aplicación tiene activada la **interactividad**.

4. Si estás integrando las notificaciones y la resolución de Slack para Issues, [activa la suscripción a eventos para tu aplicación](https://api.slack.com/events-api#prepare).  Y añade los tipos de eventos:
    - im_created
    - message.im

    Necesitas proporcionar la URL de la API de Mammut y el endpoint de Slack en la ruta de la URL:

    Webhook SMS de Mammut: https://api.mammut.io/channel/slack/actions
    >**Nota:** la URL de tu webhook puede ser diferente si estás usando un despliegue fuera de nuestra nube.

5. [Instala la aplicación en tu espacio de trabajo](https://api.slack.com/authentication/basics#installing).

### Guarda tus tokens de la aplicación Slack
Ahora que tu aplicación Slack ha sido creada e instalada en tu espacio de trabajo, tienes que tener a mano el **token de acceso a la aplicación** y el **token del bot** para tu aplicación.

Puedes encontrar tu **token de acceso a la aplicación** y tu **bot token** dentro de la página de administración de la aplicación. Búscalo en la barra lateral de **OAuth & Permissions**.

### Obtén tu ID de bot y tu ID de Workspace
También necesitas tener a mano el **ID de tu espacio de trabajo** y el **ID de usuario** de tu bot.

Para obtenerlos, puedes ir a Slack y usar el método `auth.test`. [Enlace al método de prueba](https://api.slack.com/methods/auth.test/test).

Utiliza tu bot token, y recibirá la información deseada en formato JSON:

```javascript
    {
        "ok": true,
        "url": "https:\/\/some.slack.com\/",
        "team": "Mammut's",
        "user": "your excelent app",
        "team_id": "ABCDEFJHI",
        "user_id": "JKLMNOPQR",
        "bot_id": "STUVWXYZ"
    }
```

Toma nota del campo `user_id`. Este será tu ID de usuario del bot dentro de Slack. Toma nota del campo `team_id`, este último es tu **ID de espacio de trabajo**.

-----

## Integra tu Mammut a tu aplicación

Ahora que tienes los tokens de acceso a la aplicación Slack, el id de tu espacio de trabajo y el id de tu bot, es hora de crear tu bot e integrarlo con tu aplicación Slack.

Crea el bot usando REST y añade los campos JSON:

| Nombre              | Tipo                          | Descripción                                                                    |
|-------------------|-------------------------------|--------------------------------------------------------------------------------|
| `user-type`       | String                        | Tu bot debe ser una "máquina".                                                  |
| `slack-bot-id`    | Array[Tuple2[String, String]] | Un conjunto de cadenas que contienen tuplas (pares) de `workspace id -> bot user id` |
| `slack-bot-token` | Array[Tuple2[String, String]] | Un conjunto de cadenas que contienen tuplas (pares) de `workspace id -> bot token`   |

>   + **URL**
>       
>       `/app:mammut-1/graph/user`
>
>   + **Method**
>   
>       `POST`
>
>   + **Request parameters**
>
>     - `Content-Type`: `application/json`   
>
>   + **Request Body example**
>
>       ```javascript
>           {
>               "user-type": "machine",
>               "slack-bot-id": [
>                   "(AHJOKPER, BBOTTRX13)"
>               ],
>               "slack-bot-token": [
>                   "(AHJOKPER, xoxb-438894080630-436957606977-H5i16jfuhjIsZ1zzZZqQiE9q)"
>               ]
>           }
>       ```
>       Note: Values in the example were randomnly generated.
>
>   + **Success response**
>       
>       + Code: 200
>       + **Body**: `TaskResult` response.


Si ya tienes un mammut bot creado, puedes añadir los campos mencionados anteriormente realizando una **actualización**:

| Nombre              | Tipo                          | Observación                                                                    |
|-------------------|-------------------------------|--------------------------------------------------------------------------------|
| `slack-bot-id`    | Array[Tuple2[String, String]] | Un conjunto de cadenas que contienen tuplas (pares) de `workspace id -> bot user id` |
| `slack-bot-token` | Array[Tuple2[String, String]] | Un conjunto de cadenas que contienen tuplas (pares) de `workspace id -> bot token`   |
| `mammutId`        | Long                          | El id de tu bot                                                  |
|                   |                               |                                                                                |

>   + **URL**
>       
>       /app:mammut-1/graph/user:[mammut-id]
>   
>   + **Query Parameters**
>
>     - `slack-bot-id`
>     - `slack-bot-token`
>
>   + **URL Parameters**
>
>     - `mammutId` 
>
>   + **METHOD**
>   
>       `POST`
>
>   + **Request Example**
>
>   - `URL`: /app:mammut-1/graph/user:125678
>   - `Query string`:
>       slack-bot-token=["(AHJOKPER, xoxb-438894080630-436957606977-H5i16jfuhjIsZ1zzZZqQiE9q)"]&slack-bot-id=["(AHJOKPER, BBOTTRX13)"]
>
>   + **Success response**
>   
>       + **Code**: 200

Tanto si has creado un nuevo bot, como si has actualizado uno existente, ahora está integrado en tu espacio de trabajo de Slack.

Soportará todas las conversaciones entrantes en tu aplicación Slack a través de mensajes directos.

Los bots de Mammut se pueden integrar con tantos espacios de trabajo como quieras!

-----

## Integra la Supervisión de Issues

Para activar las notificaciones de Mammut Issues y el soporte de resolución a través de un canal de Slack, tienes que seguir los siguientes pasos:

1. Crear los usuarios de tus supervisores.
    - Obtén tus identificaciones de usuario de Slack.
2. Crear el room de supervisores.

>**Nota:** continuación, encontrarás las instrucciones para llevar a cabo estos pasos. Si quieres estudiar en profundidad qué son los **usuarios supervisores** y las **salas de supervisores**, puedes consultar la [sección de documentación de asuntos oficiales].

### Crea tus usuarios supervisores

Tienes que crear usuarios supervisores capacitados (autorizados) para manejar los problemas a través de Slack. Para ello, es necesario que tengas los ID de usuario de tus supervisores de Slack.

#### Consigue tus identificaciones de usuario de Slack

Puedes encontrar el `ID de Slackp  de tus usuarios en la sección de información de su perfil de Slack.
Busca [esta referencia](https://help.workast.com/hc/en-us/articles/360027461274-How-to-find-a-Slack-user-ID) para orientarte.

Ahora, tienes que proceder a crear los usuarios de tus supervisores utilizando tu API de Mammut.

| Nombre            | Tipo                          | Observación                                                                      |
|-----------------|-------------------------------|----------------------------------------------------------------------------------|
| `slack-user-id` | Array[Tuple2[String, String]] | Un simple hilo que contiene una tupla (par) de  `workspace id -> slack user id` |
| `user-type`     | string                        | tipo 'supervisor'.                                                               |
| ...             |                               | Cualquier otro valor opcional para el tipo de `user`.                                        |
|                 |                               |                                                                                  |

>   + **URL**
>       
>       /app:mammut-1/graph/user
>
>   + **Method**
>   
>       `POST`
>
>   + **Request parameters**
>
>     - `Content-Type`: `application/json`   
>
>   + **Request example**
>
>       ```javascript
>           {
>               "user-type": "machine",
>               "slack-user-id": "(AHJOKPER,BBOTTRX13)",
>               "name": "John",
>               "lastname": "Doe"
>           }
>       ```
>
>   + **Success response**
>       
>       + **Code**: 200
>       + **Body**: `TaskResult` response.

#### Crea la sala de supervisión

Finalmente, crea tu room de supervisión de Slack. Este room dentro de Mammut está asociado con un canal en tu espacio de trabajo de Slack. Las notificaciones de problemas llegarán a ese canal. Los usuarios de los supervisores activarán acciones interactivas desde los botones proporcionados en las notificaciones.

Tu room será creado por [`Alex mammut`], quien está al tanto de enviar notificaciones cuando llegue el momento. Puedes saber cuál es el id de `Alex mammut` usando esta API request.

Para crear tu room de supervisores, realiza la solicitud a la [API de Mammut]:

| Nombre                  | Tipo   | Observación                                                                                                 |
|-----------------------|--------|-------------------------------------------------------------------------------------------------------------|
| `room-type`           | string | La sala de supervisores es del tipo 'group'                                                                     |
| `creation-date`       | string | valor 'now'.                                                                                                |
| `title`               | string |                                                                                                             |
| `has@user`            | object | Edge a los usuarios de sus supervisores. Uno para cada usuario.                                                          |
| `supervision-of@user` | object | Edge al bot que estás supervisando.                                                                                    |
| `selected-language`   | string | La cadena `local` del lenguaje de la sala. Las notificaciones llegarán con este idioma.                     |
| `slack-channel-id`    | string | Una cadena simple que contiene una tupla (par) de  (`workspace id` -> `slack channel id` \| `#slack channel name`) |
| `slack-user-token`    | string | Una cadena simple que contiene una tupla (par) de  (`workspace id` -> `slack OAuth Access Token`)                  |

>   + **URL**
>       
>       /app:mammut-1/graph/user:{MammutAlexId}/create:=room
>
>   + **Method**
>   
>       `POST`
>
>   + **Request parameters**
>
>     - `Content-Type`: `application/json`   
>
>   + **Request example**
>       ```javascript
>            {
>               "room-type": "group",
>               "creation-date": "now",
>               "title": "Supervisors slackbot",
>               "has@user": {"id": {supervisor_id}},
>               "has@user": {"id": {supervisor_id}},
>               "supervision-of@user": {"id": {bot_id}},
>               "selected-language": "en",
>               "slack-channel-id": "(T0LBYNNE5,#random)",
>               "slack-user-token": "(T0LBYNNE5,xoxp-20406770481-437434864739-669043739639-e59f765f14d5d3eb165dc9e569891255)"
>           }
>       ```
>
>   + **Success response**
>       
>       + **Code**: 200
>       + **Body**: `TaskResult` response.

Con esto, tienes un *room de supervisión* asociada a tu canal Slack, y tu equipo de supervisores podrá monitorear tu bot supervisado en esta sala.  Todos los issues que el bot encuentre, serán reportados en este canal, ya sea que ocurran dentro de Slack o cualquier otro medio.

-----

## Resumen

Has concluido tu integración del robot Mammut con tu aplicación Slack. Tu bot será capaz de manejar conversaciones con usuarios particulares a través de mensajes directos con tu Slack App. También puedes usar tu canal de Slack para monitorizar todos los problemas que tu mammut experimente en cualquier canal de comunicación.