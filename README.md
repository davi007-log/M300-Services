# M300
## 1. Beschreibung
Modulnummer:    300
Modulname:      Plattformübergreifende Dienste in ein Netzwerk integrieren

Das Modul 300 dreht sich rund um Plattformübergreifende Dienste in einem Netzwerk. Genauere Modulinformationen können auf der Internetseite der ICT-Berufsbildung gelesen werden. Link: https://cf.ict-berufsbildung.ch/modules.php?name=Mbk&a=20101&cmodnr=300&noheader=1

## Einleitung 10-Toolumgebung
Als erstes bruacht man Folgende Voraussetzungen um diesen Auftrag durchführen zu können:
#### Voraussetzungen
PC/Notebook mit min. 8 GB freiem RAM, ca. 20 GB freiem HD-Speicher und einer Ethernet-Netzwerkkarte.
Einfache Linux und Apache Web Server Kenntnisse sind von Vorteil.
Ein schneller Netzwerk- (Kabel!) und Internet-Anschluss
#### Allgemeine Hinweise

Die meisten Arbeiten erfolgen auf der Kommandozeile, hier als **Terminal** (*Bash*) bezeichnet.

In der Kommandozeile bzw. im Terminal läuft die "Bash" Shell. Das ist nur die Shell von Linux und noch kein vollständiges Linux System. 

Diese Umgebung wird verwendet, weil benötige Programme wie `git`, `ssh-keygen` in der Powershell nicht zur Verfügung stehen. 

Um sich im Filesystem zurechtzufinden, sind folgende Befehle nützlich:
* `cd /Verzeichnis` wechselt in Verzeichnis z.B. `cd /Users`, alternativ kann die Windows Schreibweise in " verwendet werden, z.B. `cd "C:\Users"`
* Alternativ kann im Windows Explorer jederzeit ein Terminal mittels rechter Maustaste und `Git Bash Here` geöffnet werden.
* `cd ~` Wechsel ins eigene Home-Verzeichnis. Dort werden SSH-Keys etc. abgelegt.
* `cd -` wird auf das zuletzt verwendete Verzeichnis gewechselt.
* Die Laufwerke von Windows stehen als `/c`, `/d/` zur Verfügung, Bsp. `cd /c/Users` und `cd "C:\Users"` sind indentisch
* `ls -l` zeigt die Dateien im aktuellen Verzeichnis an
* `pwd` zeigt den aktuellen Pfad an.
* Die Windows Befehle stehen auch im Terminal zur Verfügung, z.B. `notepad README.md`

## Leistungsbeurteilung 02 (LB02)
## Ziel der LB
- Am Schluss funktionieren alle Maschinen. 
- Es wird per Vagrantfile und Shell Scripts ein Webserver erstellt.
- Alle Codes sind im Vagrantfile ersichtlich
- Neues über die Virtualisierung gelernt


### Webserver
- Webseite kann abgerufen werden
- Apache installiert 
- Über HTTP erreichbar
- Firewall eingerichtet
- Reverse Proxy eingerichtet



#### Ablauf
Als aller erstes wurde ein Github Account erstellt. Nachdem erscheint die Willkommens-Seite wo man auf ''Stat a project'' klicken kann.
Unter Repository name definiert man einen Namen, in diesem Fall wählte ich M300-Services.
Dann wählte ich Initialize this repository with a README damit man Information festlegen kann und eine Übersicht erhält.

Danach musste ich den Github Account an den SSH Key anerkennen und in der Bash einen SSH Key generieren.
nun kann man folgenden Pfad kopieren ($HOME/.ssh/id_rsa.pub) und mit dem Command ''Cat $HOME/.ssh/id_rsa.pub'' zeigt er den kompletten Inhalt vom SSH Key an. Dieser kopiert man und fügt ihn auf dem Github Account unter settings im Abschnitt SSH Keys und GPG keys ein.

Der Rest ging nach Anleitung doch viele Konfiguration und Commands konnte ich anch Anleitung nicht machen und somit kam ich zu den Problemen. EInige Ordner wie die für Benutzer und Gruppen benötigt waren, waren nicht erstellt worden wie es in der Anleitung stand.
Neben der Anleitung die auf GitHub zu finden war, erstellte ich ein weiteres Word-Dokument mit einer selbstgemachte Dokumentation, die einige Schritte von der Kofiguration zeigen.

## 3. Leistungsbeurteilung 01 (LB01)
Diese Beurteilung beinhaltet keine Dokumente, da es sich hier um eine Theorieprüfung handelt.

## 4. Leistungsbeurteilung 03 (LB03)

### Docker

Docker nahm die bestehende Linux-Containertechnologie auf und verpackte und erweiterte sie in vielerlei Hinsicht – vor allem durch portable Images und eine benutzerfreundliche Schnittstelle –, um eine vollständige Lösung für das Erstellen und Verteilen von Containern zu schaffen.

Die Docker-Plattform besteht vereinfacht gesagt aus zwei getrennten Komponenten: der Docker Engine, die für das Erstellen und Ausführen von Containern verantwortlich ist, sowie dem Docker Hub, einem Cloud Service, um Container-Images zu verteilen.

Wichtig: Docker wurde für 64-bit Linux Systeme entwickelt, kann jedoch auch mittels VirtualBox auf Mac und Windows betrieben werden.

Architektur
Nachfolgend sind die wichtigsten Komponenten von Docker aufgelistet:

Docker Deamon

Erstellen, Ausführen und Überwachen der Container
Bauen und Speichern von Images
Der Docker Daemon wird normalerweise durch das Host-Betriebssystem gestartet.

Docker Client

Docker wird über die Kommandozeile (CLI) mittels des Docker Clients bedient
Kommuniziert per HTTP REST mit dem Docker Daemon
Da die gesamte Kommunikation über HTTP abläuft, ist es einfach, sich mit entfernten Docker Daemons zu verbinden und Bindings an Programmiersprachen zu entwickeln.

Images

Images sind gebuildete Umgebungen welche als Container gestartet werden können
Images sind nicht veränderbar, sondern können nur neu gebuildet werden.
Images bestehen aus Namen und Version (TAG), z.B. ubuntu:16.04.
Wird keine Version angegeben wird automatisch :latest angefügt.
Container

Container sind die ausgeführten Images
Ein Image kann beliebig oft als Container ausgeführt werden
Container bzw. deren Inhalte können verändert werden, dazu werden sogenannte Union File Systems verwendet, welche nur die Änderungen zum original Image speichern.
Docker Registry

In Docker Registries werden Images abgelegt und verteilt


