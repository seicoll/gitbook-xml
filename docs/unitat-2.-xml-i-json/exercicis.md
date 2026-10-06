# Exercicis

## Convertir XML a JSON i viceversa

### Exercici 1: Conversió XML a JSON

> **Objectiu**: Practicar la conversió de dades entre els formats XML i JSON.

**Instruccions**:

1.  Converteix aquest XML a un document JSON equivalent. Assegura't que l'estructura i les dades es mantinguin correctament.
2.  Valida el document JSON utilitzant una eina de validació JSON per assegurar-te que és vàlid.

**Exemple d'XML a convertir**:

```xml
<equips categoria="hardware">
    <equip tipus="sobretaula">
        <nom>Ordinador de sobretaula</nom>
        <processador marca="Intel" model="Core i7"/>
        <emmagatzematge tipus="SSD">512GB</emmagatzematge>
        <components>
            <component>Targeta gràfica NVIDIA</component>
            <component>Font alimentació 650W</component>
        </components>
    </equip>
    <equip tipus="portatil">
        <nom>Portàtil</nom>
        <processador marca="AMD" model="Ryzen 5"/>
        <emmagatzematge tipus="SSD">256GB</emmagatzematge>
        <components>
            <component>Targeta gràfica integrada</component>
            <component>Bateria 4000mAh</component>
        </components>
    </equip>
</equips>
```

### Exercici 2: Conversió JSON a XML

> **Objectiu**: Practicar la conversió de dades entre els formats JSON i XML.

**Instruccions**:

1.  **Converteix** aquest JSON a un document XML equivalent. Assegura't que l'estructura i les dades es mantinguin correctament.
2.  **Valida** el document XML utilitzant una eina de validació XML per assegurar-te que és vàlid.

**Exemple de JSON a convertir**:

```json
{
  "futbol": {
    "equips": [
      {
        "nom": "FC Barcelona",
        "pais": "Espanya",
        "any_fundacio": 1899,
        "estadi": "Spotify Camp Nou",
        "titols": ["Lliga", "Copa del Rei", "Champions League"]
      },
      {
        "nom": "Manchester United",
        "pais": "Anglaterra",
        "any_fundacio": 1878,
        "estadi": "Old Trafford",
        "titols": ["Premier League", "FA Cup", "Champions League"]
      }
    ]
  }
}
```

## Validació de documents amb DTD

### Exercici 3: Creació d'una DTD per a un document XML

> **Objectiu**: Aprendre a crear una DTD per validar l'estructura d'un document XML.

**Instruccions**:

1.  Crea una DTD que defineixi l'estructura del següent document XML:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="no" ?>
<!DOCTYPE smartphones SYSTEM "smartphones.dtd">
<smartphones any="2025">
    <smartphone id="S01" gamma="alta">
        <marca>Apple</marca>
        <model>iPhone 15 Pro</model>
        <processador fabricant="Apple">A17 Pro</processador>
        <pantalla tipus="OLED" mida="6.1" unitat="polzades"/>
        <emmagatzematge>256 GB</emmagatzematge>
        <connectivitat>
            <xarxa>5G</xarxa>
            <wifi>Wi-Fi 6E</wifi>
            <bluetooth versio="5.3"/>
        </connectivitat>
    </smartphone>

    <smartphone id="S02" gamma="mitjana">
        <marca>Samsung</marca>
        <model>Galaxy S23 FE</model>
        <processador fabricant="Samsung">Exynos 2200</processador>
        <pantalla tipus="AMOLED" mida="6.4" unitat="polzades"/>
        <emmagatzematge>128 GB</emmagatzematge>
        <connectivitat>
            <xarxa>5G</xarxa>
            <wifi>Wi-Fi 6</wifi>
        </connectivitat>
    </smartphone>
</smartphones>
```

2.  Utilitza el DTD per validar el document XML i assegura't que és vàlid.
3.  Prova a modificar el document XML per provocar errors i comprova que la DTD els detecta correctament.

### Exercici 4: Creació d'un document XML a partir d'una DTD

> **Objectiu**: Aprendre a crear un document XML que compleixi una DTD donada.

**Instruccions**:

1.  Crea un document XML que compleixi la següent DTD:

```dtd
<!ELEMENT classe (alumne+)>

<!ELEMENT alumne (nom, cognom, cognom?, any_naixement, assignatures, comentari?, foto)>
<!ATTLIST alumne id ID #REQUIRED>

<!ELEMENT nom (#PCDATA)>
<!ELEMENT cognom (#PCDATA)>
<!ELEMENT any_naixement (#PCDATA)>

<!ELEMENT assignatures (assignatura+)>
<!ELEMENT assignatura (nom_assignatura, nota)>
<!ELEMENT nom_assignatura (#PCDATA)>
<!ELEMENT nota EMPTY>
<!ATTLIST nota valor (NA | AS | AN | AE) #REQUIRED>

<!ELEMENT comentari (#PCDATA)>

<!ELEMENT foto EMPTY>
<!ATTLIST foto url CDATA #REQUIRED>
```

2.  Assegura't que el document XML és vàlid segons la DTD.
3.  Valida el document XML utilitzant una eina de validació XML per assegurar-te que és vàlid.
