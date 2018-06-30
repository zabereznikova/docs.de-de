---
title: SOA-Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 276071a5d55015f2feecc27020ad614684907b4c
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105210"
---
# <a name="soa-applications"></a>SOA-Anwendungen

SOA wurde ein Überbelastung Begriff und so viele verschiedene Bedeutungen für verschiedene Benutzer vorgesehen. Aber zumindest und als gemeinsame Nenner, SOA oder dienstausrichtung, Mittelwert Struktur die Architektur der Anwendung durch zerlegen es in mehreren Diensten (meist als HTTP-Dienste), die in verschiedenen Arten klassifiziert werden können Subsysteme oder in anderen Fällen wie leisten.

Heute können Sie diese Dienste als Docker-Containern bereitstellen, löst die Probleme in Bezug auf Bereitstellung, da alle Abhängigkeiten in Container-Abbild enthalten sind. Jedoch wenn dienstorientierter Architekturen mit horizontaler Skalierung Sie müssen, möglicherweise Probleme auftreten, wenn Sie basierend auf einzelne Instanzen bereitstellen. Dies ist, bei denen ein clustering-Software oder Orchestrator Docker Sie beitragen. Betrachten wir dies im nächsten Abschnitt ausführlich beim Untersuchen wir Microservices Ansätze.

Am Ende des Tages eignen sich die Container-clustering-Lösungen für beide eine herkömmliche SOA-Architektur oder für eine erweiterte Microservices-Architektur, in der jede Microservice seine Datenmodell besitzt. Und Dank mehrere Datenbanken Sie auch können mit horizontaler Skalierung die Datenebene statt arbeiten mit monolithisch Datenbanken, die von der SOA-Diensten gemeinsam genutzt. Ist jedoch die Erläuterung zum Teilen der Daten ausschließlich über die Architektur und Entwurf.


>[!div class="step-by-step"]
[Zurück](state-and-data-in-docker-applications.md)
[Weiter](orchestrate-high-scalability-availability.md)
