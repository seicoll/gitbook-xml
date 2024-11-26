# XML

## Introducció a XML

### Compartició d'informació

* Les empreses necessiten **compartir** la informació entre elles (factures, comandes, etc).
* La informació pot estar en **diversos formats** (fulles de càlcul, bases de dades, fitxer pdf, etc.).

**Problema:**

* La informació **no està estructurada**.
* Fa difícil l'**automatització** d'aquesta informació amb un sistema informàtic.

**Solució:**

* **Acordar quin format** o estructura ha tenir la informació.
* A més, podrem utilitzar **eines estàndards per validar** si el document compleix amb l'especificació acordada.

### Els llenguatges de marques

Un **llenguatge de marques** combina dades i etiquetes que les marquen i que contenen informació addicional sobre l'estructura del text o la seva presentació.

Les marques estan barrejades amb el propi text.

```markup
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

```javascript
{ "persona": {
    "nom": "Sergi",
    "cognom": "Coll"
} }
```

**Exemple HTML**

El llenguatge de marques més conegut és l'**HTML** (el de les pàgines web) destinat a l'intercanvi d'informació a través d'Internet.

```markup
<html>
    <head>
    <title> Pàgina </title>
    </head>
    <body>
        Hola!
    </body>
</html>
```



## SGML

> La primera tecnologia estandarditzada de llenguatges de marques va ser l'**SGML**

Es va fer servir com estàndard de la informació **de propòsit general**. Partia de la idea de que s'han de **separar les dades** d'un document **de la seva forma**.

Però:

* La majoria dels documents estaven destinats a la **impressió**.
* Era terriblement **complex** de manera que només el feien servir els especialistes.

## HTML

L'any 1989 Tim Berners-Lee i Anders Berglund van crear un llenguatge basat en etiquetes destinat a compartir informació per Internet: **HTML**.

HTML és un format que descriu la visualització d'una pàgina web.

La web s'ha fet cada vegada més i més popular:

* Cada dia es generen milions de pàgines web amb informació.
* Això implica que cal buscar per trobar la informació que ens interessa.

```markup
<html>
   <head>
     <title>Professor</title>
   </head>
   <body>
      <p>Nom: Federicu Pi </p>
   </body>
</html>
```

**Com pot una màquina determinar automàticament qué és el nom, què és el cognom, ...?**

És necessari alguna forma de poder fer-hi recerques intel·ligents i seleccionar-ne el resultats.

En general, falta una forma de:

* **Buscar**, **moure**, **visualitzar** i **manipular** la informació continguda en els documents HTML.

### Naixement de l'XML

El consorci **W3C** va desenvolupar una alternativa a l'HTML que podés satisfer les necessitats futures del web.

El 1996 el consorci W3C es va proposar introduir el poder i la flexibilitat de l'**SGML** al web.

**SGML** oferia tres avantatges que l'HTML no tenia:

* Extensibilitat
* Estructura
* Validació

## XML (Extensible Markup Language)

> **XML** és un llenguatge de descripció d'informació.

* XML és un format de text estandarditzat que serveix per representar i transportar informació estructurada.

```markup
<persona>
    <nom>
        Sergi
    </nom>
    <cognom>
        Coll
    </cognom>
</persona>
```

Una de les idees més importants és:

> Separar les dades de la presentació

* XML no es preocupa de com es presentaran les dades als usuaris
* Per fer la presentació ja s'han desenvolupat mecanismes:
  * **CSS**, **XSL-FO**, etc.
* Antigament per representar dades es feia separant els valors amb comes o algun altre símbol

```
"Nom","Cognom","Ofici","Naixament","Poblacio","Punts"
"Pere","Pi","Professor","10/04/1978","Olot",12
"Marta","Mata","Inforàtica","19/05/1990","Girona",20
```

* S'ha de saber que la primera línia són metadades
* Afegir-hi noves dades pot ser molt problemàtic pel programa que les llegeixi --> Probablement haurem de canviar el programa
* El format **CSV (Comma separated value)** encara s'utilitza molt en el món de la informàtica, per exportar/importar dades normalment.
  * Es tracta d'enviar la informació utilitzant un caràcter per a separar cada un dels conceptes. Tot i que el nom pugui suggerir que sigui una coma, molts sistemes deixen definir el caràcter a utilitzar (punt i coma, salt de línia,...)

## Característiques dels llenguatges de marques

* Els llenguatges de marques estan **basats en text**.
  * Poden ser **creats i editats** amb qualsevol editor de textos.
* Són fàcilment transportables.
  * La utilització de sistemes de codificació estàndards (UNICODE), fa els documents **fàcilment transportables** entre diferents sistemes (Linux, Windows,etc).
* Però no estan pensats per ser llegits per una persona.
* A diferència d'HTML si que es pot determinar de forma **automàtica** què **signifiquen** les dades.

**Per exemple:**

**HTML**

```markup
<html>
   <head><title>Professors</title></head>
   <body>
     <p>Pere Pi</p>
     <p>Marta Mata</p>
    <body>
</html>
```

**XML**

```markup
<professors>
  <professor>
    <nom>Pere</nom>
    <cognom>Pi</cognom>
  </professor>
  <professor>
    <nom>Marta</nom>
    <cognom>Mata</cognom>
  </professor>
</professors>
```

Es pot determinar automàticament:

* Quina informació conté el fitxer?
* Quina és l'estructura de la informació?
* Quines etiquetes s'han creat per descriure'n la informació?

## Extensible

Un altre dels avantatges de XML és que es fàcilment **extensible i adaptable**:

> XML **no defineix un nombre limitat d'etiquetes**.

Podem crear les etiquetes (tags) que tinguin significat per nosaltres. Podem crear el vocabulari que ens faci falta per allò que busquem.

A més, hi ha formes de definir quina és la **estructura** que nosaltres definim.

* Hi ha diversos estàndards _**DTD**_, _**XML Schema Language**_, _**Relax NG**_, etc..
* Ens serviran per comprovar que el document compleix amb les normes del vocabulari.

## Formats Estàndards

Tenim la capacitat de crear un vocabulari per representar dades d'un àmbit.

Ja hi ha vocabularis estàndards XML:

* **SVG**: Pensat per gràfics vectorials escalables 2D
* **MathML**: Representació de fórmules matemàtiques
* **CML**: Intercanvi d'informació química
* **SMIL**: Tractament de la informació multimèdia
* **SSML**: Síntesi de la veu

## Principals usos d'XML

XML s'està fent servir en múltiples camps:

* Un dels estàndards que es fan servir en pàgines web XHTML està basat en XML.
* Desenvolupament de **documentació tècnica** en diferents àmbits acadèmics, investigació, ...
* Intercanvi d'informació entre sistemes informàtics (distribuïts).
* Intercanvi d'informació entre empreses.
* Aplicacions ofimàtiques: **Microsoft Office, OpenOffice**, ..
  * Abans feien servir formats binaris però han passat a algun tipus d'XML.
  * Va passar de guardar els documents en binari `.DOC` a XML `.DOCX` (OOXML).
*   Molts dels **documents de configuració** dels sistemes operatius estan en XML:

    **Linux**

    ```bash
    $ locate .xml | wc -l
    21829
    ```

    **Windows**

    ```bash
    C:\> dir /a-d /s *.xml | find /c /v “”
    698
    ```

## Desavantatges de XML

* Els fitxers XML tendeixen a ocupar molt d'espai.
  * XML ocupa més espai a disc que els seus equivalents en format binari.
  * Lentitud en el temps de càrrega.
  * Temps de transferència més elevat.

Però això a vegades és compensat per:

* La facilitat d'interoperabilitat entre programes.
* El preu de l'emmagatzematge és baix.

## Versions

##
