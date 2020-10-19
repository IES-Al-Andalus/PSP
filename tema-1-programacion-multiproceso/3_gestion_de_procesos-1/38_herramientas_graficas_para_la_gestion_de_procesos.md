# 3.8. Herramientas gráficas para la gestión de procesos.

 Pero, ¿tenemos que hacerlo todo en modo comandos? ¿qué nos permite hacer el Administrador de tareas de Windows con los procesos? ¿No hay ninguna herramienta gráfica similar en los sistemas GNU/Linux?

 Tanto los sistemas Windows como GNU/Linux proporcionan herramientas gráficas para la gestión de procesos. En el caso de Windows, se trata del **Administrador de tareas**, y en GNU/Linux del **Monitor del sistema**. Ambos, son bastante parecidos, nos ofrecen, al menos, las siguientes funcionalidades e información:

* Listado de todos los procesos que se encuentran activos en el sistema, mostrando su PID, usuario y ubicación de su fichero ejecutable.
* Posibilidad de finalizar procesos.
* Información sobre el uso de CPU, memoria principal y virtual, red, …
* Posibilidad de cambiar la prioridad de ejecución de los procesos.

`SysInternals`, es un conjunto de utilidades avanzadas para SO Windows publicadas como freeware. En particular, recomendamos las herramientas gráficas "Process Explorer" y "Process Monitor". "Process Explorer" nos dará información más completa sobre los procesos activos en el sistema; y "Process Monitor" nos informará de la actividad \(de E/S\) de los procesos e hilos activos en el sistema: ficheros a los que están accediendo, actividad en red, creación de hilos, etc.

[Recopilación de utilidades para la gestión de procesos y subprocesos de SysInternals.](http://technet.microsoft.com/es-es/sysinternals/bb795533)

 La mejor forma de ver esto es con ejemplos.

## Pregunta

**El Administrador de tareas nos proporciona información sobre los archivos y recursos que está utilizando un proceso.**  


## Pregunta

**El comando `kill` en sistemas GNU/Linux se utiliza únicamente para matar procesos.**

