---
title: Parallel ForEach (eingeschränkt)
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 340e4ff154b63221ec911c872a1154bdb672cf8c
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715917"
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="2bfa2-102">Parallel ForEach (eingeschränkt)</span><span class="sxs-lookup"><span data-stu-id="2bfa2-102">Throttled Parallel ForEach</span></span>

<span data-ttu-id="2bfa2-103">Die `ThrottleParallelForEach`-Aktivität ist der <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität ähnlich, mit der einen Ausnahme, dass sie das Einstellen eines Parallelitätsfaktors zur Einschränkung der Anzahl gleichzeitiger auszuführender Verzweigungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-103">The `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="2bfa2-104">Die `ThrottleParallelForEach`-Aktivität wird von <xref:System.Activities.NativeActivity> abgeleitet, da sie andere Aktivitäten (die untergeordneten Aktivitäten) planen muss und darauf nur über die <xref:System.Activities.NativeActivityContext>-Klasse zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>

## <a name="projects"></a><span data-ttu-id="2bfa2-105">Projekte</span><span class="sxs-lookup"><span data-stu-id="2bfa2-105">Projects</span></span>

|<span data-ttu-id="2bfa2-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="2bfa2-106">**ProjectName**</span></span>|<span data-ttu-id="2bfa2-107">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2bfa2-107">**Description**</span></span>|<span data-ttu-id="2bfa2-108">**Haupt Dateien**</span><span class="sxs-lookup"><span data-stu-id="2bfa2-108">**Main Files**</span></span>|
|-|-|-|
|<span data-ttu-id="2bfa2-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="2bfa2-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="2bfa2-110">Enthält die `ThrottledParallelForEach`-Aktivität und ihren Designer.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="2bfa2-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="2bfa2-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="2bfa2-112">Die `ThrottledParallelForEach`-Aktivitätsdefinition.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-112">The `ThrottledParallelForEach` activity definition.</span></span>|
|<span data-ttu-id="2bfa2-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="2bfa2-113">CodeTestClient</span></span>|<span data-ttu-id="2bfa2-114">Beispielclientanwendung, die einen Workflow mithilfe von imperativem Code mit `ThrottledParallelForEach` konfiguriert ausführt.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="2bfa2-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="2bfa2-115">Program.cs</span></span><br /><br /> <span data-ttu-id="2bfa2-116">Definiert eine Instanz des Beispielworkflows und führt sie aus.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-116">Defines and runs an instance of the sample workflow.</span></span>|

## <a name="to-use-this-sample"></a><span data-ttu-id="2bfa2-117">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="2bfa2-117">To use this sample</span></span>

1. <span data-ttu-id="2bfa2-118">Öffnen Sie die Datei "throttledparallelforeach. sln" mithilfe von Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-118">Using Visual Studio 2010, open the ThrottledParallelForEach.sln file.</span></span>

2. <span data-ttu-id="2bfa2-119">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-119">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="2bfa2-120">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-120">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bfa2-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2bfa2-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="2bfa2-123">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2bfa2-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2bfa2-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`
