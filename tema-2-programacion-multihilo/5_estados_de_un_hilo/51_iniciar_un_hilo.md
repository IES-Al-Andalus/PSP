# 5.1. Iniciar un hilo

Cuando se crea un nuevo hilo o `thread` mediante el método `new()`, no implica que el hilo ya se pueda ejecutar.

Para que el hilo se pueda ejecutar, debe estar en el estado "Ejecutable", y para conseguir ese estado es necesario **iniciar o arrancar el hilo** mediante el método **start\(\)** de la clase `thread()`.

En los ejemplos anteriores, recuerda que teníamos el código `hilo1.start()`; que precisamente se encargaba de iniciar el hilo representado por el objeto `thread hilo1`.

En realidad el método `start()` **realiza las siguientes tareas**:

* Crea los recursos del sistema necesarios para ejecutar el hilo.
* Se encarga de **llamar a su método** `run()` **y lo ejecuta como un subproceso nuevo e independiente**.

Es por esto último que cuando se invoca a `start()` se suele decir que el hilo está "corriendo" \("running"\), pero recuerda que esto no significa que el hilo esté ejecutándose en todo momento, ya que **un hilo "Ejecutable" puede estar "Preparado" o "Ejecutándose"** según tenga o no asignado tiempo de procesamiento.

Algunas **consideraciones importantes** que debes tener en cuenta son las siguientes:

* Puedes invocar directamente al método `run()`, por ejemplo poner `hilo1.run()`; y se ejecutará el código asociado a `run()` dentro del hilo actual \(como cualquier otro método\), pero no comenzará un nuevo hilo como subproceso independiente.
* Una vez que se ha llamado al método `start()` de un hilo, no puedes volver a realizar otra llamada al mismo método. Si lo haces, obtendrás una excepción `IllegalThreadStateException`.
* El orden en el que inicies los hilos mediante `start()` no influye en el orden de ejecución de los mismos, lo que pone de manifiesto que **el orden de ejecución de los hilos es no-determinístico** \(no se conoce la secuencia en la que serán ejecutadas la instrucciones del programa\).

En el siguiente recurso didáctico puedes ver un programa que define dos hilos, construidos cada uno de ellos por los procedimientos vistos anteriormente. Cada hilo imprime una palabra 5 veces. Observa que si ejecutas varias veces el programa, el orden de ejecución de los hilos no es siempre el mismo y que no influye en absoluto el orden en el que se inician con `start()` \(el orden de ejecución de los hilos es no-determinístico\).

Nota. puede que tengas que aumentar el número de iteraciones \(número de palabras que imprime cada hilo\) para apreciar las observaciones indicadas anteriormente.

