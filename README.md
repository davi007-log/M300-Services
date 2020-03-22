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
Am Schluss stehen sechs Maschinen. Es wird per Vagrantfile und Shell Scripts ein Webserver erstellt, welches ein CMS (WordPress) einrichtet. Die entsprechende Datenbank wird auf einem Datenbankserver erstellt. Die Seite wird über einen DNS-Namen (Test.ch, www.Test.ch) erreichbar sein, damit man sich nicht die IP-Adresse merken muss. Auch wird ein Zertifikat erstellt, welches von einer lokalen CA signiert wird und anschliessend wird das Zertifikat auf dem Webserver installiert werden. Der Client intern stellt sicher, dass über LAN die Webseite erreichbar ist und der Client extern stellt sicher, dass die Webseite auch von einem anderen Netzwerk aus erreichbar ist.

## Alle Maschinen erklärt

### Webserver
- Webseite kann abgerufen werden
- Apache installiert 
- Über HTTP erreichbar
- Zertifikat eingebunden (von CA signiert)
- Firewall eingerichtet
- Reverse Proxy eingerichtet

### CA Server
- Zertifikat erstellen
- Zertifikat durch eigene CA signieren
- Firewall eingerichtet

#### Ablauf
Als aller erstes wurde ein Github Account erstellt. Nachdem erscheint die Willkommens-Seite wo man auf ''Stat a project'' klicken kann.
Unter Repository name definiert man einen Namen, in diesem Fall wählte ich M300-Services.
Dann wählte ich Initialize this repository with a README damit man Information festlegen kann und eine Übersicht erhält.

Danach musste ich den Github Account an den SSH Key anerkennen und in der Bash einen SSH Key generieren.
nun kann man folgenden Pfad kopieren ($HOME/.ssh/id_rsa.pub) und mit dem Command ''Cat $HOME/.ssh/id_rsa.pub'' zeigt er den kompletten Inhalt vom SSH Key an. Dieser kopiert man und fügt ihn auf dem Github Account unter settings im Abschnitt SSH Keys und GPG keys ein.

Der Rest ging nach Anleitung doch viele Konfiguration und Commands konnte ich anch Anleitung nicht machen und somit kam ich zu den Problemen. EInige Ordner wie die für Benutzer und Gruppen benötigt waren, waren nicht erstellt worden wie es in der Anleitung stand.

## 3. Leistungsbeurteilung 01 (LB01)
Diese Beurteilung beinhaltet keine Dokumente, da es sich hier um eine Theorieprüfung handelt.




