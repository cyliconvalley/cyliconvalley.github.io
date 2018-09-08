---
id: 1887
title: "Taller de 99 Bottles of OOP"
date: 2018-09-15T10:00:11+00:00
author: juanignaciosl
layout: post
guid: http://www.cyliconvalley.es/99-bottles-of-oop
permalink: /2018/09/01/99-bottles-of-oop/
cover: /assets/2018/99-bottles-of-oop.png
categories:
  - Charlas
  - cyliconvalley
---

¡Esperamos que hayáis descansado este verano, porque comenzamos el curso!

Este año en Cylicon tenemos intención de repetir **[WeCode el 22-23 de
febrero](https://wecodefest.com/)**, y 
**[LechazoConf en mayo](https://lechazoconf.com/)** (fecha por confirmar,
¡todo el mundo atento!).

Además, queremos inaugurar **el canal de Slack #cyliconvalley**. Apuntaos [en Slack a remotehq](https://cyliconvalley.herokuapp.com/), el canal es [#cyliconvalley](https://remotehq.slack.com/messages/CCF7QGREE)
como medio de comunicación para la comunidad local. **[¡Apuntaos!](https://remotehq.slack.com/messages/CCF7QGREE)**

Y... **¡arrancamos las jornadas de los sábados por la mañana con un taller!**

## 99 Bottles of OOP

**[99 Bottles of OOP](https://www.sandimetz.com/99bottles/)** es un fantástico libro
de Sandi Metz y Katrina Owen para explorar los **principios de la Programación Orientada
al Objeto** y buenas prácticas de programación como TDD. El hilo conductor es un
ejercicio alrededor de una canción popular.

En el WeCode [Nacho](https://twitter.com/juanignaciosl) hizo un breve taller sobre el libro 99 Bottles of OOP.
Prometió hacer una sesión completa en Cylicon, y _un Lannister siempre paga sus deudas_.

En el taller probablemente no nos dará tiempo a realizar el ejercicio del libro
completo, pero podremos practicar y debatir sobre cosas como TDD, la Premisa
de la Prioridad de Transformación o las  _Flocking Rules_. ¡La mañana será
muy interactiva!

### Instrucciones

**Hay que traer el ordenador**, ya sea individualmente, en parejas o grupos de tres.

Aunque el libro está en Ruby **el taller lo puedes hacer en cualquier lenguaje**.
Lo único que tienes que preparar para el taller es **asegurarte de que puedes lanzar
un test** en tu entorno de ejecución favorito.

1.- Bájate el código:

  a) Ruby: <https://github.com/sandimetz/99bottles>

  b) Otros: <https://github.com/sandimetz/99bottles-polyglot>

2.- Comprueba que puedes lanzar el test:

  a) Ruby:
```bash
git checkout exercise
ruby test/bottles_test.rb # debería fallar con `uninitialized constant Bottles`
```
  b) Otros: dependerá. Por ejemplo, con Scala hay que hacer esto:
```bash
mv src/test/scala/B src/test/scala/BeerSongTest.scala
sbt test # Falla con `not found: value BeerSong`
```

Si tienes alguna duda, escribe a [Nacho vía Twitter en @juanignaciosl](https://twitter.com/juanignaciosl).

## Dame más datos!

* Día: Sábado 15 de Septiembre (de 10:00 a 14:00)
* Lugar: [Agencia de Innovación](https://www.google.es/maps/place/Agencia+de+Innovaci%C3%B3n/@41.618862,-4.747401,17z/data=!3m1!4b1!4m2!3m1!1s0xd476cde13c9d9df:0xc54421ea5d686678)
* [Apúntate en el Meetup](https://www.meetup.com/es-ES/Cylicon-Valley/events/254297703/).
