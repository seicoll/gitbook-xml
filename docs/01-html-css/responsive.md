# Disseny Responsive amb CSS

## Què és el disseny responsive?

El **disseny responsive** (o *Responsive Web Design*) és una tècnica de desenvolupament web que permet que una pàgina s'adapti automàticament a diferents mides de pantalla.

Una mateixa pàgina web pot visualitzar-se en:

* 📱 Mòbils
* 📱 Tablets
* 💻 Portàtils
* 🖥️ Ordinadors de sobretaula
* 📺 Pantalles grans

L'objectiu és que el contingut sigui **fàcil de veure i utilitzar independentment del dispositiu**.

![](../uf1_images/u1-responsive_web_design.webp)



## El problema de les mides fixes

Considerem aquest CSS:

```css
.container {
    width: 1200px;
}
```

En un monitor gran pot funcionar correctament.

Però si obrim la pàgina en un dispositiu de **390 px d'amplada**, el contingut no hi cap.

El navegador haurà de mostrar una barra de desplaçament horitzontal.

Per evitar-ho, en un disseny responsive intentarem **evitar les amplades fixes** quan no siguin necessàries.

## Configurar el viewport

Perquè un document HTML s'adapti correctament als dispositius mòbils, és molt important definir el **viewport**.

Aquesta etiqueta s'ha de posar dins del `<head>` de l'HTML:

```html
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

Aquesta línia indica al navegador que:

* `width=device-width` → l'amplada de la pàgina ha de coincidir amb l'amplada del dispositiu.
* `initial-scale=1.0` → Indica que la pàgina s'ha de mostrar inicialment sense aplicar zoom (escala del 100%).

> **Important:** en una web responsive aquesta etiqueta s'ha de posar sempre.

![](../assets/u1-viewport.png)

* Sense el **viewport** definit, el navegador mòbil calcula l’amplada del lloc i l'escala la pàgina a la de la pantalla, de manera que el contingut és difícil de llegir. 
  
* Amb el **viewport** definit fa que l’amplada del lloc coincideixi amb l'amplada del dispositiu - el navegador mòbil no escala la pàgina i el contingut és llegible.



## Media Queries

Les **media queries** són una funcionalitat de CSS que permet aplicar CSS diferent segons les característiques del dispositiu o la pantalla. 

La més habitual és comprovar-ne l'amplada.

**Exemple:**

```css
@media screen and (max-width: 768px) {
    /* Regles per a pantalles de més de 768px */
    body {
        background-color: lightgray;
    }

}
```

---
### Exemple pràctic

```css
/* Estils per a pantalles petites */
@media screen and (max-width: 768px) {
    body {
        font-size: 14px;
    }
}

/* Estils per a pantalles grans */
@media screen and (min-width: 769px) {
    body {
        font-size: 18px;
    }
}
```

A partir d'una amplada de pantalla de 769 píxels o superiors, el text serà més gran.


---



## Breakpoints

> Els punts on modifiquem el disseny s'anomenen **breakpoints**.

**Breakpoints habituals**

![](../assets/u1-breakpoints.png)
Per exemple:


### Estratègia Desktop First

* Una possible manera de treballar consisteix a dissenyar primer la versió d'ordinador.

**Primer** es creen les regles CSS per als navegadors **d'ordinadors** i després s'afegeixen Media Queries per definir els estils en navegadors de tablets i mòbils.


```css
/* Regles CSS per a Ordinador */
* {
    box-sizing: border-box;
}


/* Tauleta */
@media (max-width: 768px) {


}

/* Mòbil */
@media (max-width: 480px) {

}
```


### Estratègia Mobile First

> Actualment és molt habitual utilitzar l'estratègia **Mobile First**.

* **Primer** programem la versió més senzilla: el mòbil.

* **Després** ampliem el disseny a mesura que tenim més espai.

Exemple:

```css
/* Regles CSS per a Mòbil */
* {
    box-sizing: border-box;
}


/* Tauleta */
@media (min-width: 481px) {


}

/* Ordinador */
@media (min-width: 769px) {


}
```

Aquest enfocament acostuma a ser una bona opció perquè obliga a començar pel contingut essencial.

---




per revisar


---

# 15. Exemple de menú responsive

HTML:

```html
<nav class="menu">

    <a href="#">Inici</a>
    <a href="#">Productes</a>
    <a href="#">Serveis</a>
    <a href="#">Contacte</a>

</nav>
```

CSS per a mòbil:

```css
.menu {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
```

Pantalla petita:

```text
Inici
Productes
Serveis
Contacte
```

Per a pantalles més grans:

```css
@media (min-width: 768px) {

    .menu {
        flex-direction: row;
    }

}
```

Resultat:

```text
Inici | Productes | Serveis | Contacte
```

---

# 16. Exemple complet

## HTML

```html
<!DOCTYPE html>

<html lang="ca">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Web responsive</title>

    <link rel="stylesheet" href="style.css">

</head>

<body>

<header>

    <div class="container">

        <h1>TechStore</h1>

        <nav class="menu">

            <a href="#">Inici</a>
            <a href="#">Productes</a>
            <a href="#">Contacte</a>

        </nav>

    </div>

</header>


<main class="container">

    <h2>Productes destacats</h2>

    <section class="productes">

        <article class="card">

            <img
                src="img/portatil.jpg"
                alt="Ordinador portàtil"
            >

            <h3>Portàtil</h3>

            <p>
                Ordinador portàtil per treballar
                i estudiar.
            </p>

        </article>


        <article class="card">

            <img
                src="img/monitor.jpg"
                alt="Monitor"
            >

            <h3>Monitor</h3>

            <p>
                Monitor de 27 polzades.
            </p>

        </article>


        <article class="card">

            <img
                src="img/teclat.jpg"
                alt="Teclat"
            >

            <h3>Teclat</h3>

            <p>
                Teclat mecànic.
            </p>

        </article>

    </section>

</main>

</body>

</html>
```

---

## CSS

```css
* {
    box-sizing: border-box;
}


body {
    margin: 0;

    font-family:
        Arial,
        sans-serif;
}


img {
    display: block;

    max-width: 100%;
    height: auto;
}


.container {
    width: 90%;
    max-width: 1200px;

    margin: auto;
}


header {
    background: #222;
    color: white;

    padding: 20px 0;
}


.menu {
    display: flex;
    flex-direction: column;

    gap: 10px;
}


.menu a {
    color: white;

    text-decoration: none;
}


.productes {
    display: grid;

    grid-template-columns: 1fr;

    gap: 20px;
}


.card {
    border: 1px solid #ccc;

    padding: 20px;
}


@media (min-width: 768px) {

    .menu {
        flex-direction: row;
    }


    .productes {
        grid-template-columns:
            repeat(2, 1fr);
    }

}


@media (min-width: 1100px) {

    .productes {
        grid-template-columns:
            repeat(3, 1fr);
    }

}
```

---


# 21. `display: none` i menús mòbils

És habitual tenir un botó de menú en mòbil.

Per exemple:

```text
☰
```

i un menú complet en ordinador:

```text
Inici   Productes   Serveis   Contacte
```

Podem controlar quins elements apareixen amb media queries.

```css
.menu-toggle {
    display: block;
}

.menu-desktop {
    display: none;
}


@media (min-width: 768px) {

    .menu-toggle {
        display: none;
    }

    .menu-desktop {
        display: flex;
    }

}
```

Per crear un menú desplegable funcional normalment també necessitarem una mica de **JavaScript**.

---


## Com provar una web responsive

Els navegadors actuals permeten simular diferents dispositius.

A Chrome o Edge podem obrir:

```text
F12
```

i activar:

```text
Toggle device toolbar
```

També podem utilitzar:

```text
Ctrl + Shift + M
```

Podrem seleccionar dispositius com:

- iPhone;
- Pixel;
- iPad;
- Galaxy;
- dispositius personalitzats.

Però no ens hem de limitar als dispositius predefinits.

És molt útil **arrossegar manualment l'amplada de la finestra**.

Això permet detectar exactament en quin punt es trenca el disseny.

---


# 27. Estructura CSS recomanada

Una estructura habitual podria ser:

```css
/* -------------------------
   RESET / GLOBAL
------------------------- */

* {
    box-sizing: border-box;
}

body {
    margin: 0;
}

img {
    max-width: 100%;
    height: auto;
}


/* -------------------------
   LAYOUT
------------------------- */

.container {
    width: 90%;
    max-width: 1200px;
    margin: auto;
}


/* -------------------------
   COMPONENTS
------------------------- */

.card {
    padding: 1rem;
}


/* -------------------------
   TABLET
------------------------- */

@media (min-width: 768px) {

}


/* -------------------------
   DESKTOP
------------------------- */

@media (min-width: 1024px) {

}
```

---


---

# Exercici proposat

Crea una pàgina web d'una botiga d'informàtica amb:

- capçalera;
- logotip;
- menú de navegació;
- secció de productes;
- un mínim de 6 productes;
- imatge, nom, descripció i preu de cada producte;
- peu de pàgina.

La web haurà de tenir el següent comportament:

### Mòbil

```text
1 producte per fila
```

### Tauleta

```text
2 productes per fila
```

### Ordinador

```text
3 productes per fila
```

Condicions:

- Utilitza una estratègia **Mobile First**.
- No utilitzis amplades fixes per al contenidor principal.
- Les imatges han de ser responsive.
- Utilitza **CSS Grid** per als productes.
- Utilitza almenys dues `media queries`.
- La pàgina no pot tenir scroll horitzontal en cap resolució.
- Comprova el resultat amb les eines de desenvolupador del navegador.



