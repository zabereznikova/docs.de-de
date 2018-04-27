---
title: Allgemeine Container Entwurfsprinzipien
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a289cdafc88abe8629638a84eff184829362e16
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="common-container-design-principles"></a><span data-ttu-id="7e3d8-103">Allgemeine Container Entwurfsprinzipien</span><span class="sxs-lookup"><span data-stu-id="7e3d8-103">Common container design principles</span></span>

<span data-ttu-id="7e3d8-104">Der erste in des Entwicklungsprozesses sind im Voraus einige grundlegende Konzepte in Bezug auf die Verwendung von Containern Objektzuständen.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-104">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="7e3d8-105">Container entspricht einen Prozess</span><span class="sxs-lookup"><span data-stu-id="7e3d8-105">Container equals a process</span></span>

<span data-ttu-id="7e3d8-106">Im Modell Container stellt einen Container für einen einzelnen Prozess.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-106">In the container model, a container represents a single process.</span></span> <span data-ttu-id="7e3d8-107">Durch die Definition eines Containers als eine Prozessgrenze, beginnen Sie die primitiven verwendet, um die Skalierung oder Batch-off, Prozesse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-107">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="7e3d8-108">Wenn Sie einen Docker-Container ausführen, sehen Sie ein [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) Definition.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-108">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definition.</span></span> <span data-ttu-id="7e3d8-109">Definiert den Prozess und die Lebensdauer des Containers.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-109">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="7e3d8-110">Wenn der Prozess abgeschlossen ist, wird der Lebenszyklus eines Containers beendet.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-110">When the process completes, the container life cycle ends.</span></span> <span data-ttu-id="7e3d8-111">Stehen lang andauernden Prozessen, z. B. Webserver und kurzlebige Prozessen, z. B. Batchaufträge, die als Microsoft Azure implementiert wurden [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/).</span><span class="sxs-lookup"><span data-stu-id="7e3d8-111">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="7e3d8-112">Wenn der Prozess fehlschlägt, wird der Container angehalten und der Orchestrator übernimmt seinen Platz.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-112">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="7e3d8-113">Wenn die Orchestrator angewiesen wurde, behalten Sie fünf Instanzen ausgeführt und ein Vorgang fehlschlägt, erstellt der Orchestrator einen anderen Container um den fehlgeschlagenen Vorgang zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-113">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="7e3d8-114">In einem Batchauftrag wird der Prozess mit Parametern gestartet.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-114">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="7e3d8-115">Wenn der Prozess abgeschlossen ist, ist die Arbeit abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-115">When the process completes, the work is complete.</span></span>

<span data-ttu-id="7e3d8-116">Sie möglicherweise ein Szenario, in dem mehrere Prozesse in einem einzelnen Container ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-116">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="7e3d8-117">In einem beliebigen Architekturdokument ist nie ein "nie" noch ist es immer eine "immer".</span><span class="sxs-lookup"><span data-stu-id="7e3d8-117">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="7e3d8-118">Für Szenarien mit mehreren Prozessen, ein allgemeines Muster ist die Verwendung [Supervisor](http://supervisord.org/).</span><span class="sxs-lookup"><span data-stu-id="7e3d8-118">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7e3d8-119">[Vorherigen] (Design-Docker-applications.md) [weiter] (monolithischen applications.md)</span><span class="sxs-lookup"><span data-stu-id="7e3d8-119">[Previous] (design-docker-applications.md) [Next] (monolithic-applications.md)</span></span>
