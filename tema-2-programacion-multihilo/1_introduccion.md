# 1. Introducción

Seguro que en más de una ocasión mientras te descargabas una imagen desde tu navegador web, seguías navegando por Internet e incluso iniciabas la descarga de un nuevo archivo, y todo esto ejecutándose el navegador como un único proceso, es decir, teniendo un único ejemplar del programa en ejecución.

Pues bien, ¿Cómo es capaz de hacer el navegador web varias tareas a la vez? Seguro que estarás pensando en la **programación concurrente**, y así es; pero un nuevo enfoque de la concurrencia, denominado "**programación multihilo**". Justo lo que vamos a estudiar en esta unidad.

Los programas realizan actividades o tareas, y para ello pueden seguir uno o más [flujos de ejecución_Flujo de ejecución_Es el camino que siguen las instrucciones de un programa para ejecutarse, desde un punto de inicio hasta su fin. Todo flujo tiene un comienzo, una secuencia y un final.](). Dependiendo del número de flujos de ejecución, podemos hablar de dos tipos de programas:

* **Programa de flujo único**. Es aquel que realiza las actividades o tareas que lleva a cabo una a continuación de la otra, de manera secuencial, lo que significa que cada una de ellas debe concluir por completo, antes de que pueda iniciarse la siguiente.
* **Programa de flujo múltiple**. Es aquel que coloca las actividades a realizar en diferentes flujos de ejecución, de manera que cada uno de ellos se inicia y termina por separado, pudiéndose ejecutar éstos de manera simultánea o concurrente.

La **programación multihilo** o multithreading consiste en desarrollar programas o aplicaciones de flujo múltiple. Cada uno de esos flujos de ejecución es un thread o **hilo**.

En el ejemplo anterior sobre el navegador web, un hilo se encargaría de la descarga de la imagen, otro de continuar navegando y otro de iniciar una nueva descarga. La utilidad de la programación multihilo resulta evidente en este tipo de aplicaciones. El navegador puede realizar "a la vez" estas tareas, por lo que no habrá que esperar a que finalice una descarga para comenzar otra o seguir navegando.

Cuando decimos "a la vez" recuerda que nos referimos a que las tareas se realizan concurrentemente, pues el que las tareas se ejecuten realmente en [paralelo _Paralelo_Las tareas se ejecutan realmente a la vez, una en cada procesador.]()dependerá del Sistema Operativo y del número de procesadores del [sistema_Sistema_Un ordenador con un único procesador, un ordenador con varios procesadores o una red de computadores distribuidos.]() donde se ejecute la aplicación. En realidad, esto es transparente para el programador y usuario, lo importante es la sensación real de que el programa realiza de forma simultánea diferentes tareas.

En el siguiente enlace pues ver un ejemplo muy intuitivo de lo que se puede conseguir mediante programas de flujo múltiple o multihilo, en concreto mediante `threads` en Java.

[Ejemplo de programa con varios hilos o flujos de ejecución.](http://formella.webs.uvigo.es/doc/cd04/node37.html)

