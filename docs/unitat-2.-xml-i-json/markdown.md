# Introducció a Markdown

**Markdown** és un llenguatge de marques senzill que s'utilitza per formatar text de manera clara i fàcil de llegir. És molt popular per la seva simplicitat i perquè permet generar text formatat sense la complexitat d'altres llenguatges com HTML. És àmpliament utilitzat en llocs web, blocs, documentació i fitxers README.

## Característiques principals de Markdown

1. **Encapçalaments**  
   Per crear encapçalaments, s'utilitzen símbols de coixinet (`#`). La quantitat de coixinets determina el nivell de l'encapçalament:

   - `#` Títol de nivell 1
   - `##` Títol de nivell 2
   - `###` Títol de nivell 3

2. **Text en negreta i cursiva**

   - Per **negreta**, es col·loca el text entre dos asteriscs (`**text**`).
   - Per _cursiva_, es col·loca el text entre un asterisc (`*text*`).

3. **Llistes**

   - Les llistes no numerades es creen utilitzant guions o asteriscs:

   ```
       - Element de llista 1
       - Element de llista 2
   ```

   - Les llistes numerades es creen simplement utilitzant números:

   ```
       1. Primer element
       2. Segon element
   ```

4. **Enllaços**
   Els enllaços es creen utilitzant la sintaxi `[text](url)`. Per exemple:  
   [Google](https://www.google.com)

5. **Imatges**
   Les imatges s'insereixen de manera similar als enllaços, però amb un signe d'exclamació (`!`) davant:  
   `![Alt text](url-de-la-imatge)`

6. **Codi**
   Per inserir fragments de codi inline, s'utilitza el símbol de la cometa inversa (`). Per blocs de codi més grans, s'utilitzen tres cometes inverses seguides (```).

7. **Cites**
   Per crear una cita o bloc de cita, s'utilitza el signe de major (`>`):

   > Aquesta és una cita.

8. **Taules**
   Les taules es poden crear utilitzant barres verticals i guions per definir les columnes i les files:

   ```markdown
   | Columna 1 | Columna 2 |
   | --------- | --------- |
   | Contingut | Contingut |
   ```

## Exemple combinant elements

Aquest és un exemple d'un document en Markdown:

```markdown
# Títol principal

Aquest és un paràgraf amb **negreta** i _cursiva_.

## Títol secundari

- Primer element de llista no numerada
- Segon element de llista no numerada

1. Primer element de llista numerada
2. Segon element de llista numerada

[Enllaç a Google](https://www.google.com)

> Aquesta és una cita.
```

## Exercicis

### Exercici 1

- Instal·lat VS Code
- Instal·lat un plugin per fer previsualització de markdown a VSCode.
- Crea un petit document markdown i previsualitza'l.
- Busca alguna web permeti utilitzar markdown per tal de formatar el text

### Exercici 2

**Crea document MarkDown amb el vostre perfil de GitHub**

- GitHub permet crear un repositori especial on posar dades del vostre perfil.
- Aquestes són les instruccions oficials per fer-ho:
  [https://docs.github.com/en/get-started/start-your-journey/setting-up-your-profile](https://docs.github.com/en/get-started/start-your-journey/setting-up-your-profile)

- I aquestes són unes instruccions extraoficials més divertides i amb idees: [https://github.com/rzashakeri/beautify-github-profile](https://github.com/rzashakeri/beautify-github-profile)
