---
title: Validierung von Aktivitätsbeziehungen
ms.date: 03/30/2017
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
ms.openlocfilehash: 50f08118fb5ad4d9b8fe809e7ab3cc5d57f28149
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43394684"
---
# <a name="activity-relationships-validation"></a><span data-ttu-id="8d0d0-102">Validierung von Aktivitätsbeziehungen</span><span class="sxs-lookup"><span data-stu-id="8d0d0-102">Activity Relationships Validation</span></span>
<span data-ttu-id="8d0d0-103">Dieses Beispiel besteht aus drei Aktivitäten: `CreateCity`, `CreateState` und `CreateCountry`.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-103">This sample consists of three activities, `CreateCity`, `CreateState`, and `CreateCountry`.</span></span> <span data-ttu-id="8d0d0-104">`CreateCity` muss sich innerhalb einer `CreateState`-Aktivität befinden, und `CreateState` muss sich innerhalb einer `CreateCountry`-Aktivität befinden.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-104">`CreateCity` must be inside a `CreateState` activity, and `CreateState` must be inside a `CreateCountry` activity.</span></span> <span data-ttu-id="8d0d0-105">Für dieses Beispiel ist die Validierungslogik in Code für die `CreateState`-Aktivität und in XAML für die `CreateCity`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-105">For the purpose of this sample, the validation logic is in code for the `CreateState` activity, and in XAML for the `CreateCity` activity.</span></span> <span data-ttu-id="8d0d0-106">Beide Einschränkungen weisen das gleiche Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-106">Both constraints have the same behavior.</span></span>  
  
 <span data-ttu-id="8d0d0-107">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] stellt die folgenden drei Hilfsaktivitäten bereit, mit denen die Entwickler Beziehungen zwischen Aktivitäten überprüfen können:</span><span class="sxs-lookup"><span data-stu-id="8d0d0-107">The [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] provides the following three helper activities that allow the developer to validate relationships between activities:</span></span>  
  
 <xref:System.Activities.Validation.GetParentChain>  
 <span data-ttu-id="8d0d0-108">Stellt die Auflistung aller Aktivitäten bereit, die zum übergeordneten Element des aktuellen Knotens gehören</span><span class="sxs-lookup"><span data-stu-id="8d0d0-108">Provides the collection of all activities that belong to the parent of the current node</span></span>  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 <span data-ttu-id="8d0d0-109">Stellt die Auflistung aller Aktivitäten bereit, die zur Teilstruktur des aktuellen Knotens gehören, ohne den aktuellen Knoten</span><span class="sxs-lookup"><span data-stu-id="8d0d0-109">Provides the collection of all activities that belong to the sub-tree of the current node, excluding the current node</span></span>  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 <span data-ttu-id="8d0d0-110">Stellt die Auflistung aller Aktivitäten in derselben Struktur wie der aktuelle Knoten bereit</span><span class="sxs-lookup"><span data-stu-id="8d0d0-110">Provides the collection of all activities in the same tree as the current node</span></span>  
  
 <span data-ttu-id="8d0d0-111">Im Beispiel wird eine <xref:System.Activities.Statements.ForEach%601>-Aktivität verwendet, um die Auflistung zu durchlaufen, die von <xref:System.Activities.Validation.GetParentChain> zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-111">In the sample, a <xref:System.Activities.Statements.ForEach%601> activity is used to walk through the collection returned by <xref:System.Activities.Validation.GetParentChain>.</span></span> <span data-ttu-id="8d0d0-112">Für jedes Element in der Auflistung wird der Typ mit `CreateCountry` verglichen (oder mit `CreateState`, wenn `CreateCity` überprüft wird). Wenn eine Übereinstimmung gefunden wird, wird das Ergebniskennzeichen auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-112">For every element in the collection, its type is compared to `CreateCountry` (or `CreateState` if `CreateCity` is being validated), and when a match is found the result flag is set to `true`.</span></span> <span data-ttu-id="8d0d0-113">Schließlich wird <xref:System.Activities.Validation.AssertValidation> verwendet, um einen Validierungsfehler zu generieren, wenn das Ergebniskennzeichen auf `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-113">Finally, an <xref:System.Activities.Validation.AssertValidation> is used to generate a validation error if the result flag is set to `false`.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="8d0d0-114">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d0d0-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="8d0d0-115">Öffnen Sie die Beispielprojektmappe "ContainmentValidation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d0d0-115">Open the ContainmentValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="8d0d0-116">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-116">Build the solution.</span></span>  
  
3.  <span data-ttu-id="8d0d0-117">Drücken Sie STRG+F5, um das Programm zu starten.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-117">Press CTRL + F5 to launch the program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8d0d0-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8d0d0-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="8d0d0-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8d0d0-120">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="8d0d0-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8d0d0-121">Dieses Beispiel befindet sich im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="8d0d0-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`
