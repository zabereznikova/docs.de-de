---
title: Richtlinien für das Entwerfen von Containern
description: Erfahren Sie, ein fundamentales Prinzip der gute Container entwerfen, ist es, dass ein Container nur ein Prozess hosten soll.
ms.date: 02/15/2019
ms.openlocfilehash: 69f3ff6c9303f0c4082695d861a8c90031295b6a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644797"
---
# <a name="common-container-design-principles"></a>Richtlinien für das Entwerfen von Containern

Jetzt erhalten Sie in den Entwicklungsprozess gibt es einige grundlegende Konzepte in Bezug auf die Verwendung von Containern erwähnenswert.

## <a name="container-equals-a-process"></a>Container entspricht einen Prozess

Im containermodell stellt einen Container für ein einzelner Prozess. Definieren Sie einen Container als Prozessgrenze, beginnen Sie die primitiven verwendet, um die Skalierung oder Batch-off, Prozesse zu erstellen. Wenn Sie einen Docker-Container ausführen, sehen Sie ein [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) Definition. Definiert den Prozess und die Lebensdauer des Containers. Wenn der Prozess abgeschlossen ist, endet die Container-Lebenszyklus. Lang andauernde Prozesse, z. B. Webserver und kurzlebige Prozesse wie Batchaufträge, die als Microsoft Azure implementiert wurden möglicherweise [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/). Wenn der Prozess fehlschlägt, wird der Container angehalten und der Orchestrator übernimmt seinen Platz. Wenn der Orchestrator angewiesen wurde, fünf Instanzen auszuführen, und eine davon fehlschlägt, erstellt der Orchestrator einen anderen Container, um den fehlgeschlagenen Prozess zu ersetzen. In einem Batchauftrag wird der Prozess mit Parametern gestartet. Wenn der Prozess abgeschlossen ist, ist die Arbeit abgeschlossen.

Sie möglicherweise ein Szenario, in dem mehrere Prozesse in einem einzelnen Container ausgeführt werden soll. Architektur Dokumente, es ist nie ein "never" noch ist es immer eine "immer". Für Szenarien mit mehreren Prozessen, ein allgemeines Muster ist die Verwendung [Supervisor](http://supervisord.org/).

>[!div class="step-by-step"]
>[Zurück](design-docker-applications.md)
>[Weiter](monolithic-applications.md)
