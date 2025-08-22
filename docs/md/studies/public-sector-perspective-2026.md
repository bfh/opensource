# Publikation von OSS gemäss EMBAG

Seit 2022 ist mit dem Gesetzt zum Einsatz elektronischer Mittel zur Erfüllung von Behördenaufgaben (EMBAG) eine klare Vorgabe an Bundesämter Software unter einer Open Source Lizenz zu veröffentlichen. Die Bundeskanzlei bzw. DTI hat in dieser Zeit kontinuierlich ihre [OSS Hilfsmittel](https://www.bk.admin.ch/bk/de/home/digitale-transformation-ikt-lenkung/bundesarchitektur/open_source_software/hilfsmittel_oss.html) ausgebaut. Dies ist wichtig, da das Gesetz sich auf juristische, Lizenzen und Haftung und nicht auf technische Aspekte fokussiert.

Aber das Bereitstellen von Software unter einer Open Source Lizenz allein reicht nicht aus um Nachnutzung zu erreichen. Damit andere Behörden oder Gemeinden die Software ebenfalls nutzen und eigene Verbesserungen beitragen, müssen eine Reihe von Massnahmen ergriffen werden:

1. Bekanntmachung
2. technische und nicht technische Dokumentation
3. Paketierung des Code nach aktuellem Stand der Technik
4. Regelmässige Updates
5. Interaktionsmöglichkeiten mit der Entwicklung
6. Governance Struktur

# EMBAG Good Practices: Beispiel Loom-Projekt

Am 29.4.2025 [veröffentliche](https://www.vtg.admin.ch/de/newnsb/3Cevz3zsD4R1pMdvrPsAJ) das Kommando Cyber das Projekt Loom als Open Source. Dort wurde in nicht technischen Worten die Intension und Mehrwert erklärt. Am selben Tag schon gab es unzählige News-Artikel darüber (1.). Der Source Code selber wurde auf [gitlab.com](https://gitlab.com/swiss-armed-forces/cyber-command/cea/loom) veröffentlicht, eine bekannte Platform welche alle notwendigen Tools für die Zusammenarbeit mit sich bringt (5.).

In der Dokumentation werden die Funktionen bzw. Limitierungen, Installationsanleitung und Architektur zusammengefasst (2.). In weiterführenden Links werden diese Themen entsprechend vertieft, inklusive wie man eigene Verbesserungen einbringen kann (6.). Das Projekt nutzt diverse andere Open Source Komponenten und paketiert diese in Docker (3.). Es werden regelmässig Verbesserungen veröffentlicht durch eine Vielzahl von verschiedenen Personen (4.).

Somit erfüllt das Loom Projekt alle oben genannten Kriterien vollumfänglich. Jedoch sollte angemerkt sein, Open Source Projekte können auch mit weniger Aufwand erfolgreich eine Community aufbauen.
