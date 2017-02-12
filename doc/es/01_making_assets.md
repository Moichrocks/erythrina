### Erythrina

# Creando los assets

El primer tema que cubriré será la creación de los assets. Intentaré usar programas
libres u open source. Quizás este tutorial cubrirá menos sobre Godot pero son
importantes para cada juego. Llegaremos a Godot en apenas un rato.

Estaba pensando en usar GraphicsGale para dibujar. No es un mal programa, tiene
una versión gratuita, etc. Realmente no me gusta porque no encuentro intuitivo
algunas de las herramientas aunque para pixel art no se necesita demasiado y
encuentro que encaja bien con los sprites animados de Godot. Pero justo hace poco
encontré ASEprite. Es un editor pixelado listo para pixel art,
y además es open source.

![ASEprite](../img/aseprite.png)

Justo el abrirlo aparece toda la nostalgia. Al principio pensé que un entorno
pixelado sería molesto, pero una vez que lo usé me pareció cómodo. ASEprite
puede trabajar con capas, animaciones, exportar hojas de sprites, paletas, etc.
Y se ajusta bien con los sprite animados de Godot.

Para Windows estoy usando esta versión compilada - [Enlace al zip](http://www.mediafire.com/download/a2p5m91lndrfw4g/Aseprite1.0.2-dev.zip) -
porque los últimos binarios no son gratuitos, sin embargo el código se puede encontrar
aquí - [link to github](https://github.com/aseprite/aseprite/)

## Cosas que debemos conocer antes de dibujar

Antes de ir al desnudo acto de salpicar la pantalla de píxeles, hay algunas cosas
que debemos tener en cuenta. Aquí hay algunos trucos y reglas que pueden hacer el aspecto
de nuestro juego/diseño más profesional.

Un diseñador gráfico no tiene una varita mágica para hacer parecer todo maravilloso.
En lugar de eso, tienen un conjunto de reglas que, si las seguimos, podemos hacer
que parezca impresionante casi cualquier cosa. Y aquí tenemos un pequeño subconjunto
de algunas de las reglas que he aprendido hasta ahora. (Extension de responsabilidad: no soy diseñador,
soy un técnico en electrónica y un estudiante de Informática de modo que cada
una de estas palabras debe cogerse con cautela).

## Cosas de la escuela primaria

Primero de todo, no se puede ir allí y coger colores al azar.
¿Has tenido la experiencia de sentir cuando has hecho algo grande pero los colores
no se ven bien, y no sabes por qué?. Ahí justamente, es donde entra un poco de teoría de colores.
Necesitamos atravesar un poco de materia básica y aburrida.

Supongo que todos conocen los colores elementales y básicos.

![primary colors](../img/prim_colors.png)

Sí, no estamos usando el rojo, verde y azul como todas las pantallas CRT suelen hacer. Es verdad que RGB son los colores primarios para las pantallas y también que el rojo, amarillo y azul  son colores primarios también, ¿cuál es la diferencia?.

¿Qué ocurre cuando RGB son colores de luz y RYB son colores del pigmento?. La diferencia entre ellos es cómo y qué ocurre cuando se mezclan.
Con RGB cuando se mezclan todos los colores con máxima intensidad, el resultado es la luz blanca. Pero cuando se mezcla pintura roja, azul y amarilla se consigue un cubo de pintura marrón.

![mix paint](../img/color_mix.png)

La pintura roja, amarilla y azul son los colores básicos. Cuando se mezclan en parejas se obtienen los colores secundarios.

![mix paint](../img/basic_wheel.png)

Y si mezclamos un color primario con uno secundario, se crean los colores ternarios. Y después de eso, haciendo todas las combinaciones acabamos con una fantástica rueda de doce colores.

![mix paint](../img/basic_wheel_2.png)

Podríamos continuar pero 12 colores es todo lo que necesitamos. Realmente más colores transformarían todo en algo peor.

Pero, no podemos hacer todo el juego con sólo 12 colores. ¿O sí? ¿y dónde están el negro y el blanco?

Bueno, para los físicos, el negro no es un color pero el blando sí. Para los químicos el negro es un color pero el blanco no. Pero para la teoría de los colores básicos, ninguno de ellos son colores.
Son solamente variaciones de intensidad y luminancia de un color. Añaden sombra (al agregar negro) y tinte (al agregar blanco).

Girando la rueda de colores y cambiando el color, se está cambiando realmente el
matiz (HUE) del color. Cuando hacemos una rueda de 12 colores estamos restringiendo
los matices a un pequeño subconjunto. Sin embargo todavía pondemos teñir y sombrear
los colores para hacer muchas variaciones.

Cuando un color no tiene agregado ni blanco ni negro entonces está completamente saturado.
A menor saturación del color, más negro o blanco tiene. El neutro podría ser cualquier color con saturación 0.

## Cálido y fresco

Una cosa que es importante conocer y es obvia a primera vista es la diferencia entre
colores cálidos y frescos.

La rueda de color se divide en dos secciones.

![](../img/warm_cool.png)

Es útil saber lo que estamos dibujando y qué sentimentos estamos tratando de transmitir.
Por ejemplo, los colores cálidos generalmente son vivos y enérgicos, mientras que los
colores frescos son calmados y triste en ocasiones. Trata de evitar mezclar colores
cálidos (al menos en cantidades iguales) cuando trates de dibujar algo que deba sentirse fresco.

## Selección de colores

La cosa más importante que hay que saber sobre los colores es seleccionar los menos posibles.
Hay que seleccionar la mínima cantidad de colores que represente el dibujo. Cuantos menos
colores se cojan, más 'armónico' lucirá el dibujo. Si se exagera cogiendo un único
color todo será monocromático y no habrá lugar para colores incorrectos (Sólo habrá un color).

Para algunas cosas elegir de dos a cuatro colores es suficiente. El resto son sólo
variaciones agregando negro y blanco.

Aquí vemos algunos consejos para elegir colores y algunos casos de uso.

##### Colores complementarios

![](../img/complementary_colors.png)

Escoge un color base, luego coge el color opuesto en la rueda. Ese color será
el color complementario. Tendrmos el mayor contraste de tinte de modo que no se
recomienda usarlos con total saturación. Es muy útil para hacer cosas que destaquen.

##### Colores análogos

![](../img/analogous_colors.png)

Elige un color base, luego coge el color adyacente en la rueda. Esta combinación
generalemente es muy armoniosa y agradable. Carece de contraste y requiere del uso del negro y del blanco para añadir contraste. Incluso puedes combinarlos con el color complementario para algo que deba ser realmente destacado.

##### Separar los colores complementarios

![](../img/comp_analogous_colors.png)

Elige un color base y luego, en lugar de elegir el complementario, escoge el análogo del complementario. Obtendrás casi el mismo contraste que con el complementario pero será más fácil de usar y más comfortable al ojo.

##### Triángulo de colores

![](../img/triangle_colors.png)

Elige un color base y luego escoge otros dos haciendo un triángulo en la rueda de modo que los tres colores estén separados.

##### Rectángulo de colores

![](../img/square_colors.png)

Elegir dos pares de colores complementarios. El resultado será bastante versátil para tener un buen contraste y buena armonía. Tendrás colores cálidos como colores frescos. Esta combinación funciona mejor si uno de los colores es el dominante.

Todos estos colores podrían parecer muy simples y coloridos. Pero todo lo demás está en la variación. Cogiendo un conjunto de colores análogos podríamos hacer algo como esto.

![](../img/analogous_example.png)

Realmente no sé lo que es eso. Pero en este caso sólo hay tres colores, todo lo demás es
tinte y sombra. Y esos colores son el mismo (tienen el mismo tinte HUE) que uno de la derecha. Mi cabeza echó a volar la primera vez que lo ví.

Si se quiere dibujar almo más realista no estamos restringidos a un conjunto pequeño de colores, pero eso ayudará como diirectrices para otros colores. Siempre se puede usar una pintura base en los colores básicos y luego pintar más colores, sombreado e iluminación hasta que todo se vea hermoso.

## Ahora el dibujo

Ahora estamos preparados para ir y sumergirnos dentro de el dibujo. Sentémonos, encendamos el ordenador y abramos ASEprite. Lo primero que se ve es un entorno como el siguiente..

![](../img/aseprite1.png)

Es realemente un entorno encantador una vez que se usa. Vamos a crear un nuevo fichero en aseprite y nos encontraremos un menú como este.

![](../img/aseprite2.png)

Y quizás te preguntarás qué modo de color usar, o qué color de fondo. Para pixel art una gran herramienta (al menos para mí) es una paleta de color indexado. Estamos limitados a 256, sí, pero son más que suficientes. Lo bueno es que cuando queremos cambiar un color, o ajustar toda la paleta de colores para todos los sprites, sólo necesitaremos cambiar la paleta. No necesitaremos repintar nada (En teoría).

Esto nos lleva a hacer paletas compartidas entre todas las imágenes. O quizás usar diferentes paletas para diferentes propósitos (como una paleta para un entorno corriente, y otra para un entorno frío donde todos los colores están teñidos de azul). Y esa será la primera cosa que haré.

---

En realidad la creación de una paleta desde cero es un proceso continuo en el que se agregan los colores cuando se necesitan, y eso está bien. Pero aquí voy a hacer trampa y hacer (espero) una paleta completa de los doce colores de la rueda de color. A continuación, ajustar para dar todo el aspecto deseado y utilizarlo en todas partes por lo que los colores serán coherentes sobre todos los assets.


Voy a empezar por la limpieza de hormigas arrojando la paleta actual. Al hacer clic aquí en el botón Editar paleta.


![](img/aseprite3.png)


Debe abrir un editor de paleta como éste, donde puede editar cada color.


![](img/aseprite4.png)


Pero la edición de cada color uno por uno es un proceso tedioso, y si hace clic en el botón +, algunas herramientas útiles se abrirán.


![](img/aseprite5.png)


Para borrar todos los colores actuales fácilmente puede seleccionar un gran grupo de
colores. Manteniendo pulsada la tecla ctrl o shift, como con los archivos o todo lo similar, seleccionará un grupo de colores.


![](img/aseprite6.png)


A continuación, mueva todos los deslizadores RGB a 0 para que todos los colores sean negros. Ahora tenemos una paleta agradable y vacía y estamos listos para crear.

Utilizo los colores en el modo HSB (HSV o HSL, lo que sea). En realidad refleja bien la teoría básica del color.


![](img/aseprite7.png)


En primer lugar haré un gradiente gris. Dejaré la primera fila vacía si necesito algunos colores específicos en algún momento, hacer anotaciones de color y usar el primer color como el color transparente. Selecciono el 9no color y lo hago blanco. Luego seleccionaré el último color n24 (el último de la tercera fila si vives en un universo donde las filas tienen 8 colores, y si no lo puedes escalar) y hazlo negro (si ya no es negro).


![](img/aseprite8.png)


A continuación, seleccione sólo 16 colores de blanco a negro y, a continuación, pulse el botón ramp.


![](img/aseprite9.png)


Hará un gradiente agradable con pasos del mismo tamaño y hará nuestra escala de grises.


![](img/aseprite10.png)



Luego continuaremos con los colores. Esos son un poco más difíciles porque pueden lerp en más de una dimensión, y generalmente la saturación y el valor hacen un triángulo o un cuadrado. Lo haré sucio y simple eligiendo colores de esta manera.


![](img/triangle_red.png)


Así que sacrificaré colores saturados completos (no los usaré aquí por ahora) y algunos tonos grises (los extrañaré).


Procederé como con la escala de grises, pero haciendo dos ramps y retocando un poco.


Primero vamos a empezar con el rojo. Su tonalidad es de 0, así que creo que es un buen comienzo. Primero haré un gradiente de estos colores.

![](img/aseprite11.png)

![](img/aseprite12.png)

Y pasarán de un rojo oscuro casi negro a un rojo que no está saturado y no daña el ojo al mirar. Y el resultado es algo como esto.

![](img/aseprite13.png)

Después haremos la parte ligera del gradiente entre estos colores.

![](img/aseprite14.png)

![](img/aseprite15.png)

Y el resultado es algo como esto.

![](img/aseprite16.png)

![](img/aseprite17.png)

Entonces aqui hay un trabajo aburrido pero realmente rápido de hacer esto para el resto de los 12 colores. Es realmente sólo copiar y pegar simple como la selección de las dos filas de la gradiente rojo, y luego pegarlo once veces.

![](img/aseprite18.png)

![](img/aseprite19.png)

Y después diez veces más.

![](img/aseprite20.png)

A continuación, para cambiar el tono de un agujero de gradiente es fácil sólo como seleccionar el degradado y simplemente cambiar el matiz.

![](img/aseprite21.png)

Y otra vez haremos esto como diez veces más, y terminamos teniendo esto.

![](img/aseprite22.png)

Después de que voy a engañar a todos los tonos un poco moviendo algunos de ellos como 5 grados. Y con los colores blancos haré una fila que marca las columnas de los tonos que son probables utilizar como colores bajos. Y los otros serán más propensos a ser utilizados como sombra o colores claros. Todo el resultado esta en la carpeta de assets, también se exporta como una paleta .gpl.

![](img/aseprite23.png)

### Continua en la [Part 2](02_haciendo_assets.md)
