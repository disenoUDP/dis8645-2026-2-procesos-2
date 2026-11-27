# sesion-15a

## apuntes sesión

Hoy seguimos revisando qué necesitamos para pasar nuestro proyecto a físico. le mandamos el readme a Claude para revisar la factibilidad y corregimos varias cosas a partir de sus comentarios. También actualizamos el excel con los bom para tener más claro qué debemos compra y que cositas ya tenemos

### cómo vamos a resolver el audio

Primero los profes nos dijeron que necesitábamos un dfplayer mini y que sacáramos el lector de microSD. después revisaron de nuevo nuestro bom y nos corrigieron esa indicación jj. al final seguimos con el lector de microsd por spi, porque necesitamos que la raspi pueda leer los audios y también escribir la grabación del cuidador en la misma tarjeta

La idea es guardar el mensaje como un archivo WAV y reproducir desde esa misma SD los cuentos, la música y el mensaje. dejamos anotado cambiar el ampli pam8403 por un max98357a, que recibe el audio digital por i2s y lo amplifica para el parlante

También nos recomendaron conectar la pantalla y la sd en buses spi distintos, uno en spi0 y el otro en spi1, para evitar que las actualizaciones de pantalla interrumpan la lectura del audio.

### micrófono y grabación

Decidimos que se podrá conectar un micrófono que tenga el botón de grabación ahí mismo, con ayuda de los professs, es una solución simple para que la persona cuidadora pueda acercarlo, mantener apretado para grabar y soltar para terminar. después puede desconectarlo y guardarlo, dejando los controles de grabación fuera del alcance de la infancia

Para grabar tenemos que tomar las muestras del micrófono a un ritmo fijo, entre 8 y 16 khz para voz. nos explicaron que hacerlo en un loop con pausas puede dejar tiempos distintos entre muestras y hacer que el audio suene mal.

Nos recomendaron revisar microphone-library-for-pico, que tiene ejemplos para micrófonos analógicos y pdm. quedó anotado usar el adc con fifo y dma para mantener la captura constante.

Además, al grabar necesitamos un búfer que guarde al menos medio segundo de audio y reservar el tamaño completo del archivo antes de empezar. por lo que entendí, así las pausas que puede tener la sd al escribir no interrumpen la grabación. esto todavía tenemos que probarlo con los componentes.

### materiales y carcasa

En el excel corregimos la lista de componentes y agregamos cosas que faltaban, como resistencias y la placa perforada para montar las conexiones. también cambiamos los pulsadores por botones tipo tecla, una idea de Carlo.

Para imprimir la carcasa definimos dos filamentos petg, uno café té y otro lila mate. los dejamos en la lista de compras junto con los componentes electrónicos para ordenar el presupuesto y ver bien qué necesitamos commprar.

## encargos

## lectura
pág 150–155

Última lectura!! alcancé a leer las primeras páginas del tercer capítulo y hasta aquí llegué con el libritoo. aprendí harto sobre formas de poesía que ni sabía que existían, pero estoy feliz de cerrar esta lectura porque, como ya he dicho no era mucho mi estilo y me estaba costando seguirla entre tantas cosas

Este capítulo empieza con el hipertexto, donde puedes pasar entre partes de un texto mediante enlaces y seguir distintos recorridos. también habla de la hipermedia, que suma imágenes y sonidos. aparecen antecedentes como los libros de "elige tu propia aventura" y programas que permitían conectar bloques de texto antes de que se hiciera común navegar por internet.

>“By ‘hypertext’ I mean non-sequential writing” (p. 150).
>
>“Readers explore a body of work that has been set before them on the computer.” (p. 154).
