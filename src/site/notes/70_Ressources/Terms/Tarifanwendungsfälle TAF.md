---
{"dg-publish":true,"permalink":"/70-ressources/terms/tarifanwendungsfaelle-taf/","tags":["class/note","class/termNote"],"noteIcon":""}
---

> [!note] Tarifanwendungsfälle (TAF) stellen die seitens des BSI erdachten Fallunterscheidungen für die Erhebung von Messwerten dar, die durch Smart Meter Gateways (potenziell) funktional unterstützt werden (sollen) 
> --> ⬆️ *DEFINITIONsidee*
> 
> --> :luc_arrow_big_down: *IMPLEMENTIERUNGSVORGABE*
> 
> Die konkrete Zerlegung der Messaufgaben der Tarifanwendungsfälle mittels OBIS-Kennzahlen und die daraus ggf. notwendige Bildung virtueller Register auf dem Gateway wird mit den TAF **nicht** definiert. 
> Dies geschieht nachgelagert durch anderweitige Regulation außerhalb der Hoheit des BSI. 
> 



**TAF 1 - Datensparsame Tarife** Bezieht sich auf Verbrauchsabrechnungen: Die Messdaten eines oder mehrerer Zähler werden aufaddiert und als ein Zählerstand versendet, minimaler Zeitraum ist ein Monat.
- [[70_Ressources/PDF-DOCS/TR03109-1.pdf#page=80&selection=36,0,65,0|TR03109-1, page 74]] sagt mir in Zusammenhang mit [[70_Ressources/PDF-DOCS/TR03109-1.pdf#page=81&selection=77,0,83,41|TR03109-1, page 75]] für die Implementierung, es geht um die Bereitstellung von **genau einem** Messwert, der für einen Zeitraum von einem Monat zu erheben ist, es dürfen Zeiträume von Vielfachen eines Monats definiert werden.[^1] 
- Die Logik birgt die Conclusio, dass hier im SMGW ein Register zu bilden ist, welches das Quellregister der modernen Messeinrichtung als einen Wert in die angeforderte zeitliche Rasterung fortschreibt.

**TAF 2 - Zeitvariable Tarife** Zeitabhängiger Stromtarif mit mehreren Tarifstufen (vgl. Hoch-/Niedertarife).
- [[70_Ressources/PDF-DOCS/TR03109-1.pdf#page=82&selection=27,0,74,17|TR03109-1, page 76]] sagt mir für die die Implementierung, dass neben den **zeitabhängige**n **Register**n sowohl ein **mitlaufendes Fehlerregister** als auch ein **mitlaufendes Gesamtregister** zu bilden sind.

**TAF 3 - Lastvariable Tarife** Lastabhängiger Stromtarif mit mehreren Laststufen.

**TAF 4 - Verbrauchsvariable Tarife** Verbrauchsabhängiger Stromtarif mit mehreren Verbrauchsstufen. Die Verbrauchsstufen umfassen eine vorher festgelegte Energiemenge. Wird die Energiemenge einer Stufe überschritten, wird in die nächsthöhere Stufe gewechselt. Die Abrechnung erfolgt in vorher festgelegten Zeiträumen, bspw. monatlich.

**TAF 5 - Ereignisvariable Tarife** Ereignisabhängiger Stromtarif mit mehreren Tarifstufen. Die Tarifstufen sind an Bedingungen geknüpft, die beim Eintritt des festgelegten Ereignisses die Eingruppierung in die Tarifstufe steuern. Ereignisse müssen nicht bedingt SMGW-interne Ereignisse sein, sondern können auch durch externe Marktteilnehmer hervorgerufen werden.

**TAF 6 - Abruf von Messwerten im Bedarfsfall** Dieser Anwendungsfall darf nur in begründeten Ausnahmefällen genutzt werden. Dieses sind bspw. Auszug und Einzug eines Letztverbrauchers oder der Lieferantenwechsel. Für die Auslesung werden tagesgenaue Messwerte der vergangenen 6 Wochen gespeichert. Messwerte, die älter als 6 Wochen sind, werden gelöscht. Der Anwendungsfall ist immer im Hintergrund aktiv!

**TAF 7 - Zählerstandsgangmessung** Erfassung und Versendung von mindestens viertelstündiger gemessenen Energiemengen (Verbrauch oder Erzeugung), unter anderem für die Tarifierung außerhalb des Smart Meters.

**TAF 8 - Erfassung der Extremwerte für Leistung** Ermöglicht die Erfassung und Versendung von Maximal- bzw. Minimalleistungswerten, die innerhalb eines Abrechnungszeitraumes anfallen.

**TAF 9 - Abruf der Ist-Einspeisung einer Erzeugungsanlage nach EEG/KWKG** Erlaubt die Auslesung und Versendung der Ist-Einspeiseleistung von Erzeugungsanlagen im Rahmen einer Energiemanagementmaßnahme.

**TAF 10 - Abruf von Netzzustandsdaten** Ermöglicht die Bereitstellung sowie den Versand von Netzzustandsdaten im Smart-Meter-Gateway und den Statusinformation der am Gateway angeschlossenen Zähler. Der zeitliche Versand der Daten erfolgt in festgelegten gleichen Abständen oder bei Eintritt von bestimmten Ereignissen.

**TAF 11 - Steuerung von unterbrechbaren Verbrauchseinrichtungen und Erzeugungsanlagen** Bei einem Steuerungssignal oder anderen externen Ereignissen werden der Zeitpunkt und der aktuelle Zählerstand festgehalten. Gilt für unterbrechbare Verbrauchseinrichtungen und steuerbare Erzeugungsanlagen.

**TAF 12 - Prepaid-Tarif** Mit einem Prepaid-Tarif wird ein bestimmter Betrag bei einem externen Marktteilnehmer (z.B. Energielieferanten) für eine bestimmte Energiemenge entrichtet. Verbraucher und externer Marktteilnehmer erhalten bei Unterschreiten eines festgelegten Schwellenwertes eine Benachrichtigung.

**TAF 13 - Bereitstellung von Messwertsätzen zur Visualisierung für den Letztverbraucher über die WAN-Schnittstelle** Alternative zur lokalen Visualisierung über das HAN: Die anwendungsfallspezifischen Messwertsätze (TAF1 – TAF12) werden über die WAN-Schnittstelle bereitgestellt, sodass eine Visualisierung der Daten für den Letztverbraucher realisiert werden kann.

**TAF 14 - Hochfrequente Messwertbereitstellung für Mehrwertdienste** Erlaubt die hochfrequente Bereitstellung von Messwerten als Grundlage zur Umsetzung von Mehrwertdiensten (z.B. die Visualisierung der Messwerte für den Anschlussnutzer durch ein Internetportal).

[^1]: Vielfache eines Monats sind auch 24 Monate, also Zwei-Jahres-Zeiträume, oder 13 Monate, also 13-monatige zeiträume. Laut BSI-TR ist beides ein denkbarer Beauftragungszustand an ein SMGW. Aus anderen Legalen Gründen (z.B. EnWG) dürfte sich allerdings ein längstens jährlicher Abrechnungs- und damit Ablesezeitraum als zulässig ergeben (also längstens 12-monatige Zeiträume). 