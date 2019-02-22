---
title: Container als Grundlage für die DevOps-Zusammenarbeit
description: Erfahren Sie, die wichtige Rolle der Container, DevOps zu optimieren.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 752a678be7735f7ae962005e1d373993d1496753
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583731"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Container als Grundlage für die DevOps-Zusammenarbeit

Aufgrund der Natur von Containern und Docker-Technologie können Entwickler ihrer Software und Abhängigkeiten ganz einfach mit IT-Betrieb und produktionsumgebungen freigeben beim Entfernen der typischen "es funktioniert auf meinem Computer" Entschuldigung. Container lösen Konflikte zwischen Anwendungen zwischen unterschiedlichen Umgebungen. Indirekt zusammenbringen Container und Docker-Entwickler und IT-Betrieb näher, dafür eine effektive Zusammenarbeit zu vereinfachen. Übernehmen den Container-Workflow bietet viele Kunden die DevOps-Kontinuität, die Sie gesucht haben, aber bisher über eine komplexere Konfiguration für die Version zu implementieren und Pipelines zu erstellen. Container vereinfachen die Erstellung/Testdurchführung/Bereitstellung-Pipelines in DevOps.

![Docker unterstützt das Erstellen von Brücken zwischen Entwickler und Architekten von der Vorgehensweise zum Entwickeln/Design-arbeitsauslastung und die IT-Vorgänge in der Workload ausführen, überwachen, verwalten](./media/image1.png)

**Abbildung 2-1.** Main Workloads pro "Personen" im Lebenszyklus containerisierten Docker-Anwendungen

Mit Docker-Containern, Entwickler eigene Was ist in den Container (Anwendungs- und Dienst- und Abhängigkeiten für Frameworks und Komponenten) und den Container und Dienste zusammen, wie eine Anwendung, die durch eine Sammlung von Diensten zusammengesetzt Verhalten. In die gegenseitigen Abhängigkeiten von mehreren Containern definiert sind eine `docker-compose.yml` Datei oder was aufgerufen werden, kann ein *Bereitstellungsmanifest*. In der Zwischenzeit können IT-Betriebsteams ("IT-Experten" und "Verwaltung") auf die Verwaltung von produktionsumgebungen konzentrieren; Infrastruktur Skalierbarkeit Überwachen der; und letztlich, sicherzustellen, dass die Anwendungen ordnungsgemäß für die Endbenutzer bereitstellen werden, ohne den Inhalt von den verschiedenen Containern kennen zu müssen. Daher der Name "Container" die Analogie zu echten Frachtcontainer abrufen. Daher müssen die Besitzer des Inhalts von eines Containers nicht betreffen sich wie der Container versendet werden soll, und der Protokollversand Unternehmen Transporte einen Container aus am ursprünglichen Speicherort, an das Ziel ohne wissen oder eine Rolle spielt, über den Inhalt. Auf ähnliche Weise können Entwickler erstellen und besitzen den Inhalt in einem Docker-Container, ohne die Notwendigkeit, sich mit den Transportmechanismen "" betreffen.

In der Säule auf der linken Seite der Abbildung 2-1 Entwickler schreiben und Ausführen von Code lokal in Docker-Containern mit Docker für Windows oder Mac. Sie definieren die betriebsumgebung für den Code mit einer dockerfile-Datei, der angibt, das Basisbetriebssystem sowie die Schritte zum Erstellen von Code in einem Docker-Image ausgeführt. Der Entwickler definieren, wie ein oder mehrere Abbilder wird Interoperabilität mit dem zuvor erwähnten `docker-compose.yml` Bereitstellungsmanifest für die Datei. Nach Abschluss die lokale Entwicklung, übertragen sie ihren Anwendungscode und die Docker-Konfigurationsdateien im Code-Repository ihrer Wahl (d. h. Git-Repository).

Die DevOps-Säule definiert die Build – Continuous Integration (CI)-Pipelines mit der dockerfile-Datei im coderepository bereitgestellt. Das CI-System die Basis-containerimages aus der ausgewählten Docker-Registrierung abruft und der benutzerdefinierten Docker-Images für die Anwendung erstellt. Die Bilder werden anschließend überprüft und per Push an die Docker-Registrierung für die Bereitstellung in mehreren Umgebungen verwendet.

In der Säule auf der rechten Seite bereitgestellt Vorgänge, die Teams verwalten, Anwendungen und Infrastruktur in der produktionsumgebung während der Überwachung von der Umgebung und die Anwendungen, damit sie Feedback und Einblicke für die das Entwicklungsteam dazu, wie die Anwendung möglicherweise bereitstellen können verbessert. Container-apps werden in der Regel in der Produktion mithilfe von containerorchestratoren ausgeführt.

Die beiden Teams sind über eine grundlegende Plattform (Docker-Containern) zusammenarbeiten, die eine Trennung der Belange als Vertrag, und somit eine erhebliche Steigerung der beiden Teams Zusammenarbeit im Lebenszyklus Anwendung bereitstellt. Die Entwickler besitzen Inhalte des Containers und seiner betriebsumgebung, die Container-Abhängigkeiten, während die Operations-Teams nutzen den erstellten Images zusammen mit dem Manifest und führt diese in ihren System für die Orchestrierung.

## <a name="challenges-in-application-life-cycle-when-using-docker"></a>Herausforderungen bei der Lebensdauer der Anwendung mithilfe von Docker-Zyklus.

Es gibt viele Gründe, die die Anzahl von Anwendungen in Containern in den kommenden Jahren steigern, und eine der aus diesen Gründen ist das Erstellen von Anwendungen, die auf Microservices basierenden.

In den letzten 15 Jahren die Verwendung von Webdiensten wurde die Basis des Tausende von Anwendungen, und wahrscheinlich schon, nach ein paar Jahren, finden wir die gleiche Situation mit Microservice basierende Anwendungen, die auf Docker-Container ausgeführt wird.

Es lohnt sich außerdem zu erwähnen, dass Sie auch Docker-Container für monolithische Anwendungen verwenden können und Sie weiterhin die meisten Vorteile von Docker erhalten. Container werden nicht nur Microservices erstellen.

Die Verwendung von Docker zur containerisierung und Microservices bewirkt, dass neue Herausforderungen des Entwicklungsprozesses Ihrer Organisation und aus diesem Grund benötigen eine solide Strategie zu viele Container und Microservices, die auf Produktionssystemen zu verwalten. Schließlich müssen unternehmensanwendungen Hunderte oder Tausende von Containern und Instanzen in der Produktion ausgeführt wird.

Diese Herausforderungen erstellen neue Anforderungen auf, wenn DevOps-Tools zu verwenden, damit Sie zum Definieren neuer Prozesse in Ihren DevOps-Aktivitäten und finden Sie Antworten auf diese Art von Fragen können:

- Welche Tools kann ich für die Entwicklung für CI/CD, Verwaltung und Betrieb verwenden?

- Wie kann mein Unternehmen Fehler in Containern verwalten, wenn in der produktionsumgebung ausgeführt?

- Wie können wir unsere Softwarekomponenten in der produktionsumgebung mit minimalen Ausfallzeiten ändern?

- Wie können wir skalieren, und wie können wir unserem Produktionssystem überwachen?

- Wie können wir testen und Bereitstellen von Containern in unserer releasepipeline einschließen?

- Wie können wir die Open-Source-Tools/Plattformen für Container in Microsoft Azure verwenden?

Wenn Sie all diese Fragen beantworten können, werden Sie besser vorbereitet, verschieben Sie Ihre Anwendungen (apps vorhandenen oder neuen) Docker-Containern sein. 

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Einführung in eine generische End-to-End-Docker-anwendungsworkflows des Lebenszyklus

Abbildung 2-2: Stellt einen ausführlicheren Workflow für einen Docker-Anwendungslebenszyklus mit dem Schwerpunkt auf bestimmte DevOps-Aktivitäten und Ressourcen auf dieser Instanz verwendet wird.

![Dieses Diagramm zeigt die "äußere Schleife" von DevOps. Wenn Code per Push an das Repository übertragen wird, eine CI-Pipeline wird gestartet und beginnt dann die CD-Pipeline, in dem die Anwendung bereitgestellt wird. Von bereitgestellten Anwendungen gesammelten Metriken werden eingelesen, wieder in der arbeitsauslastung "Entwicklung", die "innere Schleife", wo auftritt, müssen Entwicklungsteams tatsächliche Daten, die auf Benutzer und die geschäftlichen Anforderungen zu reagieren.](./media/image2.png)

**Abbildung 2-2.** Allgemeiner Workflow für den Lebenszyklus des Docker-containeranwendungen

Alles beginnt mit dem Entwickler, mit dem Schreiben von Code in den Workflow für die innere Schleife beginnt. Die innere Schleife-Phase ist, in dem Entwickler alles definieren, die vor dem Pushvorgang von Code im Code-Repository (z. B. ein Quellcodeverwaltungssystem wie z. B. Git) erfolgt. Nachdem sie ein Commit ausgeführt wird, löst das Repository Continuous Integration (CI) und den Rest des Workflows.

Die innere Schleife besteht im Grunde typische Schritte wie "Code", "ausführen", "test" und "Debug" sowie die zusätzlichen Schritte erforderlich, direkt vor dem Ausführen der app lokal aus. Dies ist der Entwickler-Prozess zum Ausführen und Testen Sie die app als Docker-Container. Der Workflow für die innere Schleife wird in den Abschnitten erläutert werden.

Einen Schritt zum zurückgeleitet Betrachten der End-to-End-Workflow, der DevOps-Workflow ist mehr als eine Technologie oder einen Satz von Tools: Es ist eine Haltung, die kulturelle Weiterentwicklung ist erforderlich. Es ist die Mitarbeiter, Prozesse und den entsprechenden Tools der Anwendungslebensdauer, schnellere und besser vorhersagbare vornehmen. Unternehmen, die einen Workflow in Containern in der Regel übernehmen umstrukturieren ihrer Organisationen zur Darstellung von Menschen und Prozesse, die den Containern Workflow entsprechen.

Eignen, DevOps, können Teams schneller zusammen reagieren auf Wettbewerbsdruck durch Ersetzen von fehleranfällige manuelle Prozesse durch Automatisierung, die verbesserte rückverfolgbarkeit und wiederholbare Workflows ausgeführt werden. Organisationen können auch eine effizientere Verwaltung von Umgebungen und Erkennen von kosteneinsparungen mit einer Kombination aus lokalen und Cloudressourcen sowie eng integrierte Tools.

Wenn Sie Ihre DevOps-Workflow für Docker-Anwendungen zu implementieren, werden Sie sehen, dass Docker-Technologien in fast jeder Phase des Workflows, die von Ihrem Entwicklungscomputer bei der Arbeit von der Build-Test-CI-Phase, in der inneren Schleife (Code ausführen, Debuggen) vorhanden sind und, zum Schluss die Bereitstellung dieser Container in der Staging und produktionsumgebungen.

Zur Verbesserung der Qualität Methoden kann Fehler frühzeitig im Entwicklungszyklus, identifiziert die reduziert die Kosten für die Behebung Eingriffe. Einschließlich der Umgebung und Ihre Abhängigkeiten in der Abbildung und die Einführung einer Philosophie der Bereitstellung des gleichen Images über mehrere Umgebungen hinweg, Stufen Sie eine Disziplin, extrahieren Sie die umgebungsspezifische Konfiguration, sodass Bereitstellungen zuverlässiger.

Umfangreiche Daten abgerufen werden, durch die effektive Instrumentierung (Überwachung und Diagnose) bietet Einblicke in Leistungsprobleme und Benutzerverhalten, um künftige Prioritäten und Investitionen orientieren.

DevOps sollten eine Reise, die nicht in ein Ziel berücksichtigt werden. Sie sollten über entsprechend Bereichsbezogene Projekte inkrementell implementiert werden, aus dem Erfolg zu veranschaulichen, erfahren Sie, und entwickeln.

## <a name="benefits-of-devops-for-containerized-applications"></a>Vorteile von DevOps für Anwendungen in Containern

Hier sind einige der wichtigsten Vorteile, die eine solide DevOps-Workflow:

- Übermitteln Sie Software mit höherer Qualität schneller und mit bessere Einhaltung gesetzlicher Bestimmungen.

- Fördern Sie fortlaufende Verbesserungen und Korrekturen, früher und kostengünstiger.

- Erhöhen Sie die Transparenz und die Zusammenarbeit zwischen Beteiligte zum Bereitstellen und betreiben von Software.

- Die kontrollieren Sie Kosten, und die nutzen Sie bereitgestellte Ressourcen effektiver, bei gleichzeitiger Minimierung von Sicherheitsrisiken.

- Plug & play auch mit vielen Ihrer vorhandenen DevOps-Investitionen, einschließlich der Investitionen in Open-Source.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](../Microsoft-platform-tools-containerized-apps/index.md)
