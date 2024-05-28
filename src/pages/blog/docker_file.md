---
layout: ../../layouts/Layout.astro
---
<div class="w-8/12 w-6/12 mx-auto">
<h1 class="text-4xl font-bold text-center">Dockerfile</h1>

<p class="italic text-center mt-4">
  Nota: Todos estos artículos expresan mi opinión y experiencia personal. Si encuentras algún error o tienes alguna sugerencia, no dudes en ponerte en contacto en la sección de <strong>contacto</strong>.
</p>

<h2 class="text-2xl font-semibold text-blue-300 mt-8">¿Qué es Dockerfile?</h2>
<p class="mt-4">
  Según Microsoft: <strong>dockerfile es un archivo de texto que contiene las instrucciones necesarias para crear una nueva imágen en el contenedor</strong>
</p>
<p class="mt-4">
  Para ser más simple: Dockerfile no es más que un fichero al que tienes que llamarle <em>Dockerfile (literalmente)</em>. <strong>Dentro de este fichero tú vas a tener que añadir una serie de instrucciones para que tu proyecto pueda funcionar.</strong> Esto te va a crear un elemento llamado <strong>Imagen</strong>.
</p>

<h3 class="text-xl font-semibold text-blue-300 mt-8">¿Qué es una imagen?</h3>
<p class="mt-4">
  Imagínate que una imagen en Docker es como un paquete con todo lo necesario para que tu aplicación funcione sin ningún problema. Desde el código hasta las herramientas más necesarias. Es como una caja que contiene todo lo que tu proyecto necesita para que pueda correr en cualquier lado. ¿Mola verdad?
</p>

<h3 class="text-xl font-semibold text-blue-300 mt-8">Pongamos un pequeño ejemplo:</h3>
<p class="mt-4">
  Todos los proyectos Java necesitan su ración de Java, ¿no? Pues aquí no es la excepción. Necesitamos un buen <em>OpenJDK</em> y un archivo <em>.jar</em>, que es básicamente el fruto de nuestras horas de compilación, donde residen todas esas clases .class que tanto nos ha costado escribir.
</p>
<p class="mt-4">
  Ahora, ¿cómo metemos todo eso en nuestro Dockerfile? parece fácil ¿verdad? Pero... ¿será tan sencillo como parece?
</p>
<p class="mt-4">
  Bajo mi opinión, todos debemos de empezar creando un Dockerfile más <em>sencillo</em> como el ejemplo que se va a poner a continuación:
</p>

<div class="pb-4 pt-4 rounded-lg mt-4">

```dockerfile

    FROM openjdk:11

    WORKDIR /app

    COPY MiApp.jar /app/MiApp.jar

    CMD ["java", "-jar", "MiApp.jar"]

```

</div>

<div class="mt-8">
  <ul class="list-disc list-inside">
    <li><span class="text-pink-500 font-bold">FROM openjdk:11</span>: Esta línea muestra la imagen que se va a usar en el contenedor.</li>
    <li><span class="text-pink-500 font-bold">WORKDIR</span>: Se establece en donde se va a trabajar, posteriormente se van a usar para las instrucciones en el contenedor.</li>
    <li><span class="text-pink-500 font-bold">COPY</span>: Como esta instrucción indica, nos permite copiar uno o varios archivos de nuestro local a la imagen.</li>
    <li><span class="text-pink-500 font-bold">CMD</span>: Define el ejecutable por defecto de una imagen Docker. En este caso, el contenedor ejecuta el proceso especificado por el terminal. Para que sea más sencillo, todas las instrucciones necesarias que tú pondrías en una terminal para ejecutar el proyecto.</li>
  </ul>
</div>
</div>

<style>

    pre{
         border-radius: 10px; 
    }
</style>