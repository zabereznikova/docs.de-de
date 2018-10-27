---
title: Containerdesign
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3af174279e8b6f56a10413817b05ef68cfcabea5
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50049086"
---
# <a name="common-container-design-principles"></a>Containerdesign

Jetzt erhalten Sie in den Entwicklungsprozess gibt es einige grundlegende Konzepte in Bezug auf die Verwendung von Containern erwähnenswert.

## <a name="container-equals-a-process"></a>Container entspricht einen Prozess

Im containermodell stellt einen Container für ein einzelner Prozess. Definieren Sie einen Container als Prozessgrenze, beginnen Sie die primitiven verwendet, um die Skalierung oder Batch-off, Prozesse zu erstellen. Wenn Sie einen Docker-Container ausführen, sehen Sie ein [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) Definition. Definiert den Prozess und die Lebensdauer des Containers. Wenn der Prozess abgeschlossen ist, endet der Lebenszyklus des Containers. Lang andauernde Prozesse, z. B. Webserver und kurzlebige Prozesse wie Batchaufträge, die als Microsoft Azure implementiert wurden möglicherweise [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/). Wenn der Prozess fehlschlägt, wird der Container angehalten und der Orchestrator übernimmt seinen Platz. Wenn der Orchestrator angewiesen wurde, fünf Instanzen auszuführen, und eine davon fehlschlägt, erstellt der Orchestrator einen anderen Container, um den fehlgeschlagenen Prozess zu ersetzen. In einem Batchauftrag wird der Prozess mit Parametern gestartet. Wenn der Prozess abgeschlossen ist, ist die Arbeit abgeschlossen.

Sie möglicherweise ein Szenario, in dem mehrere Prozesse in einem einzelnen Container ausgeführt werden soll. Architektur Dokumente, es ist nie ein "never" noch ist es immer eine "immer". Für Szenarien mit mehreren Prozessen, ein allgemeines Muster ist die Verwendung [Supervisor](http://supervisord.org/).


>[!div class="step-by-step"]
[Zurück](design-docker-applications.md)
[Weiter](monolithic-applications.md)
