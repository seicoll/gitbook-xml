# CSS (Cascade Style Sheets)

## Introducció

> Els **Cascading Style Sheets (CSS)** són la forma de donar format a les dades d'un document.

Les possibilitats de format de CSS es poden dividir en 3 àrees:

* **Fonts i colors**: format del contingut
* **Distàncies i marcs**
* **Layout**: modificar la posició dels elements de la pàgina web

Abans que es generalitzés l'ús dels **CSS**, s'utilitzaven etiquetes especials per modificar l'aspecte dels elements d'una pàgina.

```html
<body>
  <h1><font color="red" face="Arial" size="5">Titular de la pàgina</font></h1>
  <p><font color="gray" face="Verdana" size="2">Un paràgraf de text.</font></p>
  <p><font color="gray" face="Verdana" size="2">Un altre paràgraf de text.</font></p>
</body>
```

En els sites amb moltes pàgines, els **canvis de formats** de eren **molt laboriosos**.
* Calia anar element per element, a cada pàgina!!

### Avantatges del CSS

* Permet **separar el contingut de la seva presentació**.
* Permet **definir les regles de presentació** d'un document a partir de les etiquetes que conté.
* Permet aplicar les regles de presentació a **múltiples pàgines**.

### Versions

* **CSS 1** (1996)
* **CSS 2** (1998) 
* **CSS 2.1** es finalitza al 2011.
* **CSS 3** (versió actual) 

![CSS3](uf1_images/css3.png)

## Utilització dels CSS

Per **aplicar fulles d'estil CSS a HTML** es pot fer a través de tres formes:

* CSS **intregades** en un element HTML5 
  * Amb l'atribut `style`  en etiquetes html.

* CSS **internes** al document 
  * Amb una etiqueta `<style>`


* CSS **externes** al document 
  * Amb un arxiu extern .css i utilitzant l'etiqueta `<link>`


## CSS intregades en una etiqueda html

Permet especificar regles CSS d'una etiqueta HTML.
> És la forma **menys recomanada** de fer-ho ja que complica la compartició.

Es col·loca dins d'una etiqueta de HTML amb l'atribut `style`

![image](uf1_images/forbidden.jpg)

**Exemple 1: Estil definit per una etiqueta**

```html
<p style="color:#990000">
   Això és un paràgraf de color vermell
</p> 
<p style="color:#000099">
   Això és un paràgraf de color blau
</p> 
```

El resultat serà:

![image](uf1_images/uf1_p_css.png)

**Exemple 2: Estil definit en petites parts d'una pàgina**

Mitjançant l'etiqueta `<span>` i l'atribut `style`.

```html
<p>
   Això és un paràgraf que té diverses paraules  
   <SPAN style="color:green">de color verd</SPAN>. fàcil, no?
</p>
```

El resultat serà:

![image](uf1_images/uf1_span.png)

**Exemple 3: Estil definit en una part de la pàgina**

Mitjançant l'etiqueta `<div>` i l'atribut `style`.

```html
<div style="color:#000099; font-weight:bold">
    <h3>Aquestes etiquetes van en <i>blau i negreta</i></h3>
    <p>
        Seguim dins del DIV, encara funcionen els estils
    </p> 
</div>
```

El resultat serà:

![image](uf1_images/uf1_div-css.png)

##  CSS internes al document 

* Permet especificar regles CSS dins del document HTML.
* Estil definit s'aplicarà a tota la pàgina HTML.
* **No** és la forma més recomanada de fer-ho ja que complica la compartició.
* Es defineixen dintre del `<head>`.
* S'utilitza l'etiqueta `<style>` i `</style>`

```html
<html>
<head>
   <title>Exemple d'estils en una pàgina</title>
   <style>
       h1 {
          text-decoration: underline;
          text-align:center
        }
        p {
          font-Family:arial,verdana; 
          color: white; 
          background-color: black
        }
        body {
          color:black;
          background-color: #cccccc; 
          text-indent:1cm
        }
    </style>
</head> 
<body>
   <h1>Pàgina amb estils</h1>
   Benvinguts
   <p>n-èssim exemple sense massa importància en el contingut</p>
</body>
</html>
```

El resultat serà:

![image](uf1_images/uf1_pag-estil.png)


## CSS Externes

* Estil definit per **tot un lloc web**.
* Es crea un **arxiu a part** on guardem tota la informació d'estils de la pàgina.

> **És el millor sistema**. És reaprofitable per totes les pàgines del lloc web.

**Exemple de document CSS:**
```html
p  {
 font-size : 12pt;
 font-family : arial,helvetica;
 font-weight : normal;
} 
h1  {
 font-size : 36pt;
 font-family : verdana,arial;
 text-decoration : underline;
 text-align : center;
 background-color : Teal;
}
td  {
 font-size : 10pt;
 font-family : verdana,arial;
 text-align : center;
 background-color : 666666;
}
body  {
 background-color : #006600;
 font-family : arial;
 color : White;
}
```

### Associar full d'estils CSS a una pàgina HTML

Un cop tenim creat l'arxiu CSS, l'hem d'**enllaçar** amb les diferents pàgines que tenim, mitjançant l'etiqueta `<link>`

```html
<head>
   <link rel="stylesheet" href="estil.css">
</head>
```

* `rel="stylesheet"`: indica que l'enllaç és una fulla d'estils.
* `href="estil.css"`: indica el nom del fitxer CSS dels estils.

---

Regles d'ús
===========

* Els estils s'hereden d'una etiqueta a un altre.

**Ex:** Definim l'estil del *body*, les etiquetes de dins tenen el mateix estil.

* Sempre es té en compte la declaració més particular.

**JERARQUÍA** ( Ordre d'importància de menys a més )

* Per tot un lloc web
  
* `<style>` a la capçalera de la pàgina
* `<div>` caixes de tipus bloc
* `<span>` caixes de tipus inline

*Style de l'etiqueta en qüestió*

Sintaxis del css
================

-   S'utilitzen atributs com: font-size, font-decoration, etc... Seguits
    de “:” i el valor que els hi assignem.

**Exemple**

``` {.sourceCode .css}
font-size: 10pt; 

text-decoration: underline; 

color: black; 
```

Exemples de regles
==================

Tipus de lletra
---------------

![image](font.png)

Paràgrafs
---------

![image](paragrafs.png)

Fons de pàgina
--------------

![image](fondos.png)

Atributs amb unitats
====================

-   Es poden definir atributs amb els següents formats:

**Absoluts:**

> Pixels(px)
>
> Centimetres(cm)
>
> Polzades(in)
>
> Punts(pt) (72 punts = 1 polzada)
>
> Piques (1 pica=12 punts)

**Relatius:**

> Percentatges(%)
>
> EM (alçada “M”)
>
> Ex (alçada “x”)

Més info a: <https://www.w3.org/Style/Examples/007/units.en.html>

Coses a saber per començar amb CSS
==================================

-   Sintaxis. Els selectors
-   *Classes* i *pseudoclases*
-   Font i text
-   Propietats de les fonts
-   Propietats de text
-   Unitats de mesura
-   Fons i color
-   Color i background
-   Formatat de les caixes
-   Blocs i caixes

**Estructures**

-   Taules
-   Llistes

**Posicionament**

-   Absolut, relatiu, fixed...
-   Float

**Altres...**

-   Cursors
-   Barres de desplaçament

Tipus de selectors
==================

-   Selectors bàsics: elements HTML
-   Selectors de classe
-   Selectors ID
-   Selectors contextuals
-   Selectors pseudoclasse: links
-   Selectors pseudoelements
-   Grups de selectors

Selectors de classe
-------------------

-   Ens serveix per declarar estils que s'utilitzaran varies vegades.

``` {.sourceCode .css}
.nomdelaclasse {
                 atribut: valor;
                 atribut2:valor2; ..} 
```

-   Un cop definida la podem utilitzar en qualsevol etiqueta

```html
<etiqueta class="nomdelaclasse">
```

Selectors ID
------------

-   Ens serveix per declarar estils que s'utilitzaran UNA SOLA vegada.

``` {.sourceCode .css}
#nomdelID {
                 atribut: valor;
                 atribut2:valor2; ..} 
```

-   Un cop definida la podem utilitzar en qualsevol etiqueta

```html
<etiqueta id="nomdelID">
```

Selectors contextuals
---------------------

``` {.sourceCode .css}
h1 b { 
        font-weight: 
        bold; 
        color: red; 
    }
```

-   Només les negretes que siguin descendents d'un element H1 seran de
    color vermell.
-   Vegem l'style sheet anterior en un exemple concret:

![image](contextual.png)

Selectors pseudoclasse: links
-----------------------------

-   Aquest és un tipus de selector una mica més especial que
    els anteriors. És un **ESTAT DETERMINAT**.

![image](links.png)

Selectors pseudoelements
------------------------

Aquest tipus de selector és molt específic i prové d'efectes tipogràfics
tradicionals.

**:first-letter**:   Permet seleccionar la primera lletra

**:first-line**:   Primera línia

Grups de selectors
------------------

-   Són en realitat selectors, sinó una manera abreujada de
    definir estils. Permeten assignar el **MATEIX** estil a
    diversos selectors.

```css
h1, h2, p {
    font-family: Trebuchet MS;
    color: olive;
    margin-left: 30px; 
    margin-top: 40px; 
    }
```

Més família… pares i germans
----------------------------

**Pare:**:   L'element que conté directament al fill que es vol formatar.

```css
div > p { color =#00FF00; }
```

**Germà:**:   L'element que precedeix directament, dintre el mateix element pare,
    al que es vol formatar.

```css
p+p { color=#00FF00; }
```

El selector universal
---------------------

-   El comodí `\*`
-   Serveix per totes les caixes

```css
* {
 padding: 0;
 margin: 0;
}
```

Model de caixes \[Box Model\]
=============================

-   Quan es visualitza qualsevol cosa amb CSS és tractada com si estes
    dins d'una caixa rectangular
-   Cada caixa té quatre components

![image](box-model.png)

-   Els atributs “width” i “height” permeten forçar la mida de la caixa

![image](mides-caixa.png)

-   Per defecte els valors de margin, padding i border estan a zero

Podem canviar-ne els valors amb les propietats:

**Margin**

:   margin, margin-left, margin-right, margin-top, margin-bottom

**Padding**

:   padding, padding-left, padding-right, padding-top, padding-bottom

Amb el 'border' hi ha moltes més possibilitats:

**border-style:**

:   pot ser none, solid, dashet, dotted, double, groove, ridge, inset,
    outset

**border-width:**

:   especifiquem l'amplada. El més corrent és fer-ho amb pixels (10px)

**border-color:**

:   el color que tindrà. Pot ser amb el nom en anglès, amb la
    funció rgb() o en hexadecimal

**border:**

:   tot de cop especificant un rere l'altre amplada,estil i color

Layout
======

Les caixes es poden comportar de formes diferents en respecte a les
altres. El més corrent són dos comportaments:

**block:**

:   Blocs de contingut que ocupen tot l'espai d'una línia. Fa que la
    caixa defineixi un salt de línia rere seu.

**inline:**

:   Les altres caixes permeten que les altres es posin al seu costat.

![image](inline-block.png)

-   El primer element és un paràgraf que ocupa tota la línia perquè és
    un element de *block*.
-   El segon element és un enllaç que ocupa només l'espai necessari pel
    seu contingut ja que és un element *inline*.
-   Els elements inline no poden tenir amplada i per això s'han definit
    els *\*inline-block*\*.
-   Són elements inline que es comporten com un block

![image](inline-block2.png)

Amagar contingut
----------------

-   Una caixa serà invisible si se li aplica la propietat
    'visibility:hidden;'
-   Es reserva l'espai que ocupava l'etiqueta i queda buit.

![image](visibility.png)

Eliminar contingut
------------------

-   Perquè una etiqueta no es representi es fa servir 'display:none'
-   L'espai que ocupava l'etiqueta queda lliure i és ocupat pels
    altres elements.

![image](hidden.png)

Posicionament \[Layout\]
========================

-   CSS permet modificar el posicionament en el que es mostra
    cada caixa.
-   El posicionament en CSS reposa sobre quatre opcions:

> Posicionament Normal
>
> Posicionament Relatiu
>
> Posicionament Flotant
>
> Posicionament Absolut

Posicionament Normal
--------------------

-   Es tracta del funcionament per defecte, les caixes apareixen una
    rere l'altra i de dalt a baix

![image](posicionament-normal.png)

Posicionament Relatiu
---------------------

-   Consisteix en posicionar la caixa segons el posicionament normal i
    llavors desplaçar-la respecte de la seva posició original.
-   Podem canviar la posició “relativa” posant valors a left, right, top
    o bottom
-   Desplaça la caixa fora de la seva posició normal en el fluxe
-   Marca la posició original de l'element com a protegida (la resta de
    caixes es pensen que encara hi és.

![image](posicionament-relatiu2.png)

-   Top, right, bottom o left es calculen respecte la posició original
    en el fluxe.

> Top:25px -> es desplaça 25 píxels des de dalt de la posició normal
> de la caixa (es desplaça cap a baix)
>
> Right:25px -> es desplaça 25 píxels de la dreta de la posició
> original (es desplaça cap a l'esquerra)

![image](posicionament-relatiu3.png)

-   Canviar la posició relativa pot fer que el contingut de dues caixes
    quedi superposat

![image](posicionament-relatiu.png)

Posicionament Absolut
---------------------

-   Es pot posicionar una caixa en un lloc concret fent servir
    'position:absolute'

![image](posicionament-absolut.png)

-   Treu l'element del fluxe
-   L'element “s'eleva” i tots els altres elements es comporten com si
    no hi fos
-   La resta del contingut no quedarà al voltant sinó que pot quedar per
    sota

![image](posicionament-absolut2.png)

-   El posicionament absolut d'un element fa referència al seu
    contenidor, ja sigui amb *relatiu*, *absolut* o *fixed*.
-   És a dir que *top*, *right*, *bottom* o *left* depenen del
    seu contenidor.
-   Si no hi ha cap element contenidor, els valos faran referència a
    l'element més alt de l'estructura HTML (*body*)

Consell absolut
---------------

> Fer les posicionaments absolut dins d'un posicionament relatiu, sense
> cap valor.

![image](posicionament-absolut3.png)

Exemple absolut sobre relative
------------------------------

![image](posicionament-absolut4.png)

Posicionament fixed
-------------------

-   Un cas especial de posicionament absolut és el posicionament fix.
-   Ens fixa una caixa en la pantalla de manera que no es mourà encara
    que es mogui la pàgina amunt o avall

![image](posicionament-fixed.png)

Posicionament Flotant
---------------------

'float' ens permet especificar una caixa flotant que deixa que les
altres caixes es posin al seu voltant

![image](posicionament-float.png)

-   La caixa que hem definit float:left es posa primer i les altres es
    posen al seu voltant sense sobreesciure-la

El paràmetre “clear” pot tenir diferents valors:

![image](clear.png)

Resum visual de posionaments
============================

Inline vs block
---------------

![image](resum-inline-block.png)

Absolute
--------

![image](resum-absolute.png)

Fixed
-----

![image](resum-fixed.png)

Relatiu
-------

![image](resum-relatiu.png)

Float
-----

![image](resum-float.png)

Z-index
=======

-   Controla la profunditat de les capes

![image](z-index.png)