Validació XML amb DTD
=====================

Index
=====

Què és el DTD?
==============

El DTD (Document Type Definitions) és la forma de definició d'esquemes
que va sortir primer

-   Va sorgir en el temps del **SGML**
-   Encara hi ha molts documents XML que es validen amb DTD (tot i que
    té les seves limitacions)
-   Alguns documents HTML fan servir DTD per definir-ne la estructura

``` {.sourceCode .html}
<!DOCTYPE html PUBLIC “-//W3C//DTD XHTML 1.0 Transitional//EN”
      “http://www.w3c.org/TR/xhtml11-transitional.dtd”>

<html xmlns=”http://w3c.org/1999/xhtml”>
```

Limitacions del DTD
===================

-   El DTD no és un llenguatge XML: Això obliga a aprendre dos
    llenguatges en comptes d'un!
-   Pot ser que no puguem fer-hi tot el que ens faci falta: **DTD no pot
    fer comprovacions del contingut de dades**

``` {.sourceCode .xml}
<data>.</data>
```

-   No pot comprovar que és una data: Pot fer falta definir restriccions
    en el document i **DTD no pot: per exemple una data entre 1970 i
    2032**

Objectius
=========

-   L'objectiu principal dels DTD és donar un mecanisme per validar les
    estructures dels documents XML
-   El document XML es comprovarà amb l'esquema DTD
-   Hi poden haver documents ben formats que no siguin vàlids
-   Pot ser compartit entre organitzacions o fins i tot definir-lo com a
    estàndard públic
-   Això permetrà conèixer les especificacions que defineixen un
    vocabulari concret

Validació
=========

-   La majoria dels validadors poden validar DTD sense problemes
-   Per exemple amb xmllint ho podem fer amb 'valid':

``` {.sourceCode .bash}
$ xmllint --noout --valid exercici.xml
$
```

-   També es pot fer amb el programa *XML Copy Editor*, etc...

![image](xmlcopyeditor.png)

Definició del DTD en el document XML
====================================

Definició de DTD Interna
------------------------

-   Es poden incorporar DTD dins dels documents XML

``` {.sourceCode .xml}
<?xml version=”1.0” encoding=”UTF-8” ?>
<!DOCTYPE process [
<!ELEMENT adress (#PCDATA)>
<!ELEMENT process (adress)>
]>
<process>
    <adress>http://www.iescendrassos.net</adress>
</process>
```

-   Tot i que es pot fer és millor fer-los externs
-   Definir-los externament permet compartir-los més fàcilment i a més:

> Separa les dades de la estructura

Definició de DTD Externa
------------------------

Per definir un DTD extern fem servir l'etiqueta DOCTYPE dins del
document XML:

``` {.sourceCode .xml}
<!DOCTYPE alumnes SYSTEM “http://www.iescendrassos.net/alumnes.dtd”>
```

-   Es poden definir **DOCTYPES** d'Internet

``` {.sourceCode .xml}
<?xml version=”1.0” encoding=”UTF-8” ?>
<!DOCTYPE alumnes SYSTEM “alumnes.dtd”>
```

-   O en fitxers locals de la màquina

``` {.sourceCode .html}
<!DOCTYPE alumnes SYSTEM “C:\alumnes.dtd”>
```

-   I després només hem de crear el DTD extern en el lloc adequat:

``` {.sourceCode .dtd}
<!ELEMENT nom (#PCDATA)>
<!ELEMENT cognom (#PCDATA)>
<!ELEMENT persona (nom,cognom)>
```

DOCTYPE
=======

-   La declaració DOCTYPE és el que es posa en el document XML per
    indicar el DTD

![image](doctype.png)

Tipus de DTD
============

-   En el tipus de DTD hi solem trobar dues paraules clau: **SYSTEM** o
    **PUBLIC**

SYSTEM
------

-   Fa els DTD privats
-   Això no implica que no es puguin compartir
-   Sempre va seguit de l'adreça
-   És el que fan servir els individuals

![image](system.png)

PUBLIC
------

-   Implica que està definit per algun tipus de cos estàndard (oficial
    o no) l'ha definit i deixat disponible pel públic

ex. El fan servir els DOCTYPE de HTML

-   Va seguit d'un identificador i després l'adreça

![image](public.png)

FPI
===

![image](fpi.png)

El llenguatge
=============

Definició d'etiquetes
---------------------

-   La base de tot rau en la definició dels elements que composen el
    llenguatge
-   S'han de definir tots els elements que formen el document:

``` {.sourceCode .dtd}
<!ELEMENT nom contingut >
```

En el contingut és on definirem completament l'estructura del document
XML:

– Si hi ha dades – Si conté altres etiquetes – Etc...

![image](etiqueta.png)

Elements
========

Elements genèrics
-----------------

-   Si tenim elements que poden tenir qualsevol cosa a dins els podem
    definir amb ANY
-   Si tenim un XML semblant a aquest:

``` {.sourceCode .xml}
<persona>Federicu Pi</persona>

<persona>
    <nom>Xavier</nom>
    <cognom>Sala</cognom>
</persona>
```

-   Podem definir &lt;persona&gt;:

``` {.sourceCode .xml}
<!ELEMENT persona ANY>
```

Entrada de text: \#PCDATA
-------------------------

Un **\#PCDATA** indica que l'element que estem definint només pot tenir
dades a dins

-   Per definir una cosa com aquesta:

``` {.sourceCode .xml}
<nom>Xavier</nom>
<cognom>Sala</cognom>
```

-   Es definiria el DTD amb:

``` {.sourceCode .xml}
<!ELEMENT nom (#PCDATA)>
<!ELEMENT cognom (#PCDATA)>
```

Elements sense dades
--------------------

Si tenim elements que no tenen contingut els podem definir amb EMPTY

``` {.sourceCode .xml}
<persona>
    <nom>Xavier</nom>
    <cognom>Sala</cognom>
    <real />
</persona>

<persona>
    <nom>Federicu</nom>
    <cognom>Pi</cognom>
</persona>
```

``` {.sourceCode .dtd}
<!ELEMENT real EMPTY>
```

Elements fills
--------------

El més normal és que una etiqueta en contingui d'altres

``` {.sourceCode .xml}
<persona>
    <nom>Xavier</nom>
    <cognom>Sala</cognom>
</persona>
```

-   Els definim posant les etiquetes que pot contenir:

``` {.sourceCode .dtd}
<!ELEMENT nom (#PCDATA)>
<!ELEMENT cognom (#PCDATA)>
<!ELEMENT persona (nom,cognom)>
```

Es poden definir elements recursius

![image](fills1.png)

-   Però s'ha d'anar amb compte perquè podem generar un problema molt
    més gran
-   Definir elements que no s'acabin mai i que per tant no puguin ser
    validats ...

![image](fills2.png)

-   O sigui que es poden fer però sempre s'han de tractar amb cura

Modificadors dels elements fills
--------------------------------

-   Podem especificar quantes instàncies dels elements fills hi poden
    haver en un element

![image](modificadors.png)

-   Per tant

![image](modificadors-persones.png)

Operador d'elecció
------------------

-   També tenim un operador que ens permet posar alternatives “|”

``` {.sourceCode .dtd}
<!ELEMENT titol (president|treballador)>
```

-   Ens permetria fer o:

``` {.sourceCode .xml}
<titol>
    <president>Federicu Pi</president>
</titol>
```

-   O per contra:

``` {.sourceCode .xml}
<titol>
<treballador>Federicu Pi</treballador>
</titol>
```

Parèntesis
----------

-   Evidentment podem fer tantes agrupacions de parèntesi com ens facin
    falta
-   Centre i radi o bé centre i diàmetre

``` {.sourceCode .dtd}
<!ELEMENT cercle (centre, (radi | diametre))>
```

-   cognom o nom+inicials+cognom o nom+cognom

``` {.sourceCode .dtd}
<!ELEMENT comic (cognom | ( nom,(inicials, cognom) | cognom ))>
```

``` {.sourceCode .dtd}
<!ELEMENT paragraf (#PCDATA | nom | professio | marca | data )* >
```

Limitacions
-----------

-   No es poden posar etiquetes i **\#PCDATA** que no siguin
    “contingut mesclat”.
-   Això és erroni:

``` {.sourceCode .dtd}
<!ELEMENT exercici (#PCDATA, apartat*)>
```

-   Tampoc podem duplicar definicions:

``` {.sourceCode .dtd}
<!ELEMENT exercici (#PCDATA)  >
<!ELEMENT exercici (apartat*) >
```

-   O sigui que hem de fer això (tot i que pot no ser el que volem)

``` {.sourceCode .dtd}
<!ELEMENT exercici (#PCDATA, apartat)*>
```

Expressions deterministes
-------------------------

-   Una altra de les limitacions és que obliga a que les expressions han
    de ser deterministes
-   Això vol dir que no es pot fer això:

``` {.sourceCode .dtd}
<!ELEMENT terrestre((persona,home)|(persona,dona))>
```

-   Això és perquè el processador al rebre 'persona' no pot saber quina
    és l'expressió que estem fent
-   Ho hem d'escriure:

``` {.sourceCode .dtd}
<!ELEMENT terrestre(persona,(home|dona))>
```

-   El mateix ens passarà si fem servir modificadors:
-   Per exemple perquè surti en l'ordre que vulguem autor i títol:

``` {.sourceCode .dtd}
<!ELEMENT llibre((autor?,titol?)|(titol?,autor?))>
```

-   Després de rebre autor en quina expressió estem? I si rebem títol?
-   Ho hauríem d'escriure d'aquesta forma:

``` {.sourceCode .dtd}
<!ELEMENT llibre((autor,titol?)|(titol,autor?)|EMPTY)>
```

-   Ara no queda cap dubte de on som al rebre una etiqueta

Atributs
========

-   Ens pot interessar limitar quins atributs pot contenir una etiqueta
-   No es poden fer atributs genèrics s'han de definir en cada element
-   Els atributs es defineixen amb **ATTLIST**

![image](atributs.png)

Atributs dels atributs
----------------------

-   Un aspecte curiós és que els atributs tenen atributs que permeten
    definir com s'usaran

![image](atributs-atributs.png)

``` {.sourceCode .dtd}
<!ATTLIST equip posicio ID #REQUIRED>
<!ATTLIST nom dni NMTOKEN #IMPLIED>
<!ATTLIST document versio CDATA #FIXED "1.0">
```

-   L'etiqueta equip ha de tenir l'atribut “posicio” obligatòriament
-   El dni associat al nom és opcional
-   La versió del document és “1.0” i no es pot canviar

Tipus de dades atributs
=======================

-   Existeixen diferents tipus de dades que es poden fer servir com a
    tipus d'atributs

![image](tipus-dades.png)

CDATA i enumeracions
====================

-   Els atributs de tipus **CDATA** permeten la entrada de text de
    qualsevol tipus

``` {.sourceCode .dtd}
<!ATTLIST empresa nom CDATA #REQUIRED>
```

-   Ens permetria definir coses com

``` {.sourceCode .xml}
<empresa nom=”Microsoft Corporation”>
<empresa nom=”6tema desastre, SA”>
```

-   Un cas especial serien les enumeracions

``` {.sourceCode .dtd}
<!ATTLIST curs inici (setembre|octubre) #IMPLIED>
```

-   Que permetran que el valor de l'atribut sigui o “setembre” o
    “octubre” i cap més

ID
==

-   **ID** serveix per quan els atributs es poden usar com
    identificadors d'un element dins del document
-   Els valors no es poden repetir
-   Els valors han de començar per una lletra o pel caràcter de
    subratllat

``` {.sourceCode .dtd}
<!ATTLIST equip posicio ID #REQUIRED>
```

``` {.sourceCode .xml}
<equip posicio=”primer”>F.C.Barcelona</equip>
<equip posicio=”tretzè”>Real Madrid C.F.</equip>
```

IDREF o IDREFS
==============

-   Es fan servir quan el valor ha de ser una referència a un
    identificador

``` {.sourceCode .dtd}
<!ATTLIST recepta id ID #REQUIRED>
<!ATTLIST ingredient ref IDREF #IMPLIED>
```

``` {.sourceCode .xml}
<llibrecuina>
    <recepta id=”recepta1”>Patates fregides</recepta>
    <recepta id=”recepta2”>Patates bullides</recepta>
    <ingredient ref=”recepta1”>oli</ingredient>
</llibrecuina>
```

-   **IDREFS** ens permet fer una llista d'**ID** separades per espais

    > &lt;!ATTLIST ingredient refs IDREFS \#IMPLIED&gt;

``` {.sourceCode .xml}
<ingredient refs=”recepta1 recepta2”>patates</ingredient>
```

NMTOKEN i NMTOKENS
==================

-   Els tipus **NMTOKEN** permeten que especifiquem qualsevol caràcter
    acceptat per XML
-   Això implica text sense espais
-   Com la majoria de vegades el NMTOKENS ens en permet especificar
    diversos separats per espais

``` {.sourceCode .dtd}
<!ATTLIST home naixement NMTOKEN #IMPLIED>
<!ATTLIST home fills NMTOKENS #IMPLIED>
```

-   O sigui

``` {.sourceCode .xml}
<home naixement=”1975”>Carles Punxatí</home>
<home fills=”Maria Pere Albert”>Filomenu Pi</home>
```

NOTATION
========

-   Aquest atribut permet associar una aplicació a un tipus d'informació

``` {.sourceCode .dtd}
<!NOTATION jpg PUBLIC “JPEG”>
<!ATTLIST persona foto NOTATION jpg #IMPLIED>
```

-   Es pot canviar PUBLIC per SYSTEM per poder definir una aplicació
    en particular. Per exemple un tipus *MIME*

``` {.sourceCode .dtd}
<!NOTATION jpg SYSTEM “image/jpeg”>
```

ENTITY / ENTITIES
=================

-   Les entitats permeten definir les constants pel document
-   Els atributs poden fer referència a constants

``` {.sourceCode .dtd}
<!ATTLIST A a ENTITY #IMPLIED>
<!ATTLIST A b ENTITIES #IMPLIED>
```

-   Podem definir les nostres entitats:

``` {.sourceCode .dtd}
<!ENTITY nom “valor”>
```

-   I després usar-les en el document

``` {.sourceCode .dtd}
&nom;
```

Entitats predefinides i externes
================================

-   Tenim entitats que ens permeten escriure caràcters amb el seu valor
    hexadecimal:

``` {.sourceCode .bash}
&#41;
```

-   I les ja conegudes

``` {.sourceCode .bash}
&lt; &gt; &amp; &apos;
```

-   També podem carregar els valors d'un document extern

``` {.sourceCode .dtd}
<!ENTITY doc SYSTEM
“http://www.iescendrassos.net/altre.xml”>
```

Entitats
========

-   Un dels usos de les entitats en els DTD és combinar diferents parts
    del DTD per crear-ne un de sol:

``` {.sourceCode .dtd}
<!ENTITY % persona SYSTEM “persona.dtd”>
<!ENTITY % adreca SYSTEM “adreca.dtd”>
    %persona;
    %adreca;
<!ELEMENT home (persona, adreca)>
```

-   Això permet reutilitzar els DTD que tinguem si els hem dissenyat amb
    cura

Altres
======

-   També disposem d'unes comandes més que ens permeten especificar
    seccions condicionals:

``` {.sourceCode .dtd}
<![INCLUDE [declaracions visibles]]>
<![IGNORE [declaracions invisibles]]>
```

-   Al fer servir **INCLUDE** el contingut és visible pel DTD i a
    l'inrevés

``` {.sourceCode .dtd}
<![IGNORE[<!ELEMENT nom #PCDATA]]>
```
