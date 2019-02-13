---
title: SOA-Anwendungen
description: Beachten Sie, dass der Container kann auch nützlich für eine Bereitstellungsoption SOA-Anwendungen sein.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 4fd39e075c5730cf7fddb0138cdb5267a914c91f
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221263"
---
# <a name="soa-applications"></a>SOA-Anwendungen

SOA wurde ein hoher Auslastung Begriff und daher so viele verschiedene Bedeutungen für verschiedene Benutzer. Aber zumindest und als gemeinsame Nenner, d. h. einer SOA oder die Dienstorientierung, Mean Struktur der Architektur Ihrer Anwendung durch zerlegen es in mehrere Dienste (am häufigsten als HTTP-Dienste), die in verschiedenen Arten klassifiziert werden können Subsysteme Alternativ können Sie auch in anderen Fällen als Ebenen.

Heute können Sie diese Dienste als Docker-Container bereitstellen, die Bereitstellung-bezogene Probleme gelöst, da alle Abhängigkeiten in das Container-Abbild enthalten sind. Jedoch wenn Sie sich zur horizontalen hochskalierung SOAs müssen, können Probleme auftreten, wenn Sie basierend auf einzelne Instanzen bereitstellen. Dies ist in eine Docker-clusteringsoftware oder Orchestrator Sie unterstützen. Betrachten wir dies im nächsten Abschnitt ausführlicher beim Untersuchen wir microservicesansätzen.

Am Ende des Tages eignen sich die Container-clustering-Lösungen für beide eine konventionelle SOA-Architektur oder für eine erweiterte Microservices-Architektur, die in der besitzt jeder Microservice auf das Datenmodell. Und Dank mehrere Datenbanken, Sie auch können horizontale Skalierung die Datenebene anstelle der Arbeit mit monolithischen Datenbanken, die von der SOA-Dienste gemeinsam verwendet werden. Allerdings ist die Diskussion über die Daten aufgeteilt werden, ausschließlich über Architektur und Entwurf.

>[!div class="step-by-step"]
>[Zurück](state-and-data-in-docker-applications.md)
>[Weiter](orchestrate-high-scalability-availability.md)