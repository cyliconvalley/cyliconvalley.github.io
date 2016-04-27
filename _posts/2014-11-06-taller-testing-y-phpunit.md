---
id: 1228
title: Taller testing y PHPUnit.
date: 2014-11-06T21:57:25+00:00
author: Alvaro G. Loaisa
layout: post
guid: http://www.cyliconvalley.es/?p=1228
permalink: /2014/11/06/taller-testing-y-phpunit/
dsq_thread_id:
  - 3199334646

categories:
  - aprendizaje
  - cyliconvalley
  - Taller
---
<div style="text-align: center;">
  <img class="aligncenter size-full wp-image-1232" title="phpunit-post copia" src="/assets/2014/11/phpunit-post-copia.jpg" alt="" width="500" height="240" />
</div>

&nbsp;

<div>
  Comenzamos la andadura de actividades del grupo local de PHP.
</div>

<div>
  <strong>Isidro Merayo</strong> (<a href="https://twitter.com/isidromerayo" target="_blank">@isidromerayo</a>) impartirá una charla/taller sobre testing y PHPUnit, abriendo fuego el día 11 de noviembre.
</div>

&nbsp;

## Dame más datos!

  * **Día: martes 11/11/2014**
  * **Hora: de 18:30 a 21:00**
  * **Lugar: <a href="http://www.valladolidadelante.es/lang/agencia/?refbol=agencia&refsec=agencia_donde-estamos" target="_blank">Agencia de Innovación</a>**
  * **Si quieres apuntarte&#8230; **
<a href="http://www.eventbrite.es/e/entradas-charlataller-phpunit-8557019275?aff=estw" rel="nofollow" target="_blank"><img src="http://www.eventbrite.com/custombutton?eid=3724377714" alt="Eventbrite - Taller PHPUnit" /></a> </ul> 

****Te esperamos!! <img src="http://www.cyliconvalley.es/wp-includes/images/smilies/icon_biggrin.gif" alt=":D" class="wp-smiley" />

&nbsp;

<div>
  <strong>Para el taller es necesario tener</strong>:
</div>

&nbsp;

<div>
    * <strong>PHP</strong> (recomendable 5.4 o superior)
</div>

<div>
    * <strong>Composer</strong> (<a href="https://getcomposer.org/" target="_blank">https://getcomposer.org/</a>)
</div>

<div>
    * <strong>Git</strong>
</div>

<div>
  <strong><br /> </strong>
</div>

&nbsp;

<div>
  En Debian o Ubuntu puedes seguir el siguiente &#8220;guión&#8221;:
</div>

&nbsp;

<div>
</div>

<div>
  <pre>Instalar paquetes y configuración básica</pre>
  
  <pre>==============================&lt;wbr>==========&lt;/wbr></pre>
  
  <pre></pre>
  
  <pre>Utilidades</pre>
  
  <pre>----------</pre>
  
  <pre></pre>
  
  <pre>root@vm-taller:~# apt-get install curl tree</pre>
  
  <pre>root@vm-taller:~# apt-get install vim vim-gtk</pre>
  
  <pre>root@vm-taller:~# aptitude install git gitg meld</pre>
  
  <pre>root@vm-taller:~# aptitude install graphviz graphviz-dev</pre>
  
  <pre></pre>
  
  <pre>PHP (recomendable 5.4 )</pre>
  
  <pre>-----------------------</pre>
  
  <pre></pre>
  
  <pre>root@vm-taller:~# apt-get install php5 php5-cli php-pear php5-mysql php5-sqlite php5-xdebug php5-json php5-curl php5-xsl</pre>
  
  <pre></pre>
  
  <pre>Composer</pre>
  
  <pre>--------</pre>
  
  <pre>root@vm-taller:/usr/local/bin# curl -sS <a href="https://getcomposer.org/installer" target="_blank">https://getcomposer.org/&lt;wbr>installer&lt;/wbr></a> | php</pre>
  
  <pre>root@vm-taller:/usr/local/bin# ln -s composer.phar composer</pre>
  
  <pre></pre>
  
  <pre></pre>
  
  <pre></pre>
  
  <pre>Es recomenable revisar si todo ha ido bien.</pre>
  
  <pre></pre>
  
  <pre>Comprobar que la instalación es correcta</pre>
  
  <pre>==============================&lt;wbr>==========&lt;/wbr></pre>
  
  <pre></pre>
  
  <pre></pre>
  
  <pre>Creando proyecto con simple_php_skeleton</pre>
  
  <pre>==============================&lt;wbr>==========&lt;/wbr></pre>
  
  <pre>$ composer create-project isidromerayo/simple_php_&lt;wbr>skeleton taller_phpunit&lt;/wbr></pre>
  
  <pre>$ cd taller_phpunit</pre>
  
  <pre>$ bin/phpunit --version</pre>
  
  <pre>$ bin/phpunit tests/unit/</pre>
  
  <p>
    </div>