# 6.3.1. Monitores: Lecturas y escrituras bloqueantes en recursos compartidos

 Recordemos, el funcionamiento de los procesos cliente y suministrador podría ser el siguiente:

* Utilizan un recurso del sistema a modo de buffer compartido en el que, el suministrador introduce elementos; y, el cliente los extrae.
* Se sincronizarán utilizando una variable compartida que indica el número de elementos que contiene ese buffer compartido, cuyo tamaño máximo será N.
* El proceso suministrador, siempre comprueba antes de introducir un elemento, que esa variable tenga un valor menor que N. Al introducir un elemento incrementa en uno la variable compartida.
* El proceso cliente, extraerá un elemento del buffer y decrementará el valor de la variable; siempre que el valor de la variable indique que hay elementos que consumir.

 Los **mecanismos** de sincronismo que nos permiten el anterior funcionamiento entre procesos, son las **lecturas y escrituras bloqueantes en recursos compartidos del sistema** \(`streams`\). En el caso de java, disponemos de:

* Arquitectura java.io.
  * Implementación de **clientes:** Para sus clases derivadas de Reader como son InputStream, InputStreamReader, FileReader, …; los **métodos** read\(buffer\) y read\(buffer, desplazamiento, tamaño\).
  * Implementación de **suministradores:** Con sus análogos derivados de Writer; los **métodos** write\(info\) y write\(info, desplazamiento, tamaño\).
* Arquitectura java.nio \(disponible desde la versión 1.4 de Java\). Dentro de java.nio.channels:
  * Implementación de **clientes:** Sus clases `FileChannel` y `SocketChannel`; los **métodos** `read(buffer)` y `read(buffer, desplazamiento, tamaño)`.
  * Implementación de **suministradores**: Sus clases `FileChannel` y `SocketChannel`; los **métodos** `write(info)` y `write(info, desplazamiento, tamaño)`.

 Y recordemos que, como vimos en el apartado 5.1 Regiones críticas; tendremos que hacer uso del método `lock()` de `FileChannel`; **para implementar las secciones críticas de forma correcta. Tanto para suministradores como para clientes, cuando estemos utilizando un fichero como canal de comunicación entre ellos.**

 Si nos damos cuenta, hasta ahora sólo hemos hablado de un proceso Suministrador y un proceso cliente. El caso en el que **un suministrador tenga que dar servicio a más de un cliente**, aprenderemos a solucionarlo **utilizando hilos o threads, e implementando esquemas de cliente-servidor**, en las próximas unidades. No obstante, debemos tener claro, que el sincronismo cuando hay una información que genera un proceso \(o hilo\), y que recolecta otro proceso \(o hilo\) atenderá a las características que hemos descrito en estos aparatados.

Dependiendo de la aplicación que vayamos a implementar, podemos encontrarnos en la necesidad de que el cliente pueda realizar otras operaciones mientras que no haya datos disponibles. Es decir, que las **operaciones de lectura no sean bloqueantes**. Un ejemplo claro, es la programación de un cliente de [streaming](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Streaming%20%28DAM_PSP01%29) de música o vídeo. Ese cliente es un reproductor on-line que comienza a reproducir los datos que recibe, sin esperar a que se haya descargado completamente el archivo. Por supuesto, en estas situaciones tendremos que evaluar las variantes \(con respecto a las que hemos visto en esta unidad\) en el sincronismo de los procesos que se comunican.

Para conseguir lecturas no bloqueantes, haremos uso de la arquitectura `java.nio`, que implementa canales sobre sockets \(`SocketChannel`\). **Podremos configurar que las lecturas en un `SocketChannel` no sean bloqueantes por medio del método `configureBlocking(booleano)`, cuando booleano sea `false`.**

**Las lecturas en un canal creado sobre un fichero \(`FileSocket`\) siempre son bloqueantes.**

[Ampliar información sobre el método configureBlocking\(bool\) de la clase SocketChannel.](http://docs.oracle.com/javase/6/docs/api/java/nio/channels/spi/AbstractSelectableChannel.html#configureBlocking%28boolean%29)

## Pregunta

**Un proceso suministrador puede escribir datos en un recurso compartido al ritmo que desee, no tiene restricciones al generar datos.**

En los siguientes enlaces puedes consultar la implementación en Java de los problemas típicos de concurrencia en Java usando monitores. En el primer enlace puedes consultar un video sobre el problema de concurrencia Productor-Consumidor en Java:

Productor-Consumidor Concurrencia en Java

En el siguiente enlace puedes consultar un video sobre el problema de concurrencia Lectores-Escritores en Java con monitores:

Lectores-Escritores Concurrencia en Java

En el siguiente enlace puedes consultar un video sobre el problema de concurrencia de la Cena de los Filósofos en Java con monitores:

Cena de los Filósofos con monitores Concurrencia en Java

