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

![Ubuntu VM](assets/README-a3d0722d.PNG)

### Lernjournal

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

### Lernjournal

**Kannte ich schon:** Ich kannte Github ein wenig aber nicht besonders gut um alles auswenig zu erstellen.

**War neu für mich:** Ich habe vor diesem Project noch nie mit Git-Hub gearbeitet. Ich muss sagen, dass ich gefallen daran gefunden habe. Ich habe einen Editor benutzt namens Atom um den Text vorzubereiten. Danach konnte ich einfach alles Kopieren und hier bei Atom einsetzen.

# K3 Vagrant

Zu Vagrant habe ich schon im Abschnitt K2 geschrieben.
Dies sind die Punkte welche ich erfüllen sollte:

* Bestehende vm aus Vagrant-Cloud einrichten
* Kennt die Vagrant-Befehle
* Eingerichtete Umgebung ist dokumentiert (UmgebungsVariablen, Netzwerkplan gezeichnet, Sicherheitsaspekte)
* Funktionsweise getestet inkl. Dokumentation der Testfälle
* vorgefertigte vm auf eigenem Notebook aufgesetzt
* Projekt mit Git und Mark Down dokumentiert

Boxen sind bei Vagrant vorkonfigurierte VMs (Vorlagen). Diese sollen den Prozess der Softwareverteilung und der Entwicklung beschleunigen. Boxen können explizit durch den Befehl vagrant box add [box-name] oder vagrant box add [box-url] heruntergeladen und durch vagrant box remove [box-name] entfernt werden.
Die Konfiguration findet hier im Vagrant File Statt. In das Vagrant File sollen folgende Zeilen hineingeschrieben werden:
Vagrant File einrichten: Um die Maschine auf trap zu bringen, muss das Vagrantfile angepasst werden und zwar mit dieser Konfiguration.

    Vagrant.configure(2) do |config|
      config.vm.box = "ubuntu/xenial64"
      config.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
      config.vm.synced_folder ".", "/var/www/html"  
      config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"  
        end

        config.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update
        sudo apt-get -y install apache2
        SHELL
      end

## Netzwerkplan

![Netzwerkplan](assets/README-2ebf1c77.png)

## Testing

### Verfügbarkeit Testen

Als erstes testen wir ob die Webseite überhaupt aufrufbar ist. Dafür geben wir folgendes im Webbrowser ein: "127.0.0.1:8080". Da wir noch nichts am Index.html geändert haben, sollte nun die Apache-Standardseite angezeigt werden.


### Testergebnis: Gut

![Webseite Apache](assets/README-fea767e7.png)

### Index Testen

Zudem möchte ich noch testen ob das Template welches ich bei w3schools genommen habe sich integrieren lässt und es übernimmt.

Testergebnis: Gut

![Webseite CSS](assets/README-0fab4e60.PNG)



## Befehle Vagrant Cheat Sheet

    Vagrant box add [box add]: downloaded Vagrant image local store

    Vagrant box remove [box add]: entfernt Vagrant image local store

    Vagrant box list: Zeigd downloaded boxes an

    vagrant init [box]: initialisiert Vagrantfile

    Vagrant up: startet VM's aus Vagrantfile

    Vagrant status: Zeigt Status der Vagrant box

    Vagrant halt: stopt VM's

    Vagrant destroy: zerstört VM's

    Vagrant ssh [vmname]: Verbindet per ssh auf VM

    vagrant version: zeig Version von Vagrant

    vagrant port: Zeigt portmapping zwischen host und gast

## Versionsverwaltung / GIT

    git add -A : Änderungen im aktuellen Verzeichnis zum Zwischenspeicher hinzufügen

    git commit : Änderungen auf dem lokalen Git speichern

    git push : Lokales Git auf Github synchronisieren

    git clone : Github Repo herunterladen

    git init : Repo initialisieren

### Lernjournal

**Kannte ich nicht:** Ich kannte mich gar nicht mit Vagrant aus und wusste zuerst auch nicht wie damit umzugehen, zum Glück gab es ein Cheat Sheet auf dem BSCW.

**War neu für mich** Ich kann nun Virtuelle Maschienen mit Vagrant erstellen. Ich kann auch anschliessend auf diese drauf Verbinden und sie konfigurieren. Während meiner Arbeitszeit konnte ich die Befehle von Vagrant zu genüge einsetzen, sodass ich sie jetzt gut kenne.

# K4

Hier sind wieder die Verlangten Punkte aufgelistet:

* Firewall eingerichtet inkl. Rules
* Reverse-Proxy eingerichtet
* Benutzer- und Rechtevergabe ist eingerichtet (optional)
* Zugang mit SSH-Tunnel abgesichert
* Sicherheitsmassnahmen sind dokumentiert
* Projekt mit Git und Mark Down dokumentiert

FireWall Zuerst habe ich das Programm UFW welches wir für
diese Aufgabe verwenden sollten installiert. sudo apt-get install ufw

Mit sudo ufw status lässt sich der Status überprüfen. Mit sudo ufw enable lässt sich die FireWall einschalten und mit sudo ufw disable lässt sie sich deaktivieren.

Danach gilt es die nötigen Ports in der FireWall zu öffnen. Ich habe Port 22 für meinen Laptop freigegeben um weiterhin mit ssh darauf zugreifen zu können. sudo ufw allow from 10.0.2.2 to any port 22 Danach habe ich noch Port 80 für http freigegeben. sudo ufw allow 80/tcp

Beim installieren der FireWall ist darauf zu achten, die richtigen Ports für die richtigen IP Adressen freizugeben. So ist es mir passiert, dass ich den Port 22 für die Falsche Adresse freigegeben habe. So konnte ich nicht mehr auf meine VM Zugreifen und mein Fortschritt war dahin.

Zum Testen am Ende kann man einfach sudo ufw status eingeben. Die Ausgabe beschriebt auf welchen ports welche Komunikation zugelassen ist. Bei mir sieht dies wie folgt aus:
![](assets/README-0c95dfab.PNG)

## SSH Tunnel

Ich habe als gegensatz von der Benutzerverwaltung, welche ich nicht als sonderlich wichtig empfand bei solch einer Umgebung einen SSH Tunnel erstellt und zwar wie folgt:

    cd user
    vagrant ssh database
    # Wechsel auf User admin01
    sudo su - admin01
    # in der VM
    ssh -L 8000:localhost:80 web01 -N &
    netstat -tulpen
    curl http://localhost:8000

**Kannte ich nicht:** Ich kannte mich etwas mit FireWalls und deren Rules ein wenig aus auf der Linux umgebung aus. Zudem hatte ich ein Vorwissen über SSH Tunnel aber wusste nicht wie es einzurichten gilt.

**War neu für mich** Ich kann nun eine UFW Firewall aufsetzen und konfigurieren. Ich kann einzelne Ports freigeben. Ich kann einen ReverseProxy einrichten.

# Modul 300 LB03
