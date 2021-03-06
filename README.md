## Was bitte?

Skatrunde ist ein kleines Hilfsprogramm zum Aufschreiben der Punkte am Skat Abend. Kopfrechnen, schriftliche Addition und ordentliche handschriftliche Notizen auf einem Zettel fallen insbesondere nach ein paar Bier nicht unbedingt leichter.

Deshalb schreiben wir ein Programm mit dem die Punkte einfach notiert werden können. Die Software sollte im Browser laufen, so dass man z.B. ein Tablet zur Erfassung auf den Tisch legen kann. Die Software muss einfach sein, so dass zu jeder noch so fortgeschrittenen Stunde des Abends die Punkte immer korrekt erfasst werden.

Wir starten mit einigen wenigen Funktionen, wird aber evtl. noch mal erweitert.

[Hier geht's zur App](https://tboeker.github.io/skatrunde-app)

## Begriffe

Hier ein paar Begriffe zur Klärung:

- Runde: eine Gruppe von Menschen, meist 3 oder 4 Personen, die sich zum Skat spielen treffen
- Spieler: Teilnehmer einer Runde, spielt Skat und trinkt 2 Bier dabei
- Spiel: in einer Runde werden viele Spiele gespielt. Jedes Spiel wird zur späteren Auswertung und Abrechnung erfasst
- Verlauf: Verlauf aller Spiele in einer Runde. Geht von Spiel 1 bis X
- Gesamtpunktzahl: Wir notieren die "verlorenen" Punkte. Pro Spieler werden alle Punkte kumuliert.

## Modus

Jeder Spieler erhält Punkte auf sein Punkte-Konto wenn ein Spiel verloren ist. Pro Spiel erhält also entweder ein Spieler Punkte (wenn er sein Solo Spiel verliert, oder der Verlierer im Ramsch). Oder die anderen Spieler erhalten Punkte (wenn er sein Solo spiel gewinnt oder Durchmarsch im Ramsch).

Pro Spiel Eingabe muss also der Spieler erfasst werden, ob er gewonnen oder verloren hat und wie viele Punkte aufgeschrieben werden sollen. Nach jedem Spiel wird die Gesamtpunktahl pro Spieler entsprechend verändert.

Wird die Runde beendet, muss ein Spieler die Differenzen zu allen "besseren" Spielern in die Kasse einzahlen.

## Funktionen Version 1

- Anlegen einer neuen Runde mit Anzahl der Spieler
- Eingabe neues Spiel mit den Werten: Spieler-Nummer, Gewonnen/Verloren, Punkte
- Anzeige des Verlaufs aller Spiele
- Anzeige der Gesamtpunktzahl pro Spieler

## Funktionen für die Zukunft

Im folgenden werden beispielhaft einige Funktionen aufgelistet, die zukünftig implementiert werden können.

- Erfassen der Spielernamen
- Löschen eines Spiels aus der Historie, z.B. wenn man sich mal vertippt hat
- Auswahl von Ergebnissen laut den Skat-Regeln
- Erfassen von Zusatzinfos zum Spiel (z.B. Bock, Ramsch)
- Anzeige des Gebers (Achtung: bei Grand Hand im Ramsch wird wiederholt)
- Berechnung der Punktdifferenzen zum nächsten Gewinner und Gesamt-Abrechnung

## Technik

- Die Anwendung wird in Angluar geschrieben
- Das Hosting erfolgt auf GitHub Pages, dafür wird das Repository skatrunde-app verwendet
- Die Logik wird mit Hilfe von ngrx implementiert.
- Die erfassten Daten im Browser Storage gespeichert sein, so diese auch nach neu laden noch da sind (ngrx-store-localstorage)
-

## DEV

### Deployment neue Version

Kopieren der Dateien aus dist in das app repo mit

```powershell
.\deploy.ps1
```

CLI Befehle

```powershell

ng generate store State --root --module app.module.ts

```