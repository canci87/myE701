# ![](https://www.lpice.eu/fileadmin/_processed_/csm_LPIC-DevOpsToolsEngineer_43de3c4735.jpg) myE701 - Exam 701: DevOps Tools Engineer 


## Fahrplan
***


| Datum | behandelte Unterrichtsinhalte: | Gewichtung |
| -------- | ------ | -------- |
| 15.05.19 | Installation SW, Einrichten Linux VM(s)<br>[701.1 Modern Software Development, 1. Teil](https://github.com/w901-fr19-mi/E701#7011-modern-software-development) | 6 |
| 22.05.19 | [701.1 Modern Software Development, 2. Teil](https://github.com/w901-fr19-mi/E701#7011-modern-software-development) | 4 |
| 29.05.19 | [701.3 Source Code Management](https://github.com/w901-fr19-mi/E701#7013-source-code-management) | 5 | 
| 05.06.19 | 702.1 Container Usage, 1. Teil | 7 |
| 12.06.19 | 702.1 Container Usage, 2. Teil | (7) |
| 19.06.19 | 702.2 Container Deployment and Orchestration | 5 |
| 26.06.19 | LB1 Theoretische Prüfung und Abschluss LB2 | - |
| 03.07.19 | Sommersporttage | - |
|          | Total Punkte | 27 (34) !

Kapitel aus E701 wurden alleine erarbeitet. Davon sind mindestens 14 Punkte selbständig erarbeitet worden. 

## Dokumention des Lern- und Entwicklungsprozesses
***

### Kapitel: 701.1 Modern Software Development (Status: Abgeschlossen)

**Weight**: 6 + 4

**Beschreibung** Einführung ins Thema "Mircoservices" mit einem zusätzlich selbst erstelltem Microservice.

**Tagesziele**, Infos über das Thema sammeln und gelerntes festhalten. Beginnen einen eigenen Microservice zu erstellen. 

**Vorgehen**,Dokus lesen und Youtube Videos schauen. Microservice mit Vagrant erstellen.

**Beispiele und Arbeitsergebnisse**

Microservices werden immer bekannter und auch immer wichtiger. Schon heute werden auf vielen Websiten, welche wir tagtäglich benutzen, Microservices. Bei Amazon zum Beispiel ist der Bestellvorgang, der Zahlungsvorgang, die Vorschläge, usw... alles ein einzelner Microservice.
Eine eindeutige Definition für Microservices gibt es nicht, es gibt nur diverse Merkmale, welche einen Microservice ausmacht. Diese wären zum Beispiel:
* Applikation mit einer Reihe von kleinen Diensten
* Jeder Dienst arbeitet als unabhängiger Prozess
* Kommunikation findet über offene, standardisierte Ports staht (HTTP/Messages)
* Jeder Service wird einzeln deployed, skaliert und überwacht
* Dienste umfassen fachliche Anforderung
* Dienste sind unabhängig, austauschbar und eineln upgradefähig

Microservices sind vorallem auch durch ihre Vorteile in einem so grossem Hype. Mit Mircoservices  ist es einfacher einen einzelnen Dienst zu verstehen und auch einfacher diese einzelne Dienste zu testen, zu deployen, zu managen und zu skalieren. Durch die unabhängigkeit kann man Dienste einfacher ändern und es ist auch einfacher, neue Mitarbeiter in ihrem Bereich einzuschulen, da sie nicht von allen Diensten etwas verstehen müssen, sondern eigentlich nur von dem Dienst für welchen sie Verantwortlich sind.

Der Code sieht folgendermassen aus:
  <br>`docker run -dit --name apache -p 8080:80 -v c:\temp\apache\:/usr/local/apache2/htdocs/ httpd:2.4`


Als Microservice habe ich einen Apache Webserver ausgewählt. Um einfacher das HTML bearbeiten zu können, habe ich noch ein geshartes Volume erstellt. So kann ich die HTML Files lokal erstellen und auch lokal speichern.
Getestet habe ich die funktionalität in dem ich mich über "localhost:8080" auf den Webserver verbunden habe und mein selbst erstelltes HTML File zu sehen war.


**Fazit und Aussicht**, Was ein Micrsoservice ist habe ich bereits im M300 angeschaut. Jedoch konnte ich noch mehr darüber lernen und habe dies, anders als im M300, nun auch Dokumentiert. 


### Kapitel: 701.3 Source Code Management (Status: Abgeschlossen)

**Weight**: 5

**Beschreibung** Einführung ins Thema Source Code Management mit beispielen von bekannten Managern

**Tagesziele**, Dokumentation über Thema schreiben 

**Vorgehen**,Abschnit 701.3 von der Doku lesen, Youtube Videos schauen, allgemeine Internet Recherche zum Thema

**Beispiele und Arbeitsergebnisse**

Ein Source Code Management (SCM) ist ein Software tool welches von Softwareentwicklern benutzt wird, um Versionen eines Codes zu speichern. SCMs werden gebraucht, um Versionen einem Programm zu geben. Jede Version wird mit einem Zeitstempel versehen und es wird hinterlegt, welche Person verantwortlich für die Änderungen war.

Mit SCM kann man einfacher im Team arbeiten und seinen Code auch so isolieren, dass die Änderungen für andere Teammitglieder erst sichtbar sind, wenn der Code bereit ist.

Auch das troubleshooten wird einfacher, da man weiss wer die Änderungen gemacht hat und vorallem was die Änderungen waren.

Der bekannteste SCM momentan ist GitHub.


### Kapitel: 702.1 Container Usage (Status: In Arbeit)

**Weight**: 5

**Beschreibung** Erklärung zum Thema Containern und wie diese erstellt werden. 

**Tagesziele**, Dokumentation über Thema schreiben 

**Vorgehen**,Internet Recherche und unterlagen von Modul 300 benutzen

**Container Architektur**
Container teilen sich einen Betribessystem Kern mit anderen Containern, und muss daher nicht immer zusätzlich ein OS haben. Jede Anwendung (Container) erählt einen gewissen User space und hat somit eine isloierte Umgebung. 
Durch das teilen eines OS brauchen Container im Vergleich zu VM's viel weniger Rechenleistung, Hauptspeicher und Speicherplatz. Wo man bei VM's von Gigabytes redet, redet man bei Containern lediglich von Megabytes. Dies führt dazu, dass auf einen Server viel mehr Container als VM's Platz haben. Ein weitere Pluspunkt ist die Geschwindigkeit in welcher ein Container einsatzbereit ist, VM's benötigen teilweise mehrere Minuten und Containern maximal ein paar Sekunden.

![alt text](https://github.com/canci87/myE701/blob/master/content-grafiken-vm-container.jpg "VM vs Container")

**Repository Pushen**
Mit folgenden Befehl kann ein Image oder ein Repository zu einer Reistry gepusht werden.
<br>`docker push [OPTIONS] NAME[:TAG]`

**Docker Befehle**
|  Befehl, docker... | Funktion | 
|---|---|
| -version  |Zeigt aktuelle installierte Docker Version an   |
| pull  | Zieht images aus einem bestimmten Docker Repository  |
| run   | Erstellt Container von einem Image  |
| ps | Zeigt alle laufenden Container an |
| ps -a | Zeigt alle Container an |
| exec | Greift auf laufenden Container zu |
| stop | Stoppt einen bestimmten Container |
| kill | Stoppt den Container sofort, die weniger schönere Variante wie "stop" |
| commit | Erstellt neues Image eines editierten Containers |
| push | Pusht ein Image/Repository zu einem docker hub repository |
| login | Zum einloggen auf einem docker hub repository |
| images | Zeigt alle lokal gespeicherten Images an |
| rm | löscht einen gestoppten Container |
| rmi | löscht ein Image vom lokalen Speicher |
| build | Erstellt ein Image von einem bestimmten Docker file |

**Beispiele und Arbeitsergebnisse**
## Links

* [Exam 701: DevOps Tools Engineer](https://www.lpi.org/our-certifications/exam-701-objectives) 
* [E701 Dokumentation](https://github.com/w901-fr19-mi/E701)
* [myE701 Original Repository](https://github.com/w901-fr19-mi/myE701) 

