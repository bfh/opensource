# Publikation von OSS gemäss EMBAG

Seit 2022 ist dem Gesetzt zum Einsatz elektronischer Mittel zur Erfüllung von Behördenaufgaben (EMBAG) eine klare Vorgabe an Bundesämter
Software unter einer Open Source Lizenz zu veröffentlichen. Mittlerweile gibt es also nun auch immer mehr Open Software, welche von Bundesämter veröffentlicht wurde. Aber natürlich trennt sich hier auch die Streu vom Weizen wie die politische Intension dank Open Source mehr Transparenz, Effizienz und Sicherheit zu schaffen, in der Praxis umgesetzt wird. Denn das Gesetz fokussiert sich nur auf die juristische Dimension Lizenzen und Haftung.

Aber das Bereitstellen von Software unter einer Open Source Lizenz reicht nicht aus. Damit andere Behörden oder Gemeinden die Software ebenfalls nutzen und eigene Verbesserungen beitragen, müssen eine Reihe von Massnahmen ergriffen werden. Allen sollten folgende Aspekte beachtet werden:

1. Bekanntmachung durch einschlägige Events bzw. Medien
2. Publikation technische Dokumentation
3. Publikation nicht technische Dokumentation
4. Paketierung des Code nach aktuellem Stand der Technik
5. Regelmässige Updates bei Minimierung von Inkompatibilitäten
6. Möglichkeit zur Interaktion mit der Entwicklung und Projektleitung
7. Klare Governance Struktur, wie z.B. die Roadmap definiert wird

# EMBAG Good Practices: Beispiel Loom-Projekt durch Kommando Cyber

Am 29.4.2025 [veröffentliche](https://www.vtg.admin.ch/de/newnsb/3Cevz3zsD4R1pMdvrPsAJ) das Kommando Cyber das Projekt Loom als Open Source. Dort wurde in nicht technischen Worten die Intension erklärt, der Mehrwert und direkt ein Angebot zur Zusammenarbeit formuliert. Direkt am selben Tag schon gab es unzählige News-Artikel darüber (1.). Der Source Code selber wurde auf [gitlab.com](https://gitlab.com/swiss-armed-forces/cyber-command/cea/loom) veröffentlicht, eine bekannte Platform welche alle notwendigen Tools für die Zusammenarbeit mit sich bringt (6.).

In der Dokumentation werden die Funktionen bzw. Limitierungen, Installationsanleitung und Architektur zusammengefasst (2./3.). In weiterführenden Links werden diese Themen entsprechend vertieft, inklusive wie man eigene Verbesserungen einbringen kann (7.). Das Projekt nutzt diverse andere Open Source Komponenten und paketiert diese in Docker (4.). Es werden regelmässig Verbesserungen veröffentlicht durch eine Vielzahl von verschiedenen Personen (5.). Dabei wird auch das öffentlich einsehbare Ticketing-System von gitlab.com genutzt um Transparenz zu schaffen.

Somit erfüllt das Loom Projekt alle oben genannten Kriterien vollumfänglich. Jedoch sollte angemerkt sein, Open Source Projekte können auch mit weniger Aufwand erfolgreich eine Community aufbauen.
