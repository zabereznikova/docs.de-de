---
title: Container als Grundlage für die DevOps-Zusammenarbeit
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: ccc8ef765cadfec31a2f714767d8e6eb76508093
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126626"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Container als Grundlage für die DevOps-Zusammenarbeit

Aufgrund der Natur von Containern und Docker-Technologie können Entwickler ihrer Software und Abhängigkeiten ganz einfach mit IT-Betrieb und produktionsumgebungen freigeben beim Entfernen der typischen "es funktioniert auf meinem Computer" Entschuldigung. Container lösen Konflikte zwischen Anwendungen zwischen unterschiedlichen Umgebungen. Indirekt zusammenbringen Container und Docker-Entwickler und IT-Betrieb näher, dafür eine effektive Zusammenarbeit zu vereinfachen. Übernehmen den Container-Workflow bietet viele Kunden die DevOps-Kontinuität, die Sie gesucht haben, aber bisher über eine komplexere Konfiguration für die Version zu implementieren und Pipelines zu erstellen. Container vereinfachen die Erstellung/Testdurchführung/Bereitstellung-Pipelines in DevOps.

![](./media/image1.png)

Abbildung 2-1: Main Workloads pro "Personen" im Lebenszyklus containerisierten Docker-Anwendungen

Mit Docker-Containern, Entwickler eigene Was ist in den Container (Anwendungs- und Dienst- und Abhängigkeiten für Frameworks und Komponenten) und den Container und Dienste zusammen, wie eine Anwendung, die durch eine Sammlung von Diensten zusammengesetzt Verhalten. Die gegenseitigen Abhängigkeiten von mehreren Containern sind in was aufgerufen werden kann, oder eine Docker-compose.yml-Datei definiert eine *Bereitstellungsmanifest*. In der Zwischenzeit können IT-Betriebsteams ("IT-Experten" und "Verwaltung") auf die Verwaltung von produktionsumgebungen konzentrieren; Infrastruktur Skalierbarkeit Überwachen der; und letztlich, sicherzustellen, dass die Anwendungen ordnungsgemäß für die Endbenutzer bereitstellen werden, ohne den Inhalt von den verschiedenen Containern kennen zu müssen. Daher der Name "Container" die Analogie zu echten Frachtcontainer abrufen. Daher müssen die Besitzer des Inhalts von eines Containers nicht betreffen sich wie der Container versendet werden soll, und der Protokollversand Unternehmen Transporte einen Container aus am ursprünglichen Speicherort, an das Ziel ohne wissen oder eine Rolle spielt, über den Inhalt. Auf ähnliche Weise können Entwickler erstellen und besitzen den Inhalt in einem Docker-Container, ohne die Notwendigkeit, sich mit den Transportmechanismen "" betreffen.

In der Säule auf der linken Seite der Abbildung 2-1 Entwickler schreiben und Ausführen von Code lokal in Docker-Containern mit Docker für Windows oder Mac. Sie definieren die betriebsumgebung für den Code mit einer dockerfile-Datei, der angibt, das Basisbetriebssystem sowie die Schritte zum Erstellen von Code in einem Docker-Image ausgeführt. Die Entwickler zu definieren, wie die ein oder mehrere Abbilder Zusammenwirken werden mithilfe der oben genannten *"Docker-Compose.yml"* Bereitstellungsmanifest für die Datei. Nach Abschluss die lokale Entwicklung, übertragen sie ihren Anwendungscode und die Docker-Konfigurationsdateien im Code-Repository ihrer Wahl (d. h. Git-Repository).

Die DevOps-Säule definiert die Build – Continuous Integration (CI)-Pipelines mit der dockerfile-Datei im coderepository bereitgestellt. Das CI-System die Basis-containerimages aus der ausgewählten Docker-Registrierung abruft und der benutzerdefinierten Docker-Images für die Anwendung erstellt. Die Bilder werden anschließend überprüft und per Push an die Docker-Registrierung für die Bereitstellung in mehreren Umgebungen verwendet.

In der Säule auf der rechten Seite bereitgestellt Vorgänge, die Teams verwalten, Anwendungen und Infrastruktur in der produktionsumgebung während der Überwachung von der Umgebung und die Anwendungen, damit sie Feedback und Einblicke für die das Entwicklungsteam dazu, wie die Anwendung möglicherweise bereitstellen können verbessert. Container-apps werden in der Regel in der Produktion mithilfe von containerorchestratoren ausgeführt.

Die beiden Teams sind über eine grundlegende Plattform (Docker-Containern) zusammenarbeiten, die eine Trennung der Belange als Vertrag, und somit eine erhebliche Steigerung der beiden Teams Zusammenarbeit im Lebenszyklus Anwendung bereitstellt. Die Entwickler besitzen Inhalte des Containers und seiner betriebsumgebung, die Container-Abhängigkeiten, während die Operations-Teams nutzen den erstellten Images zusammen mit dem Manifest und führt diese in ihren System für die Orchestrierung.

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Einführung in eine generische End-to-End-Docker-anwendungsworkflows des Lebenszyklus

Abbildung 2-2: Stellt einen ausführlicheren Workflow für einen Docker-Anwendungslebenszyklus mit dem Schwerpunkt auf bestimmte DevOps-Aktivitäten und Ressourcen auf dieser Instanz verwendet wird.

![](./media/image2.png)

Abbildung 2-2: Allgemeiner Workflow für den Lebenszyklus des Docker-containeranwendungen

Alles beginnt mit dem Entwickler, mit dem Schreiben von Code in den Workflow für die innere Schleife beginnt. Die innere Schleife-Phase ist, in dem Entwickler alles definieren, die vor dem Pushvorgang von Code im Code-Repository (z. B. ein Quellcodeverwaltungssystem wie z. B. Git) erfolgt. Nachdem sie ein Commit ausgeführt wird, löst das Repository Continuous Integration (CI) und den Rest des Workflows.

Die innere Schleife besteht im Grunde typische Schritte wie "Code", "ausführen," "test" und "debug" sowie zusätzliche Schritte direkt vor dem Ausführen der app lokal aus. Dies ist bei der Entwickler ausgeführt wird, und die app als Docker-Container testet. Der Workflow für die innere Schleife wird in den Abschnitten erläutert werden.

Einen Schritt zum zurückgeleitet Betrachten der End-to-End-Workflow, der DevOps-Workflow ist mehr als eine Technologie oder einen Satz von Tools: Es ist eine Haltung, die kulturelle Weiterentwicklung ist erforderlich. Es ist die Mitarbeiter, Prozesse und den entsprechenden Tools der Anwendungslebensdauer, schnellere und besser vorhersagbare vornehmen. Unternehmen, die einen Workflow in Containern in der Regel übernehmen umstrukturieren ihrer Organisationen zur Darstellung von Menschen und Prozesse, die den Containern Workflow entsprechen.

Eignen, DevOps, können Teams schneller zusammen reagieren auf Wettbewerbsdruck durch Ersetzen von fehleranfällige manuelle Prozesse durch Automatisierung, die verbesserte rückverfolgbarkeit und wiederholbare Workflows ausgeführt werden. Organisationen können auch eine effizientere Verwaltung von Umgebungen und Erkennen von kosteneinsparungen mit einer Kombination aus lokalen und Cloudressourcen sowie eng integrierte Tools.

Wenn Sie Ihre DevOps-Workflow für Docker-Anwendungen zu implementieren, werden Sie sehen, dass der Docker-Technologien in fast jeder Phase des Workflows, die von Ihrem Entwicklungscomputer bei der Arbeit in der inneren Schleife (Code, ausführen, Debuggen), um die Build-Test-CI-Phase, vorhanden sind und, Natürlich an die Produktions- und Stagingumgebungen und bei der Bereitstellung von der Containers in diesen Umgebungen.

Zur Verbesserung der Qualität Methoden kann Fehler frühzeitig im Entwicklungszyklus, identifiziert die reduziert die Kosten für die Behebung Eingriffe. Einschließlich der Umgebung und Ihre Abhängigkeiten in der Abbildung und die Einführung einer Philosophie der Bereitstellung des gleichen Images über mehrere Umgebungen hinweg, Stufen Sie eine Disziplin, extrahieren Sie die umgebungsspezifische Konfiguration, sodass Bereitstellungen zuverlässiger.

Umfangreiche Daten abgerufen werden, durch die effektive Instrumentierung (Überwachung und Diagnose) bietet Einblicke in Leistungsprobleme und Benutzerverhalten, um künftige Prioritäten und Investitionen orientieren.

DevOps sollten eine Reise, die nicht in ein Ziel berücksichtigt werden. Sie sollten über entsprechend Bereichsbezogene Projekte inkrementell implementiert werden, aus dem Erfolg zu veranschaulichen, erfahren Sie, und entwickeln.

## <a name="benefits-of-devops-for-containerized-applications"></a>Vorteile von DevOps für Anwendungen in Containern

Hier sind einige der wichtigsten Vorteile, die eine solide DevOps-Workflow:

-   Liefern Sie Software mit höherer Qualität schneller und mit bessere Einhaltung gesetzlicher Bestimmungen

-   Fördern Sie früher und kostengünstiger Anpassungen und ständige Verbesserung

-   Erhöhen Sie Transparenz und die Zusammenarbeit zwischen Beteiligte zum Bereitstellen und betreiben von software

-   Die kontrollieren Sie Kosten und die nutzen Sie bereitgestellte Ressourcen effektiver, bei gleichzeitiger Minimierung von Sicherheitsrisiken

-   Plug & play-gut mit vielen Ihrer vorhandenen DevOps-Investitionen, einschließlich der Investitionen in open-source

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](../Microsoft-platform-tools-containerized-apps/index.md)