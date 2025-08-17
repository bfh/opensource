<div class="reveal" data-video="small top-right">

<img src="content/froscon20.svg" height="80px">

### Lernstick Linux als persönliche Lern- oder

### abgesicherte Prüfungsumgebung

<br />
📧 <a href="mailto:joerg.berkel@bfh.ch">joerg.berkel@bfh.ch</a><br />
Folien: https://ige.li/lernstick<br />

<table>
<tr>
<a href="https://www.lernstick.ch/" target="_blank"><img src="https://campla.github.io/assets/images/lernstick_logo.svg" width="190px"></a>
<a href="https://w4ASk!Po05Eafww.campla.ch/" target="_blank"><img src="https://www.bfh.ch/.imaging/mte/bfh-theme/image-and-gallery-xxs/dam/bfh.ch/forschung/wirtschaft/Digital-sustainability-lab/lernstick/campla-logo-trans-256x256.png/jcr:content/campla-logo-trans-256x256.png" width="160px"></a>
</tr>
</table>
<small>www.lernstick.ch / www.campla.ch</small>

Note:
Mastodon https://streaming.media.ccc.de/froscon2025/
https://streaming.media.ccc.de/froscon2025/HS7
Signal IPST

decktape
ige.li Link

Lernstick ist eine sichere Lern- und Arbeitsumgebung, die meistens auf externen Speichermedien wie USB-Sticks, USB-Festplatten oder SD-Karten installiert wird. Durch die "Secure Boot"-Kompatibilität kann nahezu jeder Computer von diesen Speichermedien gestartet werden, eine funktionierende Festplatte oder vorinstalliertes Betriebssystem sind nicht notwendig.

Die auf Debian GNU/Linux basierende Distribution Lernstick wird seit 15 Jahren gepflegt und bietet eine erweiterte Hardwareunterstützung für Apple Macbooks und Microsoft-Surface-Geräte. Dies vereinfacht den Bildungseinsatz durch mitgebrachte Geräte (BYOD) z.B. auch für Prüfungen durch die chancengleiche und abgesicherte Umgebung Lernstick EXAM.

Dieser Vortrag stellt die Besonderheiten von Lernstick EDU/EXAM (Persistenz, Sicherheitsfunktionen, Accessibility, Mehrsprachigkeit) sowie Nachteilsausgleichfunktionen (Sprachausgabe, lokale LLMs, ...) für Prüfungen vor.

Lernstick wird beispielsweise im Nur-Lesen-Modus als Absicherung der Prüfungsplattform CAMPLA (entwickelt durch Partnerhochschule FHNW) eingesetzt und diese Spezialversion unterstützt zusätzlich den Systemstart von Apple Silicon M1/M2-Architekturen.

Im Q&A und an auf der Tagung bin ich auch an euren Erfahrungen mit weiteren Opensource-Lösungen für Prüfungen wie dem finnischen Abitti oder Next-Exam aus Österreich interessiert!
weitere Informationen zum Referenten

--

### Inhalt

1. Überblick / Lernstick EDU
1. Spezialversion EXAM
1. Start + Menü
1. Live-Demo
1. Prüfungsplattform CAMPLA
1. Getting started
1. Q&A

--

### ⬆️ Ich & Tätigkeiten 🧭

- ➡️ Dipl.-Inf. (FH)
- ⬇️ 2009-22: PHBern
  - praktische Medienbildung
- 2020: Offene Schule Bern
- 2022: BFH Wirtschaft
  - öffentlicher Sektor
  - Bildungsinformatik / OSS
- Vorstand bei CH Open: [openeducationday.ch](https://openeducationday.ch)
- Part of Demoscene: [echtzeitkultur.org](https://echtzeitkultur.org)

---

### Was ist ❓

#### Lernstick-...

- offene und persönliche **Lern**- und Arbeitsumgebung
- kann auch von USB-**Sticks** gestartet werden
- freies Linux-Betriebssystem 🐧
  <br /><br />

#### ...-Prüfungsumgebung

- **abgesicherte und unpersönliche** Spezialversion für Prüfungen

--

### Wer? Wann?

💡 Ronny Standtke + Team 🧑🏼‍🏭<br />
_Open Source_-Produkt

<ul>
<li class="fragment">2009: Lernstick
<li class="fragment">2011: Lernstick Prüfungsumgebung
<li class="fragment">seit 2020: Lernstick mit <a href="https://campla.ch/">CAMPLA.ch</a><br />(Kooperation mit FH Nordwestschweiz 🏫)
</ul>

https://github.com/Lernstick/lernstickAdvanced/

--

### Für wen?

#### 1. BFH + FHNW 🥫🐕

#### 2. Kund\*innen 💵

- Hochschulen, ... (CAMPLA)
- Schulen (CUSTOM)<br />&nbsp;

#### 3. Lernstick-Community ([siehe Forum](https://forum.lernstick.ch/))

- Interessierte (EDU)
- Schulen (EXAM, EDU)
- ..?

--

### Wie?

- ![](https://www.debian.org/logos/openlogo-nd.svg) [Debian Live](https://wiki.debian.org/DebianLive) mit Backports, ...
- Schnelle USB-Sticks (Transcend!) ⚡
- kompatibel zu Secure Boot
- 💻 Hardware-Unterstützung:
  - Surface-Tablets
  - Intel-Macs
  - teilweise Apple Silicon

--

### Besondere Eigenschaften

- mobile Persistenz, Verschlüsselung 🔐
- BYOD-Szenarien
  - Prüfungen "offline" oder mit Online-LMS
- Accessibility in ([GNOME](https://developer.gnome.org/hig/guidelines.html))
  - \+ Nachteilsausgleich
- Mac: Tastaturlayout, Touchbar
- Btrfs-Dateisystem mit Snapshots 📸

---

### Sichere E-Assessments? 🤔

<table border="0">
 <th>Betrug braucht&hellip;</th>
 <th>Gegenmassnahmen</th>
  <tr>
    <td>
        <ul>
            <li>Kriminelle Energie</li>
            <li>Wissen</li>
            <li><u>Gelegenheit / Zeit</u></li>
        </ul> 
    </td>
    <td>
        <ul>
            <li>hohe Strafen</li>
            <li>hohe technische Hürden</li>
            <li>Entdeckungs-<br />wahrscheinlichkeit erhöhen</li>
        </ul> 
    </td>
 </tr>
</table>

--

### «Bring your own Hardware» ✅

<img src="content/byoh.svg" alt="https://drive.switch.ch/index.php/s/87fbvbqInk0dcoa/download">

Bring your own «Betriebssystem»? ❌

--

## Sicherheitsmodell 🏰

### Vollständige Kontrolle über die «Burg»

<img src="content/burg-export11.svg" alt="https://drive.switch.ch/index.php/s/KtB0yIJgwfAGAcI/download">

--

### Lernstick EXAM

- ermöglicht Offlineprüfungen
- ggf. Internetzugriff via Whitelist 🔒
- **Chancengleichheit**
  - identische Umgebung/Software<br/>z.B. LibreOffice, RStudio, VSCodium, ..
- Funktionen **Nachteilsausgleich**
  - [Sprachsynthese](https://github.com/rhasspy/piper) (offline)
  - [Übersetzung](https://mozilla.github.io/translations/firefox-models/) (offline)

--

<img src="content/ollama.svg" width="190px">

- weitere Hilfsmittel
  - Ollama: KI-Modelle integrierbar (offline)
- eingebaute VM-Detection
- Rekurssicherheit (Screenshotfunktion)
- Backups auf Austauschpartition

---

### Startmenü (🇺🇳 und ⌨️)

![](content/lernstick-12-uefi-grub2-newfont.png)

--

![](content/lernstick-12-uefi-grub2-lang.png)

<small><em>GRUB 2 (UEFI) mit neuem Font "DejaVu Sans Mono"</em></small>

--

<h3>Mehrere Desktop-Umgebungen</h3>
<small><em>Gfxboot (BIOS Legacy):</em></small>
<img src="content/lernstick-12-legacy-gfxboot-wm.png">

--

### Anpassungen: [Gerätestart](https://github.com/CAMPLA/campla-lernstick-boot/wiki/Boot-Process), [einmalige Konfiguration](https://github.com/CAMPLA/campla-lernstick-boot/wiki/Boot-Problem-Handling)

- **~80% «Plug & Play»** 🍐
  - «3rd-party Secure Boot» (~6min) 🍊
  - «gemanagte» Firmenlaptops 🍅
- «MacBooks 2018-20» 2min 🍊
- «MacBooks M1/M2» 10min 🍊
- Apple M3 oder neuer / ARM-Snapdragon 🍅
- iPads / Android / Chromebooks 🍅

---

### Windows-PC

- Doppelklick auf **start.bat**

![](content/win10-start-bat.png)

- benötigt **Admin-Autorisierung** für Autostart

--

### ... oder manuelle Auswahl (**start_manual.bat**)

![](content/w10-start-manual.png)

💡 _UEFI SanDisk / USB / Removable Device / ..._

⚠️ Secure Boot: Enable 3rd-party (Non-Microsoft)

---

### MacsBooks (Intel) (**aus**geschaltet)

#### Wahltaste (alt/option ⌥) halten

<img src="content/alt.jpg" heigth=100%>

--

### Laufwerk rechte Seite auswählen

<img src="content/mac-choose-campla-right.jpg" width=50%>

<small>💡 Geräte mit T2-Chip (2018-20): Sicherheitslevel anpassen</small>

--

### Apple M1/M2 Setup 🧰

<table border="0">
<tr>
 <td width=40%><img src="content/m1m2-installer-mac.png" width="340px"></td>
 <td width=60% style="vertical-align: top">
 <ul>
 Apple Silicon lässt nur <b>interne Startlaufwerke</b> zu:
 <li>... 3 GB benötigt</li>
 <li>... Bootloader: Asahi Linux</li>
 </ul>
 </td>
 </tr>
</table>

---

### Demotime 🛠️

- Stick flashen
- Willkommensprogramm
- Speichermedienverwaltung
  - Features: Kategorie **zurücksetzen**

--

### ISO-Abbild --> Boot-Stick (nur lesen!)

«Boot-Stick» beschreiben z.B. mit [Etcher](https://etcher.balena.io/)

<img src="https://lernstick-doc.readthedocs.io/de/latest/_images/balena-etcher-pre-flash.png" height=480px>

--

### "nur lesen" ↔️ mit Persistenz (lesen und schreiben)

--

### Demo: Speichermedienverwaltung 🛠️

1. **ISO-Abbild** in Virtueller Maschine starten<br />
   (oder auf «Boot-Stick» schreiben)
2. Mit **Speichermedienverwaltung**<br />
   «System installieren» auf leeren «Haupt-Stick»
3. «Haupt-Stick» starten und<br />
   **Anpassungen vornehmen**
4. «Haupt-Stick» im «nur lesen»-Modus starten<br />
   und **vervielfältigen**

---

### Cloud E-Assessment Management Platform

<em>Onlineplattform zur Prüfungsorchestrierung</em>

- Open Book, Closed Book, ... 📗
- Kompetenzorientierte Prüfungen 📐🧰
  - Remote Desktop: Win-VMs mit Excel, CADworks, ...
  - Softwarepakete (Flatpak) aktivieren
- u.v.m.

--

![](https://campla.ch/wp-content/uploads/2024/12/examinationLernstickDeutschMitUser-1-1024x738.png)

--

### Besonderheiten CAMPLA-Lernstick

- Hybrid-ISO: x64 + Apple Silicon
  - "nur lesen"
- Dynamische Konfiguration
- SAMBA-Share: Prüfungsunterlagen/-Abgabe
- [Remote-Attestation](<https://de.wikipedia.org/wiki/Trusted_Platform_Module#Bescheinigung_(remote_attestation)>) per TPM möglich
- ...

--

### Letzte Tipps / Vorbereitung 📋

- Standard: **user** / Password: **live**
- Vorwissen + Experimentierfreudigkeit
- [Älteres Handbuch (DE)](https://lernstick-doc.readthedocs.io/) bietet Unterstützung
- Zeit für Onboarding der Anwender\*innen
- BYOD: Ersatzgeräte bereit haben

---

### Q&A

**Fragen?**
<br /><br />

### Diskussion 💬

- Erfahrungen mit [Abitti](https://www.abitti.fi/) 🇫🇮<br />oder [Next-Exam](https://life-edu.eu/next-exam/) 🇦🇹?
- ...

---

##### Kontaktiere uns!

🗨️ **Am Stand**: [Freie Software und Bildung e.V.](https://fsub.de/)<br /><br />
📧 info@lernstick.ch<br />
📧 campla.services@fhnw.ch<br />

### nachhaltig, digital & unternehmerisch

<table>
<tr>
<a href="https://virtuelleakademie.ch/2023/12/18/sicheres-pruefen-ist-moeglich/" target="_blank"><img src="https://campla.github.io/assets/images/lernstick_logo.svg" width="190px"></a>
<a href="https://hochschulforumdigitalisierung.de/de/blog/campla-lernstick" target="_blank"><img src="https://www.bfh.ch/.imaging/mte/bfh-theme/image-and-gallery-xxs/dam/bfh.ch/forschung/wirtschaft/Digital-sustainability-lab/lernstick/campla-logo-trans-256x256.png/jcr:content/campla-logo-trans-256x256.png" width="160px"></a>
</tr>
</table>
<small>(zwei thematische Blogbeiträge in den Logos verlinkt 🔗)</small>

---

### Merci!

Präsentation mit [reveal.js](https://github.com/bfh/reveal.js/)<br />
PDF-Export mit [decktape](https://github.com/astefanutti/decktape/) erstellt.<br />

![CC-by Lernstick](https://i.creativecommons.org/l/by/4.0/88x31.png "CC-by Lernstick/IPST")
[bfh.ch/ipst](https://www.bfh.ch/ipst)<br />
[Source](https://github.com/bfh/opensource/blob/main/docs/slides/2025-froscon/content.md) licensed under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)<br />
