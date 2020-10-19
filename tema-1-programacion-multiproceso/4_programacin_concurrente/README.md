# 4. Programación concurrente

 Hasta ahora hemos programado aplicaciones secuenciales u orientadas a eventos. Siempre hemos pensado en nuestras aplicaciones como si se ejecutaran de forma aislada en la máquina. De hecho, el SO garantiza que un proceso no accede al espacio de trabajo \(zona de memoria\) de otro, esto es, unos procesos no pueden acceder a las variables de otros procesos. Sin embargo, los procesos, en ocasiones, necesitan comunicarse entre ellos, o necesitan acceder al mismo recurso \(fichero, dispositivo, etc.\). En esas situaciones, hay que **controlar la forma en la que esos procesos se comunican o acceden a los recursos, para que no haya errores, resultados incorrectos o inesperados**.

 Podemos ver la concurrencia como una carrera, en la que todos los corredores corren al mismo tiempo buscando un mismo fin, que es ganar la carrera. En el caso de los procesos, competirán por conseguir todos los recursos que necesiten.

 La definición de **concurrencia**, no es algo sencillo. En el diccionario, **concurrencia es la coincidencia de varios sucesos al mismo tiempo**.

 Nosotros podemos decir que **dos procesos son concurrentes**, cuando **la primera instrucción de un proceso se ejecuta después de la primera y antes de la última de otro proceso**.

 Por otro lado, hemos visto que los procesos activos se ejecutan alternando sus instantes de ejecución en la CPU. Y, aunque nuestro equipo tenga más de un núcleo, los tiempos de ejecución de cada [núcleo](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=N%C3%BAcleo%20de%20procesamiento%20o%20n%C3%BAcleo%20%28DAM_PSP01%29) se repartirán entre los distintos procesos en ejecución. **La planificación alternando los instantes de ejecución en la gestión de los procesos, hace que los procesos se ejecuten de forma concurrente.** O lo que es lo mismo: [multiproceso](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Multiprocesamiento%20%28o%20multiproceso%29%20%28DAM_PSP01%29) **= concurrencia**.

 En el resto de la unidad pondremos especial cuidado en estudiar cómo **solucionar los conflictos que pueden surgir cuando dos o más procesos intentan acceder al mismo recurso de forma concurrente**.

