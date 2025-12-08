# Introducció als llenguatges de marques

## Què resol un llenguatge de marques?

Un **llenguatge de marques** combina dades i etiquetes que les marquen i que contenen informació addicional sobre l'estructura del text o la seva presentació.

Els llenguatges de marques s'utilitzen per estructurar i presentar informació de manera coherent, estandarditzada i comprensible **per humans i màquines**.

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

---

## Compartició d'informació

Les empreses necessiten **compartir** la informació entre elles (factures, comandes, etc).

La informació pot estar en **diversos formats** (fulles de càlcul, bases de dades, fitxer pdf, etc.).

### Problema:

- La informació **no està estructurada**.
- Fa difícil l'**automatització** d'aquesta informació amb un sistema informàtic.

### Solució:

- **Acordar quin format** o estructura ha tenir la informació.
- A més, podrem utilitzar **eines estàndards per validar** si el document compleix amb l'especificació acordada.

Llenguatges com **XML**, **JSON** i **YAML** permeten l'intercanvi de dades estructurades entre aplicacions diferents. També asseguren que els continguts siguin accessibles en diversos dispositius.

---

## Característiques dels llenguatges de marques

- Els llenguatges de marques estan **basats en text**.
  - Poden ser **creats i editats** amb qualsevol editor de textos.
- Són fàcilment transportables.
  - La utilització de sistemes de codificació estàndards (UNICODE), fa els documents **fàcilment transportables** entre diferents sistemes (Linux, Windows,etc).
- Però no estan pensats per ser llegits per una persona.
- A diferència d'HTML si que es pot determinar de forma **automàtica** què **signifiquen** les dades.

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

- Quina informació conté el fitxer?
- Quina és l'estructura de la informació?
- Quines etiquetes s'han creat per descriure'n la informació?

---

## HTML (HyperText Markup Language)

El llenguatge de marques més conegut és l'**HTML** destinat a l'intercanvi d'informació a través d'Internet.

**Definició:**
HTML és el llenguatge de marques més comú utilitzat per crear pàgines web. Defineix l'estructura bàsica d'una pàgina web mitjançant elements com títols, paràgrafs, enllaços i imatges.

**Aplicabilitat:**
S'utilitza per estructurar el contingut web, definir hipervincles, imatges i proporcionar una base per a fulls d'estil (CSS) i JavaScript.

---

### HTML: Exemple de Codi

```html
<!DOCTYPE html>
<html>
  <head>
    <title>La Meva Pàgina Web</title>
  </head>
  <body>
    <h1>Benvinguts</h1>
    <p>Aquesta és una pàgina d'exemple.</p>
  </body>
</html>
```

---

## Markdown

**Definició:**
Markdown és un llenguatge de marques lleuger que s'utilitza comunament per escriure documentació, arxius README i contingut per a blocs o wikis.

**Aplicabilitat:**
És ideal per a documents lleugers i fàcilment llegibles, i s'utilitza molt en plataformes com GitHub i altres gestors de versions.

---

### Markdown: Exemple de Codi

```markdown
# Títol Principal

Aquest és un paràgraf amb **negretes** i _cursives_.

- Element de llista
- Un altre element

[Enllaç a GitHub](https://github.com)
```

---

## XML (Extensible Markup Language)

**Definició:**
XML és un llenguatge de marques dissenyat per emmagatzemar i transportar dades.

- A diferència d'HTML, XML no defineix etiquetes predefinides, sinó que permet als usuaris crear les seves pròpies etiquetes per adaptar-se a la informació que es vol representar.
- És autodescriptiu i està dissenyat per ser tant llegible per màquines com per humans.

**Aplicabilitat:**
És utilitzat en la transmissió de dades entre sistemes, especialment en entorns empresarials i governamentals, així com en arxius de configuració, documents estructurats i serveis web (com ara SOAP).

---

### XML: Exemple

```xml
<llibre>
  <títol>El Petit Príncep</títol>
  <autor>Antoine de Saint-Exupéry</autor>
  <any>1943</any>
</llibre>
```

---

## JSON (JavaScript Object Notation)

**Definició:**
JSON és un format lleuger per a l'intercanvi de dades, basat en una estructura de parells clau-valor. Tot i que tècnicament no és un llenguatge de marques, s'utilitza àmpliament per a la transmissió de dades en aplicacions web.

**Aplicabilitat:**
És molt utilitzat en APIs, en l'intercanvi de dades entre aplicacions i com a format per a arxius de configuració.

---

### JSON: Exemple de Codi

```json
{
  "nom": "Joan",
  "edat": 30,
  "ocupació": "Desenvolupador"
}
```

---

## YAML (YAML Ain't Markup Language)

**Definició:**
YAML és un format de serialització de dades que és més llegible i simple que JSON o XML. Es fa servir sovint en fitxers de configuració per la seva claredat i senzillesa.

**Aplicabilitat:**
S'utilitza principalment en configuracions de programari, automatització de scripts i descripcions d'infraestructura com ara Kubernetes.

---

### YAML: Exemple de Codi

```yaml
persona:
  nom: "Anna"
  edat: 25
  ocupació: "Enginyera"
```

### YAML: Exemple d'arxiu de configuració netplan (xarxa de linux)

```yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    enp3s0:
      addresses:
        - 10.10.10.2/24
      nameservers:
        search:
          - "mycompany.local"
        addresses:
          - 10.10.10.253
          - 8.8.8.8
```

---

## LaTeX

**Definició:**
LaTeX és un llenguatge de marques utilitzat per a la creació de documents científics i matemàtics. És especialment útil per incloure fórmules i equacions complexes de manera clara i estructurada.

**Aplicabilitat:**
S'utilitza en la redacció d'articles acadèmics, tesis, llibres científics i qualsevol document que necessiti una composició tipogràfica precisa, especialment en matemàtiques.

---

### LaTeX: Exemple de Codi

```latex
\documentclass{article}
\begin{document}
\title{El meu Document en LaTeX}
\author{Autor}
\date{\today}
\maketitle

\section{Introducció}
Aquest és un document d'exemple.

\end{document}
```

---

## SVG (Scalable Vector Graphics)

**Definició:**
SVG és un llenguatge de marques basat en XML per descriure gràfics vectorials escalables. Permet crear imatges i gràfics que es poden ampliar sense perdre qualitat.

**Aplicabilitat:**
És útil per a il·lustracions, gràfics, i animacions en llocs web, ja que els gràfics vectorials poden ser redimensionats sense pèrdua de resolució.

---

### SVG: Exemple de Codi

```xml
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
</svg>
```

---

## MathML (Mathematical Markup Language)

**Definició:**
MathML és un llenguatge basat en XML dissenyat per descriure notacions matemàtiques i la seva estructura. És especialment útil per mostrar equacions matemàtiques en pàgines web de manera estructurada i comprensible.

**Aplicabilitat:**
S'utilitza per incloure fórmules matemàtiques en documents interactius i llocs web que requereixen presentar contingut matemàtic de manera precisa.

---

### MathML: Exemple de Codi

```xml
<math xmlns="http://www.w3.org/1998/Math/MathML">
  <msup>
    <mi>x</mi>
    <mn>2</mn>
  </msup>
</math>
```

---

## CSV

Antigament per representar dades es feia separant els valors amb comes o algun altre símbol.

### CSV: Exemple de Codi

```
"Nom","Cognom","Ofici","Naixament","Poblacio","Punts"
"Pere","Pi","Professor","10/04/1978","Olot",12
"Marta","Mata","Inforàtica","19/05/1990","Girona",20
```

- S'ha de saber que la primera línia són metadades
- Afegir-hi noves dades pot ser molt problemàtic pel programa que les llegeixi --> Probablement haurem de canviar el programa.
- El format **CSV (Comma separated value)** encara s'utilitza molt en el món de la informàtica, per exportar/importar dades normalment.
  - Es tracta d'enviar la informació utilitzant un caràcter per a separar cada un dels conceptes. Tot i que el nom pugui suggerir que sigui una coma, molts sistemes deixen definir el caràcter a utilitzar (punt i coma, salt de línia, ...)
