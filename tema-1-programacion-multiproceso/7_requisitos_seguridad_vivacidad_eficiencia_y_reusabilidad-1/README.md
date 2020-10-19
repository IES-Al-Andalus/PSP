# 7. Requisitos: seguridad, vivacidad, eficiencia y reusabilidad

 Como cualquier aplicación, los programas concurrentes deben cumplir una serie de requisitos de calidad. En este apartado, veremos algunos aspectos que nos permitirán desarrollar proyectos concurrentes con, casi, la completa certeza de que estamos **desarrollando software de calidad**.

 Todo **programa concurrente** debe **satisfacer** dos tipos de **propiedades**:

* Propiedades de **seguridad** \("**safety**"\): estas propiedades son relativas a que **en cada instante** de la ejecución **no debe haberse producido algo que haga entrar al programa en un estado erróneo**:
  * Dos procesos **no deben entrar simultáneamente en una sección crítica.**
  * Se **respetan las condiciones de sincronismo**, como: el consumidor no debe consumir el dato antes de que el productor los haya producido; y, el productor no debe producir un dato mientras que el buffer de comunicación esté lleno.
* Propiedades de **vivacidad** \("**liveness**"\): cada sentencia que se ejecute conduce en algún modo a **un avance constructivo para alcanzar el objetivo funcional del programa**. Son, en general, muy dependientes de la política de planificación que se utilice. Ejemplos de propiedades de vivacidad son:
  * No deben producirse **bloqueos activos** \(**livelock**\). Conjuntos de procesos que ejecutan de forma continuada sentencias que no conducen a un progreso constructivo.
  * **Aplazamiento indefinido** \(**starvation**\): consiste en el estado al que puede llegar un programa que aunque potencialmente puede avanzar de forma constructiva. Esto puede suceder, como consecuencia de que no se le asigna tiempo de procesador en la política de planificación; o, porque en las condiciones de sincronización hemos establecido criterios de prioridad que perjudican siempre al mismo proceso.
  * **Interbloqueo** \(**deadlock**\): se produce cuando los procesos no pueden obtener, nunca, los recursos necesarios para finalizar su tarea. Vimos un ejemplo de esta situación en el apartado 4.2 Condiciones de competencia.

 Es evidentemente, que también nos preocuparemos por diseñar nuestras aplicaciones para que sean **eficientes:**

* No utilizarán más **recursos** de los **necesarios**.
* Buscaremos la **rigurosidad** en su **implementación: toda la funcionalidad esperada de forma correcta y concreta.**

 Y, en cuanto a la **reusabilidad**, debemos tenerlo ya, muy bien aprendido:

* Implementar el código de forma **modular**: definiendo clases, métodos, funciones, ...
* **Documentar** correctamente el código y el proyecto.

 Para conseguir todos lo anterior contaremos con los **patrones de diseño**; y pondremos especial cuidado en **documentar** y **depurar** convenientemente.

