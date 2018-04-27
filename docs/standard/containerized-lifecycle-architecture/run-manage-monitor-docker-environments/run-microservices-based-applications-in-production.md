---
title: Führen Sie in produktionsumgebungen verfasst und Microservices-basierte Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1ba71a02c1f800fd65462b0df9a435af87c9a37f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Führen Sie in produktionsumgebungen verfasst und Microservices-basierte Anwendungen

Anwendungen aus, das mehrere Microservices in Orchestrator-Clustern, um die Komplexität der Bereitstellung und aus Sicht eines IT realisierbar bereitgestellt werden müssen. Ohne eine Orchestrator-Clusters wäre es sehr schwierig, bereitstellen und die horizontale Skalierung einer komplexen Microservices-Anwendung.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Einführung in Orchestrators, Planern und Container-Clustern

Weiter oben in diesem e-Book eingeführt *Cluster* und *Zeitplanungsmodule* als Teil der detaillierte Informationen zu Software-Architektur und Entwicklung. Beispiele für Docker-Cluster sind Docker Containerhostclustern und Mesosphere Datacenter-Betriebssystem (DC/OS). Beide Optionen können als Teil von Microsoft Azure-Containerdienst bereitgestellten Infrastruktur ausführen.

Wenn Anwendungen auf mehreren Hosts Systemen skalierten sind, wird die Fähigkeit zum Verwalten von jedem Hostsystem und Abstraktion für die Komplexität der zugrunde liegenden Plattform attraktiv. Genau ist, was Orchestrators und Planer angeben. Werfen wir einen kurzen Blick auf die sie hier:

-   **Zeitplanungsmodule *** *"Planung" bezieht sich auf die Möglichkeit für einen Administrator, um eine Datei auf einem Hostsystem zu laden, die zum Ausführen von eines bestimmten Containers herstellt. Starten der Container in einem Cluster Docker ist als Planung bezeichnet werden. Obwohl planen, die auf den bestimmten Vorgang des Ladens der Dienstdefinition in einer allgemeineren Sinne bezieht sich sind Planer für Berichterstellungsprozess mit Init-System zum Verwalten von Diensten in die benötigte Kapazität des Hosts verantwortlich.

Ein Cluster Zeitplanungsmodul verfügt über mehrere Ziele: Effizientes Verwenden von Clusterressourcen, arbeiten mit vom Benutzer anzugebende platzierungsbeschränkungen, Planen von Anwendungen schnell, um sie nicht in einen Status "Ausstehend" zu belassen, müssen ein Maß "Ausgewogenheit," robust sind, um Fehler, wird und immer verfügbar sein.

-   **Orchestrierung *** *Plattformen ausdehnen Lebenszyklus komplexer, multicontainer Arbeitslasten auf einem Cluster mit Hosts bereitgestellt. Durch die Hostinfrastruktur werden so abstrahiert, bieten Orchestrierung Tools Benutzern eine Möglichkeit, den gesamten Cluster als ein einzelnes Bereitstellungsziel zu behandeln.

Der Prozess der Orchestrierung umfasst Tools und eine Plattform, die alle Aspekte der anwendungsverwaltung aus der ersten Platzierung oder Bereitstellung pro Container automatisiert werden kann; Verschieben von Containern auf verschiedenen Hosts je nach Zustand oder die Leistung des Hosts; versionsverwaltung und parallelen Updates und Integritätsüberwachung von Funktionen, die Skalierung und das Failover zu unterstützen; und vieles mehr.

Orchestrierung ist ein breites Begriff aus, auf den Container zu planen, Clusterverwaltung und möglicherweise die Bereitstellung zusätzlicher Hosts verweist.

Die Funktionen von Orchestrators und Planer sind sehr komplex zu entwickeln und Erstellen von Grund auf neu, und daher in der Regel sollten stellen mithilfe der Orchestrierung Lösungen von Lieferanten angeboten.


>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (Verwalten von-Production-Docker-environments.md)
