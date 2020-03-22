# Lerndokumentation

## Linux
Da ich mich mit Linux nicht so gut auskenne, war es nicht gerade das einfachste die VMs zu erstellen und konfigurieren. Ich musste immer wieder und weider verschiedene Konfigurationen anpassen. Den Apache Webserver hatte ich schon in sehr vielen Modulen eingrichten müssen und deswegen fiel es mir nicht schwer ihn zu erstellen und Anpassungen im Vagrantfile zu tätigen.Hin und wieder tauchten immer Probleme auf mit der VM, dies fiel mir nicht gerade leicht und musste manchmal wieder von vorne anfangen, weil immer was nicht funktionierte. Hätte am liebsten alles mit Windows gemacht und nicht auf Linux, Habe fast gar keine Kenntnisse in diesem Bereich und somit fiel mir das schwer..

## Virtualisierung
Virtualisierung habe ich in der Schule nicht so oft gehabt, dafür habe ich jetzt im ÜK gerade das Theam Virtualisierung schlage mich soweit gut durch. Ich hoffe somi, dass ich noch weitere Informationen mitnehmen kann für meine Ausbildung zum Thema Virtualisierung.

## Vagrant
Am Anfang hatte ich Vagrant gar nicht verstanden, jedoch habe ich mit der Zeit es immer besser verstanden. Zuerst hatte ich die Konfigs in einem  Vagrant File gemacht, jedoch habe ich gemerkt, dass erstens die Datei ziemlich lang sein würde, zweitens es mit der Zeit sehr unübersichtlich wird. Das was ich nicht gut finde, das die einzelnen Schritte für die LB2 in der Anleitung nicht richtig und vollständig im GitHub stehen. Es ist daher eine sehr grosse Herausforderung für mich gewesen. Bin hinter jedem Problem gestanden und alles probiert um es zu lösen.

## Versionsverwaltung mit Git
Git ist recht interessant von der Versionverwaltung her. Github merkt sich jede Änderung, die gepusht wurde (Commits) und man kann im nachhinein immer darauf zugreifen. Falls ich merke, dass ein Commit von vor einer Woche einen Fehler ausgelöst hat, kann ich einfach schauen was vor einer Woche alles geändert wurde beim Commit. Es ist auch sehr praktisch, dass ich nicht selber immer die Files hochladen muss per Hand, sondern einfach mit dem Befehl "git push". A

## Mark Down
Mark Down wird beispielsweise zum Dokumentieren verwendet. Dieser Text hier ist mit Mark Down geschrieben und formatiert worden. Mark Down funktioniert ähnlich wie HTML/CSS. Man hat Header (h1 HTML, # Mark Down). SOmit für mich keine grosse Schwierigkeit gewesen um meine Lernschritte zu dokumentieren und zu strukturieren.

## Systemsicherheit
Heutzutage ist Sicherheit ein sehr wichtiges Thema und es wird immer wichtiger und wichtiger. Angreifer werden immer schlauer und wenden immer bessere Angriffe an. Deswegen ist es für den Systemadministrator wichtig sein System zu schützen, damit dies nicht in fremde Hände gelangen kann. Aus diesem Grund habe ich bei auf der Maschine eine UFW Firewall (Uncomplicated FireWall) konfiguriert.

### Erstellte Firewallregeln

#### Web
- Allow from 10.0.2.2 to any port 22 (SSH vom Host aus)
- Allow 443/tcp (HTTPS auf die Webseite)


#### Client
- Allow from 192.168.1.25 to any port 22 (SSH vom Host aus)

