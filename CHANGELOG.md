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