---
title: Container als Grundlage für die Zusammenarbeit mit DevOps
description: Verstehen der Schlüsselrolle von Containern bei der Optimierung von DevOps.
ms.date: 04/16/2020
ms.openlocfilehash: 83bebc92a242a5ac2906d9997b7b278f87f0db96
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507342"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Container als Grundlage für die Zusammenarbeit mit DevOps

Aufgrund der Natur von Containern und der Docker-Technologie können Entwickler ihre Software und Abhängigkeiten komfortabel mit dem IT-Betrieb und Produktionsumgebungen teilen und zugleich die typische Entschuldigung „auf meinem Computer funktioniert es“ hinter sich lassen. Containers lösen Anwendungskonflikte zwischen verschiedenen Umgebungen. Indirekt bringen Container und Docker Entwickler und IT-Ops näher zusammen, was ihnen die effektive Zusammenarbeit erleichtert. Die Einführung der Containerworkflow bietet vielen Kunden die DevOps-Kontinuität, die sie angestrebt haben, aber bisher mit weit komplexeren Konfigurationen für Release- und Buildpipelines implementieren mussten. Container vereinfachen die Build-/Test-/Bereitstellungspipelines in DevOps.

![Abbildung, die den Besitz des Lebenszyklus einer Docker-App zeigt.](./media/containers-foundation-for-devops-collaboration/persona-workloads-docker-container-lifecycle.png)

**Abbildung 2-1.** Hauptworkloads nach „Personas“ im Lebenszyklus von in Containern verpackten Docker-Anwendungen

Mit Docker-Containern sind Entwickler im Besitz des gesamten Containerinhalts (Anwendung und Dienst sowie Abhängigkeiten von Frameworks und Komponenten) und der Weise, wie Container und Dienste sich gemeinsam als aus einer Sammlung von Diensten zusammengesetzte Anwendung verhalten. Die gegenseitigen Abhängigkeiten der mehreren Container sind in einer `docker-compose.yml`-Datei definiert, die man in diesem Sinne als *Bereitstellungsmanifest* bezeichnen könnte. Inzwischen können sich IT-Betriebsteams (IT-Experten und Management) um die Verwaltung von Produktionsumgebungen, Infrastruktur, Skalierbarkeit, Überwachung und schließlich darum kümmern, dass die Leistung der Anwendungen für die Endbenutzer problemlos verfügbar ist, ohne die Inhalte der verschiedenen Container kennen zu müssen. Daher der Name „Container“, die Analogie zu Frachtcontainern aus der realen Welt ist allzu deutlich. Daher brauchen sich die Besitzer der Inhalte eines Containers nicht mit der Frage des Containerversands zu befassen, und das Speditionsunternehmen transportiert einen Container von seinem Ursprungsort an seinen Zielort, ohne die Inhalte des Containers zu kennen oder sich dafür zu interessieren. In ähnlicher Weise können Entwickler die Inhalte in einem Docker-Container erstellen und besitzen, ohne sich ihrerseits mit den Transportmechanismen zu befassen.

In der linken Säule von Abbildung 2–1 erstellen Entwickler Code lokal in Docker-Containern mithilfe von Docker für Windows oder Mac und führen ihn aus. Sie definieren die Betriebssystemumgebung für den Code mithilfe eines Dockerfiles, das das auszuführende Basisbetriebssystem sowie die Buildschritte zum Erstellen des Codes in einem Docker-Image angibt. Die Entwickler definieren, wie die Zusammenarbeit eines oder mehrerer Images erfolgt, und verwenden dazu das bereits erwähnte `docker-compose.yml`-Bereitstellungsmanifest. Mit dem Abschluss der lokalen Entwicklung laden sie den Anwendungscode und die Docker-Konfigurationsdateien in das Coderepository ihrer Wahl (d.h. das Git-Repository) hoch.

Die DevOps-Säule definiert die Continuous Integration-Erstellungspipelines (CI) unter Verwendung des im Coderepository bereitgestellten Dockerfiles. Das CI-System ruft die Container-Basisimages aus der gewählten Docker-Registrierung ab und erstellt die benutzerdefinierten Docker-Images für die Anwendung. Die Images werden anschließend überprüft und in die Docker-Registrierung übertragen, die für die Bereitstellung in mehreren Umgebungen verwendet wird.

In der rechten Säule verwalten Betriebsteams Anwendungen und Infrastruktur in der Produktion, während sie Umgebung und Anwendungen überwachen, sodass sie dem Entwicklungsteam Feedback und Erkenntnisse über mögliche Verbesserungen der Anwendung geben können. Container-Apps werden in der Regel mithilfe von Containerorchestratoren wie [Kubernetes](https://kubernetes.io/) in der Produktion ausgeführt, wobei in der Regel [Helm-Diagramme](https://helm.sh/) zum Konfigurieren von Bereitstellungseinheiten anstelle von docker-compose-Dateien verwendet werden.

Die beiden Teams arbeiten mithilfe einer Grundplattform (Docker-Container) zusammen, die eine Separation of Concerns als Vertrag zur Verfügung stellt, während sie die Zusammenarbeit der beiden Teams im Anwendungslebenszyklus erheblich verbessert. Die Entwickler besitzen die Inhalte der Container, ihre Betriebsumgebung und die Abhängigkeiten zwischen Containern, während die Betriebsteams die erstellten Inhalte zusammen mit dem Manifest an sich nehmen und sie in ihrem Orchestrierungssystem ausführen.

## <a name="challenges-in-application-life-cycle-when-using-docker"></a>Herausforderungen im Lebenszyklus von Anwendungen beim Einsatz von Docker.

Es gibt viele Gründe, warum die Anzahl der containerisierten Anwendungen in den kommenden Jahren steigen wird, und einer dieser Gründe ist die Erstellung von Anwendungen, die auf Microservices basieren.

Während der letzten 15 Jahre war die Nutzung von Webdiensten die Grundlage von Tausenden von Anwendungen, und wahrscheinlich werden wir in einigen Jahren die gleiche Situation im Hinblick auf Microservice-basierten Anwendungen vorfinden, die in Docker-Containern ausgeführt werden.

Es ist darüber hinaus erwähnenswert, dass Sie Docker-Container auch für monolithische Anwendungen verwenden und trotzdem den größten Teil der Vorteile von Docker nutzen können. Container richten sich nicht nur auf Microservices.

Die Verwendung von Containerisierung mit Docker und Microservices hat zu neuen Herausforderungen im Entwicklungsprozess Ihrer Organisationen geführt und daher benötigen Sie eine solide Strategie zum Verwalten vieler Container und Microservices, die auf Produktionssystemen ausgeführt werden. Schließlich können beim Unternehmenseinsatz Hunderte oder Tausende von Containern/Instanzen in der Produktion ausgeführt werden.

Durch diese Herausforderungen entstehen neue Anforderungen für den Einsatz von DevOps-Tools, sodass Sie in Ihren DevOps-Aktivitäten neue Prozesse definieren und Antworten auf diese Art von Fragen finden müssen:

- Welche Tools kann ich für die Entwicklung, für CI/CD, Management und Betrieb verwenden?

- Wie kann mein Unternehmen mit Fehlern in Containern umgehen, die in der Produktion eingesetzt werden?

- Wie können wir Teile unserer Software in der Produktion mit minimalen Ausfallzeiten ändern?

- Wie können wir skalieren, und wie können wir unser Produktionssystem überwachen?

- Wie können wir Test und Bereitstellung von Containern in unsere Releasepipeline einbeziehen?

- Wie können wir Open Source-Tools/-Plattformen für Container in Microsoft Azure verwenden?

Wenn Sie alle diese Fragen beantworten, sind Sie besser darauf vorbereitet, Ihre Anwendungen (vorhandene oder neue) in Docker-Container zu verschieben.

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Einführung in eine allgemeine Anwendungslebenszyklus-Workflow mit Docker

Abbildung 2–2 stellt einen detaillierteren Workflow für einen Docker-Anwendungslebenszyklus dar, in dieser Instanz mit dem Schwerpunkt auf bestimmten DevOps-Aktivitäten und -Ressourcen.

![Abbildung, die den generischen End-to-End-Lebenszyklus einer Docker-App zeigt.](./media/containers-foundation-for-devops-collaboration/generic-end-to-enddpcker-app-life-cycle.png)

**Abbildung 2–2.** Allgemeiner Workflow für den Lebenszyklus von in Containern verpackten Docker-Anwendungen

Alles beginnt mit dem Entwickler, der in der Workflow der inneren Schleife mit dem Schreiben von Code beginnt. In der Phase der inneren Schleife definieren Entwickler alles, was geschieht, bevor sie den Code in das Coderepository übertragen (beispielsweise ein Quellcodeverwaltungssystem wie Git). Nach dem Commit löst das Repository Continuous Integration (CI) und den Rest der Workflow aus.

Die innere Schleife besteht im Grunde genommen aus typischen Schritten wie „Codeerstellung“, „Ausführen“, „Testen“ und Debuggen, zuzüglich der zusätzlichen Schritte, die vor der lokalen Ausführung der App erforderlich sind. Dies ist der Prozess des Entwicklers zum Ausführen und Testen der App als Docker-Container. Die Workflow der inneren Schleife wird in den folgenden Abschnitten erläutert.

Wenn wir einen Schritt zurücktreten, um die Workflow im Ganzen zu betrachten, erweist sich die DevOps-Workflow als mehr als eine Technologie oder ein Toolset: Es ist eine Geisteshaltung, für die eine kulturelle Weiterentwicklung erforderlich ist. Es geht um Personen, Prozesse und die geeigneten Tools, um Ihren Anwendungslebenszyklus schneller und besser vorhersagbar zu gestalten. Unternehmen, die einen Workflow mit Containern einführen, führen normalerweise eine Umstrukturierung ihrer Organisationen durch, um Personen und Prozesse an die Workflow mit Containern anzupassen.

Das Praktizieren von DevOps kann Teams helfen, gemeinsam schneller auf Wettbewerbsdruck zu reagieren, indem sie fehleranfällige manuelle Prozesse durch Automatisierung ersetzen, wodurch sich verbesserte Nachverfolgbarkeit und wiederholbare Workflows ergeben. Organisationen können darüber hinaus mit einer Kombination aus lokalen und Cloudressourcen sowie eng integrierten Tools Umgebungen effizienter verwalten und Kosteneinsparungen realisieren.

Beim Implementieren Ihrer DevOps-Workflow für Docker-Anwendungen werden Sie feststellen, dass Docker-Technologien in nahezu jeder Phase der Workflow präsent sind, beginnend mit Ihrer Entwicklungsbox bei der Arbeit in der inneren Schleife (Codeerstellung, Ausführen, Debuggen), der Build-Test-CI-Phase und schließlich der Bereitstellung der Container in den Staging- und Produktionsumgebungen.

Die Verbesserung der Qualitätspraktiken hilft, Fehler frühzeitig im Entwicklungszyklus zu erkennen, wodurch sich die Kosten zu ihrer Behebung verringern. Durch Einschließen von Umgebung und Abhängigkeiten in das Image und die Einführung einer Philosophie, das gleiche Image übergreifend in mehreren Umgebungen einzusetzen, fördern Sie einen Habitus, die umgebungsspezifischen Konfigurationen zu extrahieren, wodurch Bereitstellungen an Zuverlässigkeit gewinnen.

Aussagekräftige Daten, die durch effektive Instrumentierung (Überwachung und Diagnose) erhalten werden, bieten Einsicht in Leistungsprobleme und Benutzerverhalten, um die Richtung zukünftiger Prioritäten und Investitionen zu bestimmen.

DevOps sollte als ein Weg angesehen werden, nicht als ein Zielort. Es sollte inkrementell durch Projekte mit passendem Umfang implementiert werden, die Ihnen Erfolge, Erkenntnisse und Weiterentwicklung erbringen.

## <a name="benefits-of-devops-for-containerized-applications"></a>Vorteile von DevOps für Anwendungen in Containern

Dies sind einige der wichtigsten Vorteile, die sich durch eine solide DevOps-Workflow ergeben:

- Schnelleres Ausliefern besserer Software mit besserer Compliance

- Frühzeitige und ökonomisch sinnvollere Förderung von fortlaufenden Verbesserungen und Anpassungen

- Bessere Transparenz und Zusammenarbeit von Projektbeteiligten, die an Herstellung und Betrieb von Software beteiligt sind

- Kostenkontrolle und effektiverer Einsatz der bereitgestellten Ressourcen bei gleichzeitiger Minimierung von Sicherheitsrisiken.

- Plug-and-Play-Bereitschaft mit vielen Ihrer bereits getätigten DevOps-Investitionen, einschließlich Investitionen in Open-Source.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](../Microsoft-platform-tools-containerized-apps/index.md)
