Experimentación de herramientas de creación colaborativa online para plataforma Sementes Desobedientes 



#¿Qué es Popcorn.js?


Popcorn.js es una biblioteca de video HTML5 y video para la red abierta desarrollada por Mozilla. Permite crear fácilmente producciones web basadas en líneas de tiempo. 

Marco de eventos (event framework) para media HTML5. Usa propiedades, métodos, eventos HTMLMediaElement nativos, los normaliza en una API (interfaz de programación de aplicaciones)fácil de apre(he)nder y proporciona un sistema de plugins para interacciones colaborativas. 


"Butter" es el entorno de desarrollo para escribir proyectos "Popcorn".


# Usando Popcorn.js

## Consigue Popcorn.js

Clonar repositorio en tu máquina o en tu servidor

    $git clone --recursive https://github.com/mozilla/popcorn.webmaker.org.git
    $cd popcorn.webmaker.org
    $npm install -- me tira error por ahora

//te pide que lo hagas como root- "sudo"

## Introducir Popcorn.js en tu web

En el html introduce: 

   <html>
     <head>
       <script src="http://popcornjs.org/code/dist/popcorn-complete.js"></script>
     </head>
     <body>
     </body>
   </html>

//todo el código de Popcorn.js es disponible acá>>> [[http://mozillapopcorn.org/popcornjs/]]

##Introducir media

En este ejemplo introduciremos un video HTML5. Popcorn.js también anda con Youtube y Vimeo. Retomemos el código anterior: 


 <html>
     <head>
       <script src="http://popcornjs.org/code/dist/popcorn-complete.min.js"></script>
  </head>
     <body>
       <video height="180" width="300" id="ourvideo">
         <source src="http://videos.mozilla.org/serv/webmademovies/popcornplug.mp4">
         <source src="http://videos.mozilla.org/serv/webmademovies/popcornplug.ogv">
         <source src="http://videos.mozilla.org/serv/webmademovies/popcornplug.webm">
       </video>
       <div id="footnote"></div>
     </body>
   </html>

Esto creará un elemento de reproductor de video con una ID de "ourvideo", el cual indicará a Popcorn qué video "controlar".

El ejemplo muestra 3 elementos de fuente de video: .mp4, .ogv y .webm --esto es para segurar que el video se reproducirá en la mayoría de los navegadores actuales. 

//Ten en cuenta que la versión .mp4 tiene que incluirse primero si el video va a andar en Safari.
Ahora prueba cambiante la fuente por una tuya! 

Además del elemento de video, hay un div con ID "footnote" -usarás esto después para mostrar un poco de texto sincronizado con la reproducción del video. 

##Crear tu propia instancia "Popcorn" 

Aquì vamos a meter unas cuantas lineas de JavaScript para crear nuestra propia instancia de Popcorn. En este ejemplo, vamos a hacer que aparezca un poco de texto a los 2 segundos de reproducirse el video. 


   <html>
     <head>
       <script src="http://popcornjs.org/code/dist/popcorn-complete.js"></script>
       <script>
         document.addEventListener( "DOMContentLoaded", function() {
 
           var popcorn = Popcorn( "#ourvideo" );
 
           popcorn.footnote({
             start: 2,
             end: 5,
             target: "footnote",
             text: "Pop!"
           });
 
         }, false );
       </script>
     </head>
     <body>
       <video height="180" width="300" id="ourvideo">
         <source src="http://videos.mozilla.org/serv/webmademovies/popcornplug.mp4">
         <source src="http://videos.mozilla.org/serv/webmademovies/popcornplug.ogv">
         <source src="http://videos.mozilla.org/serv/webmademovies/popcornplug.webm">
       </video>
       <div id="footnote"></div>
     </body>
   </html>

Empezarás añadiendo un "event listener" en el documento que ejecutará el código que contiene cuando está preparado para ello. Siguiente: crear una variable "popcorn" cuyo valor es "new Popcorn isntance". El constructor Popcorn requiere al menos un argumento, en este caso el ID "#ourvideo". Esto permite que Popcorn sepa qué video va a controlar/ser controlado por. Una vez creada la instancia, usarás el plugin "footnote" para agregar un poco de texto en un área de la página. En este ejemplo el texto que aparecerá será "Pop!" desde el segundo 2 hasta el segundo 5 del video en el target ID especificado ("footnote").

Y ya está. Has creado tu primer proyecto Popcorn.js. 

Para mas detalle >> http://popcornjs.org/popcorn-docs/popcorn-constructor/
Para probar con otras cosas acá >>>>http://popcornjs.org/popcorn-docs/plugins/

---------------------------------------------------------
*Web de Popcorn.js >>>>  [[http://popcornjs.org/]]
*Código>>
https://github.com/mozilla/popcorn-js
https://github.com/mozilla/popcorn.webmaker.org
http://jsfiddle.net/rwaldron/xhXE6/



## Cosas por hacer

*traducir lo que queda de http://popcornjs.org/popcorn-docs/index.html
*recopilar info en castellano ya producido sobre Popcorn
*investigar proyectos parecidos

