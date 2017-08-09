# Flujo de trabajo para proyectos de publicación colaborativa

JC Castillo, Junio/Julio 2017.




El siguiente documento busca establecer un marco de referencia/sugerencia de prácticas para trabajos de investigación colaborativa orientados a publicación, que además sean abiertos y reproducibles durante el proceso de la investigación.

* El primer objetivo es lograr un flujo eficiente de trabajo, resolviendo a priori temas de orden técnico para así focalizarse principalmente en los contenidos del producto de investigación, que es lo más importante, y no perder demasiado tiempo en detalles de edición.
* El segundo objetivo se refiere a enmarcar el trabajo en una lógica de ciencia abierta (open science), que favorezca la colaboración y sinergia durante el proceso actual en lugar de la competitividad orientada a resultados en el mediano o largo plazo (como en el clásico proceso de publicación). Para más fundamentos relacionados a Open Science, recomiendo mirar: http://bit.ly/2shVxv4 . En esta línea, una plataforma que se sugiere usar es el Open Science Framework, OSF (https://osf.io, detalles más adelante).

Este marco abarca una serie de temas de edición y análisis compartido y abierto: estructura y contenido de carpetas, prácticas de edición, sugerencias de software y plataforma de ciencia abierta (OSF).

Importante: antes de comenzar el proyecto, acordar el tema central del trabajo, miembros del equipo y orden de autorías / definición de autor correspondiente, con respaldo por escrito al menos por mail. En relación a temas de coautorías, especialmente con alumnos, ver documento: http://bit.ly/2qOP9zh

Además por temas de difusión y registro de tema, escribir abstract (250 palabras), y publicar tempranamente vía OSF y/o proyectos researchgate.

## Estructura de carpetas compartidas

- El autor correspondiente genera carpeta compartida en Dropbox con la siguiente estructura:

    - Nombre de carpeta general: abreviación sustantiva, minúsculas, separado por underlined sin acento. Ej: para paper sobre meritocracia, percepción y creencias: merit_percep_creen
    - Dentro de esta carpeta, crear 2 subcarpetas, una para fines públicos y otra para trabajo interno, drafts, etc. La idea es que la pública sea luego abierta a otros investigadores durante el proceso de investigación. Recomendaciónes:
        - carpeta local/interna mismo nombre que la carpeta superior pero con prefijo "loc" (ej:loc_merit_percep_creen). Dentro de esta carpeta, seguir la estructura de subcarpetas (contenidos a detallar en siguiente punto):
            - data: bases de datos
            - analysis: código(s)
            - paper: texto
            - results: graficos, tablas
            - objects: generados por el código
            - bib: bibliografía
        - carpeta pública: prefijo pub, no necesariamente tiene que poseer subcarpetas, luego cuando la carpeta local pase a fase de draft, se sugiere crear copias sincronizadas de los dos archivos principales: código y texto (ej: pdf)

## Contenidos

- datos: contienen base(s) de datos original(es) (mantener nombre y nunca sobreescribir).
- codigo:
    - Dar título sustantivo e identificar autores
    - Comenzar estableciendo directorio de trabajo (setwd en R), uno para cada colaborador para utilizar respectivamente. Se puede comentar en la línea a quien pertenece (ej: setwd("media/dropbox/myprojectfolder") # JC
    - Idealmente, llamar los datos directamente desde la web para evitar tener que estar estableciendo distintos setwd en el código; esto se puede lograr si hay un repositorio abierto donde están los datos, o dirigir al link de la carpeta Dropbox, o mejor en GitHub. Igual aquí puede haber problemas si se liberan datos que requieren un consentimiento, por lo que los datos originales se pueden mejor guardar en la carpeta local.
    - Comentar exhaustivamente cada paso del análisis (Ej: #Recodificación de variables)
    - Ver plantilla código mínimo ejemplo (pendiente)
- Paper: aquí va el documento con los contenidos, nombrar apellido, año, nombre resumido, versión. Ej: Atria_etal_2017_Viviendo_de_los_impuestos_v1. En caso que se considere necesario se puede agregar otro archivo con un log / bitácora referida a los cambios en las distintas versiones. Idealmente mantener en esta carpeta la última version, las otras se pueden mover a la interna a una carpeta versiones_anteriores (en caso de no trabajar con control de versiones).
- Referencias: aquí se puede guardar el archivo que contiene las referencias (ej: bibtex, carpeta zotero ad-hoc).
- Results: la idea es que los resultados del análisis en forma de gráficos y tablas puedan ser grabados y luego llamados desde el código; este paso no es necesario en caso de incluir los resultados en el texto vía Knitr.

## Software

- Código de análisis : principalmente por carácter abierto, gratuito y capacidades de generación de tablas/gráficos reproducibles, se recomienda R. Una segunda opción es Stata, que tiene también buenas capacidades de análisis y reporte de resultados, muy buen software y documentación excelente. Pero es pagado, y por lo tanto en la lógica de ciencia abierta es más apropiado R (por el momento).
    - Interfaz de código: actualmente Rstudio ofrece una serie de ventajas para escritura académica con Rmarkdown y Knitr. Sin embargo, también recomiendo Atom por su flexibilidad y paquetes para trabajar en distintos entornos, y su link con git/github.

- Paper: El lenguaje recomendado, sobre todo cuando se trabaja con análisis de datos con R o Stata, es Markdown y/o Latex.
    - Tienen muchas ventajas, las principales para el trabajo académico son que a) permite que el autor se preocupe principalmente al contenido del texto, dejando que Markdown/Latex se encarguen del formato, y b) permite insertar de manera dinámica y automática resultados de análisis, así no hay que estar perdiendo tiempo formateando /reformateando manualmente tablas ni gráficos en caso de producirse cambios en los análisis.
    - La dificultad principal es que no mucha gente los utiliza en ciencias sociales, lo que puede dificultar la colaboración y lleva a que finalmente el formato por "defecto" sea Word, que implica mucho trabajo de formato.
    - Markdown parece mejor alternativa que Latex por su simpleza, formato minimalista y facilidad para convertir a otros formatos (latex, html, word, pdf). Por lo tanto, en principio sugiero comenzar escribiendo en **Markdown** y luego tal vez pasar a Latex en caso de favorecer la edición. La escritura en Markdown funciona muy bien en Rstudio, sobre todo en combinación con análisis. Si el foco es más la escritura que el análisis sugiero Atom y los paquetes language-markdown y markdown-preview-plus. Además, Atom tiene mejor soporte para vínculos con archivos de bibliografía (detalles más adelante).



## Referencias Bibliográficas

- Lógica general: poder citar referencias directamente desde Markdown/Latex. Esto se hace guardando las referencias en formato y archivo bibtex, en un archivo .bib
- Ya que almacenar manualmente las referencias en bib es muy poco eficiente, se recomienda realizar un vínculo con un software de administración y almacenamiento de referencias, en este caso Zotero.
- Exportar colección Zotero a .bib; alternativas
    - exportar manual a bibtex: crea archivo bib con referencias, seleccionadas o todas.
    - Mejor Alternativa: Better Bib Tex (BBT), extensión de Zotero, instalar siguiendo las instrucciones: https://github.com/retorquere/zotero-better-bibtex/wiki
    - Al instalar, luego en preferences aparece una pestaña nueva, dejar opciones por defecto (en principio), pero si agregar export subcollections en pestaña Export
    - Lo que hace por defecto es generar un archivo .bib que es espejo de la colección de Zotero, en la misma carpeta Zotero
    - Aquí, una opción es dar el link desde Markdown/Latex al archivo Zotero, pero en general es muy pesado y contiene todas las referencias, no el subgrupo que se utiliza en el paper
    - Por lo tanto, hacer lo siguiente:
        -  crear una colección/carpeta compartida de Zotero (asumiendo escenario de trabajo colaborativo) donde se copian las referencias que se utilizan en el paper. Esto es fácil en Zotero, solo se arrastran, y no hace que toda la información se duplique, es solo un link. Como es compartida, cualquier miembro del equipo puede modificar. Precaución: el nombre de esta carpeta sin espacios y sin acentos
        - El coordinador/primer autor exporta esta colección a la carpeta del proyecto colaborativo (eventualmente un dropbox) donde está el tex. Para ello, boton derecho sobre la carpeta, "export library", seleccionar *format Better Bibtex*, y muy importante: check box "keep updated", así cualquier cambio que se haga en la colección desde Zotero se reflejará en el .bib. Guardar en la carpeta donde se encuentra el archivo tex
        - Luego, revisar en la pestaña de BBT de preferencias, en automatic export, que la carpeta efectivamente está en el listado. Además, marcar la opción "on change", así apenas se actualice la librería de Zotero se va a actualizar el bib

- Luego para poder referenciar en tex:
    - En el preambulo (hay diferentes opciones de formato, pero para estilo clásico APA):
        - \usepackage{natbib} % for Bibtex
        - \bibliographystyle{apalike}   % ver por ej otros estilos en https://es.sharelatex.com/learn/Natbib_bibliography_styles
        - Y luego, donde se quiera la bibliografía, (usualmente, antes de \end(document)
        - \bibliography{micolección} % aquí va el nombre de la colección, cuidado con no darle nombre con espacios, y tampoco terminarla con .bib
        - Con esto, ya se puede comenzar a citar con las distintas opciones (ver https://gking.harvard.edu/files/natnotes2.pdf)
        - Para mayores detalles referentes a natbib y en general bibliographic management en Latex ver https://es.sharelatex.com/learn/Bibliography_management_with_natbib
    - Algunos issues con Latex: si se añade alguna cita a la carpeta Zotero, si bien esto es actualizado automáticamente en el bib, no necesariamente es reconocido al momento de citar. Por eso, se recomienda tener abierto el archivo .bib en el editor de tex en otra pestaña, y si la referencia no aparece al intentar citar compilar el bib, esto hace que queden disponibles para citar (lo que se ve en el .bbl, donde se encuentran las referencias citadas en el texto)
    - Por lo visto, las referencias en el .bbl se van sumando, y no se borran. Por lo tanto, puede pasar que se cite algo en alguna ocasión, pero si esa cita se decide borrar va a seguir de todas maneras apareciendo en la bibliografía final. Para ajustar esto, cuando se genere una versión más definitiva del documento, borrar el bbl y compilar el tex nuevamente.
    - Atención: si se quiere cambiar el estilo (\bibliographystyle{}), a veces no lo reconoce y se queda con el anterior o arroja error; la opción que me resulta es borrar los archivos aux y bbl, y luego compilar nuevamente.
    - También hay problemas cuando alguna entrada del archivo .bib no tiene el año, en este archivo aparecen como ???? y esto crea dificultades de compilación; arreglar en Zotero, sincronizar nuevamente y compilar.

## Roles / tareas

- Es posible identificar una serie de tareas a realizar para publicar un trabajo, que además se pueden asociar a distintos roles. Cuando es una sola autora/o en general es ella la que asume todas las tareas, pero en caso de trabajo colaborativo la idea es que las distintas integrantes puedan asumir también distintas tareas. Entre las principales
    - Primer autor: es quien lidera el trabajo y asigna roles y funciones, y tiene un rol central en proponer y/o afinar el "concepto" central del artículo, plantear su relevancia y las preguntas precisas que responde. Por lo mismo, asume un rol clave en la escritura principalmente de la introducción y las conclusiones, aún cuando también se involucra en el resto de las áreas del artículo. Esta definición puede ser un poco ambigüa, pero de todas maneras es mejor que la de "es quien más trabaja", ya que esto lleva a una discusión bastante bizantina. Por lo tanto, el primer autor es quien conduce al resto del equipo.
    - Autor correspondiente: usualmente también el primer autor, es quien lleva  la relación con el editor: envío, revise & resubmit, y también se preocupa de la selección de la revista donde se enviará el trabajo y de adaptar el artículo en esa dirección. Idealmente, quien asuma este rol debe tener algo de experiencia en este proceso
    - Revisión/actualización bibliográfica, para cada concepto y principalmente basada en hipótesis (sección de marco conceptual y empírico)
    - Documentación de análisis (sección métodos)
    - Análisis empírico (sección análisis)
-  Por supuesto, es posible que un colaborador asuma más de un rol, o se intercambien los roles en el proceso.

## Sobre Open Science Framework, https://osf.io

- Plataforma web orientada a hacer el proceso de investigación transparente y abierto, favoreciendo además la reproducibilidad, colaboración, feedback y la sinergia en el momento que el trabajo se realiza, sin tener que esperar hasta que esté publicado.
- Más ad-hoc a valores científicos, ver artículo  ["Normative dissonance in Science "](http://www.jstor.org/stable/10.1525/jer.2007.2.4.3?seq=1)
- Permite también una opción "privada" para compartir entre colaboradores seleccionados, que también luego se puede hacer pública
- También permite tener varios trabajos y grupos (llamados componentes) dentro de un proyecto mayor
- Tiene mucho sentido cuando existen varios proyectos/componentes paralelos, ya que permite a colaboradores de distintos proyectos poder conocer los avances de los demás, y también compartir/usar recursos comunes, como código, bibliografía, etc.
- Permite sincronización con Dropbox, por lo tanto si se sincroniza la carpeta pública a este sitio, todo eso va a quedar disponible a el resto de los colaboradores del proyecto y miembros en componentes paralelos.
- Y otras ventajas como registro de propiedad y referenciación (doi), wiki.
- Vinculo de carpeta pública con OSF (en desarrollo, pero en general es fácil con Dropbox, y también se puede con GitHub)

## Link con Git / Github para Control de Versiones (VCS) (en desarrollo)

## Socarxiv https://socopen.org/ (en desarrollo)


## Links varios:

- Check Authorea - git integration: https://www.authorea.com/
- revisar sitio y cursos de Kieran Healey, https://kieranhealy.org/
- about open source: https://kieranhealy.org/files/papers/oss-activity.pdf
