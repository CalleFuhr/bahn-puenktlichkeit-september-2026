# ICE- und IC-Pünktlichkeit: Köln & Düsseldorf – September 2026

Dieser Datensatz enthält von uns erhobene Pünktlichkeitsdaten von ICE- und IC-Zügen am Köln Hauptbahnhof und Düsseldorf Hauptbahnhof im September 2026.

## Datensatz

Enthalten sind 10.445 beobachtete Fahrten:

- Köln Hbf: 6.080
- Düsseldorf Hbf: 4.365
- ICE: 9.093
- IC: 1.352

Zeitraum: 01.09.2026 bis 30.09.2026.

Die Datei `ice_ic_september_2026.csv` enthält eine Zeile pro Fahrt und Bahnhof.

## Spalten

- `bahnhof`: Köln Hbf oder Düsseldorf Hbf
- `trip_id`: Kennung der Fahrt aus den Quelldaten
- `zug`: Zugnummer, z. B. ICE 558
- `geplante_zeit`: planmäßige Zeit am jeweiligen Bahnhof im Format YYMMDDHHMM
- `verspaetung_minuten`: zuletzt erfasste Verspätung in Minuten
- `ausgefallen`: 1 = als ausgefallen erfasster Halt, 0 = nicht ausgefallen

## Wie wurden die Daten erhoben?

Die Daten wurden über die DB Timetables API der Deutschen Bahn erhoben. Die beiden Bahnhöfe wurden ungefähr alle fünf Minuten abgefragt.

Da dieselbe Fahrt dadurch mehrfach in den Rohdaten vorkommt, wurden die Daten für diese Veröffentlichung bereinigt. Pro Bahnhof und Fahrt wird nur eine Fahrt gezählt. Von mehrfach vorhandenen Statusmeldungen wurde der jeweils zuletzt beobachtete Stand verwendet.

Ankunft und Abfahrt derselben Fahrt am selben Bahnhof werden nicht als zwei verschiedene Fahrten gezählt.

## Was bedeutet „pünktlich“?

Für unsere Auswertungen gilt:

- bis einschließlich 5 Minuten Verspätung = pünktlich
- mehr als 5 Minuten Verspätung = verspätet
- als ausgefallen gemeldete Halte werden separat ausgewiesen

Wichtig: `ausgefallen = 1` bedeutet, dass der Halt am jeweiligen Bahnhof als ausgefallen erfasst wurde. Daraus folgt nicht zwingend, dass der gesamte Zuglauf ausgefallen ist.

## Selbst mit den Daten arbeiten

Die CSV-Datei kann beispielsweise mit Excel, LibreOffice, Python, R oder anderen Datenanalyseprogrammen geöffnet werden.

Auch ohne Programmierkenntnisse lassen sich damit Fragen untersuchen wie:

- Wie pünktlich waren ICE und IC in Köln?
- Wie unterscheiden sich Köln und Düsseldorf?
- Welche Zugnummern waren besonders häufig verspätet?
- An welchen Wochentagen war die Pünktlichkeit besonders niedrig?
- Wie unterscheidet sich die Pünktlichkeit morgens und abends?

## Quelle und Lizenz

Datenquelle: Deutsche Bahn, DB Timetables API.

Die zugrunde liegenden Daten der DB Timetables API werden von der Deutschen Bahn unter der Lizenz **Creative Commons Attribution 4.0 International (CC BY 4.0)** bereitgestellt.

Lizenz: https://creativecommons.org/licenses/by/4.0/

Informationen zur DB Timetables API:
https://developers.deutschebahn.com/db-api-marketplace/apis/product/timetables

Die hier veröffentlichten Daten wurden aus den über die API erhobenen Daten gefiltert, dedupliziert und aufbereitet. Es handelt sich nicht um eine Veröffentlichung der Deutschen Bahn.

Die Deutsche Bahn übernimmt für die über die API bereitgestellten Daten keine Gewähr für Richtigkeit und Vollständigkeit.
