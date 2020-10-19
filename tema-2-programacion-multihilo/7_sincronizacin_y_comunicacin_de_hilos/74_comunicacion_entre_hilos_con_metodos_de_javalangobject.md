# 7.4. Comunicación entre hilos con métodos de java.lang.Object

 La comunicación entre hilos la podemos ver como un mecanismo de auto-sincronización, que consiste en logar que un hilo actúe solo cuando otro ha concluido cierta actividad \(y viceversa\).

 Java soporta **comunicación entre hilos** mediante los siguientes métodos de la clase `java.lang.Object`.

* `wait()`. Detiene el hilo \(pasa a "no ejecutable"\), el cual no se reanudará hasta que otro hilo notifique que ha ocurrido lo esperado.
* `wait(long tiempo)`. Como el caso anterior, solo que ahora el hilo también puede reanudarse \(pasar a "ejecutable·\) si ha concluido el tiempo pasado como parámetro.
* `notify()`. Notifica a uno de los hilos puestos en espera para el mismo objeto, que ya puede continuar.
* `notifyAll()`. Notifica a todos los hilos puestos en espera para el mismo objeto que ya pueden continuar.

 La llamada a estos métodos se realiza dentro de bloques `synchronized`.

¿**Cómo funcionan realmente estos métodos**? En el siguiente documento tienes la explicación de cómo funcionan estos métodos y un ejemplo de su uso.

Dos **problemas clásicos** que permiten ilustrar la necesidad de sincronizar y comunicar hilos son:

* El problema del **Productor-Consumidor**. Del que has visto un ejemplo anteriormente y que permite modelar situaciones en las que se divide el trabajo entre los hilos. Modela el acceso simultáneo de varios hilos a una estructura de datos u otro recurso, de manera que unos hilos producen y almacenan los datos en el recurso y otros hilos \(consumidores\) se encargan de eliminar y procesar esos datos.
* El problema de los **Lectores-Escritores**. Permite modelar el acceso simultáneo de varios hilos a una base de datos, fichero u otro recurso, unos queriendo leer y otros escribir o modificar los datos.

En el siguiente recurso tienes el ejemplo del problema de los lectores-escritores, resuelto mediante los métodos wait\(\) y notify\(\) vistos anteriormente.

[https://github.com/jmfdiazAL/PSP-Tema-2/tree/master/7.4.1%20PintorVendedor](https://github.com/jmfdiazAL/PSP-Tema-2/tree/master/7.4.1%20PintorVendedor)

