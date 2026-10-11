# Ordinations-Terminbuch – Programmbeschreibung

Stand: 11. Oktober 2026

## Überblick

Das Ordinations-Terminbuch ersetzt den Papierkalender am Empfang durch eine einzelne HTML-Datei, die im Browser läuft. Es verwaltet Termine mit frei wählbarer Dauer, zeigt freie und belegte Zeiten auf einen Blick und braucht weder Installation noch Internet.

Das Programm ist auf eine Ordination mit wenigen Öffnungstagen und langer Vorlaufzeit zugeschnitten, voreingestellt sind Mittwoch und Freitag von 08:00 bis 13:00 Uhr. Öffnungstage, Zeiten und Termindauer lassen sich frei ändern, daher passt es auch für andere Betriebe mit Terminvergabe.

Die wichtigsten Funktionen:

- Monatsübersicht für 1 bis 12 Monate, wahlweise als Auslastung in Farbstufen oder als Zeitleiste je Tag
- Tagesblatt mit allen Terminen und freien Zeiten des gewählten Tages
- Eintragen, Ändern, Verschieben, Einschieben und Absagen von Terminen, auch durch Ziehen mit der Maus
- Suche nach dem nächsten freien Termin und nach Terminen eines Patienten
- Rückgängig für bis zu 30 Änderungen
- Namensliste mit Vorschlägen für Name, Telefon und Notiz
- Ausgabe der Tagesblätter als PDF, Word, Excel, OpenDocument, Text oder Markdown
- Datendatei, in die jede Änderung von selbst geschrieben wird, dazu Sicherung auf Knopfdruck
- Oberfläche auf Deutsch oder Englisch, umschaltbar in den Einstellungen

## Start und Voraussetzungen

Das ganze Programm ist die Datei `Terminbuch.html`. Ein Doppelklick öffnet sie im Browser, es gibt keine Installation und keine weiteren Dateien.

- **Browser:** Chrome oder Edge in aktueller Version sind empfohlen. In Firefox läuft alles außer Datendatei und Namensdatei.
- **Internet:** Wird nicht gebraucht. Die Datei lädt nichts aus dem Netz nach.
- **Gerät:** Gedacht ist ein PC mit Maus am Empfang. Auf Tablet und Handy ordnet sich die Seite einspaltig an, das Ziehen mit der Maus entfällt dort.
- **Hell und dunkel:** Die Darstellung folgt der Einstellung des Betriebssystems.

Im Reiter des Browsers zeigt die Seite ein eigenes Symbol: ein Kalenderblatt mit Feldern in den Belegungsfarben, das orange Feld steht für heute. Das Symbol steckt in der HTML-Datei. Dieselbe Grafik liegt als `Terminbuch.ico` für eine Verknüpfung auf dem Desktop bei.

Beim ersten Start zeigt das Programm erfundene Beispieldaten, damit ein gefülltes Buch zu sehen ist. Der Knopf „Beispieldaten löschen“ in der Leiste oben entfernt sie samt den dazugehörigen Namen, danach ist das Buch leer und einsatzbereit.

Vor dem ersten echten Termin sollten unter „Öffnungszeiten, Termindauer und Sicherung“ die Ordinationstage, die Zeiten und die übliche Termindauer eingestellt und der Speicherordner gewählt werden. Dabei entsteht auch die Datendatei.

## Aufbau der Oberfläche

Die Seite hat links die Übersicht und die Werkzeuge, rechts das Tagesblatt des gewählten Tages. Das Tagesblatt bleibt beim Blättern stehen und hat eine eigene Bildlaufleiste.

| Bereich | Wo | Inhalt |
| --- | --- | --- |
| Kopf | oben | Name der Ordination, Öffnungszeiten, übliche Termindauer, Zustand der Datendatei und drei Kennzahlen |
| Monatsübersicht | links | Kalender mit Auslastung je Tag, Navigation, Anzahl der Monate, Rückgängig |
| Tagesblatt | rechts | Termine und freie Zeiten des gewählten Tages |
| Freien Termin finden | links unten | Die nächsten freien Termine ab einem Datum |
| Termin eines Patienten suchen | links unten | Suche nach Name, Telefon oder Notiz |
| Tagesblätter speichern | links unten | Ausgabe eines Zeitraums in sieben Dateiformaten |
| Öffnungszeiten, Termindauer und Sicherung | ganz unten, aufklappbar | Einstellungen, Datendatei, Sicherung, Namensliste |

Die drei Kennzahlen im Kopf sind:

- **Nächster freier Termin:** Ein Klick springt zu diesem Tag und öffnet das Formular zum Eintragen.
- **Frei in 4 Wochen:** Anzahl der freien Termine in üblicher Länge in den nächsten 28 Tagen.
- **Termine ab heute:** Anzahl aller eingetragenen Termine von heute an.

## Monatsübersicht

Die Monatsübersicht zeigt für jeden Ordinationstag, wie voll er ist, und dient zugleich zur Auswahl des Tages. Ein Klick auf einen Tag öffnet sein Tagesblatt.

### Bedienung

- **Pfeile und „Heute“:** Die Pfeile blättern um einen Monat, „Heute“ springt zum aktuellen Monat und zum nächsten Ordinationstag.
- **Monate:** Die Auswahl stellt 1 bis 12 Monate nebeneinander dar. Die Wahl bleibt gespeichert.
- **Auslastung oder Zeitfenster:** Der Umschalter wechselt zwischen den beiden Darstellungen.
- **Hinweis beim Überfahren:** Die Maus über einem Tag zeigt Datum, Öffnungszeit, Zahl der Termine und freie Termine.

### Darstellung „Auslastung“

Jeder Ordinationstag ist nach dem Anteil der belegten Öffnungszeit eingefärbt und trägt die Zahl der freien Termine.

| Stufe | Bedeutung |
| --- | --- |
| leer (weiß mit Rand) | kein Termin eingetragen |
| bis ⅓ | höchstens ein Drittel der Öffnungszeit belegt |
| bis ⅔ | höchstens zwei Drittel belegt |
| über ⅔ | mehr als zwei Drittel belegt, aber noch mindestens ein Termin frei |
| voll (dunkelste Stufe) | kein Termin in üblicher Länge mehr frei |

Im Feld steht „3 frei“ oder „voll“. Gezählt wird, wie oft die übliche Termindauer noch in die Lücken passt. In der dunklen Darstellung sind die Stufen umgekehrt, dort ist der vollste Tag der hellste.

### Darstellung „Zeitfenster“

Jeder Tag zeigt seine Öffnungszeit als Zeitleiste in ein bis vier Zeilen, von früh nach spät. Belegte Abschnitte sind blau, freie grau, und die Länge entspricht der Dauer. So ist zu sehen, zu welcher Tageszeit noch Platz ist.

### Weitere Kennzeichen

- **Kalenderwoche:** Klein und grau in der schmalen Spalte links jeder Woche.
- **Ordinationstage:** Ihre Wochentage sind in der Kopfzeile fett.
- **Gesperrte Tage:** Schraffiert mit dem Wort „zu“, etwa Feiertage oder Urlaub.
- **Heute:** Ein oranger Punkt in der Ecke des Feldes.
- **Vergangene Tage:** Abgeblasst.
- **Frei im Monat:** Rechts neben dem Monatsnamen steht die Summe der freien Termine ab heute.

### Einen Monat vergrößern

Steht die Auswahl auf einem Monat, lässt sich das Raster an der Ecke rechts unten mit der Maus größer ziehen. Zahlen und Zeitleisten wachsen mit, die Größe bleibt gespeichert.

## Tagesblatt

Das Tagesblatt listet alle Termine und freien Zeiten des gewählten Tages in zeitlicher Reihenfolge. Darüber stehen Datum, Zahl der Termine, Zahl der freien Termine und eine Zeitleiste über die ganze Öffnungszeit.

### Freie Zeiten

Freie Zeiten sind die Lücken zwischen den Terminen. Jede Lücke wird von ihrem Beginn an in Stücke der üblichen Termindauer zerlegt.

- Endet ein Termin um 15:15, wird 15:15 als nächste freie Zeit angeboten.
- Ein Rest, der kürzer als die übliche Dauer ist, steht als „frei · nur 10 Min.“ in der Liste. Er zählt nicht zu den freien Terminen.
- Bereits vergangene freie Zeiten werden nicht mehr angezeigt.

### Termin eintragen

1. Bei der gewünschten freien Zeit auf „Eintragen“ klicken.
2. Den Namen eingeben. Bekannte Namen werden vorgeschlagen, die Telefonnummer wird dann eingesetzt.
3. Bei Bedarf Beginn und Dauer anpassen. Der Beginn hat ein 5-Minuten-Raster, die Dauer reicht von 5 bis 600 Minuten. Darunter steht zur Kontrolle „von 15:00 bis 15:15 Uhr“.
4. Telefon und Notiz sind freiwillig. Für die Notiz werden früher verwendete Begriffe vorgeschlagen.
5. Mit „Eintragen“ oder der Eingabetaste speichern. „Abbrechen“ oder Esc verwirft die Eingabe.

### Prüfungen beim Speichern

- **Überschneidung:** Ragt der neue Termin in folgende Termine hinein, wird er eingeschoben und diese rücken nach hinten. Das Programm nennt sie vorher, ein zweiter Klick bestätigt. Ein Beginn mitten in einem laufenden Termin wird abgelehnt.
- **Außerhalb der Öffnungszeit, gesperrter Tag oder Vergangenheit:** Es erscheint eine Warnung. Ein zweiter Klick auf den Speicherknopf trägt den Termin trotzdem ein. Bleiben beim Ändern Datum, Beginn und Dauer gleich, entfällt die Warnung.
- **Über Mitternacht:** Wird abgelehnt.

### Termin ändern oder auf einen anderen Tag verschieben

„Ändern“ öffnet den Termin mit Name, Datum, Beginn, Dauer, Telefon und Notiz.

- Das neue Datum lässt sich eintippen oder durch Klick auf einen Tag in der Monatsübersicht wählen. Der Zieltag ist dort gestrichelt orange umrandet.
- Unter dem Formular stehen die freien Zeiten des Zieltages. Ein Klick übernimmt die Uhrzeit.
- Nach dem Speichern zeigt das Tagesblatt den Zieltag.
- Solange das Formular offen ist, wählt ein Klick in die Monatsübersicht das Zieldatum und wechselt nicht den Tag.

### Termin absagen

„Absagen“ verlangt eine Bestätigung mit „Wirklich absagen“. Danach ist der Termin gelöscht und seine Zeit steht wieder als frei in der Liste und in der Übersicht.

### Tage sperren und Zusatztage

Der Knopf am Fuß des Tagesblatts ändert den Status des Tages.

| Ausgangslage | Knopf | Wirkung |
| --- | --- | --- |
| Ordinationstag | Tag sperren | Keine freien Zeiten mehr, etwa bei Urlaub oder Fortbildung |
| Von Hand gesperrter Tag | Tag wieder öffnen | Der Tag gilt wieder als Ordinationstag |
| Feiertag oder anderer Wochentag | Als Zusatztag öffnen | Der Tag bekommt einmalig Öffnungszeiten |
| Zusatztag | Zusatztag wieder schließen | Der Tag ist wieder geschlossen |

Ein Zusatztag übernimmt die Zeiten des ersten eingestellten Ordinationstages. Sind an einem gesperrten Tag noch Termine eingetragen, bleiben sie erhalten und das Tagesblatt weist darauf hin.

## Verschieben mit der Maus

Jeder Termin im Tagesblatt lässt sich mit der Maus anfassen und auf eine freie Zeit, auf einen anderen Termin oder auf einen anderen Tag ziehen. Alle übrigen Termine behalten ihren Eintrag, solange der Platz reicht.

### Auf eine freie Zeit desselben Tages

- **Der Termin passt in die Lücke:** Er wird sofort dorthin verschoben.
- **Die Lücke ist zu kurz:** Es erscheint eine Warnung mit den betroffenen Terminen und ihren neuen Zeiten. „Fortfahren“ führt die Verschiebung aus, „Abbrechen“ lässt alles, wie es war.

Beim Fortfahren rücken die folgenden Termine nur so weit nach hinten, wie es nötig ist. Beispiel: Ein Termin von 15 Minuten wird auf eine freie Zeit von 10 Minuten gezogen, die folgenden Termine rücken um 5 Minuten. Kommt danach eine Lücke, fängt sie den Unterschied auf und spätere Termine bleiben an ihrem Platz.

Zwei Sonderfälle:

- Würde der letzte verschobene Termin nach Ordinationsende enden, steht das zusätzlich in der Warnung.
- Würden Termine über Mitternacht hinausrücken, wird die Verschiebung abgelehnt.

### Zwischen zwei Terminen einschieben

Wird ein Termin auf einem anderen Termin abgelegt, wird er vor diesem eingeschoben. Eine blaue Linie über dem Zieltermin zeigt die Einfügestelle.

Der Zieltermin und die direkt folgenden Termine rücken um die Dauer des eingeschobenen Termins nach hinten, bis eine Lücke den Unterschied auffängt. Vor dem Ausführen listet ein Hinweis alle neuen Zeiten und verlangt „Fortfahren“.

Beispiel: Ein Termin von 15 Minuten wird auf den Termin um 08:30 gezogen. Er bekommt 08:30, der bisherige Termin rückt auf 08:45 und der nächste von 09:00 auf 09:15.

Ein neuer Termin lässt sich genauso einschieben. Der Knopf „+ davor“ in der Zeile eines Termins öffnet das Formular mit dessen Beginn. Beim Speichern nennt das Programm die Termine, die nachrücken, und ein zweiter Klick bestätigt.

### Auf einen anderen Tag

Wird ein Termin auf einen Tag in der Monatsübersicht gezogen, öffnet sich das Änderungsformular mit diesem Datum und den freien Zeiten des Zieltages. Gespeichert wird erst mit „Speichern“.

Termine an vergangenen Tagen lassen sich nicht ziehen. Auf Geräten ohne Maus führt der Weg über „Ändern“.

## Freien Termin finden und Patientensuche

### Freien Termin finden

Das Werkzeug listet die nächsten acht freien Termine in üblicher Länge ab einem Datum. Es ist für Kontrolltermine mit langer Vorlaufzeit gedacht.

- Die Knöpfe „ab heute“, „in 1 Monat“, „in 2 Monaten“, „in 3 Monaten“, „in 4 Monaten“ und „in 6 Monaten“ setzen das Startdatum.
- Im Feld „Frühestens ab“ lässt sich jedes andere Datum wählen.
- Ein Klick auf einen Treffer springt zu diesem Tag und öffnet das Formular zum Eintragen.
- Gesucht wird bis zu 18 Monate voraus.

### Termin eines Patienten suchen

Die Suche findet Termine nach Name, Telefon oder Notiz und beginnt ab zwei Buchstaben. Sie hilft, wenn jemand anruft und seinen Termin nicht mehr weiß.

- Angezeigt werden bis zu zwölf Treffer mit Datum, Uhrzeit und Name.
- Kommende Termine stehen oben, vergangene am Ende mit dem Vermerk „vergangen“.
- Ein Klick auf einen Treffer öffnet das Tagesblatt dieses Tages.

## Rückgängig

Der Knopf „↶ Rückgängig“ nimmt bis zu 30 Änderungen Schritt für Schritt zurück. Die Zahl in Klammern zeigt, wie viele Schritte möglich sind, Strg+Z wirkt genauso.

Zurückgenommen werden:

- Eintragen, Ändern, Verschieben, Einschieben und Absagen von Terminen
- Sperren und Öffnen von Tagen
- Änderungen an Öffnungszeiten, Termindauer, Feiertagsregel und Name
- Änderungen an der Namensliste
- Das Einlesen einer Sicherung, das Laden des Stands aus der Datendatei und das Löschen der Beispieldaten

Die Ansicht selbst gehört nicht dazu, also Sprache, Darstellung, Anzahl der Monate und Vergrößerung. Die Liste der Schritte gilt nur, solange die Seite geöffnet ist. Strg+Z greift nicht, während der Cursor in einem Eingabefeld steht.

## Namensliste und Namensdatei

Das Programm merkt sich bei jedem gespeicherten Termin Name, Telefonnummer und Notizbegriff und schlägt sie beim nächsten Eintragen vor. Die Liste steht in den Einstellungen unter „Namensliste“.

### Vorschläge beim Eintragen

- Im Feld „Name“ erscheinen passende Namen, sobald getippt wird.
- Wird ein bekannter Name gewählt, setzt das Programm die gespeicherte Telefonnummer ein.
- Eine neu eingegebene Telefonnummer ersetzt die gespeicherte.
- Im Feld „Notiz“ erscheinen früher verwendete Begriffe.

### Liste pflegen

| Knopf | Wirkung |
| --- | --- |
| Einträge einzeln löschen | Klappt die Liste mit Suchfeld auf. Je Zeile lässt sich der Name löschen oder nur seine Telefonnummer, darunter jeder Notizbegriff. |
| Namensliste speichern | Schreibt die Liste in die Datei `terminbuch-namen.json`. |
| Namensliste einlesen | Liest eine solche Datei ein und ergänzt die vorhandene Liste. |
| Liste leeren | Entfernt alle Namen und Notizbegriffe. |

Jede Löschung lässt sich mit „Rückgängig“ zurückholen. Eingetragene Termine bleiben vom Löschen eines Namens unberührt.

### Namensdatei: automatisch speichern und einlesen

Mit „Namensdatei verbinden“ wird einmal eine JSON-Datei ausgewählt. Danach schreibt das Programm jede Änderung der Liste von selbst in diese Datei und liest sie beim Start ein.

- **Erlaubnis:** Der Browser verlangt beim nächsten Start die Zustimmung zum Zugriff. Dann erscheint oben eine Leiste mit dem Knopf „Zugriff erlauben“. Ab Chrome 122 bietet die Abfrage auch an, den Zugriff bei jedem Besuch zu erlauben.
- **Zusammenführen:** Beim Einlesen werden Datei und Liste vereint, es geht kein Name verloren.
- **Schutz fremder Dateien:** Eine Datei mit anderem Inhalt wird abgelehnt und nicht überschrieben.
- **Trennen:** „Verbindung trennen“ beendet das automatische Speichern. Die Datei bleibt erhalten.

Die Funktion gibt es nur in Chrome und Edge mit der lokalen Datei. In anderen Browsern steht an ihrer Stelle ein Hinweis, Speichern und Einlesen von Hand bleiben möglich. Die Namensliste steckt auch in der Datendatei. Die eigene Namensdatei ist nur nötig, wenn die Liste getrennt gebraucht wird.

## Tagesblätter speichern

Das Werkzeug schreibt die Tagesblätter eines Zeitraums in eine Datei, zum Ausdrucken, Ablegen oder Weitergeben. Enthalten sind alle Ordinationstage des Zeitraums und geschlossene Tage, an denen Termine stehen.

1. Bei „Von“ und „Bis“ den Zeitraum wählen, höchstens 400 Tage. Voreingestellt sind heute und die folgenden 14 Tage.
2. Das Format wählen.
3. Bei Bedarf „Freie Zeiten mit ausgeben“ ankreuzen. Zusammenhängende freie Zeiten erscheinen dann als eine Zeile.
4. Auf „Speichern“ klicken. Die Datei landet im Speicherordner. Ist keiner gewählt, landet sie im Download-Ordner des Browsers.

„Nur gewählter Tag“ setzt beide Datumsfelder auf den Tag, der gerade im Tagesblatt offen ist.

| Format | Endung | Aufbau |
| --- | --- | --- |
| PDF | .pdf | A4, je Tag eine Überschrift mit Tabelle, Seitenzahlen. Sehr lange Namen und Notizen werden gekürzt. |
| Word | .docx | Je Tag eine Überschrift mit Tabelle |
| OpenDocument Text | .odt | Je Tag eine Überschrift mit Tabelle |
| Excel | .xlsx | Eine Tabelle „Termine“, eine Zeile je Termin, Datum und Uhrzeit als echte Datums- und Zeitwerte |
| OpenDocument Tabelle | .ods | Eine Tabelle „Termine“, eine Zeile je Termin |
| Text | .txt | Spalten mit fester Breite |
| Markdown | .md | Überschriften und Tabellen in Markdown |

PDF, Word, OpenDocument Text, Text und Markdown führen die Spalten Beginn, Ende, Dauer, Name, Telefon und Notiz. Die Tabellenformate haben zusätzlich Datum und Wochentag, damit sich die Liste sortieren und filtern lässt.

Der Dateiname lautet `tagesblaetter_VON_bis_BIS` mit der jeweiligen Endung, zum Beispiel `tagesblaetter_2026-10-19_bis_2026-10-30.pdf`.

## Einstellungen

Alle Einstellungen stehen im aufklappbaren Bereich „Öffnungszeiten, Termindauer und Sicherung“ am Ende der linken Spalte. Jede Änderung wirkt sofort und lässt sich rückgängig machen.

| Einstellung | Werte | Wirkung |
| --- | --- | --- |
| Sprache / Language | Deutsch oder English | Sprache der ganzen Oberfläche und der gespeicherten Tagesblätter |
| Name im Kopf | freier Text, bis 60 Zeichen | Überschrift der Seite und Titel der gespeicherten Tagesblätter |
| Übliche Termindauer | 5, 10, 15, 20, 30, 45 oder 60 Minuten | Länge, in der freie Zeiten angeboten und gezählt werden. Vorgabe für neue Termine. |
| Ordinationstage | Montag bis Sonntag, je Tag Beginn und Ende | Legt fest, an welchen Wochentagen und zu welchen Zeiten Termine angeboten werden |
| Österreichische Feiertage automatisch sperren | ein oder aus | Sperrt die 13 gesetzlichen Feiertage |

Hinweise dazu:

- **Geänderte Öffnungszeiten:** Bereits eingetragene Termine bleiben erhalten, auch wenn sie danach außerhalb der Öffnungszeit liegen. Die Zeitleisten zeigen dann den erweiterten Bereich.
- **Geänderte Termindauer:** Sie verändert nur, wie freie Zeiten angeboten werden. Eingetragene Termine behalten ihre Dauer.
- **Feiertage:** Berücksichtigt sind Neujahr, Heilige Drei Könige, Ostermontag, Staatsfeiertag, Christi Himmelfahrt, Pfingstmontag, Fronleichnam, Mariä Himmelfahrt, Nationalfeiertag, Allerheiligen, Mariä Empfängnis, Christtag und Stefanitag. Ein einzelner Feiertag lässt sich im Tagesblatt als Zusatztag öffnen.
- **Prüfung:** Liegt das Ende eines Tages nicht nach dem Beginn, wird die Eingabe mit einer Meldung abgelehnt.

### Sprache

Die Oberfläche gibt es auf Deutsch und auf Englisch. Beim ersten Start gilt die Sprache des Browsers: Deutsch bei einem deutschen Browser, sonst Englisch. Umgeschaltet wird in den Einstellungen bei „Sprache / Language“, die Wahl wirkt sofort und bleibt gespeichert.

| Bereich | Was sich mit der Sprache ändert |
| --- | --- |
| Oberfläche | alle Beschriftungen, Hinweise und Meldungen |
| Datum | Wochentage und Monate, dazu die Schreibweise: „Mi 21.10.2026“ wird „Wed 21 Oct 2026“ |
| Feiertage | die Namen der 13 österreichischen Feiertage, etwa „Christtag“ und „Christmas Day“ |
| Tagesblätter | Überschriften und Spalten in allen sieben Formaten. Der Dateiname lautet auf Englisch `daysheets_VON_to_BIS`. |
| Beispieldaten | Notizen und der vorgegebene Name im Kopf, solange die Beispieldaten nicht gelöscht sind |

Gleich bleiben in beiden Sprachen:

- eingetragene Namen, Telefonnummern, Notizen und ein selbst gewählter Name im Kopf
- die Dateinamen `terminbuch-daten.json`, `terminbuch-namen.json` und die der Sicherungen
- Uhrzeiten im 24-Stunden-Format und die Woche von Montag bis Sonntag
- die Feiertagsregel, sie bezieht sich immer auf Österreich

Arbeiten zwei PCs mit derselben Datendatei, behält jeder Browser seine eigene Sprache. Mit „Rückgängig“ lässt sich ein Sprachwechsel nicht zurücknehmen, dafür genügt die Auswahl.

Die wichtigsten Begriffe in beiden Sprachen:

| Deutsch | Englisch |
| --- | --- |
| Ordinationstage | Opening days |
| Tagesblatt | Day sheet |
| Auslastung, Zeitfenster | Occupancy, Timeline |
| Eintragen, Ändern, Absagen | Book, Edit, Remove |
| + davor | + before |
| Tag sperren, Zusatztag | Close day, Extra day |
| Übliche Termindauer | Usual appointment duration |
| Speicherordner, Datendatei | Storage folder, Data file |
| Sicherung, Namensliste | Backup, Name list |
| Rückgängig | Undo |

## Datenspeicherung und Sicherung

Das Programm speichert nach jeder Änderung von selbst, einen Speicherknopf gibt es nicht. Gespeichert wird immer im internen Speicher des Browsers und zusätzlich in der Datendatei, sobald eine verbunden ist.

Gespeichert werden Termine, gesperrte Tage und Zusatztage, Einstellungen, die Namensliste sowie Sprache, Darstellung, Anzahl der Monate und Vergrößerung.

### Speicherordner

Der Speicherordner legt fest, wohin das Programm seine Dateien schreibt. Empfohlen ist der Ordner, in dem die `Terminbuch.html` liegt, zum Beispiel `D:\Terminbuch`.

1. Im Kopf auf „Speicherort einrichten“ klicken. Die Einstellungen klappen auf und nennen den Ordner der HTML-Datei.
2. „Speicherordner wählen“ anklicken und diesen Ordner auswählen.
3. Ist noch keine Datendatei verbunden, legt das Programm dort `terminbuch-daten.json` an oder öffnet die vorhandene.

| Datei | Entsteht durch | Dateiname |
| --- | --- | --- |
| Datendatei | jede Änderung, von selbst | `terminbuch-daten.json` |
| Sicherung | „Sicherung erstellen“ | `terminbuch-JJJJ-MM-TT_HHMM.json` |
| Namensliste | „Namensliste speichern“ | `terminbuch-namen.json` |
| Tagesblätter | „Speichern“ unter „Tagesblätter speichern“ | `tagesblaetter_VON_bis_BIS` mit Endung |

Hinweise:

- Ohne Speicherordner landen Sicherung, Namensliste und Tagesblätter im Download-Ordner des Browsers.
- Ein Browser kennt den Ordner einer HTML-Datei nicht von selbst, deshalb muss er einmal gewählt werden.
- Beim ersten Speichern nach dem Start fragt der Browser nach der Erlaubnis für den Ordner.
- Eine Datei mit gleichem Namen wird überschrieben. Sicherungen tragen deshalb Datum und Uhrzeit im Namen.
- Manche Ordner lässt der Browser nicht zu. Ein eigener Unterordner funktioniert.
- Den Speicherordner gibt es nur in Chrome und Edge mit der lokalen Datei.

### Datendatei

Die Datendatei ist eine gewöhnliche JSON-Datei mit dem ganzen Terminbuch, etwa `terminbuch-daten.json` in einem Ordner auf dem PC oder auf einer Netzwerkfreigabe. Für den Einsatz in der Ordination ist sie der empfohlene Speicherort.

- Jede übliche Datensicherung nimmt die Datei mit.
- Die Termine überstehen das Löschen der Browserdaten und einen Browserwechsel.
- Für den Umzug auf einen anderen PC genügt es, die Datei dort zu öffnen.

Einrichten:

1. Am einfachsten den Speicherordner wählen. Die Datendatei entsteht dabei von selbst in diesem Ordner.
2. Soll sie an einem anderen Ort liegen, etwa auf einer Netzwerkfreigabe, in den Einstellungen „Neue Datendatei anlegen“ wählen und Ordner und Namen festlegen. Der aktuelle Stand wird sofort hineingeschrieben.
3. Auf einem weiteren PC oder nach einer Neuinstallation stattdessen „Vorhandene Datendatei öffnen“ wählen.

Danach steht der Zustand in der Zeile unter den Öffnungszeiten, zum Beispiel „Datendatei terminbuch-daten.json · zuletzt gespeichert um 09:58:12“. „Verbindung trennen“ in den Einstellungen beendet das automatische Speichern, die Datei bleibt erhalten.

### Abgleich zwischen Datei und Browser

Beim Start und vor jedem Schreiben prüft das Programm, ob die Datei inzwischen von anderer Stelle geändert wurde.

| Lage | Was das Programm tut |
| --- | --- |
| Datei und Browser sind gleich | Nichts, die Kopfzeile meldet „auf dem aktuellen Stand“ |
| Die Datei wurde anderswo geändert, hier nichts | Der Stand aus der Datei wird übernommen |
| Nur hier wurde geändert | Der Stand hier wird in die Datei geschrieben |
| Beides wurde geändert | Das automatische Speichern hält an. Eine rote Leiste nennt die Zahl der Termine auf beiden Seiten und fragt, welcher Stand gelten soll. |
| Der Browser ist leer oder zeigt Beispieldaten, die Datei enthält ein Terminbuch | Die Datei wird ohne Rückfrage übernommen |
| Die Datei enthält etwas anderes als ein Terminbuch | Sie wird abgelehnt und nicht überschrieben |
| Die Datei ist nicht erreichbar | Eine Meldung erscheint. Die Änderungen bleiben im Browser und werden beim nächsten Speichern nachgetragen. |

Die Leiste bietet „Stand aus der Datei laden“ und „Datei mit dem Stand hier überschreiben“. Sie bleibt beim Blättern sichtbar. Das Laden aus der Datei lässt sich mit „Rückgängig“ zurücknehmen.

### Erlaubnis des Browsers

Der Browser verlangt beim nächsten Start die Zustimmung zum Zugriff auf die Datei. Dann erscheint oben eine Leiste mit „Zugriff erlauben“, bis dahin wird nur im Browser gespeichert. Ab Chrome 122 bietet die Abfrage auch an, den Zugriff bei jedem Besuch zu erlauben.

Die Datendatei gibt es nur in Chrome und Edge mit der lokalen Datei `Terminbuch.html`.

### Ohne Datendatei

- Die Daten hängen an diesem einen Browser. In einem anderen Browser oder auf einem anderen PC ist das Buch leer.
- Wer im Browser die Websitedaten löscht, löscht auch das Terminbuch.
- Eine regelmäßige Sicherung ist dann Pflicht, am besten am Ende jedes Ordinationstages.

### Sicherung erstellen und einlesen

| Knopf | Wirkung |
| --- | --- |
| Sicherung erstellen | Schreibt alle Daten in die Datei `terminbuch-JJJJ-MM-TT_HHMM.json` im Speicherordner, ohne Speicherordner im Download-Ordner |
| Sicherung einlesen | Ersetzt den gesamten Stand durch den Inhalt der gewählten Sicherungsdatei |

Das Einlesen lässt sich mit „Rückgängig“ zurücknehmen, solange die Seite offen bleibt. Eine Datei, die keine Terminbuch-Sicherung ist, wird abgelehnt.

Mit Datendatei genügt es, diese Datei in die übliche Datensicherung aufzunehmen. Die Sicherung auf Knopfdruck bleibt für eine Kopie mit Datum, etwa vor größeren Änderungen.

## Grenzwerte

Das Programm fasst im Test rund 60.000 Termine, eine feste Obergrenze ist nicht eingebaut. Die Grenze setzt der interne Speicher des Browsers mit etwa 5 Millionen Zeichen.

| Größe | Wert |
| --- | --- |
| Termine insgesamt | rund 60.000 im Test, bei Einträgen mit Name, Telefon und Notiz |
| Termine je Tag | bis 288, das sind 5-Minuten-Termine über 24 Stunden. In 5 Stunden Öffnungszeit bis 60. |
| Dauer eines Termins | 5 bis 600 Minuten in 5-Minuten-Schritten |
| Beginn eines Termins | 5-Minuten-Raster |
| Übliche Termindauer | 5, 10, 15, 20, 30, 45 oder 60 Minuten |
| Öffnungszeit | ein durchgehendes Zeitfenster je Wochentag, an bis zu 7 Wochentagen |
| Name, Telefon, Notiz | 80, 40 und 120 Zeichen |
| Name im Kopf | 60 Zeichen |
| Namensliste | keine feste Grenze. Die Pflegeliste zeigt je Suche 300 Einträge. |
| Rückgängig | 30 Schritte |
| Monate in der Übersicht | 1 bis 12 |
| Freien Termin finden | 8 Treffer, bis 18 Monate voraus |
| Patientensuche | 12 Treffer angezeigt |
| Tagesblätter speichern | Zeitraum bis 400 Tage |

Zur Einordnung:

- **Platzbedarf:** 1.000 Termine belegen rund 82.000 Zeichen. Bei zwei Ordinationstagen je Woche mit zehn Terminen sind das etwa 1.000 Termine im Jahr.
- **Geschwindigkeit:** Mit 50.000 Terminen dauerten Speichern 38 Millisekunden und Anzeigen 21 Millisekunden.
- **Alte Termine:** Sie bleiben erhalten und werden nie von selbst gelöscht.
- **Voller Speicher:** Eine rote Leiste meldet, wenn der Browser nicht mehr speichern kann. In eine verbundene Datendatei wird weiter geschrieben.

Gemessen wurde in einem Testbrowser auf Chromium-Basis. In Chrome und Edge sind ähnliche Werte zu erwarten, sie können je nach Version abweichen.

## Grenzen und Hinweise für den Einsatz

Das Terminbuch ist ein Einzelplatzprogramm für die reine Terminvergabe. Die folgenden Punkte sollten vor dem Einsatz in der Ordination bekannt sein.

### Was das Programm nicht kann

- **Kein Mehrplatzbetrieb:** Zwei PCs können nicht gleichzeitig im selben Buch arbeiten. Liegt die Datendatei auf einer Freigabe, können sie es nacheinander. Gleichzeitige Änderungen werden erkannt und gemeldet, aber nicht zusammengeführt.
- **Kein Kennwort, keine Verschlüsselung:** Wer an den PC und den Browser kommt, sieht die Termine. Auch die Sicherungsdatei ist unverschlüsselt.
- **Keine Online-Buchung und keine Erinnerungen:** Patienten können nicht selbst buchen, das Programm verschickt weder SMS noch E-Mail.
- **Keine Serientermine:** Wiederkehrende Termine werden einzeln eingetragen.
- **Keine Patientenkartei und keine Abrechnung:** Gespeichert werden nur Name, Telefon und eine kurze Notiz.

### Datenschutz

Namen, Telefonnummern und Termine von Patienten sind personenbezogene Daten. Der PC sollte ein eigenes Benutzerkonto mit Kennwort haben, und Sicherungen sowie gespeicherte Tagesblätter gehören an einen geschützten Ort. Die rechtliche Beurteilung liegt bei der Ordination.

### Stand der Prüfung

- Alle Funktionen wurden in einem Testbrowser auf Chromium-Basis durchgespielt.
- Die sieben Dateiformate wurden mit LibreOffice und weiteren Werkzeugen geöffnet und geprüft. Mit Microsoft Word und Excel wurde nicht getestet.
- Speicherordner, Datendatei und Namensdatei wurden mit Ersatzdateien geprüft. Der echte Dateidialog von Chrome und Edge ist noch nicht erprobt.
- Die englische Oberfläche wurde am 11. Oktober 2026 in allen Abläufen durchgespielt, auch mit den sieben Dateiformaten. Es blieb kein deutscher Text stehen. Die deutsche Oberfläche lieferte danach dieselben Ergebnisse wie zuvor.
- Ein Probelauf über einige Ordinationstage neben dem Papierkalender ist empfohlen, bevor der Papierkalender wegfällt.

Die Durchsicht des gesamten Programmcodes am 9. Oktober 2026 hat sechs Schwachstellen ergeben, die behoben sind:

- Ein voller oder gesperrter Browser-Speicher wurde nicht gemeldet. Jetzt erscheint eine rote Leiste.
- Zwei offene Fenster desselben Terminbuchs konnten einander überschreiben. Jetzt übernimmt jedes Fenster die Änderungen des anderen.
- Entzog der Browser die Erlaubnis für Datendatei oder Namensdatei, fehlte der Knopf zum erneuten Erlauben.
- Ein Wechsel der Ansicht galt als Datenänderung und konnte beim Abgleich mit der Datendatei eine unnötige Rückfrage auslösen.
- Im PDF wurden Buchstaben wie Š, č oder ő durch Fragezeichen ersetzt. Jetzt bleibt Š erhalten, č und ő erscheinen als c und o.
- Das Ändern von Telefon oder Notiz bei einem vergangenen Termin verlangte eine unnötige Bestätigung.

### Tastatur

| Taste | Wirkung |
| --- | --- |
| Eingabetaste | Speichert das offene Terminformular |
| Esc | Schließt Formular, Absagefrage oder Verschiebewarnung |
| Strg+Z | Nimmt die letzte Änderung zurück |
