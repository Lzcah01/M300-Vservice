# M300-Vservice

## Modul 300 LB02

Luca Raschetti

Dies ist eine Dokumentation für die LB02 im Modul 300. In dieser Dokumentation soll ich meine Arbeitsschritte festhalten.




# K1 Einrichtung


In diesem Punkt soll die Struktur für die Weitere LB aufgebaut werden. Hierzu waren folgende Programme notwendig:

* VirtualBox
* Vagrant
* Visualstudio-Code
* Git-Client
* SSH-Key für Client erstellt

Für die meisten Elemente in dieser Liste bedarf es keiner Erklärung. Den SSH Key habe ich entsprechend der Aufgabe auf Github in den Einstellungen erstellt. Den Git-Client konnte ich auch dort herunterladen.

Mit der Lizenz welche wir von der TBZ zur Verfügung hatten, konnte ich VisualStudio Code installieren, da ich aber Probleme damit hatte, habe ich mich kurzfristig auf Atom umgestellt.

Vagrant konnte ich als Add-On zu Git-Hub herunterladen. Mit Vagrant lassen sich VMs einfach über die Git-Bash Konsole erstellen.

VirtualBox war gratis für die Installation auf ihrer Webseite.

Danach habe ich noch einen Linux Ubuntu Client aufgesetzt.
![Image of Ubuntu VM](./Desktop/ubuntu.png)

**Kannte ich schon:** Ich kannte schon die Programme Virtual Box und den Git-Client.

**War neu für mich:** Das Programm Vagrant und dessen Vorteile kannte ich noch nicht. Auch habe ich einen schnelleren Umgang mit Git-Bash gelernt. Auch habe ich noch nie einen SSH Key über git Bash aufgesetzt.


# K2 Lernumgebung

In diesem Punkt geht es um das registrieren und vorbereiten für die nächsten Aufgaben. Hierzu sollten folgende Punkte erledigt werden. Auf der Webseite von Github www.github.com kann man ganz simple ein neue Konto eröffnen.

* GitHub oder Gitlab-Account ist erstellt
* Git-Client wurde verwendet
* Dokumentation ist als Mark Down vorhanden
* Markdown-Editor ausgewählt und eingerichtet
* Mark down ist strukturiert
* Persönlicher Wissenstand im Bezug auf die wichtigsten Themen sind  dokumentiert
* Wichtige Lernschritte sind dokumentiert

Nun zu einigen von diesen Punkten braucht es wieder keine Erklärung. Die Dokumentation wurde als Mark Down angelegt.
Kommen wir zu einigen Begriffen welche geklärt werden sollten.
**Linux** ist ein Open Source Betriebssystem. Die Vorteile von Linux liegen darin, dass jeder den Code einsehen und benutzen kann. So können Sicherheitslücken besser geschlossen werden und es kann viel optimiert werden.
Die **Virtualisierung** soll die Wartung von Arbeitsplätzen oder Servern vereinfachen. Anstelle von Vielen Servern, werden nur weniger eingesetzt. Es wird also weniger Hardware gebraucht. Auf den Servern ist ein Programm für die Virtualisierung installiert. Nun lassen sich auf diesem Server mithilfe der Virtualisierung Virtuele Server, Clients und Netze installieren.
**Vagrant** ist eine Freie Software für das erstellen von Virtuellen Maschinen. Mit Vagrant lassen sich auch einige Arbeitsschritte automatisieren.
**Git** ist eine Freeware welche zur Pensionierung und Veröffentlichung/Verteilung von Programmen gebraucht wird.

**Auf gutem Wege:** Ehrlich gesagt war mir das alles mehr oder wenig fremd doch ich mache Fortschritt und bin

**War neu für mich:** Ich habe vor diesem Project noch nie mit Git-Hub gearbeitet. Ich muss sagen, dass ich gefallen daran gefunden habe. Ich habe einen Editor benutzt namens Atom um den Text vorzubereiten. Danach konnte ich einfach alles Kopieren und hier bei Github einsetzen.

# K3 Vagrant

Zu Vagrant habe ich schon im Abschnitt K2 geschrieben.
Dies sind die Punkte welche ich erfüllen sollte:

* Bestehende vm aus Vagrant-Cloud einrichten
* Kennt die Vagrant-Befehle
* Eingerichtete Umgebung ist dokumentiert (UmgebungsVariablen, Netzwerkplan gezeichnet, Sicherheitsaspekte)
* Funktionsweise getestet inkl. Dokumentation der Testfälle
* vorgefertigte vm auf eigenem Notebook aufgesetzt
* Projekt mit Git und Mark Down dokumentiert


# Befehle

## Vagrant
    Vagrant up: startet VM's aus Vagrantfile

    Vagrant halt: stopt VM's

    Vagrant destroy: zerstört VM's

    Vagrant ssh [vmname]: Verbindet per ssh auf VM

## Versionsverwaltung / GIT

    git add -A : Änderungen im aktuellen Verzeichnis zum Zwischenspeicher hinzufügen

    git commit : Änderungen auf dem lokalen Git speichern

    git push : Lokales Git auf Github synchronisieren

    git clone : Github Repo herunterladen

    git init : Repo initialisieren
