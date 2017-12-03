---
title: "Bedingte Aktivitätsgruppe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e0df4ddc6f2cc5404c8153b30df66cda41487691
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="conditioned-activity-group"></a><span data-ttu-id="3c0e5-102">Bedingte Aktivitätsgruppe</span><span class="sxs-lookup"><span data-stu-id="3c0e5-102">Conditioned Activity Group</span></span>
<span data-ttu-id="3c0e5-103">Im Beispiel wird eine Reisebuchungsanwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-103">The sample demonstrates a travel booking application.</span></span> <span data-ttu-id="3c0e5-104">Die <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) verfügt über zwei Codeaktivitäten: Eine Car-Aktivität und eine Airline-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-104">The <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) has two code activities: a Car activity and an Airline activity.</span></span> <span data-ttu-id="3c0e5-105">Im `SimpleCAGWorkflow`-Konstruktor wird ein "travelNeedType"-ArrayList-Objekt mit den erforderlichen Reisebuchungstypen ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-105">In the `SimpleCAGWorkflow` constructor, a "travelNeedType" ArrayList object is populated with the types of travel bookings that are required.</span></span> <span data-ttu-id="3c0e5-106">Sie ändern das CAG-Verhalten entsprechend, indem Sie eine oder beide `travelNeeds.Add`-Anweisungen auskommentieren.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-106">By commenting out one or both of the `travelNeeds.Add` statements, you modify the CAG behavior accordingly.</span></span> <span data-ttu-id="3c0e5-107">Die <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>-Bedingung sowohl der Car-Aktivität als auch der Airline-Aktivität werden mit der <xref:System.Workflow.Activities.CodeCondition> ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-107">Both the Car and Airline activities have their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> condition populated with a <xref:System.Workflow.Activities.CodeCondition>.</span></span> <span data-ttu-id="3c0e5-108">Die Car-Aktivität wird nur dann ausgeführt, wenn die `travelNeeds`-Auflistung über einen `TravelNeeds.Car`-Eintrag verfügt, und die Airline-Aktivität wird nur dann ausgeführt, wenn die `travelNeeds`-Auflistung über einen `TravelNeeds.Airline`-Eintrag verfügt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-108">The Car activity executes only if the `travelNeeds` collection has a `TravelNeeds.Car` entry, and the Airline activity executes only if the `travelNeeds` collection has a `TravelNeeds.Airline` entry.</span></span>  
  
 <span data-ttu-id="3c0e5-109">Durch die Ausführung der einzelnen Aktivitäten wird der entsprechende Eintrag aus der Auflistung entfernt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-109">The execution of each activity removes the corresponding entry from the collection.</span></span> <span data-ttu-id="3c0e5-110">Die <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>-Standardbedingung gibt an, dass die CAG beendet werden soll, wenn keine untergeordneten Elemente ausgeführt werden oder bereit für die Ausführung sind (basierend auf deren <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>-Bedingungen).</span><span class="sxs-lookup"><span data-stu-id="3c0e5-110">The default <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> condition specifies that the CAG should exit when no children are executing or are ready for execution (based on their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> conditions).</span></span> <span data-ttu-id="3c0e5-111">In diesem Beispiel bedeutet dies, dass die CAG beendet wird, wenn die `travelNeeds`-Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-111">In this sample, this means that the CAG exits when the `travelNeeds` collection is empty.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="3c0e5-112">So erstellen Sie das Beispiel</span><span class="sxs-lookup"><span data-stu-id="3c0e5-112">To build the sample</span></span>  
  
1.  <span data-ttu-id="3c0e5-113">Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c0e5-113">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="3c0e5-114">Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-114">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="3c0e5-115">Führen Sie die Projektmappe ohne Debuggen aus, indem Sie STRG+F5 drücken.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-115">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="3c0e5-116">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="3c0e5-116">To run the sample</span></span>  
  
-   <span data-ttu-id="3c0e5-117">Führen Sie im Eingabeaufforderungsfenster des SDKs die EXE-Datei im Ordner "SimpleCAG\bin\debug" aus (bzw. im Ordner "SimpleCAG\bin" für die Visual Basic-Version des Beispiels), der sich unter dem Hauptordner des Beispiels befindet.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-117">In the SDK Command Prompt window, run the .exe file in the SimpleCAG\bin\debug folder (or the SimpleCAG\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c0e5-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3c0e5-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="3c0e5-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3c0e5-120">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3c0e5-121">Dieses Beispiel befindet sich im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="3c0e5-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a><span data-ttu-id="3c0e5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c0e5-122">See Also</span></span>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
