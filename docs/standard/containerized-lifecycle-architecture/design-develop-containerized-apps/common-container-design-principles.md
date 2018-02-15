---
title: Allgemeine Container Entwurfsprinzipien
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a9cd569a931824c4fab060b99265ea9e3ca75129
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="common-container-design-principles"></a>Allgemeine Container Entwurfsprinzipien

Der erste in des Entwicklungsprozesses sind im Voraus einige grundlegende Konzepte in Bezug auf die Verwendung von Containern Objektzuständen.

## <a name="container-equals-a-process"></a>Container entspricht einen Prozess

Im Modell Container stellt einen Container für einen einzelnen Prozess. Durch die Definition eines Containers als eine Prozessgrenze, beginnen Sie die primitiven verwendet, um die Skalierung oder Batch-off, Prozesse zu erstellen. Wenn Sie einen Docker-Container ausführen, sehen Sie ein [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) Definition. Definiert den Prozess und die Lebensdauer des Containers. Wenn der Prozess abgeschlossen ist, wird der Lebenszyklus eines Containers beendet. Stehen lang andauernden Prozessen, z. B. Webserver und kurzlebige Prozessen, z. B. Batchaufträge, die als Microsoft Azure implementiert wurden [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/). Wenn der Prozess fehlschlägt, wird der Container angehalten und der Orchestrator übernimmt seinen Platz. Wenn die Orchestrator angewiesen wurde, behalten Sie fünf Instanzen ausgeführt und ein Vorgang fehlschlägt, erstellt der Orchestrator einen anderen Container um den fehlgeschlagenen Vorgang zu ersetzen. In einem Batchauftrag wird der Prozess mit Parametern gestartet. Wenn der Prozess abgeschlossen ist, ist die Arbeit abgeschlossen.

Sie möglicherweise ein Szenario, in dem mehrere Prozesse in einem einzelnen Container ausgeführt werden soll. In einem beliebigen Architekturdokument ist nie ein "nie" noch ist es immer eine "immer". Für Szenarien mit mehreren Prozessen, ein allgemeines Muster ist die Verwendung [Supervisor](http://supervisord.org/).


>[!div class="step-by-step"]
[Vorherigen] (Design-Docker-applications.md) [weiter] (monolithischen applications.md)
