# 4. Creación de hilos

En Java, un **hilo** se representa mediante una instancia de la clase `java.lang.thread`. Este **objeto** `thread` se emplea para iniciar, detener o cancelar la ejecución del hilo de ejecución.

Los hilos o `threads` se pueden **implementar o definir de dos formas**:

* Extendiendo la clase `thread`.
* Mediante la interfaz `Runnable` .

En **ambos casos, se debe proporcionar una definición del método** `run()`, ya que este método es el que contiene el código que ejecutará el hilo, es decir, su comportamiento.

El procedimiento de construcción de un hilo es independiente de su uso, pues una vez creado se emplea de la misma forma. Entonces, ¿**cuando utilizar uno u otro procedimiento**?

* Extender la clase `thread` es el procedimiento más sencillo, pero no siempre es posible. Si la clase ya hereda de alguna otra clase padre, no será posible heredar también de la clase `thread` \(recuerda que Java no permite la herencia múltiple\), por lo que habrá que recurrir al otro procedimiento.
* Implementar `Runnable` siempre es posible, es el procedimiento más general y también el más flexible.

Por ejemplo, piensa en la programación de [applets_Applet_Componente de una aplicación Java que se ejecuta en el contexto de un navegador web.](), cualquiera de ellos tiene que heredar de la clase `java.applet.Applet`; y en consecuencia ya no puede heredar de `thread` si se quiere utilizar hilos. En este caso, no queda más remedio que crear los hilos implementando `Runnable`.

Cuando la Máquina Virtual Java \(JVM\) arranca la ejecución de un programa, ya hay un hilo ejecutándose, denominado hilo principal del programa, controlado por el método `main()`, que se ejecuta cuando comienza el programa y es el último hilo que termina su ejecución, ya que cuando este hilo finaliza, el programa termina.

El siguiente ejemplo muestra lo que te acabamos de comentar, siempre hay un hilo que ejecuta el método `main()`, y por defecto, este hilo se llama "main". Observa que para saber qué hilo se está ejecutando en un momento dado, el hilo en curso, utilizamos el método `currentThread()` y que obtenemos su nombre invocando al método `getName()`, ambos de la clase `thread`.

