---
title: SOA-Anwendungen
description: Beachten Sie, dass Container auch eine nützliche Bereitstellungsoption für SOA-Anwendungen sein können.
ms.date: 02/15/2019
ms.openlocfilehash: f8619cb50a7d90b911db9ff2c8ef37c3c5fde210
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738384"
---
# <a name="service-oriented-applications"></a>Dienstorientierte Anwendungen

Der Begriff dienstorientierte Architektur (Service-Oriented Architecture, SOA) hat eine inflationäre Verwendung erfahren und daher verschiedene Bedeutungen entwickelt. Der gemeinsame Nenner der Bedeutung von „serviceorientierter Architektur“ ist jedoch, dass die Architektur Ihrer Anwendung strukturiert wird, indem sie in mehrere Dienste zerlegt wird (meistens HTTP-Dienste), die als unterschiedliche Typen klassifiziert werden können, z.B. als Subsysteme oder in anderen Fällen als Schichten.

Heutzutage können Sie diese Dienste als Docker-Container bereitstellen. Dadurch werden Bereitstellungsprobleme gelöst, da alle Abhängigkeiten im Containerimage enthalten sind. Beim horizontalen Skalieren von SOAs können Sie sich jedoch Herausforderungen gegenüber sehen, wenn Sie die Bereitstellung auf der Grundlage einzelner Instanzen vornehmen. Diese Herausforderung kann mithilfe von Docker-Clustersoftware auf einem Orchestrator gemeistert werden. Wir betrachten Orchestratoren im nächsten Abschnitt ausführlicher, in dem wir Ansätze für Microservices untersuchen.

Für herkömmliche serviceorientierte Architekturen und erweiterte Microservicesarchitekturen sind Docker-Container nützlich, jedoch nicht erforderlich.

Unterm Strich sind die Clusterlösungen mit Containern sowohl für eine traditionelle SOA-Architektur als auch für eine fortschrittlichere Microservicearchitektur nützlich, bei der jeder Microservice sein Datenmodell besitzt. Und dank mehrerer Datenbanken können Sie auch die Datenschicht horizontal skalieren, statt mit monolithischen Datenbanken zu arbeiten, die von den SOA-Diensten gemeinsam verwendet werden. Bei der Diskussion über das Aufteilen der Daten geht es allerdings ausschließlich um Architektur und Entwurf.

>[!div class="step-by-step"]
>[Zurück](state-and-data-in-docker-applications.md)
>[Weiter](orchestrate-high-scalability-availability.md)
