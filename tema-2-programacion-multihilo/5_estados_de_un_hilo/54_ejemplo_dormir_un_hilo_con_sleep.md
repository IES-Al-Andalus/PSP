# 5.4. Ejemplo. Dormir un hilo con sleep

  ¿Por qué puede interesar dormir un hilo? Pueden ser diferentes las razones que nos lleven a dormir un hilo durante unos instantes. En este apartado veremos un ejemplo en el que si no durmiéramos unos instantes al hilo que realiza un cálculo, no le daría tiempo al hilo que dibuja el resultado a presentarlo en pantalla.

 ¿`Cómo funciona` el método `sleep()`?

 El método `sleep()` de la clase `thread` recibe como argumento el tiempo que deseamos dormir el hilo que lo invoca. Cuando transcurre el tiempo especificado, el hilo vuelve a estar "Ejecutable" \("Preparado"\) para continuar ejecutándose.

 Hay dos formas de llamar a este método.

* La primera le pasa como argumento un entero \(positivo\) que representa milisegundos:
* La segunda le agrega un segundo argumento entero \(esta vez, entre 1 y 999999\), que representa un tiempo extra en nanosegundos que se sumará al primer argumento:

  ```text
  sleep(long milisegundos, int nanosegundos)
  ```

 Cualquier llamada a `sleep()` puede provocar una excepción, que el compilador de Java nos obliga a controlar ineludiblemente mediante un bloque `try-catch`.

 El siguiente recurso didáctico ilustra la necesidad de dormir un hilo en una aplicación que muestra como avanza un marcador gráfico desde 0 hasta 20. Podrás comprobar que si no utilizamos un hilo auxiliar y lo dormimos, no podremos apreciar como se va incrementando el marcador.

