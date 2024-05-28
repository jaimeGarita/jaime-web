---
layout: ../../layouts/Layout.astro
---

<h1 style="color: #4caf50; text-align:center;">Dockerfile</h1>

_Nota: Todos estos artículos expresan mi opinión y experiencia personal. Si encuentras algún error o tienes alguna sugerencia, no dudes en ponerte en contacto en la sección de **contacto**._

<h2 style="color: #9ECBFF;">¿Qué es Dockerfile?</h2>

Según Microsoft: **dockerfile es un archivo de texto que contiene las instrucciones necesarias para crear una nueva imágen en el contenedor**

Para ser mas simple: Dockerfile no es mas que un fichero al que tienes que llamarle _Dockerfile (literalmente)_. **Dentro de este fichero tu vas a tener que añadir una serie de instrucciones para que tu proyecto pueda funcionar.** Esto te va a crear un elemento llamado **Imágen**

<h3 style="color: #9ECBFF;">¿Qué es una imágen?</h3>
Imagínate que una imágen en Docker es como un paquete con todo lo necesario para que tu aplicación funcione sin ningún problema. Desde el código hasta las herramientas más necesarias. Es como una caja que contiene todo lo que tu proyecto necesita para que pueda correr en cualquier lado. ¿Mola verdad?
<br></br>

<h3 style="color: #9ECBFF;">Pongamos un pequeño ejemplo:</h3>

Todos los proyectos Java necesitan su ración de Java, ¿no? Pues aquí no es la excepción. Necesitamos un buen *OpenJDK* y un archivo *.jar*, que es básicamente el fruto de nuestras horas de compilación, donde residen todas esas clases .class que tanto nos ha costado escribir.

Ahora, ¿cómo metemos todo eso en nuestro Dockerfile? parece fácil ¿verdad? Pero... ¿será tan sencillo como parece?

Bajo mi opinión, todos debemos de empezar creando un Dockerfile mas *sencillo* como el ejemplo que se va a poner a continuación:

```dockerfile

    FROM openjdk:11

    WORKDIR /app

    COPY MiApp.jar /app/MiApp.jar

    CMD ["java", "-jar", "MiApp.jar"]

```

Donde:

- <span style="color:#F97583">`FROM openjdk:11`</span> : Esta línea muestra la imagén que se va a usar en el contenedor.
- <span style="color:#F97583">`WORKDIR`</span> : Se establece en donde se va a trabajar, posteriormente se van a usar para las instrucciones en el contenedor
- <span style="color:#F97583">`COPY`</span> : Como esta instrucción indica, nos permite copiar uno o varios archivos de nuestro local a la imágen.
- <span style="color:#F97583">`CMD`</span> : Define el ejecutable por defecto de una imágen Docker. En este caso, el contenedor ejecuta el proceso especificado por el terminal. Para que sea mas sencillo, todas las instrucciones necesarias que tu pondrias en una terminal para ejecutar el proyecto.

