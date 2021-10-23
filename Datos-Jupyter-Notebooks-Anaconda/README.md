<h1>Entorno de Trabajo para Ciencia de Datos con Jupyter Notebooks y Anaconda</h1>

<h3>Jesús Vélez Santiago</h3>

<h1>Tabla de Contenido</h1>

- [1. Introducción a las notebooks](#1-introducción-a-las-notebooks)
  - [¿En qué lugares programar para ciencia de datos?](#en-qué-lugares-programar-para-ciencia-de-datos)
      - [Notebooks Vs Scripts](#notebooks-vs-scripts)
    - [Notebooks vs. Scripts](#notebooks-vs-scripts-1)
  - [Google Colab: primeros pasos](#google-colab-primeros-pasos)
  - [Google Colab: ciencia de datos](#google-colab-ciencia-de-datos)
  - [Utilizar Deepnote](#utilizar-deepnote)
- [2. Configuración de VSCode](#2-configuración-de-vscode)
  - [Instalar VSCode](#instalar-vscode)
  - [Instalar WSL: usa Linux dentro de Windows](#instalar-wsl-usa-linux-dentro-de-windows)
  - [Agregar extensiones para VSCode](#agregar-extensiones-para-vscode)
  - [Uso de VSCode notebooks](#uso-de-vscode-notebooks)
- [3. Entorno de desarrollo con Anaconda](#3-entorno-de-desarrollo-con-anaconda)
  - [¿Qué son los ambientes virtuales?](#qué-son-los-ambientes-virtuales)
  - [Instalar Conda a través de la terminal](#instalar-conda-a-través-de-la-terminal)
  - [Conda: crear y actualizar ambientes](#conda-crear-y-actualizar-ambientes)
  - [Conda: abrir VSCode Notebooks con tu ambiente creado](#conda-abrir-vscode-notebooks-con-tu-ambiente-creado)
  - [Conda: eliminar ambientes y librerías](#conda-eliminar-ambientes-y-librerías)
  - [Conda: comandos avanzados](#conda-comandos-avanzados)
  - [Acelerar la creación de ambientes virtuales con Mamba](#acelerar-la-creación-de-ambientes-virtuales-con-mamba)
  - [Bonus: divide y vencerás](#bonus-divide-y-vencerás)
- [4. ¿Qué sigue con estas herramientas?](#4-qué-sigue-con-estas-herramientas)
  - [Cómo seguir tu camino en ciencia de datos](#cómo-seguir-tu-camino-en-ciencia-de-datos)

# 1. Introducción a las notebooks

## ¿En qué lugares programar para ciencia de datos?

Existen muchas plataformas para trabajar en Data Science, se recomiendo usar algún Sistema Operativo basado en UNIX usando Linux, MacOS o WSL en Windows, en editores estan VSCode, PyCharm, Deepnote, Google Colab, y el que usaremos Jupyter, todo basado en Notebooks que te permiten ir ejecutando trozos de código, en el cual puedes escribir pocas lineas de código probarlas, asegurarse de que estén bien y seguir adelante con otro trozo, allí también se pueden añadir código, ecuaciones, gráficas, texto enriquecido, etc.

[DataScience.pdf](https://drive.google.com/file/d/1X4pLS115QHX9svkk9_Y6YQPjlvbMfz4I/view?usp=sharing//)

#### Notebooks Vs Scripts

Ambos son útiles, aunque los Scripts son mas directos, los Notebooks te permiten ver lo que haces, a medida de que lo haces, en estos puedes encargarte de experimentar y hacer el prototipado de tu script y finalmente pasarlo a un Script cuando ya este listo y estés seguro de que todo funciona como es esperado.

**Razones para estudiar ciencia de datos…**

1. Si te gusta la tecnología, la programación y los números.
2. Si quieres domar un campo que se puede aplicar en casi cualquier entorno de la vida práctica.
3. Si te gusta resolver problemas y entender situaciones.
4. Si consideras que los datos son el petróleo del siglo 21.
5. Si quieres pertenecer a un sector con alta demanda laboral y una aspiración salarial gratificante.

### Notebooks vs. Scripts

Ambos son útiles, en entornos y momentos específicos.

En la etapa de diseño y prototipado es conveniente utilizar Jupyter Notebook, también se puede emplear como informe y presentación de datos.

En un entorno de producción generalmente se utilizan scripts ya que son más flexibles para escalar los proyectos (reproducible), generar procesos automáticos y hacer deploy.

Los siguientes escenarios son tomados de una publicación que pretende justificar porqué podría ser una buena idea el uso de scripts:

> 1. If you want to run 20 big models in parallel, will you open 20 notebooks?
> 2. Suppose you are willing to open 20 notebooks, how will you configure the hyperparameters? Go to each notebook and find related cells?
> 3. Suppose you manually configure 20 notebooks, how will you analyze the results? Go to each notebook?
> 4. Suppose you can handle 20 notebooks for the first 3 steps, what if you have a great idea but you need to experiment with 200 sets of hyperparameters, are you willing to repeat steps 1–3?
> 5. Suppose you find a bug in the original notebook and need to rerun everything, are you willing to repeat steps 1–3?

> If you answer YES to all, then this article is NOT for you, bye and have a good day 😊

[![img](https://www.google.com/s2/favicons?domain=https://jupyter.org/favicon.ico)Project Jupyter | Home](https://jupyter.org/)

## Google Colab: primeros pasos

- Es una herramienta basada en la nube que te permite trabajar en notebooks, y se guardan en tu cuenta de Google Drive 😃.

- **Nube vs local**: Ambas son útiles, pero se diferencian en la configuración de entornos, ya que en la nube ya están precargadas, y de local tienes que configurarlo manualmente. También es diferente el tiempo de ejecución y la escalabilidad: la nube tiene más poder porque puedes rentarlo!. 💸

- **Google Colab**: Servicio en la nube basado en Jupyter Notebooks, no requiere configuración y tiene un trabajo a nivel de archivo (el notebook es la base). Tiene uso de gratuito de GPUs y TPUs para correr modelos grandes. ☁️

- Puedes acceder a Google Colab desde tu drive o desde el navegador.

- Para aprender **Markdown**.

  [Markdown Guide](https://www.markdownguide.org/)

- Las variables son persistentes (se conservan) entre celdas de código!. 🔥

- Para llamar a la **línea de comandos**, debemos usar primero un signo de admiración `!` y luego un comando válido, por ejemplo `!pwd` o `!pip install session-info`.

[![img](https://www.google.com/s2/favicons?domain=https://colab.research.google.com/notebooks//img/favicon.ico?vrz=colab-20210831-060048-RC01_394015668)Google Colab](https://colab.research.google.com/notebooks/)

[![img](https://www.google.com/s2/favicons?domain=https://www.markdownguide.org//favicon.ico)Markdown Guide](https://www.markdownguide.org/)

[![img](https://www.google.com/s2/favicons?domain=https://static.platzi.com/media/favicons/platzi_favicon.png)LaTeX - A document preparation system](https://www.latex-project.org/)

## Google Colab: ciencia de datos

Puedes cargar archivos a tu notebook desde tu computadora, pero se borrarán una vez cierres tu notebook. También puedes vincular tu google drive para que tome los archivos desde ahí y de esta forma conservarlos.

Colab está enfocado a trabajar con Python (también puede usar otros lenguajes) y ya trae librerías de ciencia de datos precargadas como:

- matplotlib: Generación de gráficos a partir de listas o arrays.
- numpy: Cómputo científico para la manipulación de vectores.
- pandas: Manipulación y análisis de datos de tablas y series temporales.
- scipy: Herramientas y algoritmos matemáticos.
- seaborn: Visualización de datos estadísticos.

Colab también tiene fragmentos de código (parecido a la herramienta para insertar funciones de Excel) que te facilita la programación.
Con ctrl + shift +p abres la paleta de comandos, si escribes shortcuts o atajos de teclado te mostrará una lista de todos los atajos que puedes ejecutar en Colab.

[![img](https://www.google.com/s2/favicons?domain=https://colab.research.google.com/notebooks//img/favicon.ico?vrz=colab-20210831-060048-RC01_394015668)Google Colab](https://colab.research.google.com/notebooks/)

[![img](https://www.google.com/s2/favicons?domain=https://ssl.gstatic.com/images/branding/product/1x/drive_2020q4_32dp.png)introduccion_colab.ipynb - Google Drive](https://drive.google.com/file/d/1ZNrGJdIHb0mvnwkNbdyaoV4uIzYBuRmJ/view?usp=sharing)

## Utilizar Deepnote

Dejo un [enlace](https://deepnote.com/sign-in?token=e46e565c94d0) para que reciban 20 horas de maquina Pro (16GB of RAM, 4vCPUs).
También los invito a que compartan su propio código para que todos reciban horas extra por cada platzinauta que se una.
Lo pueden encontrar dando clic en su perfil (esquina superior derecha), seleccionando **settings** y luego la sección **refer a friend**.

- Deepnote es un servicio en la nube basado en Jupyter Notebooks. No requiere configuración y tiene un trabajo a nivel de **proyecto**. Tiene colaboración en tiempo real, integración con múltiples Apps y tiene acceso a una terminal o línea de comandos integrada 😎.
- Tiene también variables de entorno y permite publicar proyectos (para construir portafolio). 🎉
- Podemos correr y agregar lo mismo que en Colab, pero además podemos subir archivos que se quedan siempre en el proyecto.
- Permite previsualizar los archivos CSV de manera muy bonita 😄.
- Parte de lo poderoso de Deepnote es que podemos integrar muchas cosas 🔥.
- No solo podemos agregar celdas de código y de texto, si no que en la opción de *Bloque* vienen muchos más tipos, como input, chart, dataframe sql, etc 🤯. Puede crear gráficas de manera automática sin código!
- Para acceder a los atajos de teclado usamos *Ctrl + i*.
- También es importante resaltar que tenemos una terminal integrada 🤖.

[![img](https://www.google.com/s2/favicons?domain=https://deepnote.com//static/apple-touch-icon.png)Deepnote - Data science notebook for teams](https://deepnote.com/)

[![img](https://www.google.com/s2/favicons?domain=https://deepnote.com/@jvelezmagic/Introduccion-a-Deepnote-_OWPZMb8RSq-lAu_7PoQiQ/static/apple-touch-icon.png)Introducción a Deepnote | Deepnote](https://deepnote.com/@jvelezmagic/Introduccion-a-Deepnote-_OWPZMb8RSq-lAu_7PoQiQ)

# 2. Configuración de VSCode

## Instalar VSCode

- Editores de código: Enfocados a multiples lenguajes. Se pueden potencial con extensiones o plugins. Por lo general son gratuitos. Mejor este 😄. Tenemos Pycharm VSCode, Atom, etc.
- IDE (entornos de desarrollo integrado): Enfocado a un solo lenguaje y seguimiento a un solo proyecto. Por lo general son de pago 💸

[Temas a su editor](https://vscodethemes.com/)

[![img](https://www.google.com/s2/favicons?domain=https://code.visualstudio.com/download/favicon.ico)Download Visual Studio Code - Mac, Linux, Windows](https://code.visualstudio.com/download)

## Instalar WSL: usa Linux dentro de Windows

Hola, estamos a punto de instalar **WSL (Windows Subsystem for Linux)**, una de las herramientas más poderosas que, como científica o científico de datos, usarás en tu día a día si utilizas Windows 10 o posterior.

Si utilizas Linux de forma nativa o macOS como tu sistema operativo puedes saltarte esta clase. Pero si utilizas Windows 10 es momento de que sigas cada uno de los siguientes puntos.

## 1. Instalar WSL y Ubuntu 20.04

**WSL** es la base con la que haremos que alguna distribución de Linux pueda correr dentro de nuestra computadora con Windows 10.

Una vez que se tenga instalada esta herramienta podrás instalar una gran variedad de distribuciones de Linux como Ubuntu o Debian. Para nuestro caso instalaremos **Ubuntu 20.04**, pero puedes escoger alguna otra por la que tengas preferencia y ya sepas utilizar.

Para instalar estas dos herramientas toma las siguientes 3 clases del **Curso de Prework: Configuración de Entorno de Desarrollo en Windows**:

1. [¿Qué es Windows Subsystem for Linux?](https://platzi.com/clases/2042-prework-windows/32465-que-es-windows-subsystem-for-linux/)
2. [Instalación de Windows Subsystem for Linux](https://platzi.com/clases/2042-prework-windows/32489-instalacion-de-windows-subsystem-for-linux/)
3. [Configuración de Ubuntu en WSL](https://platzi.com/clases/2042-prework-windows/32934-configuracion-de-ubuntu-en-wsl/)

Sigue paso a paso las instrucciones de estas clases para que tengas con éxito la instalación de WSL y Ubuntu en tu computadora.

De igual forma te comparto la [documentación oficial de Microsoft](https://docs.microsoft.com/es-mx/windows/wsl/install-win10) de este proceso y te invito a que dejes en los comentarios cualquier duda o inconveniente con el que te hayas topado al instalarlas para que podamos apoyarte.

## 2. Probar versión de Python 3

Al instalar Ubuntu tendremos una instalación de Python 3 disponible para utilizar. Probemos esta instalación:

1. Abre Windows Terminal y dentro de las opciones escoge Ubuntu 20.04 que acabas de instalar.
   ![Seleccionar_ubuntu.png](https://static.platzi.com/media/user_upload/seleccionar_ubuntu-f906bb64-b3b9-40ea-877e-df3a8dbd4e18.jpg)
2. Dentro de la terminal con Ubuntu 20.04 escribe el siguiente comando:

```bash
python3 --version
```

![Python_version.png](https://static.platzi.com/media/user_upload/python_version-08b8ac15-c6a6-4f7a-a950-8765df191257.jpg)
Como puedes observar en la imagen, esto te imprimirá en pantalla que cuentas con una versión de Python 3 lista para su uso.

## 3. Instalar pip3

Ahora es momento de instalar pip3, el manejador de paquetes y librerías más utilizado de Python. Con esta herramienta podrás instalar librerías de terceros como Pandas o Numpy que usarás en tu día a día en ciencia de datos.

1. Escribe en tu terminal el siguiente comando para instalar pip3:

```bash
sudo apt-get -y install python3-pip
```

![install_pip3.png](https://static.platzi.com/media/user_upload/install_pip3-1af35218-ea77-477e-93d1-8e357722c37f.jpg)

1. Prueba la instalación de pip3 una vez que haya terminado todo el proceso con el comando:

```bash
pip3 --version
```

![probar_pip.png](https://static.platzi.com/media/user_upload/probar_pip-4faeca1b-8a87-4928-9a3f-1e6975817cdd.jpg)

Muy bien, con esto ya tienes instalado pip3 en tu terminal con Ubuntu 20.04.

## 4. Abrir VSCode desde WSL

Ahora que tienes tu sistema de Linux en Windows, Visual Studio Code lo abrirás de una forma un tanto distinta para que toda librería o configuración que instales en ese sistema funcione.

1. Busca VSCode desde tu buscador de Windows y ábrelo dando clic en su ícono:
   ![buscar_vscode.png](https://static.platzi.com/media/user_upload/buscar_vscode-106bb0e3-291f-49b9-b7d1-353277404fac.jpg)
2. Una vez abierto VSCode ve al panel izquierdo y da clic en el ícono de extensiones:

![extensiones.png](https://static.platzi.com/media/user_upload/extensiones-07c59cae-12a6-49e0-b4d7-b18b96ab41ae.jpg)

1. Busca en el menú izquierdo la extensión **[Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)** e instálala con el botón azul install:
   ![instalar_RemoteWSL.png](https://static.platzi.com/media/user_upload/instalar_RemoteWSL-451a06b1-8b0e-431e-9c39-5ddaee5dd565.jpg)
2. Escribe el siguiente comando desde tu terminal para abrir VSCode en WSL:

```bash
code .
```

![VSCode_WSL.png](https://static.platzi.com/media/user_upload/VSCode_WSL-468a3ca0-c148-4f73-8177-e1e68479e947.jpg)

Este comando abrirá una versión de VSCode que correrá desde WSL. Esto puedes comprobarlo porque en la parte inferior izquierda de tu editor verás un recuadro verde que indica que estás en WSL y qué versión de Linux utilizas:

![WSL_version.png](https://static.platzi.com/media/user_upload/WSL_version-c7aae367-1402-4644-a3d4-55d893c505c1.jpg)

Excelente, ya está usando VSCode desde WSL. Recuerda que siempre debes abrir VSCode con el comando `code` desde tu terminal con WSL, de lo contrario te encontrarías utilizando la versión del editor de tu Windows y no la de tu versión de Linux.

------

¡Listo, hemos terminado la instalación de todas las herramientas para utilizar Linux desde tu computadora con Windows! Sé que ha sido un largo camino, pero créeme que ya tienes todas las bases para instalar cualquier herramienta adicional que deba utilizarse desde Linux en ciencia de datos.

Recuerda que si tuviste cualquier inconveniente o duda en el proceso de instalación puedes dejarla en los comentarios para que toda la comunidad de Platzi podamos apoyarte. 😄

Sin más, te veo en la siguiente clase. Profundizaremos en la instalación de extensiones para VSCode.

## Agregar extensiones para VSCode

**Agregar extensiones para VSCode.**

- Hay muchas extensiones para VSCode que hacen trabajar con datos más cómodo. ☁️
- Se pueden instalar todas las extensiones directamente desde VSCode 😄.
- Es recomendable activar la sincronización automática en la nube, para que siempre puedas tener tu entorno de trabajo en cualquier lugar. Lo puedes contectar con tu cuenta de GitHub 🤖
- Hay extension para Python que incluye muchas funcionalidades 🔥.
- MagicPython sirve mucho para darle formato a Python y que sea más legible.
- Las extensiones de Icon sirven para diferenciar tipos de archivos. 📁
- Rainbow Brackets sirve para cambiar los colores de los paréntesis y no tener errores 🌈.
- Remote Development te descarga múltiples extensiones que te sirven trabajar de manera remota. 🌎.

**Extensiones que yo utilizo:**

- Pythom y Jupyter
- Kite (para autocompletado)
- GitLens (para git)
- Indented Block Highlighting
- VScode Icons
- Rainbow CSV
- Remote Development

## Uso de VSCode notebooks

Python como:

- Python: Extencion de python.
- MagicPython: Colores para la identación de python
- MaterialIconTheme: Iconos para todos los archivos y documentos manejados
- Rainbow Brackets: Colores para la identificación de los parentesis o corchetes, inicio y cierre
- Remote Development: Conección remota

[![img](https://www.google.com/s2/favicons?domain=https://code.visualstudio.com/docs/datascience/jupyter-notebooks/favicon.ico)Working with Jupyter Notebooks in Visual Studio Code](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)

# 3. Entorno de desarrollo con Anaconda

## ¿Qué son los ambientes virtuales?

![img](https://i0.wp.com/dataaspirant.com/wp-content/uploads/2020/11/5-Anaconda-Vs-Python-virtual-env-comparison.png?w=750&ssl=1)

En local solo había trabajado scripts .py, para los cuales creaba ambientes virtuales con el comando venv.

A raíz del curso me surgió la duda de cuál era la diferencia o cuando usar conda o venv, encontré está infografía.

**¿Qué son los ambientes virtuales?**

- En la vida real, no vas a trabajar en un solo trabajo, si no en varios, y cada uno tendrá diferentes dependencias y requerimientos 🤔.
- Cuando se actualizan o se cambia la configuración de las dependencias de un ambiente que tiene varios proyectos asociados puede haber errores 🛑.
- Para poder separar proyectos, lo que hacemos es crear ambientes virtuales diferentes para cada proyecto. 🧠 Entonces la configuración y actualizaciones son para cada proyecto.
- **Ambiente virtual**: Proyecto que puede tener sus propias dependencias, independientemente de las dependencias que tengan los demás proyectos (Scott Robinson y la gente de Real Python).

En python existen herramientas como:

- .venv
- Pipenv
- conda

> **Ambiente Virtual**: *Proyecto que puede tener sus propias dependencias, independiente de las dependencias que tengan los demás proyectos*

[![img](https://www.google.com/s2/favicons?domain=https://www.anaconda.com/blog/understanding-conda-and-pip/assets/build/favicons/apple-touch-icon-5bbdb087c5.png)Anaconda | Understanding Conda and Pip](https://www.anaconda.com/blog/understanding-conda-and-pip)

## Instalar Conda a través de la terminal

Descargar `anaconda`

```sh
wget -O anaconda https://repo.anaconda.com/archive/Anaconda3-2021.05-Linux-x86_64.sh
```

**Instalar Conda a través de la terminal.**

- Conda: Programa diseñado para gestión de paquetes, dependencias y entorno para cualquier lenguaje: Python, R, Ruby, Lua, Scala, Java, JavaScript, etc. Además, es multiplataforma. 🖥️

- Para instalar conda debes instalar anaconda (versión completa, metapaquete de ciencia de datos) o miniconda (versión mínima). 🐍

- Para instalar conda:

  [Anaconda | Individual Edition](https://www.anaconda.com/products/individual)

  O bien hacer 

  ```sh
  wget -0 anaconda.sh https://repo.anaconda.com/archive/Anaconda3-2021.05-Linux-x86_64.sh
  ```

  Para instalar hacemos `bash anaconda.sh`. 🐍

- Para abrir notebooks usamos `jupyter-notebook`o bien `jupyterlab`. Los notebooks que creas ahí también los puedes abrir en VSCode.

- Para abrir VSCode en la carpeta en el que te encuentras, usas 

  ```bash
  code .
  ```

  >  **Anaconda**: *Gestión de paquetes, dependencias y entornos para cualquier lenguaje: Python, R, Ruby, Lua, Scala, Java, JavaScript, C/C++, FORTRAN y más*.

[![img](https://www.google.com/s2/favicons?domain=https://www.anaconda.com/products/individual/assets/build/favicons/apple-touch-icon-5bbdb087c5.png)Anaconda | Individual Edition](https://www.anaconda.com/products/individual)

[![img](https://www.google.com/s2/favicons?domain=https://docs.conda.io/projects/conda/en/latest/commands.html#conda-vs-pip-vs-virtualenv-commands_static/conda-logo.png)Command reference — conda 4.10.3.post29+a34aeac02 documentation](https://docs.conda.io/projects/conda/en/latest/commands.html#conda-vs-pip-vs-virtualenv-commands)

[![img](https://www.google.com/s2/favicons?domain=https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html../../_static/conda-logo.png)Installing on Linux — conda 4.10.3.post29+a34aeac02 documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)

[![img](https://www.google.com/s2/favicons?domain=https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html../../_static/conda-logo.png)Installation — conda 4.10.3.post29+a34aeac02 documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html)




## Conda: crear y actualizar ambientes


## Conda: abrir VSCode Notebooks con tu ambiente creado


## Conda: eliminar ambientes y librerías


## Conda: comandos avanzados


## Acelerar la creación de ambientes virtuales con Mamba


## Bonus: divide y vencerás

# 4. ¿Qué sigue con estas herramientas?


## Cómo seguir tu camino en ciencia de datos
