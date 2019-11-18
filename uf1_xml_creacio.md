# Creació de documents XML

## Declaració de XML

Els documents XML han de començar amb la declaració que indiqui quina versió estem fent servir d'XML.

```xml
<?xml version="1.0" ?>
```

Atribut **Encoding** defineix el joc de caràcters que fem servir en el document:

```xml
<?xml version="1.0" encoding="UTF-8" ?>
```


## Regles bàsiques

### Tots els documents tenen una etiqueta arrel

L'etiqueta arrel és aquella que es defineix després de la declaració del document. 

```xml
<persona>           <!-- Etiqueta arrel -->
  <nom>Pere Pi</nom>
  <nom>Marta Mata</nom>
</persona>          <!--Tancament etiqueta arrel -->
```

Aquest no seria un document XML correcte:
```xml
  <nom>Pere Pi</nom>
  <nom>Marta Mata</nom>
```

### Totes les etiquetes s'han de tancar

```xml
<article>Pissarra</article>
```

No es poden fer coses com les que permet HTML:

```html
<img src="pissarra.png">
```

Si tenim una etiqueta sense dades el podem representar amb el tancament `/>`:

```xml
<article nom="pissarra"/>
```

### Les etiquetes han d'estar niades correctament

Cal tancar les etiquetes per l'ordre invers en què s'han obert.

**INCORRECTE**
```xml
<inventari>
  <article>
    Pissarra
  </inventari>
</article>
```
Les etiquetes estan tancades en ordre invers i per tant és incorrecte.

### Les majúscules i minúscules són diferents

Per tant aquestes dues són etiquetes diferents:

```xml
<article>Pissarra</article>
<Article>Pissarra</Article>
```

**I això és incorrecte!**

```xml
<Article>Pissarra</article>
```

### Els valors dels atributs han d'estar entre cometes

Els valors dels **atributs** han d'estar entre **cometes** fins i tot si són números

I no importa si són cometes simples o dobles.

```xml
<article quantitat="3">Pissarra</article>
```

**I això és incorrecte:**
```xml
<article quantitat=3>Pissarra</article>
```
