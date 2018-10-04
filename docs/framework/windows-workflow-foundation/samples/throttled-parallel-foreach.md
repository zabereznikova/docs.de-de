---
title: Parallel ForEach (eingeschränkt)
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 8691edb8a5a61204b187be8def553f2f06be0f0d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48581861"
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="c1dff-102">Parallel ForEach (eingeschränkt)</span><span class="sxs-lookup"><span data-stu-id="c1dff-102">Throttled Parallel ForEach</span></span>
<span data-ttu-id="c1dff-103">Die `ThrottleParallelForEach` -Aktivität ist vergleichbar mit der <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` Aktivität mit einer Ausnahme, dass können einstellen eines parallelitätsfaktors zur Einschränkung der Anzahl gleichzeitiger auszuführender Branches auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c1dff-103">The `ThrottleParallelForEach` activity is similar to the <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="c1dff-104">Die `ThrottleParallelForEach`-Aktivität wird von <xref:System.Activities.NativeActivity> abgeleitet, da sie andere Aktivitäten (die untergeordneten Aktivitäten) planen muss und darauf nur über die <xref:System.Activities.NativeActivityContext>-Klasse zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c1dff-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>

## <a name="projects"></a><span data-ttu-id="c1dff-105">Projekte</span><span class="sxs-lookup"><span data-stu-id="c1dff-105">Projects</span></span>

|<span data-ttu-id="c1dff-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="c1dff-106">**ProjectName**</span></span>|<span data-ttu-id="c1dff-107">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c1dff-107">**Description**</span></span>|<span data-ttu-id="c1dff-108">**Hauptdateien**</span><span class="sxs-lookup"><span data-stu-id="c1dff-108">**Main Files**</span></span>|
|-|-|-|
|<span data-ttu-id="c1dff-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="c1dff-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="c1dff-110">Enthält die `ThrottledParallelForEach`-Aktivität und ihren Designer.</span><span class="sxs-lookup"><span data-stu-id="c1dff-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="c1dff-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="c1dff-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="c1dff-112">Die `ThrottledParallelForEach`-Aktivitätsdefinition.</span><span class="sxs-lookup"><span data-stu-id="c1dff-112">The `ThrottledParallelForEach` activity definition.</span></span>|
|<span data-ttu-id="c1dff-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="c1dff-113">CodeTestClient</span></span>|<span data-ttu-id="c1dff-114">Beispielclientanwendung, die einen Workflow mithilfe von imperativem Code mit `ThrottledParallelForEach` konfiguriert ausführt.</span><span class="sxs-lookup"><span data-stu-id="c1dff-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="c1dff-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="c1dff-115">Program.cs</span></span><br /><br /> <span data-ttu-id="c1dff-116">Definiert eine Instanz des Beispielworkflows und führt sie aus.</span><span class="sxs-lookup"><span data-stu-id="c1dff-116">Defines and runs an instance of the sample workflow.</span></span>|

#### <a name="to-use-this-sample"></a><span data-ttu-id="c1dff-117">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1dff-117">To use this sample</span></span>

1.  <span data-ttu-id="c1dff-118">Öffnen Sie die Datei "throttledparallelforeach.sln" in mit Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="c1dff-118">Using Visual Studio 2010, open the ThrottledParallelForEach.sln file.</span></span>

2.  <span data-ttu-id="c1dff-119">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1dff-119">To build the solution, press CTRL+SHIFT+B.</span></span>

3.  <span data-ttu-id="c1dff-120">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c1dff-120">To run the solution, press F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="c1dff-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c1dff-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c1dff-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c1dff-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c1dff-123">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c1dff-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c1dff-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c1dff-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`