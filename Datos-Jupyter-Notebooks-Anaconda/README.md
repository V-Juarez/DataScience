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

[DataScience.pdf](https://drive.google.com/file/d/1X4pLS115QHX9svkk9_Y6YQPjlvbMfz4I/view?usp=sharing)

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



[Temas a su editor](https://vscodethemes.com/)


## Instalar WSL: usa Linux dentro de Windows


## Agregar extensiones para VSCode


## Uso de VSCode notebooks

# 3. Entorno de desarrollo con Anaconda


## ¿Qué son los ambientes virtuales?


## Instalar Conda a través de la terminal


## Conda: crear y actualizar ambientes


## Conda: abrir VSCode Notebooks con tu ambiente creado


## Conda: eliminar ambientes y librerías


## Conda: comandos avanzados


## Acelerar la creación de ambientes virtuales con Mamba


## Bonus: divide y vencerás

# 4. ¿Qué sigue con estas herramientas?


## Cómo seguir tu camino en ciencia de datos
