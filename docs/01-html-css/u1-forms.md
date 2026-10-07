# Formularis HTML

## Introducció als formularis

> HTML permet crear **formularis** perquè els usuaris puguin introduir dades i interactuar amb una aplicació web.

Un formulari es defineix amb l'etiqueta `<form>`.

```html
<form action="resultat.html" method="post">
    Escriu el teu nom
    <input type="text" name="nom" value="">
    <br>
    <input type="submit" value="Enviar">
</form>
```
/* IMATGE */

---

## L'etiqueta `<form>`

L'etiqueta `<form>` té dos atributs especialment importants:

### `action`

Indica **on s'enviaran les dades** del formulari.

```html
<form action="processar.php">
```

En aquest cas, quan l'usuari enviï el formulari, les dades es processaran a `processar.php`.

### `method`

Indica **com s'enviaran les dades** al servidor.

Els dos mètodes HTTP més habituals són:

- `GET`: les dades s'envien a través de l'adreça URL.
- `POST`: les dades s'envien dins de la petició HTTP.

```html
<form method="get" action="resultat.html">
```

```html
<form method="post" action="resultat.html">
```

---

## Camps d'entrada amb `<input>`

### L'etiqueta `<input>`

L'etiqueta `<input>` defineix un **punt d'entrada de dades**.

L'atribut `type` determina quin tipus de control es mostrarà.

```html
<input type="text" name="usuari">
```

---

### Camps de text

#### `type="text"`

Permet introduir text.

```html
<input type="text" name="usuari">
```

#### `type="password"`

Permet introduir una contrasenya ocultant visualment els caràcters.

```html
<input type="password" name="contrasenya">
```

#### `type="hidden"`

Permet enviar una dada sense mostrar cap control visible a l'usuari.

```html
<input type="hidden" name="id" value="25">
```



### Checkbox

Els `checkbox` permeten seleccionar **una o diverses opcions**.

```html
<input type="checkbox" name="opcio1" value="Cafe" checked> Cafè
<input type="checkbox" name="opcio2" value="Llet"> Llet
<input type="checkbox" name="opcio3" value="Sucre"> Sucre
```

En l'exemple de la presentació, cada checkbox té un `name` diferent.

### Radio buttons

Els `radio` permeten triar **una única opció** dins d'un grup.

Perquè formin part del mateix grup han de tenir el **mateix `name`**.

```html
<input type="radio" name="paga" value="comptat"> Comptat
<input type="radio" name="paga" value="visa"> Visa
```

## Fitxers i botons

### `type="file"`

Permet seleccionar un fitxer.

```html
<input type="file">
```

### `type="submit"`

Envia les dades del formulari.

```html
<input type="submit" value="Acceptar">
```

### `<button>`

L'etiqueta `<button>` també permet crear botons i pot contenir text o altres elements.

```html
<button type="button">Acceptar</button>
```

### `type="reset"`

Permet buidar o restaurar els camps del formulari.

```html
<input type="reset" value="Netejar">
```



## Atributs importants de `<input>`

### `name`

Defineix el nom del camp.

Aquest nom és el que permet identificar la dada quan el formulari s'envia.

```html
<input type="text" name="usuari">
```

### `value`

Defineix el valor inicial del control.

```html
<input type="text" name="ciutat" value="Olot">
```

### Altres atributs

- `maxlength`: longitud màxima permesa.
- `disabled`: desactiva el camp.
- `checked`: marca inicialment un `radio` o `checkbox`.
- `readonly`: fa que el camp sigui només de lectura.

## Altres controls de formulari

### L'etiqueta `<select>`

Permet crear una **llista desplegable**.

```html
<select name="desplegable">
    <option value="Llet2">Llet</option>
    <option value="Cafe2">Cafè</option>
    <option value="Sucre2">Sucre</option>
</select>
```

Cada opció es defineix amb `<option>`.

---

### L'etiqueta `<textarea>`

Permet introduir **text de diverses línies**.

```html
<textarea name="comentaris" rows="6" cols="40"></textarea>
```

---

### L'etiqueta `<label>`

`<label>` permet associar una etiqueta de text a un camp del formulari.

És especialment important per millorar l'**accessibilitat**.

```html
<label for="nom">Nom</label>
<input type="text" id="nom">
```

El valor de `for` ha de coincidir amb l'`id` del camp.

Quan l'usuari fa clic sobre el `label`, el navegador posiciona el focus en el control associat.



## Formularis amb HTML5

HTML5 incorpora nous tipus de camps que permeten:

- una entrada de dades més adequada;
- un millor control del format;
- validació automàtica per part del navegador.



### `type="email"`

S'utilitza per introduir una adreça de correu electrònic.

```html
<input type="email" name="correu">
```

El navegador pot comprovar si el valor té un format de correu electrònic vàlid.

---

### `type="url"`

S'utilitza per introduir una URL.

```html
<input type="url" name="paginaweb">
```

El navegador pot validar que el contingut tingui format d'URL.

---

### `type="date"`

Permet seleccionar una data.

```html
<input type="date" name="aniversari">
```

El navegador pot mostrar un selector de calendari.

---

### `type="time"`

Permet introduir una hora vàlida.

```html
<input type="time" name="hora">
```



### `type="number"`

S'utilitza per introduir valors numèrics.

```html
<input type="number" name="quantitat" min="1" max="5">
```

Atributs habituals:

- `min`: valor mínim.
- `max`: valor màxim.
- `value`: valor inicial.
- `step`: increment entre valors.

---

### `type="range"`

Permet seleccionar un valor dins d'un interval numèric.

```html
<input type="range" name="points" min="1" max="10">
```

Normalment el navegador el representa com un control lliscant.

---

### `type="color"`

Permet seleccionar un color utilitzant el selector de colors del navegador.

```html
<input type="color" name="color">
```

---

## Atributs HTML5 per als camps

### `autofocus`

Fa que un camp tingui el focus automàticament quan es carrega la pàgina.

```html
<input type="text" name="nom" autofocus>
```

La presentació indica que només hi ha d'haver un element amb aquest atribut dins del document.

---

### `placeholder`

Permet mostrar un text orientatiu dins del camp.

```html
<input type="text" name="cognom" placeholder="Primer Cognom">
```

Pot servir per mostrar:

- un exemple;
- una breu descripció;
- el format esperat.

La presentació l'aplica als tipus `text`, `search`, `url`, `tel`, `email` i `password`.

---

### `required`

Indica que el camp és obligatori.

```html
<input type="text" name="cognom" required>
```

Si el camp està buit, el navegador no permet enviar el formulari.

---

### `pattern`

Permet definir una **expressió regular** per validar el contingut del camp.

Exemple: codi postal de cinc dígits.

```html
<input type="text" name="CP" pattern="[0-9]{5}">
```

El valor introduït haurà de complir el patró indicat.

---

## Llistes de suggeriments amb `<datalist>`

### Què és `<datalist>`?

`<datalist>` no és un tipus d'entrada.

Serveix per definir una llista de **valors suggerits** per a un camp.

A diferència de `<select>`, l'usuari **no està obligat** a seleccionar una de les opcions proposades.

El navegador mostra suggeriments a mesura que l'usuari escriu.

```html
<label for="xocolata">Tipus de xocolata preferit</label>

<input type="text" id="xocolata" list="tipusXocolata">

<datalist id="tipusXocolata">
    <option value="white">
    <option value="milk">
    <option value="dark">
</datalist>
```

La connexió entre l'`input` i el `datalist` es fa amb:

```html
list="tipusXocolata"
```

i:

```html
<datalist id="tipusXocolata">
```





