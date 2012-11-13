---
layout: post
title: "Servicios Abiertos o Cerrados (I): last.fm"
category: [webservices]
tags: [last.fm, scrobblings, mp3, software]
published: true
image: /images/posts/lastfm_logo_red.png
---
{% include JB/setup %}

<p>Hoy <strong>es habitual que guardes tus datos en</strong> la llamada nube,<strong> en Internet</strong> vamos. Es algo que haces constantemente y casi sin darte cuenta. Esto no es nada nuevo, seguro que utilizas <a href="http://mail.google.com/mail?hl=es" target="_blank">gmail </a>o <a href="http://www.hotmail.com/" target="_blank">hotmail</a> en vez de tu Outlook u otro programa de correo o escuchas tus canciones con <a title="Spotify" href="http://www.spotify.com/" target="_blank">Spotify</a> en vez de con ese viejo winamp 3.X que te acompañó durante tanto tiempo. Esto se puede plantear como un problema y también como una ventaja, pero lo que sí es cierto es que <strong>ésta es una tendencia general </strong>de los usuarios de Internet.</p>

<p>Antes de valorar este hecho, me gustaría hablar de diferentes aplicaciones que se han servido de esta <strong>tendencia </strong>para sacarle partido con estrategias muy diferentes:<strong> last.fm, IMBd</strong> y <strong>Filmaffinity </strong>(dejaré éstas dos últimas para otro post).</p>

<img title="Logo de last.fm" src="{{ site.production_url }}/images/posts/lastfm_logo_red.png" alt="Logo de last.fm"   />

<p>Last.fm es una de esas aplicaciones que <strong>utilizas casi sin darte cuenta</strong>, <strong>no te molestan</strong> y te <strong>aportan mucho</strong> cuando empiezas a comprender todas sus posibilidades, <em>y lo digo porque no es inmediato ver su potencial</em>.</p>


<p>Por si aún no lo conocías, last.fm es un servicio que se encarga de <strong>conocer tus gustos musicales</strong>, <em>¿cómo un programa va a conocer qué es lo que te gusta?</em>, &#8230;pues bien, él simplemente se va a ir enterando de la música que escuchas.</p>

<p>La idea del funcionamiento básico de last.fm se puede explicar en unas líneas. Se basa en algo que ellos denominan <em><strong>scrobblings </strong></em>y que representan cada tema que tu has escuchado. Cada vez que escuchas un tema en soporte digital, un &#8220;<em>programita</em>&#8221; que ellos te facilitan llamado <em><strong>s</strong><strong>crobbler </strong>se encarga de </em>&#8220;decriselo&#8221; a last.fm ya sea desde <strong>tu dispositivo</strong> iOS o Android o instalando el <strong>programa en tu ordenador</strong> windows, mac osx o linux. Así que resumiendo, last.fm se entera de lo que escuchas cuando:</p>

<ul>
	<li>
		Escuchas una canción en tu ordenador a través de tu reproductor favorito, como por ejemplo <a title="Spotify" href="http://www.spotify.com/" target="_blank">Spotify</a>, <a href="http://www.apple.com/es/itunes/" target="_blank">iTunes</a>, <a href="http://www.winamp.com/" target="_blank">Winamp</a>, <a href="http://windows.microsoft.com/es-ES/windows/products/windows-media" target="_blank">Windows Media Player</a>, <a href="http://www.rhythmbox.org" target="_blank">Rhythmbox</a>, <a href="http://banshee.fm/" target="_blank">Banshee</a>, <a href="http://amarok.kde.org/" target="_blank">Amarok</a>, <a title="Songbird" href="http://www.getsongbird.com/" target="_blank">Songbird</a>, <a href="http://www.videolan.org/vlc/" target="_blank">VLC</a> &#8230;(y un largo <a href="http://www.lastfm.es/group/Does%2520It%2520Scrobble" target="_blank">etcétera</a>).
	</li>
	
	<li>
		Cuando escuchas algo desde tu <a href="http://www.apple.com/es/ipod/" target="_blank">ipod</a>, <a href="http://www.apple.com/es/iphone/" target="_blank">iphone</a>, o cualquier <a href="http://www.google.com/phone/" target="_blank">dispositivo con android</a>.
	</li>
	
	<li>O cuando sincronizas tu mp3 o mp4 con tu ordenador.</li>
</ul>

<img title="Fondo de pantalla con carátulas de last.fm" src="{{ site.production_url }}/images/posts/caratulasLastFMrobertovg24.png" alt="Fondo de pantalla con carátulas de last.fm"   />
<p>Fondo de pantalla generado con las carátulas de mis discos más escuchados</p>

<p>Es decir que last.fm realmente <strong>te puede conocer </strong>de muchísimas maneras y <strong>sin tener que cambiar tus hábitos</strong>, instalas el &#8220;<strong>programita&#8221; </strong>y te olvidas. <em>Pero a ver, ¿qué es lo que gano yo diciendoles a los de last.fm que es lo que escucho?</em></p>
<ul>
	<li>Tienen la opción de pagar por una radio (3€ al mes) que como ya te conoce perfectamente, te va a poner música acorde con tus gustos.</li>
	<li>Te va a recomendar, nuevos artistas, nuevos discos, conciertos, festivales, etc.,  relacionados con la música que tu realmente escuchas.</li>
	<li>Tiene un componente social, que aunque no lo potencian todo lo que deberían, está muy conseguido. <em>Por ejemplo puedes buscar gente con gustos musicales parecidos a los tuyos para ver qué grupos escuchan y así conocer novedades.</em></li>
	<li>Por último, y para mí lo más importante<strong>, tu eres dueño de tus datos, </strong>aunque ellos lo administran, <strong>tu tienes el control</strong>.</li>
</ul>

<p>Last.fm hace que toda esa <strong>información </strong>que recogen de ti <strong>sea accesible </strong>de hecho puedes acceder a ella <strong>desde su web</strong>, a través de <strong>rss</strong> y desde la <strong><a href="http://www.lastfm.es/api" target="_blank">api</a></strong> que ofrecen. Ello posibilita que terceras aplicaciones puedan enriquecer tu experiencia con todos esos datos. Además, <strong>tu eres quien tiene el cotrol de tus datos</strong>; puedes borrar de tu lista de scrobblings un artista o canción en concreto o si así lo decides, puedes borrar tu cuenta haciendo desaparecer todo el rastro que hayas dejado en el servicio.<em> Me parece muy importante tener todas estas opciones para sentirme agusto con un servicio web</em>.</p>

<p>Pero no todo iban a ser cosas buenas, un fallo general de diseño que tiene <strong>last.fm </strong>es que no se pensó mucho en los <strong>scrobblings offlines. </strong>Estos scrobblings son los que se realizan sin conexión a internet, por ejemplo cuando escuchas canciones desde tu reproductor de mp3 o desde tu ordenador estando desconectado, que suelen ser la mayoría.<strong> La limitación es que no te deja hacer <em>scrobblings </em>con fechas &#8220;muy&#8221; antiguas si ya existen <em>scrobblings</em> más recientes</strong>. Esto no debería ser un problema, pues cuando escuchas una canción, la siguiente siempre la escucharás en una fecha más reciente. El problema viene cuando por ejemplo escuchas canciones en un reproductor, al día siguiente te pones a escuchar Spotify haciendo scrobblings y luego sincronizas tu reproductor con tu ordenador; todas esas reproducciones no se podrán enviar ya que al tener fechas más antiguas que las que le llegaron cuando pusiste el spotify, el servicio de last.fm directamente las ignora, para protegerse de peticiones erróneas.</p>

<p>Parece un problema rebuscado, pero es algo que suele pasar más de lo que piensas, así que mi consejo es que si sueles utilizar un reproductor y también reproducir música desde el ordenador,<strong> lo tengas en mente y decidas</strong> qué vas a conectar a last.fm, ya que si lo conectas todo, puede que no se te actualicen las canciones escuchadas de manera <strong>offline.</strong></p>
<p>Como dato curioso, decir que last.fm tiene hasta dispositivos físicos, como <a href="http://www.lastfm.es/group/Logitech+Squeezebox+Scrobblers">éstos de Logitech</a> que reproducen su rádio:</p>

<img title="Logitech Squeezebox duet" src="{{ site.production_url }}/images/posts/squeezebox_51.jpg" alt="Logitech Squeezebox duet"   />
<p>Squeezebox duet: dispositivo compatible con last.fm </p>

<p>Y tú, ¿utilizas last.fm?, ¿conoces otro servicio similar?.</p>
<p><em>Logotipo last.fm | <a href="http://en.wikipedia.org/wiki/Last.fm" target="_blank">Wikipedia</a></em></p>
<p><em>Fondo caratulas generado con &#8220;Last.Fm personal wallpaper generator&#8221; | <a href="http://lastfm.alekc.org/index.php" target="_blank">URL</a></em></p>
<p><em>Gama de dispositivos Squeezebox | <a href="http://www.logitech.com/es-es/speakers-audio/wireless-music-systems" target="_blank">Logitech</a></em>
</p>