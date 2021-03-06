# Flujo de trabajo para investigación reproducible

JC Castillo, updated: Marzo 2018

Recomendados: Tutoriales de Karl Broman: http://kbroman.org/pages/tutorials.html

El siguiente documento busca establecer un marco de referencia/sugerencia de prácticas para trabajos de investigación reproducibles orientados a publicación, que además sean abiertos y que favorezcan la colaboración durante el proceso de la investigación.

* El primer objetivo es lograr un flujo eficiente de trabajo, resolviendo a priori temas de orden técnico para así focalizarse principalmente en los contenidos del producto de investigación, que es lo más importante, y no perder demasiado tiempo en detalles de edición.

* El segundo objetivo se refiere a enmarcar el trabajo en una lógica de ciencia abierta (open science), que favorezca la colaboración y sinergia durante el proceso actual en lugar de la competitividad orientada a resultados en el mediano o largo plazo (como en el clásico proceso de publicación). Para más fundamentos relacionados a Open Science, recomiendo mirar: http://bit.ly/2shVxv4 . En esta línea, una plataforma que se sugiere usar es el Open Science Framework, OSF (https://osf.io, detalles más adelante).

Este marco abarca una serie de temas de edición y análisis compartido y abierto: estructura y contenido de carpetas, prácticas de edición, sugerencias de software y plataforma de ciencia abierta (OSF).

Importante: antes de comenzar el proyecto, acordar el tema central del trabajo, miembros del equipo y orden de autorías / definición de autor correspondiente, con respaldo por escrito al menos por mail. En relación a temas de coautorías, especialmente con alumnos, ver documento: http://bit.ly/2qOP9zh

Además por temas de difusión y registro de tema, escribir abstract (250 palabras), y publicar tempranamente vía OSF y/o proyectos researchgate.

## Sobre estructura de carpetas

La estructura de las carpetas debe favorecer tanto el flujo de la investigación como la reproducibilidad. De hecho, se puede pensar en estas dos por separado, ya que inicialmente lo que prima es un buen flujo, y al final la reproducibilidad ... pero de todas maneras mientras más se puedan acoplar ambas mejor, para no hacer el trabajo dos veces. Lo que sigue abajo está más orientado al flujo de trabajo, para afinar en términos de reproducibilidad se sugiere seguir los estándares de TIER: https://www.projecttier.org/


1- El autor principal genera carpeta con la siguiente estructura:

  - Nombre de carpeta general: abreviación sustantiva, minúsculas, separado por underlined sin. Ej: para paper sobre meritocracia, percepción y creencias: merit_percep_creen (este formato evita posibles errores posteriores de compilación debidos a encoding).
  - Dentro de esta carpeta, crear 2 subcarpetas, una para fines públicos y otra para trabajo interno, drafts, etc. La idea es que la pública sea luego abierta a otros investigadores durante el proceso de investigación.
  - Recomendaciones:
        - carpeta local/interna mismo nombre que la carpeta superior pero con prefijo "loc" (ej:loc_merit_percep_creen). Dentro de esta carpeta, seguir la estructura de subcarpetas (contenidos a detallar en siguiente punto):
            - data: bases de datos
            - analysis: código(s)
            - paper: texto
            - results: graficos, tablas
            - objects: generados por el código
            - bib: bibliografía
        - carpeta pública: prefijo pub, ajustar a estándares de reproducibilidad tipo TIER (ej: pdf)

## Contenidos carpeta local

- datos: contienen base(s) de datos original(es) (mantener nombre y nunca sobreescribir).
- codigo:
    - Dar título sustantivo e identificar autores
    - Comenzar estableciendo directorio de trabajo (setwd en R), uno para cada colaborador para utilizar respectivamente. Se puede comentar en la línea a quien pertenece (ej: setwd("media/dropbox/myprojectfolder") # JC
    - Idealmente, llamar los datos directamente desde la web para evitar tener que estar estableciendo distintos setwd en el código; esto se puede lograr si hay un repositorio abierto donde están los datos, o dirigir al link de la carpeta Dropbox, o mejor en GitHub. Igual aquí puede haber problemas si se liberan datos que requieren un consentimiento, por lo que los datos originales se pueden mejor guardar en la carpeta local.
    - Comentar exhaustivamente cada paso del análisis (Ej: #Recodificación de variables)
    - Ver plantilla código mínimo ejemplo (pendiente)

- paper: aquí va el documento con los contenidos, nombrar apellido, año, nombre resumido, versión. Ej: Atria_etal_2017_Viviendo_de_los_impuestos_v1. En caso que se considere necesario se puede agregar otro archivo con un log / bitácora referida a los cambios en las distintas versiones. Idealmente mantener en esta carpeta la última version, las otras se pueden mover a la interna a una carpeta versiones_anteriores (en caso de no trabajar con control de versiones).
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

ver: https://juancarloscastillo.github.io/citando-plano/

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
