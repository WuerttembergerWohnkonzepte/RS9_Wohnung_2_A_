# Roseggerstrasse 9, Kirchheim unter Teck, Wohnung Nr. 2 (EG rechts)

## Was in diesem Ordner liegt

    index.html          das Expose
    bilder/             14 Bilddateien, vom Expose eingebunden
    unterlagen/         18 PDF, ueber die Downloadkarten verlinkt

Alle drei muessen beieinander bleiben. Fehlt "bilder", zeigt die Seite
keine Fotos. Fehlt "unterlagen", laufen die Downloads ins Leere.

Zusaetzlich liegt eine Stufe hoeher die Datei
`Vorschau_Roseggerstrasse-9_Wohnung-2.html`. Darin sind alle Bilder
eingebettet, sie laesst sich also per Doppelklick oeffnen und
weitergeben. Die Downloadkarten funktionieren dort nicht, weil der
Ordner "unterlagen" fehlt. Die Vorschau ist nur zum Gegenlesen,
veroeffentlicht wird der Ordner.

## Zahlengrundlage im Expose

Alle Werte stammen aus EG_rechts.xlsx.

    Kaufpreis                    192.000 EUR
    Kaufpreis je m2                3.231 EUR
    Erwerbsnebenkosten 7 %        13.440 EUR
    Gesamtinvestition            205.440 EUR
    Grund und Boden               35.567 EUR
    Abschreibungsbasis           169.873 EUR   = 82,69 % der Gesamtinvestition
    Restnutzungsdauer            19 Jahre      Gutachten WE2 vom 08.06.2026
    Abschreibung im Jahr           8.941 EUR   = 5,26 %
    Nettokaltmiete                   504 EUR   = 8,48 EUR/m2
    Mietsubvention                 5.640 EUR   siehe Staffelung unten
    Cashflow nach Steuern, 1. Monat   45,34 EUR bei Vollfinanzierung,
                                               5,00 Prozent Zins

## Stand nach der Umstellung auf die Mieterhoehung im April 2027

Das Expose ist auf denselben Stand gebracht wie das der Wohnung Nr. 3.
Geaendert wurden vier Dinge:

1. Die erste Mieterhoehung um 15 Prozent faellt im April 2027, danach
   alle 36 Monate. Der Rechner arbeitet dafuer monatsweise. In einem
   Wechseljahr enthaelt der Jahreswert drei Monate zum alten und neun
   Monate zum neuen Stand, deshalb stehen dort krumme Jahresmieten wie
   6.728 EUR fuer 2027.
2. Hausgeld und Instandhaltungsruecklage steigen mit je 3 Prozent im
   Jahr. Bisher waren es 3 Prozent beim Hausgeld und 2 Prozent bei der
   Ruecklage.
3. Der Zinsregler startet bei 5,00 Prozent, Bereich 4,50 bis
   5,50 Prozent, Schrittweite 0,05 Prozent. Eingestellt ueber
   `<input id="s-z" min="450" max="550" step="5" value="500">`.
4. Die Mietsubvention haengt jetzt an der Mietstufe und nicht mehr am
   Kalenderjahr.

Im Rechenmodell der index.html steht dafuer

    kost: 0.03
    stufeM: 3
    sub: [150, 100, 40, 0]

Die Werte in `sub` sind dem Mietstand zugeordnet, nicht dem
Kalenderjahr. Die 150 EUR fuer den Dezember 2026 liegen vor dem ersten
Rechenjahr und sind im Rechner nicht enthalten, weil er ab Januar 2027
in ganzen Jahren rechnet.

**ACHTUNG, GEAENDERTER GESAMTBETRAG.** Die Staffelung haengt seit der
Umstellung an der Mieterhoehung im April 2027 und laeuft damit drei
Monate laenger auf der hoechsten Stufe als bisher:

    Dez. 2026 bis Maerz 2027   150 EUR je Monat      600 EUR
    April 2027 bis Maerz 2030  100 EUR je Monat    3.600 EUR
    April 2030 bis Maerz 2033   40 EUR je Monat    1.440 EUR
    Summe                                         5.640 EUR

Vorher waren es 5.190 EUR, wie in Zelle M44 der Kalkulation. Der
Unterschied betraegt 450 EUR und ist eine kaufmaennische Entscheidung,
keine Rechenfrage. Sie ist noch offen, und sie haengt hier an zwei
Stellen:

- Die Herleitung des Kaufpreises ging bisher auf mit
  185.000 + 5.190 + 1.810 Aufrundung = 192.000 EUR. Mit 5.640 EUR
  geht diese Rechnung nicht mehr auf.
- Bei der Wohnung Nr. 3 steht dieselbe Frage offen, dort mit
  570 EUR Unterschied.

Entweder wird die Kalkulation auf 5.640 EUR angehoben, oder im Expose
wird die erste Stufe auf einen Monat verkuerzt. Fuer den zweiten Weg
sind in der index.html vier Stellen zu aendern: `sub:[150, 100, 40, 0]`
wird zu `sub:[100, 100, 40, 0]`, die erste Tabellenzeile im Kasten
"Unsere Mietsubvention" wird wieder auf Dezember 2026 und 150 EUR
gesetzt, die Zuschusszeile in der Monatsrechnung auf 100,00 EUR, und
alle vier Nennungen von 5.640 EUR gehen zurueck auf 5.190 EUR.
Solange das nicht entschieden ist, weichen Expose und Kalkulation an
dieser Stelle voneinander ab.

## Vor der Veroeffentlichung erledigen

1. **Adresse der veroeffentlichten Seite eintragen.** In der index.html
   steht im Kapitel Finanzierung genau eine Zeile:

       var EXPOSE_URL = "";

   Dort die Adresse der GitHub-Pages-Seite eintragen. Bleibt das Feld
   leer, steht in der vorbereiteten Mail an die Moeglichmacher ein
   Platzhalter statt des Links.

2. **Herleitung der Kaufpreisaufteilung vervollstaendigen.** Die
   uebergebene Datei enthaelt noch Platzhalter: "Erdgeschoss [bitte
   ergaenzen: links oder rechts]" ist rechts, der Kaufpreis fehlt, der
   Gebaeudeanteil und die Prozentwerte sind offen, und der Absatz zur
   Vermietungssituation ist leer. Fuer den letzten Punkt: Nettokaltmiete
   504 EUR, Mietverhaeltnis seit 15.09.2011, Miete unter der ortsueblichen
   Vergleichsmiete, dadurch eingeschraenkte Nutzbarkeit.

3. **Entfernungen im Kapitel Lage pruefen.** Die Gehzeiten und
   Fahrzeiten sind aus dem Expose der Wohnung Nr. 1 uebernommen und
   gerundet. Bitte einmal gegenlesen.

4. **Kostenrahmen Modernisierung.** Im Kapitel 07 steht bewusst kein
   Kostenrahmen, weil fuer dieses Haus kein Handwerkerangebot vorliegt.
   Sobald es da ist, laesst es sich in den rechten Kasten einsetzen, so
   wie es im Expose Tulpenstrasse 15 aufgebaut war.

5. **Fotos vom Treppenhaus und vom Keller.** Sie fehlen noch und liessen
   sich in die Galerie in Kapitel 02 ergaenzen.

## Zu den Bildern

Die sieben Innenaufnahmen zeigen die Wohnung Nr. 2 selbst, also den
heutigen bewohnten Bestandszustand. Sie stehen deshalb in Kapitel 02 und
nicht im Modernisierungskapitel. In einer Galerie liegen sie zusammen mit
der Aufnahme des Gemeinschaftsgartens, der unbearbeitet ist.

Die Strassenansicht ist nur das Titelbild und steht nicht in der Galerie.

Der Hinweis auf die KI-Aufbereitung steht kurz unter der Galerie und
ausfuehrlich in den rechtlichen Hinweisen unter "Einsatz von KI".

Der Grundriss ist ein Ausschnitt aus dem Aufteilungsplan, Seite
Erdgeschoss, Planstand 08.06.2026. Er zeigt nur die Wohnung Nr. 2 mit
allen Raumgroessen. Der vollstaendige Plan liegt in den Unterlagen.

## Hochladen

Ein eigenes Repository fuer diese Wohnung anlegen. Dann auf
"Add file", danach "Upload files", und in das Fenster alles drei
zusammen ziehen:

    index.html
    bilder            (der ganze Ordner)
    unterlagen        (der ganze Ordner)

Wichtig: nicht den Ordner "Roseggerstrasse-9-EG-rechts" hochladen,
sondern seinen Inhalt. Die index.html muss im Repository ganz oben
liegen.

## Pages einschalten

Settings, dann Pages. Bei Source "Deploy from a branch" waehlen,
Branch `main`, Ordner `/ (root)`. Speichern. Der erste Aufbau dauert
ein bis zwei Minuten.

## Groessen

Keine Datei ist groesser als rund 4,7 MB, der Weblader von GitHub nimmt
einzelne Dateien bis 25 MB. Die Scans wurden auf 150 dpi gerechnet, aus
45 MB wurden 19 MB. Die Seite selbst laedt beim Besucher mit rund
1,7 MB, davon 1,6 MB Bilder. Das Paket "Alle herunterladen" ist rund
19 MB gross, das dauert auf dem Telefon einen Moment.

## Nicht enthalten, mit Absicht

Nicht im Ordner "unterlagen" liegen Grundbuchauszug,
Restnutzungsdauergutachten, Herleitung der Kaufpreisaufteilung und die
Mietvertraege. Sie enthalten personenbezogene Daten. Auf GitHub Pages
ist jede Datei im Repository oeffentlich abrufbar, auch wenn sie auf der
Seite nicht verlinkt ist. Im Expose steht deshalb, dass diese Unterlagen
bei ernsthaftem Kaufinteresse nachgereicht werden.

Ebenfalls nicht enthalten sind das Expose und die
Modernisierungsaufstellung der Wohnung Nr. 1, das sind Verkaufsunterlagen
einer anderen Einheit.

Ein Hinweis zur Teilungserklaerung, die im Ordner liegt: Sie enthaelt in
Abteilung III die Grundschulden des Verkaeufers. Das war in Sindelfingen
genauso, deshalb liegt sie hier wieder im oeffentlichen Ordner. Falls das
nicht gewuenscht ist, die Datei `01_Teilungserklaerung.pdf` loeschen und
den ersten Eintrag in der Liste `DOKS` in der index.html entfernen.

## Falls ein Ordner anders heissen soll

In der index.html steht im Skript genau eine Zeile:

    var DOKBASE='unterlagen/';

Nur diese aendern. Der Schraegstrich am Ende muss bleiben.
Der Bildordner ist in den Bildpfaden hinterlegt und heisst "bilder".

## Hinweis zum Oeffnen von der Festplatte

Oeffnest du die index.html per Doppelklick, sperrt der Browser bei
manchen Einstellungen den Zugriff auf Nachbarordner. Die Seite
erscheint, die Downloads funktionieren dort aber nicht immer. Auf der
veroeffentlichten Seite laeuft alles.
