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

