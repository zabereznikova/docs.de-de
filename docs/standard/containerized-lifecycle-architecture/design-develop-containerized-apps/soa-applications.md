---
title: SOA-Anwendungen
description: Beachten Sie, dass der Container kann auch nützlich für eine Bereitstellungsoption SOA-Anwendungen sein.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: ee71873ac15246f979fd2b08d92280ba797ff6ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795400"
---
# <a name="service-oriented-applications"></a>Dienstorientierte Anwendungen

Dienstorientierte Architektur (SOA) wurde ein hoher Auslastung Ausdruck, der viele verschiedene Dinge an andere Personen gedacht. Der gemeinsame Nenner, SOA bedeutet jedoch, dass Sie strukturieren die Architektur Ihrer Anwendung durch zerlegen ihn in mehrere Dienste (am häufigsten als HTTP-Dienste), die in verschiedenen wie Subsysteme oder in anderen Fällen als Ebenen klassifiziert werden können.

Heute können Sie diese Dienste als Docker-Container bereitstellen, die Bereitstellung-bezogene Probleme zu lösen, da alle Abhängigkeiten im containerimage enthalten sind. Jedoch wenn Sie zu SOAs skalieren müssen, können Probleme auftreten, wenn Sie basierend auf einzelne Instanzen bereitstellen. Diese Aufforderung kann mit Docker-clusteringsoftware oder ein Orchestrator behandelt werden. Betrachten wir orchestratoren ausführlicher im nächsten Abschnitt, wenn, Ansätze für Microservices untersucht.

Für herkömmliche serviceorientierte Architekturen und erweiterte Microservicesarchitekturen sind Docker-Container nützlich, jedoch nicht erforderlich.

Am Ende des Tages eignen sich die Container-clustering-Lösungen für beide eine konventionelle SOA-Architektur und für eine erweiterte Microservices-Architektur, die in der besitzt jeder Microservice auf das Datenmodell. Und Dank mehrere Datenbanken, außerdem können Sie horizontal hochskalieren der Datenebene anstelle der Arbeit mit monolithischen Datenbanken, die von der SOA-Dienste gemeinsam verwendet werden. Allerdings ist die Diskussion über die Daten aufgeteilt werden, ausschließlich über Architektur und Entwurf.

>[!div class="step-by-step"]
>[Zurück](state-and-data-in-docker-applications.md)
>[Weiter](orchestrate-high-scalability-availability.md)
