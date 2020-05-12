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
![](https://sitecore.namics.com/files/2018/04/docker_logo.png)
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

### Docker download
Als Erstes geht es darum Docker zu installieren. Ich arbeite auf einer Ubuntu VM.

Hierzu habe ich die Anleitung von Docker [Docker Anleitung Download](https://phoenixnap.com/kb/how-to-install-docker-on-ubuntu-18-04)

Nach der Installation kann man die Funktionsfähigkeit von Docker mit dem folgenden Command testen:

> run 'Hello-world'

![](/Images/docker/holamundo.JPG)

Falls dieses Bild erscheint kann man mit den Container & Images fortfahren.

### Docker Container & Images
Ein Container beinhaltet Services, ohne dass man diese installieren. Das Konzept dahinter basiert auf Dockerfiles. Mit diesen kann man Images erstellen.

Images kann man auch von Dockerhub herunterladen. Jedoch muss man sich dort einlogen.

Ich werde im folgenden mit den Apache und mysql Images arbeiten.

Apache werde ich als Backend installieren und mysql als frontend.

![](/Images/docker/docker-container.JPG)

Mit folgenden Command lässt sich der Apache Container installieren: 

> docker container run -d -p 8081:80 --name MyApache httpd


> docker container run -it -p 8082:80 mysql 

Nun sind die Container installiert und laufen. Für den Test kann man im Browser: http://localhost:port eingeben. Wenn die Webserver ersichtlich sind dann hat es geklappt.

Beim erstellen eines Containers, für welches ein neues Image gebraucht wird, beziehungsweise ein Image benötigt wird, welches nicht lokal vorhanden ist, wird ein Pull Request von docker hub ausgeführt, damit es lokal downgeloaded ist.

![](/Images/docker/pull-image.JPG)

Hier sind noch weitere Docker commands:

Alle laufende Container anzeigen:
> docker ps

Alle Container anzeigen
> docker container ls -a

Alle Images anzeigen
> docker images

Image herunterladen
> pull (Imagename)

Image erstellen
> docker image build -t

Container stoppen
> docker container stop [ID]

den Container "betreten"
> docker container exec -it "containername" bash

## Image erstellen 
Man kann auch Images erstellen. Für das habe ich ein bestehendes Image genommen (nginx) und habe darauf meine Webseite gemacht. Das Image habe ich im Anschluss auf Dockerhub gepushed.

Als erstes erstellt man den Container mit dem Image und mapped den Ordner im Image drin, welchen man bearbeiten will in einen Ordner auf dem Hostsystem:
> docker container run -d -p 8080:80 nginx -v $(pwd):/usr/share/nginx/html --name nginx-website-m300 nginx

Ich habe mir einen Test Ordner erstellt, welchen ich gemappt habe. Im Command ist das "$(pwd)" zu finden, und das ist dafür da, dass dieser Ordner in dem man sich gerade befindet, gemeint ist. 

Im Testordner habe ich nun ein index.html file erstellt, welches das Original überschreibt. Diese Änderungen geschehen allem im Container.

![](/Images/docker/docker-testdir.JPG)

Hier kann man nun ein Image erstellen. Dies ist mit dem Docker File zu machen. Hierzu habe ich in der SELBEN Direcotory ein Dockerfile erstellt.

![](/Images/docker/docker-file.JPG)

Im Dockerfile habe ich definiert, mit welchem Image ich arbeite, wo meine Workdirectory ist und, dass das Image alle Inhalte von der Workdirectory in mein Image kopieren soll.

Als nächstes geht es darum, das Image zu "bauen". Dies macht man mit folgendem Command:
> docker image build -t davidem300/homepage-nginx . 

Docker image build -t würde das Image lokal abspeichern. Da ich es jedoch nachher noch auf mein Dockerhub pushen möchte habe ich noch mein Username von Dockerhub und den namen der Webseite festgelegt. Der Punkt am Schluss bezieht sich auf das Dokerfile in der Directory.

Nun ist das Image lokal verfügbar, und man kann bereits mit dem einen Container erstellen. Jedoch möchte ich, dass ich das von jedem Computer aus machen kann. Also pushe ich das noch von meinem Dockerhub Account.

Der Command dazu wäre:
> Docker push davidem300/nginx-website-m300

![](/Images/docker/push-docker-image.JPG)

Wichtig: Man muss sich natürlich zuerst noch authentifizieren. Hierzu einfach folgenden Command eingeben:
> Docker login

Danach kann man sich auf Dockerhub mit Username und Passwort einloggen.

![](/Images/docker/dockerhub.JPG)

## Testprotokoll
| Testfall                      | Check          |
| --------                      | -------------- |
| Container wird angezeigt      | positiv        |
| Webseite erreichbar           | positiv        |
| Applikation erreichbar        | positiv        |
| Ports sind nicht besetzt      | positiv        |
| Image funktioniert            | positiv        |
| Image Dockerhub erreichbar    | positiv        |


Als nächstes werde ich meine Container mit Sicherheitselementen beschmücken.

## Docker Projekt Sicherheit
Im letzten Projekt habe ich meine Container erstellt und verwaltet. Nun geht es darum diese Container abzusichern. Es ist wichtig, dass Logging und Mitteilungen aktiviert sind. Das System muss dem Administrator behilflich sein. Im Ernstfall müssen Warnungen gesendet werden.

### Meldungen an den Admin
Eine gute Monitoring-Lösung sollte auf einen Blick den Zustand des Systems zeigen und rechtzeitig warnen, wenn Ressourcen knapp werden.
Docker Tools cAdvisor von Google ist das am häufigsten eingesetzte Monitoring-Tool für Docker.

Dieses Programm ist als Container verfügbar und man kann darauf zugreifen. Der folgende Command muss dazu aktiviert werden:
>docker run -d --name cadvisor -v /:/rootfs:ro -v /var/run:/var/run:rw -v /sys:/sys:ro -v /var/lib/docker/:/var/lib/docker:ro -p 8080:8080 google/cadvisor:latest

### Weitere Sicherheitsaspekte
Ich habe folgende weitere Sicherheitsaspekte für meine Container realisiert:

#### Speicher
Wenn man den Speicher schützt, kann man die Chancen von DDos Attacken minimieren. Dies ist wichtig, da der Speicher nicht "aufgefressen" werden darf. Hier wäre der Command dazu:

> docker run -m 128m --memory-swap 128m amouat/stress stress --vm 1 --vm-bytes 127m -t 5s

![](/Images/docker/RAM-protection.JPG)

#### Neustarts begrenzen
Ein Neustart verhindert Zeitverluste und Ressorcenverluste von einem sterbenden Container. Auch hier kann eine DDos Attacke verhindert werden. Der Command dazu wäre:

> docker run -d --restart=on-failure:10 my-flaky-image

![](/Images/docker/Restart-protection.JPG)

#### Ressourcenbeschränken
Der Kernel definiert Ressourcenbeschränkungen, die für Prozesse gesetzt werden können. Diese lassen sich auch auf Docker-Container anwenden. Hierzu wäre der Command:

> docker run --ulimit cpu=12:14 amouat/stress stress --cpu 1

![](/Images/docker/Ressource-protection.JPG)

#### Capabilities einschränken 
Der Linux-Kernel definiert eine Reihe von Berechtigungen, welche Prozessen zugewiesen werden können, um ihnen einen erweiterten Zugriff auf das System zu gestatten.

Die Capabilities decken einen grossen Funktionsbereich ab, vom Ändern der Systemzeit bis hin zum Öffnen von Netzwerk-Sockets. Der Command dazu ist:

> docker run --cap-drop all --cap-add CHOWN ubuntu chown 100 /tmp
 
![](/Images/docker/Capabilities-protection.JPG)

## Docker Projekt Node & Mongo DB
Für mein letztes Projekt habe ich zwei Dockercontainer miteinander verbunden. Eine App erstellt eine Einkaufsliste. Die Elemente werden in einer Datenbank abgespeichert. Hierzu habe ich Node und Mongo DB verwendet.

## Wissenszuwachs
In den letzten Jahren habe ich stets mit VMs gearbeitet. Container waren mir nicht bekannt. Ich habe die Services immer installieren müssen und konfigurieren müssen. Mit Docker erspart man sich da viel Arbeit. 

Ich habe mit intensiv mit Docker befasst und viele nützliche Dinge kennengelernt, welche mir auf meinem weiteren Weg nützlich sein werden.

## Reflexion
In dieser zweiten Arbeit von diesem Modul habe ich einen guten Einblick in die Welt der Container erhalten. Ich weiss jetzt wie man mit Docker sehr schnell Services zum laufen bringt und diese auch verwalten kann. Ich habe sehr viel Freude an diesem Bereich erhalten und kann mir vorstellen in Zukunft damit zu arbeiten.
