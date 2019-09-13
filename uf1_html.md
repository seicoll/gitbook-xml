LLENGUATGE HTML
===============

Index
=====

HTML
====

-   És el llenguatge amb el qual s’escriuen les pàgines web.
-   Les pàgines són vistes pels usuaris mitjançant un tipus d’aplicació
    anomenat navegador.
-   Conseqüentment, el llenguatge HTML serveix al navegador per mostrar
    les pàgines a l’usuari.

Història d'Internet
-------------------

<https://www.youtube.com/watch?v=h8K49dD52WA>

Què és una pàgina web?
----------------------

-   És un arxiu de text amb extensió .html o . htm
-   Pot ser creada amb el bloc de notes o programes Editors de
    codi HTML.
-   HTML és únicament text pla

Sintaxis HTML
-------------

-   El llenguatge HTML base la seva sintaxis en un element de base que
    anomenem etiqueta.

Una obertura de forma general &lt;etiqueta&gt; Un tancament de tipus
&lt;/etiqueta&gt;

-   Tot el que estiqui dintre d’aquesta etiqueta tindrà les
    modificacions que caracteritzen aquesta etiqueta.

```html
<b> Hola a tots. </b>
```

El resultat serà:

![image](hola.png)

Però tot i que funciona, no és el que busquem, falta especificar molt
millor les parts de la pàgina i la sintaxi de les etiquetes.

Aquí hi trobaràs una llista d'etiquetes vàlides:
<https://www.w3schools.com/TAGS/default.asp>

Parts d'un document HTML
------------------------

Un document HTML ha d’estar delimitat per l’etiqueta &lt;HTML&gt; i
&lt;/HTML&gt;.

A dins podem distingir-hi dues parts:

**L’encapçalament** definit per *&lt;head&gt;* i *&lt;/head&gt;* on
col·locarem etiquetes de tipus informatiu, com per exemple el títol de
la pàgina.

**El cos**, flanquejat per les etiquetes *&lt;body&gt;* i
*&lt;/body&gt;* que serà on col·locarem el nostre text i imatges
delimitat per altres etiquetes.

Format dels paràgrafs
=====================

Per definir els paragrafs utilitzem l’etiqueta *&lt;p&gt;*, la qual
introdueix una línia en blanc després del paràgraf.

> L’etiqueta &lt;br&gt; la qual no té tancament, ens serveix per fer un
> salt de línia, dins dels paràgrafs.

A dins de l’etiqueta *&lt;p&gt;* podem definir atributs a fi de
justificar el text del paràgraf.

Invocacions a
-------------

Cthulhu
-------

![image](cthulhu.png)

Aquí comencem amb els perills de les coses mal fetes però que sembla que
funcionin...

Llegireu que hi ha atributs per alinear els paràgrafs, com *align*

antigament...

> Text alineat a l’esquerre: &lt;p align=“left”&gt; Text left.&lt;/p&gt;
>
> Text alineat al centre: &lt;p align=“center”&gt; Text center&lt;/p&gt;
>
> Text alineat a la dreta: &lt;p align=“right”&gt; Text right&lt;/p&gt;

això no és correcte, a vegades el camí més ràpid no és el millor.
Coneixeu el CSS?

Mireu l'exemple de l'"abadia del crimen", per entendre que una cosa ben
feta dura més, és més fàcil de mantenir i es pot millorar amb facilitat.
Si comencem a fer codi brut, "espaguetti" o altres defectes, les pàgines
esdevenen totalment **inmantenibles**.

En voleu més exemples? (en MAJÚSCULES EL QUE HEM D'EVITAR)

Color, tamany i tipus de lletra

Això es feia mitjançant l’etiqueta *&lt;FONT&gt;* i el seu tancament.

Atributs pel tipus de lletra

> FACE: Defineix el tipus de lletra.
>
> SIZE: Defineix el tamany de la lletra.
>
> COLOR: Defineix el color del text de la lletra.

Es defineix dins de l’etiqueta &lt;BODY&gt;

> ATRIBUTS
>
> BGCOLOR: Especifica el color de fons de la pàgina
>
> BACKGROUND: Serveix per indicar la col·locació d’una imatge com a fons
> de pàgina.
>
> COLOR DEL TEXT
>
> TEXT: Serveix per definir el color del text de la pàgina.
>
> LINK: El color del enllaços que no han estat visitats ( per defecte,
> és blau ) VLINK: El color dels enllaços visitats.

... i un llarg etcètera...

> Negreta: &lt;b&gt; i &lt;/b&gt; ( bold ) o &lt;strong&gt; i
> &lt;/strong&gt;
>
> Italica: &lt;i&gt; i &lt;/i&gt;
>
> Subratllat &lt;u&gt; i &lt;/u&gt; ( underlined )
>
> Subindex: &lt;sub&gt; i &lt;/sub&gt;
>
> Superindex: &lt;sup&gt; i &lt;/sup&gt;
>
> > Hem de mirar de formatar el contingut mitjançant les fulles d'estil
> > (CSS)

D'aquests caràcters els farem servir només pel tema del signficat o la
forma, *&lt;b&gt;* (important), *&lt;i&gt;* (cursiva), MAI fer servir
*&lt;u&gt;* per subratllar. Dóna lloc a equivocacions per l'usuari, que
es pot pensar que és un link (enllaç).

Altres paràgrafs
================

Pre
---

-   És un paràgraf que respecte els codis propis del text pla (intros,
    número d'espais...)
-   Adequat per fer textos literals, per exemple els poemes amb els seus
    salts de línia sense *&lt;br&gt;*

Tipus d'atributs
================

**Atributs bàsics**

:   són els que hem vist en un ús incorrecte, però la major part
    d'equites tenen atributs ben vàlids, útils i de
    vegades imprescindibles.

**Atributs per la internacionalització**

:   per pàgines multi-idiomes, s'indica de forma explícita amb quin
    idioma està fet una pàgina. Per exemple: *lang=ca*

**Atributs d'events**

:   s'utilitzen a les pàgines web dinàmiques, fetes amb *Javascript*,
    exemples: onclick, ondblclick, onmousedown, onmouseup, ...

**Atributs pels elements que poden obtenir el focus**

:   per exemple *tabindex=3*, estableix la posició en l'ordre de
    tabulació de la pàgina

Doctype
=======

-   S'indica al programa client amb quina sintaxi s'ha creat la pàgina,
    és una sentencia que es posa al principi de tot de la pàgina

Pots veure els principals doctypes a la
[Wiki](http://wiki.boscdelacoma.cat/mediawiki/index.php/M04._Llenguatge_de_marques#DOCTYPES)

DOCTYPE HTML4
-------------

> ESTRICTE: &lt;!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN"
> "<http://www.w3.org/TR/html4/strict.dtd>"&gt; TRANSICIONAL:
> &lt;!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
> "<http://www.w3.org/TR/html4/loose.dtd>"&gt; FRAMES: &lt;!DOCTYPE html
> PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN"
> "<http://www.w3.org/TR/html4/frameset.dtd>"&gt;

DOCTYPE XHTML 1.0
-----------------

> ESTRICTE: &lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
> "<http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd>"&gt;
> TRANSITIONAL: &lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0
> Transitional//EN"
> "<http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd>"&gt;

DOCTYPE HTML5
-------------

> &lt;!DOCTYPE html&gt;

Metadades
=========

-   L'etiqueta *&lt;meta ..&gt;* serveix per afegir informació sobre la
    pàgina
-   Els buscadors consultes l'informació d'aquesta etiqueta per millorar
    la seva cerca i indexació
-   Conté els atributs *name* i *content*
-   La metadada més important és la **codificació**, és a dir declarar
    amb quin joc de caràcters s'ha dissenyat la pàgina

charse=utf-8

``` {.sourceCode .html}
<meta http-equiv="Content-Type" content="text/html;charset=utf-8">
```

Caràcters especials
===================

-   En anglès entities, en català no se sol fer servir "entitats"
-   Una pàgina web es veu en diferents països que tenen
    diferents codificacions.

Exmples

> &nbsp; -&gt; espai
>
> &gt; -&gt; &gt;
>
> &lt; -&gt; &lt;

``` {.sourceCode .html}
h&nbsp;o&nbsp;&nbsp;l&nbsp;&nbsp;a
```

Llistes
=======

Serveixen per enumerar i definir elements. Podem distingir tres tipus de
llistes:

-   Llistes desordenades
-   Llistes ordenades
-   Llistes de definició

Llistes sense ordre
-------------------

Definides per les etiquetes *&lt;ul&gt;* i *&lt;/ul&gt;* (unordered
list). Cada element de la llista queda enmarcat per l’etiqueta
*&lt;li&gt;* ( no cal fer el tancament )

``` {.sourceCode .html}
<p> Països del mon </p>
<ul>
    <li> Argentina </li>
    <li> Perú </li>
</ul>
```

![image](cthu.png)

L’atribut type ens serveix per definir el tipus de vinyeta. &lt;ul
TYPE=“tipus vinyeta”&gt; On tipus vinyeta pot ser: circle, disc o square

(fer-ho amb **CSS**)

Llistes ordenades
-----------------

Definides per les etiquetes &lt;ol&gt; i &lt;/ol&gt; ( ordered list).
Cada element de la llista queda enmarcat per l’etiqueta *&lt;li&gt;*

``` {.sourceCode .html}
<p> Països del mon </p>
<ol>
    <li> Argentina </li>
    <li> Perú </li>
</ol>
```

![image](cthu.png)

L’atribut **TYPE** ens serveix per definir el tipus de numeració que
utilitzarem.

> 1 per ordenar amb nombres
>
> > a per lletra de l’alfabet
>
> A per lletres majúscules de l’alfabet
>
> i per ordenar amb xifres romanes
>
> I per ordenar amb xifres romanes majúscules

Llistes de definició
--------------------

-   Cada element és presentat juntament amb la seva definició.
-   Definides per les etiquetes *&lt;dl&gt;* i *&lt;/dl&gt;*
    (definition list).
-   Les etiquetes de cada element són *&lt;dt&gt;* (definition term) i
    la seva definició *&lt;dd&gt;* (definition definition).

``` {.sourceCode .html}
<dl>
      <dt>Casa</dt>
      <dd>Lloc on habitar</dd>
      <dt>Llar</dt>
      <dd>Lloc on viure</dd>
</dl>
```

Aniuar les llistes
------------------

Podem aniuar els tipus de llista:

``` {.sourceCode .html}
<p>Ciutats del mon</p>
<ul>
    <li>
    Argentina
        <ol>
           <li>Buenos Aires</li>
           <li>Bariloche</li>
        </ol>
    </li>
    <li>
    Uruguay
    <ol>
       <li>Montevideo</li>
       <li>Punta del Este</li>
    </ol>
    </li>
</ul>
```

Enllaços
========

-   Necessitat de que les pàgines HTML estiguin interconnectades.
-   Un enllaç és facilment detectable en una pàgina HTML
-   Per col·locar un enllaç utlitzarem les etiquetes *&lt;a&gt;* i
    *&lt;/a&gt;*.
-   L’atribut *href*, ens indica el destí d’aquest enllaç.

``` {.sourceCode .html}
<a href=“destí”> contingut </a>
```

essent *contingut* un text o una imatge i destí un arxiu, un correu
electrònic o una pàgina

-   Els enllaços es poden classificar de la següent manera:

**Enllaços interns:**

:   els que es dirigeixen a diferents llocs de la mateixa pàgina.

**Enllaços locals:**

:   els dirigeixen a un altre pàgina dintre de la mateixa web.

**Enllaços remots:**

:   els dirigits cap a altres pàgines web.

**Enllaços amb direccions de correu:**

:   per crear un missatge de correu dirigit a una direcció.

**Enllaços amb arxius:**

:   perquè els usuaris puguin fer downloads d’arxius.

Enllaços interns
----------------

-   Són enllaços que apunten a un lloc diferent dins de la
    mateixa pàgina.
-   Per crear un enllaç d’aquest tipus és necessari a part de l’enllaç
    de l’origen, col·locar un enllaç al destí.

Ex:

``` {.sourceCode .html}
enllaç origen: <a href="#avall"> Anar al final </a>

enllaç destí: <a name=“avall”> </a>
```

No utilitzar-los molt, és millor fer pàgines més petites ja que llavors
tarden menys a carregar-se i són més fàcils de llegir.

Enllaços locals
---------------

-   Un lloc web està constituit de pàgines interconnectades.

``` {.sourceCode .html}
<a href=“arxiu.html”> Arxiu </a>
```

Per regla general, un lloc web ha d’estar ordenat per directoris. S’ha
d’utilitzar la “/” per especificar on es troben les coses. Clarificació
del desplaçament entre diferents arxius.

-   Els enllaços locals també poden apuntar a una secció en concret
    dintre d’un altre pàgina.

``` {.sourceCode .html}
<a href=“arxiu.html#seccio”> Arxiu </a>
```

-   La pàgina **arxiu.html** ha de contenir la marca referent a
    la secció.

``` {.sourceCode .html}
<a name=“seccio”> </a>
```

Enllaços externs
----------------

-   Dirigits cap a altres llocs web.
-   A l’atribut *href* i col·loquem la URL o direcció de la pàgina amb
    la que es vol enllaçar.
-   Totes les direccions van precedides de <http://>

``` {.sourceCode .html}
<a href=“http://www.elmundodeportivo.es”> Anar a El Mundo deportivo </a>
```

Enllaços a direccions de correu
-------------------------------

-   Ens obren una nova finestra de correu electrònic per enviar a una
    direcció de correu determinat.
-   A l’atribut *href* i col·loquem la paraula
    \*\*[mailto:\*\*](mailto:**) seguit de la direcció d’enllaç.

``` {.sourceCode .html}
<a href=“mailto:pep@hotmail.com”> Contactar amb en Pep </a>
```

-   Per tal de configurar altres paràmetres del correu electrònic
    s’afegeix un interrogant després de la direcció de correu.
-   No és recomenable posar enllaços a correus, pel tema dels robots
    i l'SPAM.

Enllaços a arxius
-----------------

-   El mecanisme és el mateix que hem vist en els enllaços remots
    i locals.
-   En comptes d’indicar la direcció web el que hem de fer és indicar el
    nom del fitxer (i en cas que sigui necessari la ruta).

``` {.sourceCode .html}
<a href=“fitxer.pdf”> Descarregar el fitxer </a>
```

Imatges
=======

-   L’aspecte més vistós i atractiu d’una pàgina web és el grafisme. Les
    imatges són emmagatzemades en forma d’arxius, principalment GI /PNG
    ( per dibuixos ) i JPG ( per fotos ).

L’etiqueta que utilitzem per insertar una imatge és *&lt;img&gt;*, no
cal fer el tancament.

-   Mitjançant l’atribut *src* ( source ), especifiquem el lloc on es
    troba la imatge.

ATRIBUTS DE L’ETIQUETA &lt;img&gt;
----------------------------------

**Alt:**

:   Breu descripció de l’imatge.

i el ja vist *src* són els únics atributs que hauria de tenir... però
com sempre, històricament s'ha fet malament...

![image](cthu.png)

Altres coses mal fetes:

> HEIGHT I WIDTH: Defineixen l’altura i amplada de les imatges en
> pixels.
>
> BORDER: Defineix el tamany en pixels del quadrat que rodeja l’imatge.
>
> LOWSRC: Quant tenim activada aquesta opció primer es descarrega la
> imatge amb una baixa resolució i va millorant a mesura que es va
> descarregant.

Tipus d’arxius per les imatges
------------------------------

GIF ( per dibuixos ) JPG ( per fotos )

Els dos formats comprimeixen les imatges per guardar-les.

**GIF** - Arxiu ideal per imatges que estan dibuixades.

-   Compresió: És molt bona per dibuixos.
-   Transparència: És una utilitat per definir algunes parts de la
    imatge com a transparents.
-   Colors: Es poden utilitzar paletes, conjunts de 256 o menys. Quant
    menys colors utilitzem menys tamany ocuparà l’imatge.

Actualment s'està utilitzant un format **PNG** que té les mateixes
prestacions que el GIF (transparència i animació) i a més a més
incorpora **color real**, 48 bits per píxel i compresió sense pèrdua.

**JPG**

-   Compresió: El seu algorisme de compressió és ideal per
    guardar fotos.
-   Transparència: Aquest format no té possiblitats de crear
    arees transparents.
-   Colors: Treballa sempre amb 16 milions de colors.

Optimitzar els fitxers d'imatge
-------------------------------

-   Hem de procurar de no posar imatges de tamany més gran que el que
    s'ha de visualitzar, per exemple si té 200x200 la imatge màxima no
    té sentit posar-hi una imatge a descarregar de més de 1000x1000
    píxels!

**ARXIUS GIF**

Reduïm el numero de colors de la paleta.

**ARXIUS JPG**

-   Ajustem la qualitat i la mida de l’arxiu quant l’estem guardant.
-   És impresindible disposar d’un bon editor fotogràfic a fi
    d’optimitzar una imatge: **GIMP**

Taules
======

-   Una taula és un conjunt de cel·les organitzades dintre de les quals
    podem col·locar diferents continguts.
-   Una taula ens permet organitzar i distribuir els espais d’una manera
    més òptima.
-   L’etiqueta per definir les taules és: *&lt;table&gt; &lt;/table&gt;*

Les taules són descrites per línies d’esquerra a dreta, mitjançant
*&lt;tr&gt; &lt;/tr&gt;*

``` {.sourceCode .html}
<table>
    <tr>
        <td> Cel.la1-fila1 </td>
        <td> Cel.la2-fila1 </td>
        <td> Cel.la3-fila1 </td>
    </tr>
    <tr>
        <td> Cel.la1-fila2 </td>
        <td> Cel.la2-fila2 </td>
        <td> Cel.la3-fila2 </td>        
    </tr>
</table>
```

![image](taula1.png)

Com es pot veure així no es veu massa clar que hi hagi una taula...

si afegim un atribut *border="1"* ho veurem més clar:

``` {.sourceCode .html}
<table boder="1">
```

![image](cthulhu.png)

ATRIBUTS PER FILES I CEL·LES

> Align: Justifica el text de la cel·la
>
> Valign: Podem escollir si el text apareix a dalt (top), a baix
> (bottom) o al mig (middle) de la cel.la.
>
> Bgcolor: Donar color a la cel·la o la fila escollida.
>
> Bordercolor: Defineix el color del marc.
>
> ATRIBUTS PER CEL.LES
>
> Background: Ens permet col·locar de fons una imatge en
>
> una cel·la.
>
> Height: Defineix l’altura de la cel·la en pixels o percentatge.
>
> Width: Defineix l’amplada de la cel·la en pixels o percentatge.
>
> Align: Alinea la taula respecte al seu entorn
>
> Background: Ens permet col·locar un fons per la taula a partir d’una
> imatge.
>
> Bgcolor: Color de fons de la taula.
>
> Border: Defineix el tamany del marc.
>
> Bordercolor: Defineix el color del marc.
>
> Cellpadding: Defineix en pixels l’espai entre les cel·les dela taula i
> el seu contingut.
>
> Cellspacing: Defineix l’espai entre els marcs ( en pixels )
>
> Height: Defineix l’altura de la taula en pixels o percentatge.
>
> Width: Defineix l’amplada de la taula en pixels o percentatge.

Atributs de taula vàlids
------------------------

**Colspan:**

:   Expandeix una cel·la horitzontalment.

**Rowspan:**

:   Expandeix una cel·la verticalment.TAULES EN HTML

Es poden utilitzar taules anidades.

Formularis
==========

Validació de camps:
<https://lenguajehtml.com/p/html/formularios/validaciones-html5>

Frames
======

Previ targets
-------------

Atribut **target** a enllaços

:   s'utilitza per decidir on es carrega l'enllaç, pot ser:

-   \_blank: nova finestra
-   \_top: finestra
-   \_self:(per defecte) en el frame actual
-   \_parent: es carrega al frame "pare", el que era havia cridat
    l'actual
-   o també un nom de **frame** (definit amb l'atribut name)

``` {.sourceCode .html}
<a href="nom-pagina-a-carregar.html" target="nom-del-marc-a-carregar">
```

invoquem?
---------

![image](cthu.png)

-   Estan obsolets per l'HTML5, però són vàlids per altres DOCTYPES
-   Té l'interès "històric" de saber com es feien abans les pàgines web,
    el CSS actualment les millora molt
-   Antigament els layouts una mica complexes es feien o bé amb taules o
    bé amb frames. Les dues coses estan en desús avui en dia.
-   Podria interessar saber-los fer per actualitzar alguna pàgina web
    antiga
-   Doctypes de 4.01 o de XHTML, amb FRAMESET

html 4.01

> &lt;!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN"
> "<http://www.w3.org/TR/html4/frameset.dtd>"&gt;

xhtml

> &lt;!DOCTYPE html PUBLIC “-//W3C//DTD XHTML 1.0 Frameset//EN”
> “<http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd>”&gt;

-   L'estructura també es veu modificada. No té *body*, té *frameset*

``` {.sourceCode .html}
<HTML>
<HEAD><TITLE> Mi titulo ></TITLE></HEAD>

<FRAMESET>
     <NOFRAMES>
         <BODY>
             Su visualizador no soporta frames. Pulse 
             <A HREF="indice.htm">aqui </A> para volver.
         </BODY>
    </NOFRAMES>

    <FRAME SRC="pagina1.htm" >
    <FRAME SRC="pagina2.htm" >

</FRAMESET>

</HTML>
```

Per què no s'utilitzen els frames
---------------------------------

-   Els motors de búsqueda tenen problemes per indexar-los
-   Ocupen espai a la pantalla
-   No es poden utilitzar les funcionalitats d'anar endavant o endarrere
    a l'historial de navegació
-   Tenen problemes d'usabilitat i accessibilitat web per persones
    invidents

Etiquetes
---------

**frameset**

:   l'atribut cols o rows defineix el percentatge total de la pantalla
    que ocuparà cada secció. És interessant que alguna secció tingui \*
    perquè el navegador calculi de forma automática l'ampada o l'alçada
    que ha de tenir.

**frame**

:   hi ha tants frames com blocs s'hagin indicat a l'etiqueta frameset.
    L'atribut *src* fa referència a la url de la pàgina volem que
    es carregui. L'atribut *name* indica el nom del frame per ser
    utilitzat amb *targets*

Exemples
--------

-   Anem a veure diferents dissenys de frames

3 àrees verticals
-----------------

![image](frames1.png)

``` {.sourceCode .html}
<FRAMESET COLS=30%,20%,50%>
   <FRAME SRC="a.htm">
   <FRAME SRC="b.htm">
   <FRAME SRC="c.htm">
</FRAMESET>
```

3 àrees horitzontals
--------------------

![image](frames2.png)

``` {.sourceCode .html}
<FRAMESET ROWS=25%,25%,50%>
   <FRAME SRC="a.htm">
   <FRAME SRC="b.htm">
   <FRAME SRC="c.htm">
</FRAMESET>
```

combinat 2 àrees vertical amb 2 horitzontals
--------------------------------------------

![image](frames3.png)

``` {.sourceCode .html}
<FRAMESET COLS=20%,*>
     <FRAME SRC="a.htm">
         <FRAMESET ROWS=40%,*>
              <FRAME SRC="b.htm">
              <FRAME SRC="c.htm">
        </FRAMESET>
</FRAMESET>
```

combinat 2 àrees horitzontals amb 2 verticals
---------------------------------------------

![image](frames4.png)

``` {.sourceCode .html}
<FRAMESET ROWS=50%,*>
   <FRAME SRC="a.htm">
   <FRAMESET COLS=50%,*>
       <FRAME SRC="b.htm">
               <FRAME SRC="c.htm">  
       </FRAMESET>
    </FRAMESET>
```

Xuletes ràpides de frames
-------------------------

![image](xuleta-html-framesets.png)

Iframes
=======

-   El frame que ha sobreviscut a l'HTML5 és l'**iframe**.
-   És un frame *intern*

``` {.sourceCode .html}
<iframe name="pag-interna" 
     src="index.htm" 
     width="300" hight="100" 
     frameborder="1" 
     marginwidth="5" marginheight="5" 
     scrolling="Auto">
 </iframe> 
```

-   (posem el codi en minúscules com a codi que es pot utilitzar en
    HTML5)\*

Es poden veure coses que semblarins pròpies del CSS, però que en el cas
dels *iframe* podrem utilitzar.

**scrolling**

:   apareixen barres d'scroll en el frame si la pàgina és més gran que
    l'espai dissenyat


