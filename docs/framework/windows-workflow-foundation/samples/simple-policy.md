---
title: Einfache Richtlinie
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 884a099c1334b53c904173987d2f1ccfe6dd741a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="simple-policy"></a><span data-ttu-id="1b870-102">Einfache Richtlinie</span><span class="sxs-lookup"><span data-stu-id="1b870-102">Simple Policy</span></span>
<span data-ttu-id="1b870-103">Dieses Beispiel veranschaulicht, wie eine <xref:System.Workflow.Activities.PolicyActivity>-Aktivität in einem Workflow verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1b870-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="1b870-104">Der sequenzielle Workflow in diesem Beispiel wird mit einer <xref:System.Workflow.Activities.PolicyActivity>-Aktivität erstellt.</span><span class="sxs-lookup"><span data-stu-id="1b870-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="1b870-105">Der Workflow definiert die Felder `orderValue`, `customerType` und `discount`, die zum Definieren eines Produktrabattworkflows verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b870-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="1b870-106">Die in der Regeldatei definierten Regeln legen einen Rabattwert fest, der auf `orderValue` und `customerType` basiert.</span><span class="sxs-lookup"><span data-stu-id="1b870-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="1b870-107">`orderValue` und `customerType` sind in der `SimplePolicyWorkflow`-Klassendefinition festgelegt und können geändert werden, um das Verhalten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1b870-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="1b870-108">Der sich ergebende Rabatt wird in der Konsole im <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted>-Ereignishandler, der in der `SimplePolicyWorkflow`-Klasse definiert ist, ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1b870-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="1b870-109">So erstellen Sie das Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b870-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="1b870-110">Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b870-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="1b870-111">Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="1b870-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1b870-112">Führen Sie die Projektmappe ohne Debuggen aus, indem Sie STRG+F5 drücken.</span><span class="sxs-lookup"><span data-stu-id="1b870-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="1b870-113">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="1b870-113">To run the sample</span></span>  
  
-   <span data-ttu-id="1b870-114">Führen Sie im Eingabeaufforderungsfenster des SDK die EXE-Datei im Ordner "SimplePolicy\bin\debug" aus (bzw. im Ordner "SimplePolicy\bin" für die Visual Basic-Version des Beispiels), der sich unter dem Hauptordner des Beispiels befindet.</span><span class="sxs-lookup"><span data-stu-id="1b870-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1b870-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="1b870-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1b870-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="1b870-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1b870-117">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1b870-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1b870-118">Dieses Beispiel befindet sich im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="1b870-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="1b870-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b870-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="1b870-120">Erweiterte Richtlinie</span><span class="sxs-lookup"><span data-stu-id="1b870-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
