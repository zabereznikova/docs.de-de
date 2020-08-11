---
title: Richtlinien für das Entwerfen von Containern
description: Lernen Sie ein grundlegendes Prinzip guten Containerdesigns kennen – nämlich dass ein Container nur einen Prozess beherbergen sollte.
ms.date: 08/06/2020
ms.openlocfilehash: 7dcf4b4af3385a2a500c5bc16a889b56fa2c25d5
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916005"
---
# <a name="common-container-design-principles"></a>Richtlinien für das Entwerfen von Containern

Vor dem Einstieg in den Entwicklungsprozess sind ein paar grundlegende Konzepte erwähnenswert, die die Art betreffen, wie Sie Container verwenden.

## <a name="container-equals-a-process"></a>Ein Container entspricht einem Prozess

Im Containermodell stellt ein Container einen einzelnen Prozess dar. Durch Definieren eines Containers als Prozessgrenze beginnen Sie, die Primitive zu erstellen, die zum Skalieren von Prozessen verwendet werden. Wenn Sie einen Docker-Container ausführen, sehen Sie eine [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#entrypoint)-Definition. Diese definiert den Prozess und die Lebensdauer des Containers. Wenn der Prozess abgeschlossen ist, endet der Lebenszyklus des Containers. Es gibt Prozesse mit langer Ausführungsdauer, wie etwa Webserver, und kurzlebige Prozesse, wie etwa Batchaufträge, die beispielsweise als Microsoft Azure-[WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/) implementiert worden sein können. Wenn der Prozess fehlschlägt, wird der Container angehalten und der Orchestrator übernimmt seinen Platz. Wenn der Orchestrator dazu angewiesen wurde, fünf Instanzen auszuführen und eine davon fehlschlägt, erstellt der Orchestrator einen weiteren Container, um den fehlgeschlagenen Prozess zu ersetzen. In einem Batchauftrag wird der Prozess mit Parametern gestartet. Wenn der Prozess abgeschlossen ist, ist die Arbeit abgeschlossen.

Es gibt Szenarien, in denen mehrere Prozesse in einem einzigen Container ausgeführt werden sollen. In einem Architekturdokument gibt es kein „niemals“, und ebenso wenig bedeutet „immer“ wirklich immer. Für Szenarien, die mehrere Prozesse erfordern, besteht ein gängiger Ansatz im Einsatz eines [Supervisors](http://supervisord.org/).

>[!div class="step-by-step"]
>[Zurück](design-docker-applications.md)
>[Weiter](monolithic-applications.md)
