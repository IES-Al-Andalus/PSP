# 7.2. Documentación

 Para la documentación de nuestras aplicaciones tendremos en cuenta:

 Hay que añadir **explicaciones a todo lo que no es evidente**. Pero, no hay que repetir lo que se hace, sino explicar **por qué se hace**.

 Documentando nuestro código responderemos a estas preguntas:

* ¿De qué se encarga una clase? ¿Un paquete?
* ¿Qué hace un método? ¿Cuál es el uso esperado de un método?
* ¿Para qué se usa una variable? ¿Cuál es el uso esperado de una variable?
* ¿Qué algoritmo estamos usando? ¿De dónde lo hemos sacado?
* ¿Qué limitaciones tiene el algoritmo? ¿... la implementación?
* ¿Qué se debería mejorar ... si hubiera tiempo?

 En la siguiente tabla tenemos un resumen de los distintos tipos de comentarios en Java:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Tipos de comentarios en Java</th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="../../../../../mod/glossary/showentry.php?displayformat=dictionary&amp;concept=javadoc%20%28DAM_PSP01%29">Javadoc</a>
      </td>
      <td style="text-align:left">Una l&#xED;nea</td>
      <td style="text-align:left">Tipo C</td>
    </tr>
    <tr>
      <td style="text-align:left">Sint&#xE1;xis</td>
      <td style="text-align:left">
        <p>Comienzan con &quot;/**&quot;, se pueden prolongar a lo largo de varias
          l&#xED;neas (que probablemente comiencen con el car&#xE1;cter &quot;*&quot;)
          y terminan con los caracteres &quot;*/&quot;.</p>
        <p>Cuenta con etiquetas espec&#xED;ficas tipo: <code>@author</code>, <code>@param</code>, <code>@return</code>,...</p>
      </td>
      <td style="text-align:left">Comienzan con &quot;//&quot; y terminan con la l&#xED;nea.</td>
      <td style="text-align:left">Comienzan con &quot;/*&quot;, se pueden prolongar a lo largo de varias
        l&#xED;neas (que probablemente comiencen con el car&#xE1;cter &quot;*&quot;)
        y terminan con los caracteres &quot;*/&quot;.</td>
    </tr>
    <tr>
      <td style="text-align:left">Prop&#xF3;sito</td>
      <td style="text-align:left">Generar documentaci&#xF3;n externa.</td>
      <td style="text-align:left">Documentar c&#xF3;digo que no necesitamos que aparezca en la documentaci&#xF3;n
        externa.</td>
      <td style="text-align:left">Eliminar c&#xF3;digo.</td>
    </tr>
    <tr>
      <td style="text-align:left">Uso</td>
      <td style="text-align:left">
        <p><b>Obligado:</b>
        </p>
        <ul>
          <li>Al principio de cada clase.</li>
          <li>Al principio de cada m&#xE9;todo.</li>
          <li>Antes de cada variable de clase.</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Al principio de fragmento de c&#xF3;digo no evidente.</li>
          <li>A lo largo de los bucles.</li>
          <li>Siempre que hagamos algo raro o que el c&#xF3;digo no sea evidente.</li>
        </ul>
      </td>
      <td style="text-align:left">Ocurre a menudo que c&#xF3;digo obsoleto no queremos que desaparezca,
        sino mantenerlo &quot;por si acaso&quot;. Para que no se ejecute, se comenta.</td>
    </tr>
  </tbody>
</table>

Debes consultar los siguientes enlaces para completar tus conocimientos en la generación de documentación con javadoc.

[Documentación oficial sobre Javadoc \(inglés\).](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html)

 **Además** de lo anterior, al **documentar** nuestras aplicaciones concurrentes destacaremos:

* Las **condiciones de sincronismo** que se hayan implementado en la clase o método \(en la documentación javadoc\).
* Destacaremos las **regiones críticas** que hayamos identificado y el **recurso que compartido** a proteger.

