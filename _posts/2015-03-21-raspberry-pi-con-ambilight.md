---
id: 1370
title: Raspberry Pi con Ambilight
date: 2015-03-21T21:39:21+00:00
author: Alvaro G. Loaisa
layout: post
guid: http://www.cyliconvalley.es/?p=1370
permalink: /2015/03/21/raspberry-pi-con-ambilight/
cover: /assets/2015/03/Screen-Shot-2015-03-21-at-21.08.37.png
categories:
  - Charlas
---
<img class="alignnone wp-image-1371 aligncenter" title="Screen Shot 2015-03-21 at 21.08.37" src="/assets/2015/03/Screen-Shot-2015-03-21-at-21.08.37.png" alt="" width="489" height="301" />

&nbsp;

&nbsp;

<h3 dir="ltr">
  <span style="color: #000000;"><strong>Como surgió la idea</strong></span>
</h3>

<p dir="ltr">
  La idea de montar mi propio sistema <a href="http://es.wikipedia.org/wiki/Ambilight">Ambilight</a>, surgió cuando asistí a un <a href="http://www.cyliconvalley.es/2014/03/18/aprende-arduino-taller-quincenal/">Taller de Arduino</a> que impartía CyliconValley. Siempre me gustó todo lo relacionado con DIY (Do It Yourself), y durante el primer taller, se me encendió la bombilla y pensé: ¿dónde puedo comprar lo necesario para montarme un sistema de luces detrás de mi TV? Así que abrí un navegador, y ahí comenzó toda la aventura. A continuación, comentaré lo necesario en hardware, software y algunos pequeños diagramas que os ayudarán a montar vuestro propio sistema ambilight casero. Todos los componentes, tanto hardware como software que indico en el post, son los que yo he utilizado, que no quita que puedas utilizar otros.
</p>

&nbsp;

<h3 dir="ltr">
  <span style="color: #000000;">¿Que necesito?</span>
</h3>

<p dir="ltr">
  No necesitas mucho:
</p>

<p dir="ltr">
  - Raspberry Pi con Raspbmc (RPi). Comprado en <a href="http://www.raspipc.es/public/home/index.php?ver=tienda&accion=verArticulo&idProducto=1032">RaspiPC</a>.
</p>

<p dir="ltr">
  - Tira de 50 LEDs (modelo WS2801). Comprado en <a href="http://www.ebay.es/itm/181345440845?ssPageName=STRK:MEWNX:IT&_trksid=p3984.m1439.l2649">Ebay</a>.
</p>

<p dir="ltr">
  - Adaptador de corriente de 5V a 2A (para 25 leds con 1A es suficiente). Comprado en una tienda de electrónica.
</p>

<p dir="ltr">
  - Cables jumper (usé los que tenía del Arduino). Para conectar la RPi a un extremo de los LEDs necesitarás 3 cables hembra-hembra, y para el otro extremo 2 cables macho-macho para conectarlos a la alimentación (estos últimos los soldé).
</p>

<p dir="ltr">
  - Adaptadores <a href="http://www.ebay.es/itm/10x-2-1mm-x-5-5mm-Male-10x-Female-Pair-DC-Power-Plug-Socket-Jack-Connector-/261358467412?pt=UK_BOI_Electrical_Components_Supplies_ET&hash=item3cda2db954&_uhb=1">Macho y Hembra</a> para conectar los LEDs al adaptador de corriente. Comprado en una tienda de electrónica son mucho más baratos, el link solo es para que veais exactamente los que tengo. Estos son para soldar, pero lo puedes encontrar para atornillar los cables, <a href="http://www.dx.com/es/p/male-female-dc-power-converter-connector-adapters-w-terminal-blocks-for-cctv-camera-pair-105084">como estos</a>.
</p>

&nbsp;

<h3 dir="ltr">
  <span style="color: #000000;"><strong>Conectamos la RPi con los LEDs</strong></span>
</h3>

<p dir="ltr">
  Antes de empezar con la instalación deberás tener conectados todos los cables en su sitio, así que para que no te rompas la cabeza, se muestro un diagrama:
</p>

<div>
   <img class="alignnone size-full wp-image-1372" title="Screen Shot 2015-03-21 at 21.13.37" src="/assets/2015/03/Screen-Shot-2015-03-21-at-21.13.37.png" alt="" width="477" height="412" />
</div>

<div>
</div>

<div>
  <p dir="ltr">
    Dependiendo de tu tira de LEDs, pueden variar los colores y el número de cables, para más información <a href="http://www.doityourselfchristmas.com/wiki/index.php?title=Pixel_Wiring_Colors">visita esta web</a>.
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <h3>
    <span style="color: #000000;">Instalación</span>
  </h3>
  
  <p dir="ltr">
    Primero, he de decir que instalé Boblight, pero no conseguí nada, bueno si, poner todos los leds de un solo color, pero ese no era el objetivo. Seguí buscando y apareció un nombre “Hyperion” y me lancé a probarlo, sobre todo porque a diferencia de otros servicios, este consume menos CPU. A continuación pondré paso a paso lo que fui ejecutando.
  </p>
  
  <p dir="ltr">
    Para poder seguir los pasos, necesitarás un terminal SSH, por ejemplo: <a href="http://raspberrypi4dummies.wordpress.com/2013/03/17/connect-to-the-raspberry-pi-via-ssh-putty/">PuTTy</a>.
  </p>
  
  <div>
    <p dir="ltr">
      Lo primero es tener actualizada la RPi con la última versión.
    </p>
    
    <blockquote>
      <p dir="ltr">
        <strong># sudo apt-get update</strong>
      </p>
    </blockquote>
    
    <p dir="ltr">
      Para poder bajarnos el código de GitHub más adelante, necesitamos instalar unas librerias de certificados:
    </p>
    
    <blockquote>
      <p dir="ltr">
        <strong># sudo apt-get install libqtcore4 libqtgui4 libqt4-network libusb-1.0-0 libprotobuf7 ca-certificates</strong>
      </p>
    </blockquote>
    
    <p dir="ltr">
      Si tienes instalado Boblight, debe detener el servicio, Boblight e Hyperion, se llevan mal, para ello para el servicio, sino sáltate esta línea:
    </p>
    
    <blockquote>
      <p dir="ltr">
        <strong># sudo /sbin/initctl stop boblight</strong>
      </p>
    </blockquote>
    
    <p dir="ltr">
      Vete al siguiente directorio para descargar el código:
    </p>
    
    <blockquote>
      <p dir="ltr">
        <strong># cd /home/pi</strong>
      </p>
    </blockquote>
    
    <p dir="ltr">
      Ahora nos bajamos de GitHub el código:
    </p>
    
    <blockquote>
      <p dir="ltr">
        <strong># wget -N https://raw.github.com/tvdzwan/hyperion/master/bin/install_hyperion.sh</strong>
      </p>
    </blockquote>
    
    <p dir="ltr">
      y lo instalamos:
    </p>
    
    <blockquote>
      <p dir="ltr">
        <strong># sudo sh ./install_hyperion.sh</strong>
      </p>
    </blockquote>
    
    <p dir="ltr">
      Para probar si se ha instalado bien, puede hacerlo con esto:
    </p>
    
    <blockquote>
      <p dir="ltr">
        <strong># hyperion-remote &#8211;priority 50 &#8211;color red &#8211;duration 5000</strong>
      </p>
    </blockquote>
    
    <p dir="ltr">
      (donde se indica el color ‘red’, puede indicar un valor hexadecimal RRGGBB).
    </p>
    
    <p dir="ltr">
      Y listo, puedes poner una película y ya se encenderán los LEDs. Si los colores no encajan con la posición de la imagen, sencillamente, es porque el fichero de configuración:
    </p>
    
    <blockquote>
      <p dir="ltr">
        <strong>Path: /etc/hyperion.confing.json</strong>
      </p>
    </blockquote>
    
    <p dir="ltr">
      es el que viene por defecto, para adaptar la posición de los Leds a tus necesidades puedes crearte un nuevo fichero con esta aplicación, <a href="https://raw.github.com/tvdzwan/hypercon/master/deploy/HyperCon.jar">HyperCon</a>. Es un fichero *.jar. Para usuario de windows, debes ejecutar:
    </p>
    
    <div>
      <blockquote>
        <p dir="ltr">
          <strong># java HyperCon.jar</strong>
        </p>
      </blockquote>
      
      <p dir="ltr">
        mostrará la siguiente ventana:
      </p>
      
      <div>
         <img class="alignnone wp-image-1373" title="Screen Shot 2015-03-21 at 21.17.02" src="/assets/2015/03/Screen-Shot-2015-03-21-at-21.17.02.png" alt="" width="509" height="274" />
      </div>
      
      <div>
      </div>
      
      <div>
        <p dir="ltr">
          Puesto que el fichero que genera es un poco grande, indico algunos datos de mi fichero de configuración:
        </p>
        
        <ul>
          <li>
            Output: /dev/spidev0.0
          </li>
          <li>
            LED Type: WS2801
          </li>
          <li>
            Baudrate: 250.000
          </li>
          <li>
            RGB Byte Order: RGB
          </li>
          <li>
            Direction: Clockwise (sentido horario viendo la parte delantera de la TV).
          </li>
          <li>
            Led in Top Corners: true
          </li>
          <li>
            Led in Bottom Corners: true
          </li>
          <li>
            Horizontal: 15
          </li>
          <li>
            Vertical: 8
          </li>
          <li>
            Bottom Gap: 0
          </li>
          <li>
            1st LED offset: -9 (mi primer Led empieza, en la esquina inferior izquierda)
          </li>
        </ul>
        
        <p dir="ltr">
          Las variables de la sección Image Process, por defecto.
        </p>
        
        <p dir="ltr">
          Ya creado el fichero, deberás reemplazarlo por el existente, pero antes debes parar el servicio de hyperion:
        </p>
        
        <blockquote>
          <p dir="ltr">
            <strong># sudo /sbin/initctl stop hyperion</strong>
          </p>
        </blockquote>
        
        <p dir="ltr">
          Reemplazamos el fichero creado:
        </p>
        
        <blockquote>
          <p dir="ltr">
            <strong># sudo cp /home/pi/mihyperion.config.json /etc/hyperion.config.json</strong>
          </p>
        </blockquote>
        
        <p dir="ltr">
          Y volvemos a arrancar el servicio:
        </p>
        
        <blockquote>
          <p dir="ltr">
            <strong># sudo /sbin/initctl start hyperion</strong>
          </p>
        </blockquote>
        
        <p dir="ltr">
          Y reinicias la RPi:
        </p>
        
        <blockquote>
          <p dir="ltr">
            <strong># sudo reboot</strong>
          </p>
        </blockquote>
        
        <p dir="ltr">
          Aquí os dejo un par videos para testear:
        </p>
        
        <p dir="ltr">
          Video 1:
        </p>
        
        <p dir="ltr">
          <a href="https://www.youtube.com/watch?v=sr_vL2anfXA">https://www.youtube.com/watch?v=sr_vL2anfXA</a>
        </p>
        
        <p dir="ltr">
          Video 2:
        </p>
        
        <p dir="ltr">
          <a href="https://www.youtube.com/watch?v=7rpto3bZz6g">https://www.youtube.com/watch?v=7rpto3bZz6g</a>
        </p>
        
        <p dir="ltr">
          Y listo para poner una película!!
        </p>
        
        <p dir="ltr">
          Aprovechando el post, si quieres usar tu tira de Leds con Arduino, necesitarás esta <a href="https://github.com/adafruit/Adafruit-WS2801-Library">librería</a> de Adafruit, trae dos ejemplos para que pruebes.
        </p>
        
        <p dir="ltr">
          Y recuerda, tu vista te lo agradecerá!!
        </p>
        
        <p dir="ltr">
          Aquí os dejo el resultado:
        </p>
        
        <p>
        </p>
        
        <p dir="ltr">
          Para más información aquí os dejo, la guía que yo usé: <a href="https://github.com/tvdzwan/hyperion/wiki">Hyperion Wiki</a>.
        </p>
        
        <div>
        </div>
      </div>
    </div>
  </div>
</div>

&nbsp;