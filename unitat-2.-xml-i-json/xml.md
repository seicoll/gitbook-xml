# XML (Extensible Markup Language)

> **XML** és un llenguatge de descripció d'informació.

- XML és un format de text estandarditzat que serveix per representar i transportar informació estructurada.
- El consorci **W3C** va desenvolupar una alternativa a l'HTML que podés satisfer les necessitats futures del web.

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

- XML no es preocupa de com es presentaran les dades als usuaris
- Per fer la presentació ja s'han desenvolupat mecanismes:
  - **CSS**, **XSL-FO**, etc.

## Extensible

Un altre dels avantatges de XML és que es fàcilment **extensible i adaptable**:

> XML **no defineix un nombre limitat d'etiquetes**.

Podem crear les etiquetes (tags) que tinguin significat per nosaltres. Podem crear el vocabulari que ens faci falta per allò que busquem.

A més, hi ha formes de definir quina és la **estructura** que nosaltres definim.

- Hi ha diversos estàndards _**DTD**_, _**XML Schema Language**_, _**Relax NG**_, etc..
- Ens serviran per comprovar que el document compleix amb les normes del vocabulari.

## Formats Estàndards

Tenim la capacitat de crear un vocabulari per representar dades d'un àmbit.

Ja hi ha vocabularis estàndards XML:

- **SVG**: Pensat per gràfics vectorials escalables 2D
- **MathML**: Representació de fórmules matemàtiques
- **CML**: Intercanvi d'informació química
- **SMIL**: Tractament de la informació multimèdia
- **SSML**: Síntesi de la veu

## Principals usos d'XML

XML s'està fent servir en múltiples camps:

- Un dels estàndards que es fan servir en pàgines web XHTML està basat en XML.
- Desenvolupament de **documentació tècnica** en diferents àmbits acadèmics, investigació, ...
- Intercanvi d'informació entre sistemes informàtics (distribuïts).
- Intercanvi d'informació entre empreses.
- Aplicacions ofimàtiques: **Microsoft Office, OpenOffice**, ..
  - Abans feien servir formats binaris però han passat a algun tipus d'XML.
  - Va passar de guardar els documents en binari `.DOC` a XML `.DOCX` (OOXML).
- Molts dels **documents de configuració** dels sistemes operatius estan en XML:

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

- Els fitxers XML tendeixen a ocupar molt d'espai.
  - XML ocupa més espai a disc que els seus equivalents en format binari.
  - Lentitud en el temps de càrrega.
  - Temps de transferència més elevat.

Però això a vegades és compensat per:

- La facilitat d'interoperabilitat entre programes.
- El preu de l'emmagatzematge és baix.

---

# Creació documents XML

## Declaració de XML

Els documents XML han de començar amb la declaració que indiqui quina versió estem fent servir d'XML.

```markup
<?xml version="1.0" ?>
```

Atribut **Encoding** defineix el joc de caràcters que fem servir en el document:

```markup
<?xml version="1.0" encoding="UTF-8" ?>
```

## Regles bàsiques

### Tots els documents tenen una etiqueta arrel

L'etiqueta arrel és aquella que es defineix després de la declaració del document.

```markup
<persona>           <!-- Etiqueta arrel -->
  <nom>Pere Pi</nom>
  <nom>Marta Mata</nom>
</persona>          <!--Tancament etiqueta arrel -->
```

Aquest no seria un document XML correcte:

```markup
  <nom>Pere Pi</nom>
  <nom>Marta Mata</nom>
```

### Totes les etiquetes s'han de tancar

```markup
<article>Pissarra</article>
```

No es poden fer coses com les que permet HTML:

```markup
<img src="pissarra.png">
```

Si tenim una etiqueta sense dades el podem representar amb el tancament `/>`:

```markup
<article nom="pissarra"/>
```

### Les etiquetes han d'estar niades correctament

Cal tancar les etiquetes per l'ordre invers en què s'han obert.

**INCORRECTE**

```markup
<inventari>
  <article>
    Pissarra
  </inventari>
</article>
```

Les etiquetes estan tancades en ordre invers i per tant és incorrecte.

### Les majúscules i minúscules són diferents

Per tant aquestes dues són etiquetes diferents:

```markup
<article>Pissarra</article>
<Article>Pissarra</Article>
```

**I això és incorrecte!**

```markup
<Article>Pissarra</article>
```

### Els valors dels atributs han d'estar entre cometes

Els valors dels **atributs** han d'estar entre **cometes** fins i tot si són números

I no importa si són cometes simples o dobles.

```markup
<article quantitat="3">Pissarra</article>
```

**I això és incorrecte:**

```markup
<article quantitat=3>Pissarra</article>
```
