# 3.3.1. Planificación de procesos por el Sistema Operativo \(II\)

Una vez que el proceso ya está cargado en memoria, será el **planificador el encargado de tomar las decisiones relacionadas con la ejecución de los procesos.** Se encarga de decidir qué proceso se ejecuta y cuánto tiempo se ejecuta. El planificador es otro proceso que, en este caso, es parte del SO. La política en la toma de decisiones del planificador se denominan: **algoritmo de planificación.** Los más importantes son:

* **Round-Robin.** Este algoritmo de planificación favorece la ejecución de procesos interactivos. Es aquél en el que cada proceso puede ejecutar sus instrucciones en la [CPU](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=CPU%20%28DAM_PSP01%29) durante un `quamtum`. Si no le ha dado tiempo a finalizar en ese `quamtum`, se coloca al final de la cola de procesos listos, y espera a que vuelva su turno de procesamiento. Así, todos los procesos listos en el sistema van ejecutándose poco a poco.
* **Por prioridad.** En el caso de Round-Robin, todos los procesos son tratados por igual. Pero existen procesos importantes, que no deberían esperar a recibir su tiempo de procesamiento a que finalicen otros procesos de menor importancia. En este algoritmo, se asignan prioridades a los distintos procesos y la ejecución de estos, se hace de acuerdo a esa prioridad asignada. Por ejemplo: el propio planificador tiene mayor prioridad en ejecución que los procesos de usuario, ¿no crees?
* **Múltiples colas.** Es una combinación de los dos anteriores y el implementado en los sistemas operativos actuales. Todos los procesos de una misma prioridad, estarán en la misma cola. Cada cola será gestionada con el algoritmo Round-Robin. Los procesos de colas de inferior prioridad no pueden ejecutarse hasta que no se hayan vaciado las colas de procesos de mayor prioridad.

En la **planificación** \(scheduling\) de procesos se busca conciliar los siguientes **objetivos**:

* **Equidad.** Todos los procesos deben poder ejecutarse.
* **Eficacia.** Mantener ocupada la CPU un 100 % del tiempo.
* **Tiempo de respuesta.** Minimizar el tiempo de respuesta al usuario.
* **Tiempo de regreso.** Minimizar el tiempo que deben esperar los usuarios de procesos por lotes para obtener sus resultados.
* **Rendimiento.** Maximizar el número de tareas procesadas por hora.

En el siguiente enlace puedes ver una simulación del algoritmo de planificación Round-Robin, en él podrás ver cómo los procesos van tomando su turno de ejecución en la CPU hasta su finalización.

[Enlace a un simulador del algoritmo de planificación Round-Robin.](https://www.youtube.com/watch?v=TfwLl9AWvNA)

