# 5. Comunicación entre procesos

**Ana**, repasando sus apuntes de programación concurrente, recuerda que le costó un poquito de trabajo entender que hiciera falta la implementación de mecanismos específicos, para que los procesos se comunicaran entre ellos. La comunicación de procesos, ¿qué es?, pasar datos de unos a otros, ¿no? Pero, ¿no están todos en memoria? ¿No pueden acceder a la dirección de memoria en la que se encuentre la información que necesitan y ya está?

 Como ya hemos comentado en más de una ocasión a lo largo de esta unidad, cada proceso tiene su espacio de direcciones privado, al que no pueden acceder el resto de procesos. Esto constituye un mecanismo de seguridad; imagina qué locura, si tienes un dato en tu programa y cualquier otro, puede modificarlo de cualquier manera. Tu programa generaría errores, como poco.

 Por supuesto, nos damos cuenta de que, si cada proceso tiene sus datos y otros procesos no pueden acceder a ellos directamente, cuando otro proceso los necesite, tendrá que existir alguna forma de comunicación entre ellos.

**Comunicación entre procesos: un proceso da o deja información; recibe o recoge información.**

 Los **lenguajes de programación y los sistemas operativos, nos proporcionan** [primitivas](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Primitiva%20%28DAM_PSP01%29) **de sincronización que facilitan la interacción entre procesos de forma sencilla y eficiente.**

 Una primitiva, hace referencia a una operación de la cual conocemos sus restricciones y efectos, pero no su implementación exacta. Veremos que usar esas primitivas se traduce en utilizar **objetos y** sus **métodos**, teniendo muy en cuenta sus **repercusiones reales en el comportamiento de nuestros procesos.**

 Clasificaremos las interacciones entre los procesos y el resto del sistema \(recursos y otros procesos\), como estas tres:

* **Sincronización:** Un proceso puede conocer el punto de ejecución en el que se encuentra otro en ese determinado instante.
* **Exclusión mutua:** Mientras que un proceso accede a un recurso, ningún otro proceso accede al mismo recurso o variable compartida.
* **Sincronización condicional:** Sólo se accede a un recurso cuando se encuentra en un determinado estado interno.

## Pregunta

**Las primitivas de sincronización que utilizamos en nuestras aplicaciones, las proporcionan:**

### Respuestas

 [Opción 4]()

 Los lenguajes de programación y sistemas operativos.

