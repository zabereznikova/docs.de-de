---
title: SOA-Anwendungen
description: Beachten Sie, dass Container auch eine nützliche Bereitstellungsoption für SOA-Anwendungen sein können.
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672357"
---
# <a name="service-oriented-applications"></a>Dienstorientierte Anwendungen

Der Begriff dienstorientierte Architektur (Service-Oriented Architecture, SOA) hat eine inflationäre Verwendung erfahren und daher verschiedene Bedeutungen entwickelt. Der gemeinsame Nenner der Bedeutung von „serviceorientierter Architektur“ ist jedoch, dass die Architektur Ihrer Anwendung strukturiert wird, indem sie in mehrere Dienste zerlegt wird (meistens HTTP-Dienste), die als unterschiedliche Typen klassifiziert werden können, z.B. als Subsysteme oder in anderen Fällen als Schichten.

Heutzutage können Sie diese Dienste als Docker-Container bereitstellen. Dadurch werden Bereitstellungsprobleme gelöst, da alle Abhängigkeiten im Containerimage enthalten sind. Beim horizontalen Skalieren von SOAs können Sie sich jedoch Herausforderungen gegenüber sehen, wenn Sie die Bereitstellung auf der Grundlage einzelner Instanzen vornehmen. Diese Herausforderung kann mithilfe von Docker-Clustersoftware auf einem Orchestrator gemeistert werden. Wir betrachten Orchestratoren im nächsten Abschnitt ausführlicher, in dem wir Ansätze für Microservices untersuchen.

Für herkömmliche serviceorientierte Architekturen und erweiterte Microservicesarchitekturen sind Docker-Container nützlich, jedoch nicht erforderlich.

Unterm Strich sind die Clusterlösungen mit Containern sowohl für eine traditionelle SOA-Architektur als auch für eine fortschrittlichere Microservicearchitektur nützlich, bei der jeder Microservice sein Datenmodell besitzt. Und dank mehrerer Datenbanken können Sie auch die Datenschicht horizontal skalieren, statt mit monolithischen Datenbanken zu arbeiten, die von den SOA-Diensten gemeinsam verwendet werden. Bei der Diskussion über das Aufteilen der Daten geht es allerdings ausschließlich um Architektur und Entwurf.

>[!div class="step-by-step"]
>[Zurück](state-and-data-in-docker-applications.md)
>[Weiter](orchestrate-high-scalability-availability.md)
