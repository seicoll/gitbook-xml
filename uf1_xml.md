# Introducció a XML

## Els llenguatges de marques

Un **llenguatge de marques** combina dades i etiquetes que les marquen i que contenen informació addicional sobre l'estructura del text o la seva presentació.

Les marques estan barrejades amb el propi text.

```xml
<persona>
    <nom>
        Sergi
    </nom>
    <cognom>
        Coll
    </cognom>
</persona>
```

Tot i que els sistemes de marques en que ens concentrarem són els d'estil web cal no oblidar que n'hi ha d'altres:

* Wikitext, TeX, DocBook, RTF, JSON

**Exemple Wikitext:**

```
> = Intercanvi de dades =
* [[ XML ]]
* [[ JSON ]]
* [[ LDIF ]]
```

**Exemple JSON:**

```json
{ "persona": {
    "nom": "Sergi",
    "cognom": "Coll"
} }
```

El llenguatge de marques més conegut és l'**HTML**, el de les pàgines web.

```html
<html>
    <head>
    <title> Pàgina </title>
    </head>
    <body>
        Hola!
    </body>
</html>
```

Però no és el primer que ha existit , ni l'únic

SGML
====

Recordant la història...

<http://www.tiki-toki.com/timeline/entry/7339/Histria-del-xHTMLnn/>

<http://webdirections.org/history/>

<http://www.internethalloffame.org/brief-history-internet>

* La primera tecnologia estandarditzada de llenguatges de marques va ser l'**SGML**
* Es va fer servir com estàndard de la informació de propòsit general.
* Partia de la idea de que s'han de separar les dades d'un document de la seva forma.

Però:

* La majoria dels documents estaven destinats a la **impressió**.
* Era terriblement **complex** de manera que només el feien servir els especialistes.

HTML
====

-   L'any 1989 Tim Berners-Lee i Anders Berglund, dos investigadors del
    [CERN](https://ca.wikipedia.org/wiki/Organitzaci%C3%B3_Europea_per_a_la_Recerca_Nuclear),
    van crear un llenguatge basat en etiquetes destinat a compartir
    informació per Internet: **HTML**
-   HTML és un format que descriu la visualització d'una pàgina web
-   HTML està molt orientat a la visualització
-   HTML ha sofert molts canvis al llarg dels anys
-   El suport HTML dels navegadors cada vegada és més complexe

![image](uf1-xml-01.png)

-   Tot i això la web s'ha fet cada vegada més i més popular
-   Cada dia es generen milions de pàgines web amb informació
-   Això implica que cal buscar per trobar la informació que ens
    interessa

![image](uf1-xml-02.png)

-   Però l'HTML és molt difícil de reutilitzar
-   Fa falta alguna forma de poder fer-hi recerques intel·ligents i
    seleccionar-ne el resultats

![image](uf1-xml-03.png)

En general, falta una forma de:

> “Buscar, moure, visualitzar i manipular la informació continguda en
> els documents HTML”

Naixement de l'XML
------------------

-   El consorci W3C va desenvolupar una alternativa a l’HTML que podés
    satisfer les necessitats futures del web.
-   El 1996 el consorci W3C es va proposar introduir el poder i la
    flexibilitat de l’**SGML** al web.

**SGML** oferia tres avantatges que l’HTML no tenia:

> -   Extensibilitat
> -   Estructura
> -   Validació

XML
===

Extensible Markup Language
--------------------------

El febrer de 1998 es llença l'especificació 1.0 d’XML:

<http://www.w3.org/TR/2004/REC-xml-20040204/>

L'ultima especificació d’XML és la 1.1 que va sortir el 2004:

<http://www.w3.org/TR/xml11/>

Però d'alguna manera s'ha millorat la 1.0 en posteriorat (2008)

<https://www.w3.org/TR/2008/REC-xml-20081126/>

Totes les especificacions es revisen periòdicament

<https://www.w3.org/standards/techs/xml#w3c_all>

Què és l'XML
============

XML és un simple llenguatge de descripció d'informació

-   És una estàndard que permet dissenyar i desenvolupar llenguatges
    de marques. XML és un format de text estandarditzat que serveix per
    representar i transportar informació estructurada
-   Una de les idees més importants és

    > “Separar les dades de la presentació”

-   XML no es preocupa de com es presentaran les dades als usuaris
-   Per fer la presentació ja s'han desenvolupat mecanismes:

    **CSS** **XSL-FO** ...

-   Antigament per representar dades es feia separant els valors amb
    comes o algun altre símbol

![image](uf1-xml-04.png)

-   S'ha de saber que la primera línia són metadades
-   Afegir-hi noves dades pot ser molt problemàtic pel programa que les
    llegeixi --&gt; Probablement haurem de canviar el programa
-   El format **CSV** encara s'utilitza molt en el món de la
    informàtica, per exportar/importar dades normalment

Fitxers de marques
==================

-   Els llenguatges de marques estan basats en text
-   Poden ser creats amb qualsevol editor de textos
-   Però no estan pensats per ser llegits
-   XML està pensat per transportar dades
-   A diferència d'HTML si que es pot determinar de forma automàtica què
    **signifiquen** les dades

![image](uf1-xml-05.png)

Formats Estàndards
==================

Tenim la capacitat de crear un vocabulari que només entengui el nostre
programa

-   No necessita llicència --&gt; podem fer-lo obert perquè l'entengui
    tothom
-   Al fer servir el mateix format la comunicació de dades és més fàcil
-   Ja hi ha vocabularis estàndards XML:

  -------- ---------------------------------------------
  SVG      Pensat per gràfics vectorials escalables 2D
  MathML   Representació de fórmules matemàtiques
  CML      Intercanvi d'informació química
  SMIL     Tractament de la informació multimèdia
  SSML     Síntesi de la veu
  -------- ---------------------------------------------

-   Molts programes que feien servir formats binaris han passat a algun
    tipus d'XML:

Microsoft Office
----------------

Va passar de guardar els documents en binari .DOC a XML .DOCX (OOXML) al
estandaritzar-lo

OpenOffice.org
--------------

Molts dels documents de configuració dels sistemes operatius estan en
XML!

Linux
-----

``` {.sourceCode .bash}
$ locate .xml | wc -l
21829
```

Windows
-------

``` {.sourceCode .bash}
C:\> dir /a-d /s *.xml | find /c /v “”
698
```

Extensible
==========

Un altre dels avantatges de XML és que es fàcilment extensible i
adaptable

-   Creem els tags que tinguin significat per nosaltres
-   Podem crear el vocabulari que ens faci falta per allò que busquem

Però hi ha formes de definir quina és la estructura que nosaltres
definim

Hi ha diversos estàndards *DTD*, *XML Schema Language*, *Relax NG*,
etc..

-   Ens serviran per comprovar que el document compleix amb les normes
    del vocabulari

Perquè es fa servir?
====================

XML s'està fent servir en múltiples camps:

-   Contingut de pàgines web

Un dels estàndards que es fan servir en pàgines web XHTML està basat en
XML Però XML de forma inherent té múltiples formes en que pot ser
representat (**XSL-FO**, **CSS**, ...)

-   Computació distribuïda

L'intercanvi de dades entre sistemes diferents que permetin les crides
entre objectes entre màquines

-   Comerç electrònic

Bussines to Bussines (**BTB**), Bussines to Consumer (**BTC**)

-   Reduir la càrrega de servidors

Problemes
=========

XML ocupa més espai a disc que els seus equivalents en format binari

-   Hi ha tendència a crear fitxers molt grans
-   Això pot tenir un impacte en el rendiment dels programes
-   El fitxer és molt gran!
-   En format text!

Però això a vegades és compensat per:

-   La facilitat d'interoperatibilitat entre programes
-   El preu de l'emmagatzematge és baix

