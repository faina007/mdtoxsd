# 📘 MDTO XML-Schema

## Inleiding

**MDTO (Metagegevens voor Duurzaam Toegankelijke Overheidsinformatie)** is een norm voor het eenduidig vastleggen en uitwisselen van metagegevens, met het doel de **duurzame toegankelijkheid van overheidsinformatie** mogelijk te maken.  

Het schema richt zich op generieke metagegevens die gelden voor (bijna) alle overheidsorganisaties, werkprocessen en informatiesoorten.  
MDTO sluit aan op de verplichtingen zoals opgenomen in de *Archiefregeling 2009*.  

➡️ Meer informatie: [Nationaal Archief – MDTO](https://www.nationaalarchief.nl/archiveren/mdto)

---

## Doel van het XML-schema

Het XML-schema beschrijft de XML-syntax waarmee MDTO-metagegevens conform het metagegevensmodel kunnen worden vastgelegd en uitgewisseld.  
Het schema maakt het mogelijk om systemen en koppelingen te ontwerpen waarin consistente metagegevens worden gebruikt — wat bijdraagt aan betere gegevensuitwisseling, lagere vertaalkosten en hogere kwaliteit van metagegevens.

📄 **Schema-locatie:**  
[https://www.nationaalarchief.nl/archiveren/mdto/xml-schema](https://www.nationaalarchief.nl/archiveren/mdto/xml-schema)

---

## Namespace en opbouw

- **Namespace:** `https://www.nationaalarchief.nl/mdto`  
- **Hoofdelement:** `<MDTO>` van het type `mdtoType`  
- Binnen het schema worden o.a. de objecttypen **Informatieobject** en **Bestand** onderscheiden, elk met hun eigen set metagegevens.  
- Het schema is uitbreidbaar en kan worden toegepast in verschillende contexten binnen het archief- en informatiemanagementdomein.

---

## Versiebeheer en publicatie

Het schema wordt onderhouden en gepubliceerd door het **Nationaal Archief**.  
Voor elke officiële wijziging wordt een nieuwe versie uitgegeven, bijvoorbeeld `MDTO-XML1.0.1.xsd`.  

Versies worden beheerd via **GitHub** en zijn publiek beschikbaar.  
Gebruikers wordt aangeraden in hun implementaties en documentatie altijd de gebruikte schema-versie te vermelden.

> **Tip:** Voor publicatie kan een stabiele URL worden gebruikt, zoals  
> `https://www.nationaalarchief.nl/mdto/MDTO-XML.xsd`  
> Deze kan verwijzen (redirecten) naar de meest recente versie, terwijl oudere versies onder hun specifieke naam blijven bestaan.

---

## 📜 MDTO-XSD1.0.2. - Wijzigingen en validatie-updates 

### Validatie van verplichte elementen op lege waarden

Binnen het MDTO-schema zijn bepaalde elementen **verplicht** gesteld.  
Voorheen controleerde het XML-schema alleen op de **aanwezigheid** van deze elementen, niet op hun **inhoud**.  

De validatie is uitgebreid zodat nu ook wordt gecontroleerd dat een verplichte tekstwaarde **niet leeg is** en **niet uitsluitend witruimte bevat**.

> **Regel:** Tekst mag spaties bevatten, maar moet minstens één niet-witruimtekarakter bevatten.  
> Lege waarden of enkel witruimte zijn niet toegestaan.

---

### Herhaalbaarheid van `<raadpleeglocatie>`, `<raadpleeglocatieFysiek>` en `<raadpleeglocatieOnline>`

Binnen het element `<Informatieobject>` mag het element `<raadpleeglocatie>` **maximaal één keer** voorkomen.  
Binnen dit element kunnen zowel `<raadpleeglocatieFysiek>` als `<raadpleeglocatieOnline>` **meerdere keren** worden opgenomen.  

De **volgorde** waarin deze elementen voorkomen is vrij en heeft **geen betekenis** voor de interpretatie van de gegevens.

---

### Bestandsomvang mag niet negatief zijn

Het datatype van het element `<omvang>` (onderdeel van `<bestand>`) is gewijzigd van  
`xsd:integer` naar `xsd:nonNegativeInteger`.  

Hiermee wordt geborgd dat de opgegeven **bestandsomvang**:
- een geldige, **niet-negatieve waarde** heeft, en  
- dat er daadwerkelijk **bestanden zijn vastgelegd**.

---

### Opschoning van witruimtes in `<xsd:documentation>`-elementen

In diverse `<xsd:documentation>`-elementen kwamen overbodige spaties voor aan het einde van zinnen.  
Deze spaties zijn verwijderd om de documentatie in het schema te **normaliseren** en te **verbeteren**.

---

### Inline changelog verwijderd

De inline changelog die eerder als commentaar bovenin het XML-schema was opgenomen, is verwijderd.  
De wijzigingsgeschiedenis wordt voortaan beheerd en bijgehouden via de **GitHub-omgeving**.

---

## 📂 Voor wie is dit schema bedoeld?

Het MDTO-schema is bedoeld voor:

- Overheidsorganisaties die metadata van blijvend te bewaren informatieobjecten vastleggen en uitwisselen.  
- Leveranciers van informatiesystemen en archiveringsoplossingen die interoperabiliteit en duurzame toegankelijkheid ondersteunen.  
- Beheerders van informatiesystemen die gebruikmaken van koppelingen of uitwisselformaten tussen organisaties.

---

## 📌 Meer informatie

- Website: [Nationaal Archief – MDTO](https://www.nationaalarchief.nl/archiveren/mdto)  
- Schema’s: [XML-Schema – MDTO](https://www.nationaalarchief.nl/archiveren/mdto/xml-schema)  
- Contact: [info@nationaalarchief.nl](mailto:info@nationaalarchief.nl)

---

© Nationaal Archief – MDTO XML-Schema  
Laatste update: **v1.0.2**
