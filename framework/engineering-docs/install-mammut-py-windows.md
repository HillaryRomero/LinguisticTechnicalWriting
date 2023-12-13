# Instalación local de Mammut-Py en Windows

## Contenido (especie de outline)
1. Requisitos Previos (o instalaciones/configuraciones previas)
   1. Instalar VSCode
   2. Instalar/Actualizar Python (64 bits)
   3. Instalar Pip
2. Instalar Pyenv-win **Vínculo:  https://pip.pypa.io/en/stable/installing/**
   1. Establecer/Instalar Python (64bit) en el ambiente
      1.1 Ejecutar pip install pyenv-win --target %USERPROFILE%\.pyenv
      1.2 Crear variables de entorno en Windows: 
         - Ingresa al buscador de windows
         - Escribe 'edit' y selecciona la opción 'editar variables de entorno' para ingresar a las propiedades de sistema de Windows. 
         - Haz click en el botón 'variables de entrono'.
         - En el recuadro inferior titulado 'variables del sistema' haz click en la opción 'nueva' para crear una nueva variable.
         - Crea una nueva variable con los siguientes datos:
            Nombre de la variable: PYENV
            Valor de la variable: %USERPROFILE%\.pyenv\pyenv-win Finalmente haz click en 'aceptar'. 
         - En el recuadro superior titulado 'variables de ususario' haz click en el término 'path' y seguidamente haz click en 'editar'. 
         Nota importante: las rutas que crearás a continuación deberán estar ubicadas por encima de este path que puede estar o no en tu equipo: %USERPROFILE%\AppData\Local\Microsoft\WindowsApps
         - Crea nuevos paths de la siguiente manera: 
            Haz click en la opción 'nueva', escribe %PYENV%\bin y selecciona 'aceptar'. 
            Haz click una vez más en la opción 'nueva', escribe %PYENV%\shims y selecciona 'aceptar'.
         - Finalmente en el recuadro 'variables de entorno' haz click en 'aceptar' para que se pueda guardar de manera correcta la variable y sus paths. 
3. Instalar Poetry
   1. Crear el virtual environment con poetry
   2. Activar el ambiente
   3. Levantar Jupyter

# Pasos para levantar el ambiente en Windows
Parado en el proyecto en VSC:
1. Escribe en la terminal: cmd
2. Escribe poetry env info
3. Para activar el ambiente escribe: 
call \Users\hilla\AppData\Local\pypoetry\Cache\virtualenvs\mammut-py-ZiEgiZ3P-py3.8\Scripts\activate.bat  
4. Finalmente escribe: jupyter notebook


## Requisitos previos
# Pasos de Marco
•	Eliminar el python que se tenga en el sistema. 
•	Instalar una version 64Bits de python. La version es a gusto. 
•	Instalar pip usando ese python. **Vínculo:  https://pip.pypa.io/en/stable/installing/**
•	Instalar pyenv-win **Vínculo https://pypi.org/project/pyenv-win/**
•	Instalar en pyenv-win la misma version que instalaron mas arriba como python del sistema.
•	Usar pyenv para moverse a la version adecuada del proyecto. 
•	Instalar poetry.
Es crucial tener un unico python de 64bits en el sistema antes de instalar pyenv. Y que pyenv se active primero con esa misma version.


# Errores: 
[EnvCommandError]
Command ['C:\\Users\\Miguel\\AppData\\Local\\pypoetry\\Cache\\virtualenvs\\mammut-py-yEKRL5A1-py3.8\\Scripts\\pip.exe', 'install', '--no-deps', 'tf-sentencepiece==0.1.92'] errored with the following return code 1, and output:
Collecting tf-sentencepiece==0.1.92
  ERROR: Could not find a version that satisfies the requirement tf-sentencepiece==0.1.92 (from versions: 0.1.1, 0.1.2, 0.1.3)
ERROR: No matching distribution found for tf-sentencepiece==0.1.92
WARNING: You are using pip version 19.2.3, however version 20.2 is available.
You should consider upgrading via the 'python -m pip install --upgrade pip' command.

# Solución 
poetry remove tf-sentencepiece
poetry add tf-sentencepiece@0.1.3
poetry install
pip list (para verificar)


# Pasos de Edilmo
Corriendo MammutPy local
    
- Lo primero que les pido es que instalen VSCode al menos. Idealmente, deberian aprovechar de tener tanto VSCode como PyCharm instalados en sus maquinas, no es mas que descargar e instalar.

- Los siguientes pasos son independientes del IDE (VSCode o PyCharm). Los estare dando en VSCode porque es el que comento arriba como minimo (dado que es el mas ligero tanto para descargar como para correr). Esto es mas de lo que se necesita para usar MammutPy, es lo que se necesita para usar y desarrollar DENTRO de MammutPy.

- Abrir el proyecto en vscode: esto es tan simple como abrir el directorio raiz del proyecto.

- Abrir una consola DENTRO de VSCode: esto no es obligatorio pero si es mucho mas practico en este momento y mas adelante (cuando se configuren otras cosas del IDE) hay cosas que les funcionaran aqui y no en una consola cualquiera por las automatizaciones e integraciones que tiene esa consola con el resto del IDE (Integrated Development ENvironment - es el nombre que se le da a estas herramientas de desarrollo de software). Esta consola sera usada en todos los comandos siguientes de los pasos a continuacion.

- Revisar que version de python tienen por defecto en el sistema: para los linguistas, por simplicidad, les sugiero tener Python 3.8.3. Para chequear si tienen esto simplemente hacen: python --version si eso dice algo distinto a Python 3.8.3 cuadren con Marco o Juan para que les ayuden a instalar PyEnv en su sistema y poner por defecto este Python. Dejo eso por fuera aqui para que no se extienda demasiado.

- Instalar Nox y Poetry: una vez tengan la version correcta de Python que quieren usar para desarrollar con MammutPy, deben hacer dos instalaciones a nivel del sistema que son simples:
	
**pip install poetry**
**pip install nox**
**pip install black** es esto no lo usaremos ahorita. Para poder usarlo hay que configurar algo en el IDE. No es dificil pero no es el objetivo de estas instrucciones.
	
- Crear el virtual environment con poetry: esto es lo que permitira que tengan un ambiente aislado de Python donde se instalaran todas las librerias y cosas que MammutPy requiere para desarrollar. Solo deben correr lo siguiente:
	
**poetry install**
	
- Activar el virtual environment creado: activar significa hacer que esta consola que estas usando se mueva a usar el python y librerias (ambiente python general) que esta en ese virtual environment y asi no use y no afecte el de tu sistema operativo. Para lograr esto hay que hacer varios pasos:
	

		
**poetry env info** esto es para confirmar el ambiente que se creo con **poetry install** del paso anterior. De aqui lo importante es ver el nombre y la ruta en el sistema. 
AL final coloco un ejemplo de como luce el mio y asumire esos valores alli en los siguientes comandos. Ustedes los sustituyen por los suyos
**source /Users/edilmo/Library/Caches/pypoetry/virtualenvs/mammut-py-oqYg1Zxu-py3.6/bin/activate** esto activa el ambiente en la consola. Lo que esta en negrita es la ruta del ambiente en mi maquina que lo obtuve con el poetry env info del paso anterior.
	
	
- Levantar Jupyter: esto levanta el servidor de notebooks en sus maquinas. El deberia abrir un browser automaticamente. Si no lo hace, igual el imprime el URL alli en la consola y ustedes o le dan click o la copian y la pegan en un browser. EL comando es el siguiente: **jupyter notebook**

- Cuando quieran dejar de trabajar con el servidor, salven todos sus notebooks, cierrenlos, haganle stop en el UI a cada notebook si es posible, y por ultimo van a esta consola y presionan **Ctrl+c**. Eso matara el servidor.
Eso es todo!!! A partir de aqui solo tienen que asegurarse de tener el ambiente activo (paso source .../bin/activate) y luego ejecutar el comando de jupyter notebook.

- El source activate y el code formatting automatico usando VSCode (o PyCharm) requieren unas configuraciones del IDE que hacen todo mas facil. Eso junto con las diferencias para PyCharm, se dejan para otro momento para que no compliquen este proceso y puedan avanzar.


**Ejemplo:**
(mammut-py-oqYg1Zxu-py3.6) ➜  mammut-py git:(initial-ci) ✗ poetry env info                                                                               

Virtualenv
Python:         3.6.9
Implementation: CPython
Path:           /Users/edilmo/Library/Caches/pypoetry/virtualenvs/mammut-py-oqYg1Zxu-py3.6
Valid:          True


System
Platform: darwin
OS:       posix
Python:   /Users/edilmo/.pyenv/versions/3.6.9




