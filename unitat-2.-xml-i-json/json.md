# JSON

> JSON (**J**ava **S**cript **O**bject **N**otacion) és un format utilitzat per emmagatzemar i intercanviar dades de manera estructurada.

**JSON** és text, escrit amb sintaxi de JavaScript aprofitant l'ús dels objectes JavaScript.

Va néixer com a alternativa al **XML**.

S’utilitza molt per enviar informació des del servidor a una pàgina web.

Actualment està superant l'ús del **XML** en aplicacions web, gràcies a la **facilitat**, **portabilitat** i **llegibilitat.**

L'**extensió** dels fitxers JSON és **`.json`**.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

![](../.gitbook/assets/1_vcvipmqmjdbefcqf5f7p9q.png)

## **Sintaxi JSON**

A JSON existeixen dos tipus d’elements: **objectes** i **arrays**.

### Objectes `{}`

- Els objectes en JSON estan delimitats per claudàtors `{}`.
- Els objectes s'escriuen com a parelles de **clau**-**valor**.
- La **clau** és sempre un string i el **valor** pot ser de diferents tipus (string, número, array, objecte, booleà o null).
- Per **assignar** valor s'utilitza els dos punts ( **`:`** ).
- Les dades se separen per comes ( **`,`** )

> Les claus a JSON requereixen **cometes dobles.**

**Exemple d'un objecte:**

```json
{ "nom": "Pau", "edad": "55" }
```

En aquest exemple:

- `"nom"` és la clau i `"Pau"` és el valor.
- `"edad"` és la clau i `"55"` és el valor.

### Arrays `[ ]`

- Els arrays en JSON estan delimitats per claudàtors quadrats `[]`.
- Un **array** es una llista ordenada de valores.
- Cada valor pot ser de diferents tipus, inclosos altres objectes o arrays.
- Cada valor va separat per una coma ( **`,`** ).

**Exemple d'un array:**

```javascript
{
    "name":"John",
    "age":30,
    "cars": [ "Ford", "BMW", "Fiat" ]
}
```

Un valor d'un array també pot ser un objecte **JSON**.

**Exemple d'array que conté objectes**:

```json
{
  "students": [
    { "firstName": "Tom", "lastName": "Jackson" },
    { "firstName": "Linda", "lastName": "Garner" },
    { "firstName": "Adam", "lastName": "Cooper" }
  ]
}
```

### Arrays anidats

Els valors d'un **array** també poden ser **altres arrays**:

**Exemple d'array que conté altres arrays:**

```javascript
{
  "name":"John",
  "age":30,
  "cars": [
    { "name":"Ford", "models":[ "Fiesta", "Focus", "Mustang" ] },
    { "name":"BMW", "models":[ "320", "X3", "X5" ] },
    { "name":"Fiat", "models":[ "500", "Panda" ] }
  ]
 }
```

En aquest exemple:

- `cars`és un array que conté objectes.
- Cada objecte té una clau `models` que és un array de strings.

# Comparació de JSON i XML

Els següents exemples JSON i XML defineixen un objecte d'empleats, amb una matriu de 3 empleats:

#### Exemple JSON

```javascript
{"employees":[
  { "firstName":"John", "lastName":"Doe" },
  { "firstName":"Anna", "lastName":"Smith" },
  { "firstName":"Peter", "lastName":"Jones" }
]}
```

**Exemple XML**

```javascript
<employees>
  <employee>
    <firstName>John</firstName> <lastName>Doe</lastName>
  </employee>
  <employee>
    <firstName>Anna</firstName> <lastName>Smith</lastName>
  </employee>
  <employee>
    <firstName>Peter</firstName> <lastName>Jones</lastName>
  </employee>
</employees>
```

#### Similituds

Tant JSON com XML:

- Són "**autodescriptibles**" (llegibles per humans)
- Són **jeràrquics** (valors dins dels valors)
- Es poden analitzar i utilitzar en molts llenguatges de programació.

#### Avantatges de JSON

- No utilitza **etiquetes de tancament**.
- És més **curt**. Ocupa menys espai i es transfereix més ràpidament.
- És més ràpid de llegir i escriure.

# Validació

Podem comprovar la validesa d'un fitxer JSON amb eines on-line com per exemple:

- [JSONFormatter](https://jsonformatter.curiousconcept.com/)
- [JSONViewer](http://jsonviewer.stack.hu/)
- [JSONLint](https://jsonlint.com/)

Tot i que hi ha editors o **IDEs** que, directament o afegint plugins, també ens permeten fer aquesta validació.

Però si, a més, ens volem assegurar que compleix una determinada estructura, podem fer servir:

- [JSON Schema](https://json-schema.org/)

# Exercicis

## Exercici 1: Creació i validació d'un document JSON

> **Objectiu**: Aprendre a estructurar informació en un document JSON i validar que la sintàxi és correcte.

### 1. Crea un fitxer JSON

Crea un fitxer JSON que contingui la mateixa informació que el fitxer `receptes.xml` de l'exercici de XML.

Assegura't que la informació està ben estructurada i que no es perd cap dada.

### 2. Validació del document JSON

Utilitza una eina de validació JSON per comprovar que el teu fitxer JSON és vàlid.

Podeu fer proves de validar el vostre JSON a JSONLint per comprovar si el document té una estructura vàlida i una sintaxi correcta.

### 3. Provar errors

Feu modificacions en el document JSON per provocar errors, per exemple:

- Oblidar posar cometes al voltant de les claus o valors de tipus string.
- Eliminar una clau o valor.
- Oblidar una coma després d'un element.

**Exemple amb un error:**

```json
{
  "menjars": [
    {
      "nom": Pit de pollastre,
      "kilocalories": 100,
      "proteines": 20,
      "greixos": 10
    }
  ]
}
```

**Nota:** En aquest exemple, falta posar cometes al voltant del valor "Pit de pollastre".

**Error detectat pel validor:**

```
Error: Parse error on line 3:
{ "menjars": [ { "nom": Pit de pollastre...
```
