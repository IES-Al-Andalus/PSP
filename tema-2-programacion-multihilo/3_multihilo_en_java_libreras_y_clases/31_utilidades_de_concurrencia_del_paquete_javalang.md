# 3.1. Utilidades de concurrencia del paquete java.lang

 Dentro del **paquete** `java.lang` disponemos de una interfaz y las siguientes clases para trabajar con hilos:

* **Clase** `thread`. Es la clase responsable de producir hilos funcionales para otras clases y proporciona gran parte de los métodos utilizados para su gestión.
* **Interfaz** `Runnable`. Proporciona la capacidad de añadir la funcionalidad de hilo a una clase simplemente implementando la interfaz, en lugar de derivándola de la clase `thread`.
* **Clase** `ThreadDeath`. Es una clase de error, deriva de la clase Error, y proporciona medios para manejar y notificar errores.
* **Clase** `ThreadGroup`. Esta clase se utiliza para manejar un grupo de hilos de modo conjunto, de manera que se pueda controlar su ejecución de forma eficiente.
* **Clase** `Object`. Esta clase no es estrictamente de apoyo a los hilos, pero proporciona unos cuantos métodos cruciales dentro de la arquitectura multihilo de Java. Estos métodos son `wait()`, `notify()` y `notifyAll()`.

En el siguiente enlace tienes una **tabla resumida de la clase** `thread`, en español, que incluye los métodos más comunes para gestionar y controlar hilos.

[Tabla resumida de la clase thread.](http://dhw.umh.es/alex-bia/teaching/PC/material/metodos-clase-thread.htm)

