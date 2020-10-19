# 4.2. Creación de hilos mediante la interfaz Runnable

 Para **definir** y **crear hilos implementando la interfaz** `Runnable` seguiremos los siguientes pasos:

* Declarar una nueva clase que implemente a `Runnable`.
* Redefinir \(o sombrear\) en la nueva clase el método `run()` con el código asociado al hilo. Lo que queremos que haga el hilo.
* Crear un objeto de la nueva clase.
* Crear un objeto de la clase `thread` pasando como argumento al constructor, el objeto cuya clase tiene el método `run()`. Este será realmente el hilo.

 Una vez creado el hilo, para ponerlo en marcha o iniciarlo:

* Invocar al método `start()` del objeto `thread` \(el hilo que hemos creado\).

 El siguiente ejemplo muestra cómo crear un hilo implementado `Runnable`. El hilo que se crea \(objeto `thread hilo1`\) imprime un mensaje de saludo, como en el caso anterior.

## Pregunta

**Señala la opción correcta. Un hilo creado mediante `Runnable` es:**

### Respuestas

 [Opción 1]()

 No necesita ser un objeto `thread`.

 [Opción 2]()

 Es un objeto `thread` a cuyo constructor se le pasa como argumento un objeto de la clase que implementa `Runnable` y define un método `run()`.

 [Opción 4]()

 Es un objeto de la clase que implementa `Runnable` y en la que se define el método `run()`.

