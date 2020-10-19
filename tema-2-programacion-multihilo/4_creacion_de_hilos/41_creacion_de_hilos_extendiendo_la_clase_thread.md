# 4.1. Creación de hilos extendiendo la clase Thread

 Para **definir** y **crear un hilo extendiendo la clase** `thread`, haremos lo siguiente:

* Crear una nueva clase que herede de la clase `thread`.
* Redefinir en la nueva clase el método `run()` con el código asociado al hilo. Las sentencias que ejecutará el hilo.
* Crear un objeto de la nueva clase `thread`. Éste será realmente el hilo.

 Una vez creado el hilo, para ponerlo en marcha o iniciarlo:

* Invocar al método `start()` del objeto `thread` \(el hilo que hemos creado\).

 En el siguiente ejemplo puedes ver los pasos indicados anteriormente para la creación de un hilo extendiendo la clase `thread`. El hilo que se crea \(objeto `thread` hilo1\) imprime un mensaje de saludo. Para simplificar el ejemplo se ha incluido el método `main()` que inicia el programa en la propia clase `Saludo`.

