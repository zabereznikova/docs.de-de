---
title: Ausführen von zusammengesetzten und auf Microservices basierende Anwendungen in produktionsumgebungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 18e6cb1fb5f496b66c89cb8e009a67894b8a76ad
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845299"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Ausführen von zusammengesetzten und auf Microservices basierende Anwendungen in produktionsumgebungen

Aus mehreren microservices bestehende Anwendungen müssen in der Orchestrator-Cluster, um die Komplexität der Bereitstellung und Umsetzung aus Sicht eines IT bereitgestellt werden. Ohne ein orchestratorcluster wäre es sehr schwierig, bereitstellen und horizontale Skalierung eine komplexe Microservices-Anwendung.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Einführung in orchestratoren, Planer und Container-Clustern

Weiter oben in diesem e-Book vorgestellt *Cluster* und *Zeitplanungsmodule* als Teil der Diskussion auf Softwarearchitektur und-Entwicklung. Beispiele für Docker-Cluster sind Docker Swarm und Mesosphere Datacenter Operating System (DC/OS). Beide können als Teil der Infrastruktur von Microsoft Azure Container Service ausführen.

Wenn Anwendungen über mehrere Hostsysteme hinweg horizontal sind, wird die Möglichkeit zum Verwalten von jedem Hostsystem und abstrahieren die Komplexität der zugrunde liegenden Plattform attraktiv. Das ist genau das, was orchestratoren und Planer bereitstellen. Werfen wir einen kurzen Blick auf die sie hier:

- **Planer.** "Planung" bezieht sich auf die Fähigkeit, ein Administrator eine Dienstdatei auf einem Hostsystem zu laden, die wie einen bestimmten Container ausgeführt wird. Starten Container in einem Docker-Cluster ist wie das Planen bekannt sein. Obwohl planen, die mit dem bestimmten Laden der Definition des Diensts in gewisser Hinsicht allgemeineren bezieht sich dienen Zeitplanungsmodule Hooks für Host in der Init-System zum Verwalten von Diensten in beliebige benötigte Kapazität.

   Ein clusterplaner ist, mehrere Ziele: die Ressourcen des Clusters effizient zu verwenden, arbeiten mit benutzerdefinierten platzierungseinschränkungen, Planen Anwendungen schnell nicht im Status "Ausstehend", lassen müssen ein Maß an "faire", wird auf Fehler, robuste und immer verfügbar sein.

- **Orchestrierung**. Plattformen erweitern Life-Cycle Management-Funktionen für komplexe Workloads mit mehreren Containern auf einem Cluster mit Hosts bereitgestellt werden. Durch das abstrahieren die Hostinfrastruktur, Benutzern orchestrierungstools eine Möglichkeit, den gesamten Cluster als ein Bereitstellungsziel aus einzelnen zu behandeln.

   Der Prozess der Orchestrierung umfasst Tools und eine Plattform, die alle Aspekte der Verwaltung von Anwendungen von anfängliche Platzierung oder Bereitstellung pro Container automatisiert werden kann; zu anderen Hosts je nach Zustand oder die Leistung des Hosts Container verschieben versionsverwaltung und parallele Updates und Funktionen, die Skalierung und das Failover unterstützen die Systemüberwachung; und vieles mehr.

   Orchestrierung ist ein weitgefasster Begriff, der auf den Container zu planen, Clusterverwaltung und möglicherweise die Bereitstellung von weitere Hosts verweist.

Die Funktionen von orchestratoren und Planer sind sehr komplex, entwickeln und Erstellen von Grund auf neu, und daher in der Regel möchten stellen Verwendung Orchestrierung Lösungen, die von Lieferanten angeboten werden.


>[!div class="step-by-step"]
[Zurück](index.md)
[Weiter](manage-production-docker-environments.md)
