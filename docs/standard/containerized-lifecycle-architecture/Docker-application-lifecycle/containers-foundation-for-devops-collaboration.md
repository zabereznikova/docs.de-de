---
title: Container als Grundlage für die Zusammenarbeit mit DevOps
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 0fa43263e789bba5b720792e7e8dc5321af795b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576219"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Container als Grundlage für die Zusammenarbeit mit DevOps

Aufgrund der Natur der Container und Docker-Technologie können Entwickler ihre Software- und Abhängigkeiten problemlos IT-Betrieb und produktionsumgebungen Freigeben der typische "Funktionsweise auf meinem Computer" Entschuldigung Geschäftslogikkomponenten bei. Container lösen Anwendungskonflikte zwischen verschiedenen Umgebungen. Indirekt, bringen Sie Container und Docker Entwickler und IT-Betrieb näher zusammen, erleichtert es Ihnen, effektiv zusammenarbeiten. Den Container-Workflow einsetzen bietet viele Kunden die Kontinuität DevOps, die haben sie gesucht, aber bisher mussten implementieren, die über eine komplexere Konfiguration für die Version und Pipelines erstellen. Container vereinfachen die Pipelines erstellen, testen, bereitstellen, im DevOps.

![](./media/image1.png)

Abbildung 2 – 1: Main Arbeitslasten pro "Rollen" in den Lebenszyklus Sammelartikeleinheit Docker

Mit der Docker-Containern Entwickler eigene Was ist in den Container (Anwendung und Dienst und Abhängigkeiten zu Frameworks und Komponenten) und wie die Container und die Dienste zusammen als eine Anwendung aus, das eine Sammlung von Diensten Verhalten. Abhängigkeiten von mehreren Containern werden definiert, in eine Datei Docker compose.yml oder was aufgerufen werden könnte eine *Bereitstellungsmanifest*. In der Zwischenzeit können IT-Betriebsteams (IT-Experten und Verwaltung) auf die Verwaltung von produktionsumgebungen konzentrieren; Infrastruktur; Skalierbarkeit; Überwachen der; und letztlich sicherstellen, dass die Anwendungen ordnungsgemäß für die Endbenutzer übermittelt werden, ohne den Inhalt von den verschiedenen Containern wissen zu. Daher wird der Name "Container" zurückrufen die Analogie zu realen Shipping Container. Folglich müssen der Besitzer der Inhalte des Containers nicht betreffen mit wie der Container übertragen wird, und der Protokollversand Unternehmen Transporte einen Container ab dem Punkt der Ursprung an ihr Ziel ohne wissen oder eine Rolle spielt, über den Inhalt. Auf ähnliche Weise können Entwickler erstellen und den Inhalt in einem Docker-Container ohne die Notwendigkeit, selbst mit den Transportmechanismen "" betreffen besitzen.

In der Säule auf der linken Seite der Abbildung 2-1 Entwickler schreiben und Ausführen von Code lokal in Docker-Containern mit Docker für Windows oder Mac Sie definieren die betriebsumgebung für den Code mit einer dockerfile-Datei, der angibt, das zugrunde liegende Betriebssystem sowie Buildschritte zum Erstellen von Code in einem Docker-Image ausführen. Die Entwickler zu definieren, wie die ein oder mehrere Abbilder Zusammenwirken werden mit den zuvor erwähnten *Docker compose.yml* Datei Bereitstellungsmanifest. Nach Abschluss der lokalen Entwicklung mithilfe von Push übertragen sie ihren Anwendungscode sowie den Docker-Konfigurationsdateien im Code-Repository ihrer Wahl (d. h. Git-Repository).

Die DevOps Pillar definiert den Build – Continuous Integration (CI) Pipelines mit dem die dockerfile-Datei im Code-Repository bereitgestellt. Das CI-System zieht die basiscontainerimages aus der ausgewählten Docker-Registrierung und erstellt die benutzerdefinierten Docker-Images für die Anwendung. Die Bilder werden dann überprüft und abgelegt werden, an der Docker-Registrierung für die Bereitstellung in mehreren Umgebungen verwendet.

In der Säule auf der rechten Seite bereitgestellt Vorgänge, die Teams verwalten, Anwendungen und Infrastrukturen, die in der produktionsumgebung während der Überwachung der Umgebung und Anwendungen, damit sie Feedback und Einblicke für das Entwicklungsteam dazu, wie die Anwendung bereitstellen können verbessert. Container-apps werden in der Regel in der Produktion mithilfe Container Orchestrators ausgeführt.

Die zwei Teams zusammenarbeiten über eine grundlegende Plattform (Docker-Container), die eine Trennung von Anliegen als einen Vertrag, der zwei Teams Zusammenarbeit im Lebenszyklus Anwendung erheblich zu verbessern. Die Entwickler besitzen Inhalte des Containers, seiner betriebsumgebung und die Wechselbeziehungen Container, während das Betriebsteam dauern die erstellte Images zusammen mit dem Manifest und führt diese in ihre Orchestrierung System.

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Einführung in den Lebenszyklus einer generischen End-to-End-Docker Anwendungsworkflow

Abbildung 2 x 2 zeigt einen ausführlicheren Workflow für einen Lebenszyklus der Anwendung Docker schwerpunktmäßige in dieser Instanz bestimmte DevOps-Aktivitäten und Ressourcen an

![](./media/image2.png)

Abbildung 2 x 2: Allgemeine Workflow für die Docker Container Lebenszyklus einer Anwendung verwendet.

Alles beginnt mit dem Entwickler, Schreiben von Code in der inneren Schleife Workflow startet. Die innere Schleife Stufe ist, in denen Entwickler alles definieren, die vor dem Übertragen von Code im Code-Repository (z. B. ein Quellcodeverwaltungssystem z. B. Git). Nachdem eine Zusicherung erfolgt ist, löst das Repository fortlaufende Integration (CI) und dem Rest des Workflows.

Die innere Schleife besteht im wesentlichen Schritte wie "Code", "ausführen" "test" und "debug" plus zusätzliche Schritte direkt vor dem Ausführen der app lokal aus. Dies ist bei der Entwickler ausgeführt wird, und die Anwendung als einen Docker-Container testet. Der Workflow für die innere Schleife wird in den Abschnitten beschrieben werden, die folgen.

Machen einen Schritt zurück an die End-to-End-Workflow gesucht werden soll, ist der DevOps-Workflow mehr als eine Technologie oder ein Toolset: Es handelt sich um eine Denkweise, die kulturelle Entwicklung erforderlich sind. Es ist Personen, Prozesse und die geeigneten Tools Anwendungslebenszyklus schnellere und besser vorhersagbare vornehmen. Unternehmen, die in der Regel einen Datenvolumes Workflow übernimmt Strukturieren ihrer Organisationen darstellt, Personen und Prozesse, die die Datenvolumes Workflow entsprechen.

DevOps üben können Teams zusammen verkürzt, Wettbewerber Druck durch Ersetzen der fehleranfällige manuelle Prozesse mit Automatisierung, was verbesserte rückverfolgbarkeit und wiederholbare Workflows zur Folge. Organisationen können auch Umgebungen effizienter verwalten und bemerken kosteneinsparungen mit einer Kombination von lokalen und Cloud-Ressourcen sowie nahtlos integrierte Tools.

Wenn Sie den DevOps-Workflow für Docker-Anwendungen implementieren, werden Sie sehen, dass des Docker-Technologien in fast jeder Phase des Workflows, die Ihrer Entwicklung aus, bei der Arbeit in der inneren Schleife (Code, ausführen, Debuggen), um die Phase, in der CI-Build-Test-vorhanden sind und, Natürlich, auf die Produktions- und Stagingumgebungen und die Container für diese Umgebungen bereitstellen.

Zur Verbesserung der Qualität Methoden hilft, um Mängel früh im Entwicklungszyklus, zu ermitteln, die reduziert die Kosten für die Behebung Eingriffe. Durch u. a. die Umgebung und die Abhängigkeiten in der Abbildung und die Übernahme einer Philosophie der Bereitstellung des gleichen Images in mehreren Umgebungen, fördern Sie eine Disziplin umgebungsspezifische Konfigurationen vornehmen Bereitstellungen zuverlässiger extrahieren.

Umfangreiche Daten, die durch die effektive Instrumentierung (Überwachung und Diagnose) abgerufen Einblick in die Leistungsprobleme und Benutzerverhalten als Anleitung für die zukünftige Prioritäten und -Investitionen.

DevOps sollte einen Weg ist, nicht auf ein Ziel angesehen werden. Es sollte durch entsprechend Bereichsbezogene Projekte inkrementell implementiert werden, aus dem Erfolg veranschaulichen, erfahren Sie, und entwickeln.

## <a name="benefits-of-devops-for-containerized-applications"></a>Vorteile der DevOps für Sammelartikeleinheit

Hier sind einige der wichtigsten Vorteile, die eine solide DevOps-Workflow:

-   Bereitstellen von Software mit höherer Qualität, schneller und mit der eine bessere Kompatibilität

-   Laufwerk zur stetigen Verbesserung und Korrekturen, kostengünstiger und früher

-   Erhöhen Sie Transparenz und Zusammenarbeit zwischen den Beteiligten in der Bereitstellung und den Betrieb von software

-   Kostenkontrolle und bereitgestellten Ressourcen effizienter nutzen, und minimiert gleichzeitig die Sicherheitsrisiken

-   Plug & play-gut mit vielen vorhandenen DevOps-Investitionen, einschließlich der Investitionen in open-source

>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (.. /Microsoft-Platform-Tools-containerized-Apps/Index.MD)
