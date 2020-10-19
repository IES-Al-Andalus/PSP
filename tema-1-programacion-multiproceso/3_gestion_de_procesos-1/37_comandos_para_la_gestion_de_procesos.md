# 3.7. Comandos para la gestión de procesos

 Es cierto que podemos pensar que ya no necesitamos comandos. Y que podemos desterrar el intérprete de comandos, terminal o shell. Hay múltiples motivos por los que esto no es así:

* En el apartado anterior, hemos visto que necesitamos comandos para lanzar procesos en el sistema.
* Además de las llamadas al sistema, los comandos son una forma directa de pedirle al sistema operativo que realice tareas por nosotros.
* Construir correctamente los comandos, nos permitirá comunicarnos con el sistema operativo y poder utilizar los resultados de estos comandos en nuestras aplicaciones.
* En GNU/Linux, existen programas en modo texto para realizar casi cualquier cosa. En muchos casos, cuando utilizamos una interfaz gráfica, ésta es un frontend del programa en modo comando. Este [frontend](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Frontend%20%28DAM_PSP01%29), puede proporcionar todas o algunas de las funcionalidades de la herramienta real.
* La administración de sistemas, y más si se realiza de forma remota, es más eficiente en modo comando. Las administradoras y administradores de sistemas experimentadas utilizan scripts y modo comandos, tanto en sistemas Windows como GNU/Linux.

 El comienzo en el mundo de los comandos, puede resultar aterrador, hay muchísimos comandos, ¡es imposible aprendérselos todos! Bueno, no nos alarmemos, con este par de trucos podremos defendernos:

1. El **nombre de los comandos** suele estar relacionado con la tarea que realizan, sólo que expresado en inglés, o utilizando siglas. Por ejemplo: tasklist muestra un listado de los procesos en sistemas Windows; y en GNU/Linux obtendremos el listado de los procesos con `ps`, que son las siglas de 'process status'.
2.  Su **sintaxis** siempre tiene la misma forma:

    `nombreDelComandoopciones`

 Las opciones, dependen del comando en si. Podemos consultar el manual del comando antes de utilizarlo. En GNU/Linux, lo podemos hacer con "`man` nombreDelComando"; y en Windows, con "nombreDelComando /?"

 **Recuerda dejar siempre un espacio en blanco después** del nombreDelComando y entre las opciones.

 Después de esos pequeños apuntes, los **comandos que nos interesa conocer para la gestión de procesos** son:

1.  **Windows.** Este sistema operativo es conocido por sus interfaces gráficas, el intérprete de comandos conocido como Símbolo del sistema, no ofrece muchos comandos para la gestión de procesos. Tendremos:
   * **tasklist.** Lista los procesos presentes en el sistema. Mostrará el nombre del ejecutable; su correspondiente Identificador de proceso; y, el porcentaje de uso de memoria; entre otros datos.
   * **taskkill.** Mata procesos. Con la opción /PID especificaremos el Identificador del proceso que queremos matar.
2.  **GNU/Linux.** En este sistema operativo, todo se puede realizar cualquier tarea en modo texto, además de que los desarrolladores y desarrolladoras respetan en la implementación de las aplicaciones, que sus configuraciones se guarden en archivos de texto plano. Esto es muy útil para las administradoras y administradores de sistemas.
   * `ps`. Lista los procesos presentes en el sistema. Con la opción "`aux`" muestra todos los procesos del sistema independientemente del usuario que los haya lanzado.
   * `pstree`. Muestra un listado de procesos en forma de árbol, mostrando qué procesos han creado otros. Con la opción "`AGu`" construirá el árbol utilizando líneas guía y mostrará el nombre de usuario propietario del proceso.
   * `kill`. Manda señales a los procesos. La señal -9, matará al proceso. Se utiliza "`kill -9 <PID>`".
   * `killall`. Mata procesos por su nombre. Se utiliza como "`killall` nombreDeAplicacion".
   * `nice`. Cambia la prioridad de un proceso. "`nice -n 5 comando`" ejecutará el comando con una prioridad 5. Por defecto la prioridad es 0. Las prioridades están entre -20 \(más alta\) y 19 \(más baja\).

 Veremos al final del siguiente apartado un ejemplo, en el que comprobaremos si, realmente, nuestro proyecto `CrearProcesos` creábamos distintos procesos. También daremos respuesta a la pregunta que planteamos en el apartado de la Gestión de procesos por parte del sistema operativo: ¿quién es el que gestiona los procesos java, el sistema operativo o la máquina virtual java?

