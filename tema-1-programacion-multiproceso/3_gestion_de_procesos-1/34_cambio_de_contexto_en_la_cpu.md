# 3.4. Cambio de contexto en la CPU

 Un **proceso es una unidad de trabajo completa.** El sistema operativo es el encargado de gestionar los procesos en ejecución de forma eficiente, intentando evitar que haya conflictos en el uso que hacen de los distintos recursos del sistema. Para realizar esta tarea de forma correcta, se asocia a cada proceso un conjunto de información \(PCB\) y de unos mecanismos de protección \(un espacio de direcciones de memoria del que no se puede salir y una prioridad de ejecuión\).

 Imaginemos que, en nuestro equipo, en un momento determinado, podemos estar escuchando música, editando un documento, al mismo tiempo, chateando con otras personas y navegando en Internet. En este caso, tendremos ejecutándose en el sistema cuatro aplicaciones distintas, que pueden ser: el reproductor multimedia VLC, el editor de textos writer de OpenOffice, el Messenger y el navegador Firefox. Todos ellos, ejecutados sin fallos y cada uno haciendo uso de sus datos.

 El sistema operativo \(el planificador\), al realizar el cambio una aplicación a otra, tiene que guardar el estado en el que se encuentra el microprocesador y cargar el estado en el que estaba el microprocesador cuando cortó la ejecución de otro proceso, para continuar con ese. Pero, ¿qué es el **estado de la CPU?**

 Una CPU, además de circuitos encargados de realizar las operaciones con los datos \(llamados circuitos operacionales\), tiene unas pequeños espacios de memoria \(llamados registros\), en los que se **almacenan temporalmente la información que, en cada instante, necesita la instrucción que esté procesando la CPU. El conjunto de registros de la CPU es su estado.**

 Entre los registros, destacamos el **Registro Contador de Programa y el puntero a la pila.**

* El **Contador de Programa**, en cada instante almacena la **dirección de la siguiente instrucción a ejecutar**. Recordemos, que cada instrucción a ejecutar, junto con los datos que necesite, es llevada desde la memoria principal a un registro de la CPU para que sea procesada; y, el resultado de la ejecución, dependiendo del caso, se vuelve a llevar a memoria \(a la dirección que ocupe la correspondiente variable\). Pues el Contador de Programa, apunta a la dirección de la siguiente instrucción que habrá que traer de la memoria, cuando se termine de procesar la instrucción en curso. Este Contador de Programa **nos permitirá continuar en cada proceso por la instrucción en dónde lo hubiéramos** dejado todo.
* El **Puntero a Pila**, en cada instante apunta a la parte superior de la pila del proceso en ejecución. En la pila de cada proceso es donde será almacenado el contexto de la CPU. Y de donde se recuperará cuando ese proceso vuelva a ejecutarse.

