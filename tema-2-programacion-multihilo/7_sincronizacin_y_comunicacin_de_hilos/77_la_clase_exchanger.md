# 7.7. La clase Exchanger

 La clase `Exchanger`, del paquete `java.util.concurrent`, establece **un punto de sincronización donde se intercambian objetos entre dos hilos**. La clase `Exchanger<V>` es genérica, lo que significa que tendrás que especificar en `<V>` el tipo de objeto a compartir entre los hilos.

 Existen dos **métodos** definidos en esta clase:

* `exchange(V x).`
* `exchange(V x, long timeout, TimeUnit unit).`

 Ambos métodos `exchange()` permiten intercambiar objetos entre dos hilos. El hilo que desea obtener la información, esperará realizando una llamada al método `exchange()` hasta que el otro hilo sitúe la información utilizando el mismo método, o hasta que pase un periodo de tiempo establecido mediante el parámetro `timeout` .

 El **funcionamiento**, tal y como puedes apreciar en la imagen anterior, sería el siguiente:

* Dos hilos \(hiloA e hiloB\) intercambiarán objetos del mismo tipo, objetoA y objetoB.
* El hiloA invocará a `exchange(objetoA)` y el hiloB invocará a `exchange(objetoB)`.
* El hilo que procese su llamada a `exchange(objeto)` en primer lugar, se bloqueará y quedará a la espera de que lo haga el segundo. Cuando eso ocurra y se libere el bloqueo sobre ambos hilos, la salida del método `exchange(objetoA)` proporciona el objeto objetoB al hiloA, y la del método `exchange(objetoB`\) el objeto objetoA al hiloB.

 Te estarás preguntando ¿y **cuándo puede ser útil** `Exchanger`? Los intercambiadores se emplean típicamente cuando un hilo productor está rellenando una lista o búfer de datos, y otro hilo consumidor los está consumiendo.

 De esta forma cuando el consumidor empieza a tratar la lista de datos entregados por el productor, el productor ya está produciendo una nueva lista. Precisamente, esta es la principal utilidad de los intercambiadores: que la producción y el consumo de datos, puedan tener lugar concurrentemente.

 En el siguiente enlace encontrarás un ejemplo donde un hilo productor se encarga de rellenar una cadena de diez caracteres \(o sea, una lista de 10 caracteres\) mientras que un hilo consumidor la imprime.

