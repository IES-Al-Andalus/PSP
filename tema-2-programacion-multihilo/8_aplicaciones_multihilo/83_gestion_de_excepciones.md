# 8.3. Gestión de excepciones

 ¿Cómo podemos gestionar la excepciones de una aplicación multihilo?

 Para gestionar las excepciones de una aplicación multihilo puedes utilizar el método uncaughtExceptionHandler\(\) de la clase thread, que permite definir un manejador de excepciones.

 Para **crear un manejador de excepciones** haremos lo siguiente:

* Crear una clase que implemente la interfaz `thread.UncaughtExceptionHandler`.
* Implementar el método `uncaughtException()`.

 Por ejemplo, podemos crear un manejador de excepciones que utilizarán todos los hilos de una misma aplicación de la siguiente forma:

* El manejador sólo mostrará qué hilo ha producido la excepción y la pila de llamadas de la excepción.

 En el siguiente enlace te facilitamos el proyecto completo. Se creará el anterior manejador de excepciones y se implementará un hilo que divide el número 100 por un número aleatorio comprendido entre 0 y 4, dando así la posibilidad de dividir por 0. Se crean e inician 5 hilos que harán uso del manejador.

