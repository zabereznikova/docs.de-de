---
title: Containerdesign
description: Erfahren Sie, ein fundamentales Prinzip der gute Container entwerfen, ist es, dass ein Container nur ein Prozess hosten soll.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: ce51eb296591490fba2d37e753be7881a55ea556
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220334"
---
# <a name="common-container-design-principles"></a>Containerdesign

Jetzt erhalten Sie in den Entwicklungsprozess gibt es einige grundlegende Konzepte in Bezug auf die Verwendung von Containern erwähnenswert.

## <a name="container-equals-a-process"></a>Container entspricht einen Prozess

Im containermodell stellt einen Container für ein einzelner Prozess. Definieren Sie einen Container als Prozessgrenze, beginnen Sie die primitiven verwendet, um die Skalierung oder Batch-off, Prozesse zu erstellen. Wenn Sie einen Docker-Container ausführen, sehen Sie ein [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) Definition. Definiert den Prozess und die Lebensdauer des Containers. Wenn der Prozess abgeschlossen ist, endet der Lebenszyklus des Containers. Lang andauernde Prozesse, z. B. Webserver und kurzlebige Prozesse wie Batchaufträge, die als Microsoft Azure implementiert wurden möglicherweise [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/). Wenn der Prozess fehlschlägt, wird der Container angehalten und der Orchestrator übernimmt seinen Platz. Wenn der Orchestrator angewiesen wurde, fünf Instanzen auszuführen, und eine davon fehlschlägt, erstellt der Orchestrator einen anderen Container, um den fehlgeschlagenen Prozess zu ersetzen. In einem Batchauftrag wird der Prozess mit Parametern gestartet. Wenn der Prozess abgeschlossen ist, ist die Arbeit abgeschlossen.

Sie möglicherweise ein Szenario, in dem mehrere Prozesse in einem einzelnen Container ausgeführt werden soll. Architektur Dokumente, es ist nie ein "never" noch ist es immer eine "immer". Für Szenarien mit mehreren Prozessen, ein allgemeines Muster ist die Verwendung [Supervisor](http://supervisord.org/).

>[!div class="step-by-step"]
>[Zurück](design-docker-applications.md)
>[Weiter](monolithic-applications.md)