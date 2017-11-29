---
title: IfElse mit Regeln
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5cd0859db8071f9af130756fdc9b34726199be9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ifelse-with-rules"></a><span data-ttu-id="b427b-102">IfElse mit Regeln</span><span class="sxs-lookup"><span data-stu-id="b427b-102">IfElse With Rules</span></span>
<span data-ttu-id="b427b-103">Dieses Beispiel veranschaulicht die Verwendung einer Regelbedingung mit einer <xref:System.Workflow.Activities.IfElseActivity>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b427b-103">This sample shows the use of a rule condition with an <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span>  
  
 <span data-ttu-id="b427b-104">Das Beispiel übergibt einen `OrderValue`-Parameter vom Host.</span><span class="sxs-lookup"><span data-stu-id="b427b-104">The sample passes in an `OrderValue` parameter from the host.</span></span> <span data-ttu-id="b427b-105">Der Wert des Parameters wird in einer Regelbedingung für die erste Verzweigung der <xref:System.Workflow.Activities.IfElseActivity>-Aktivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="b427b-105">The value of the parameter is used in a rule condition on the first branch of the <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span> <span data-ttu-id="b427b-106">Wenn der Wert kleiner als 10.000 ist, wird die erste Verzweigung ausgeführt, und die <xref:System.Workflow.Activities.CodeActivity> -Aktivität in der ersten Verzweigung gibt **Genehmigung eines Managers abrufen** an die Konsole.</span><span class="sxs-lookup"><span data-stu-id="b427b-106">If the value is less than 10,000, the first branch executes, and the <xref:System.Workflow.Activities.CodeActivity> activity in the first branch prints **Get Manager Approval** to the console.</span></span> <span data-ttu-id="b427b-107">Wenn der Wert größer als 10.000 ist, ist die <xref:System.Workflow.Activities.CodeActivity> -Aktivität in der zweiten Verzweigung ausgeführt und druckt **VP Genehmigung erhalten**.</span><span class="sxs-lookup"><span data-stu-id="b427b-107">If the value is greater than 10,000, the <xref:System.Workflow.Activities.CodeActivity> activity in the second branch executes and prints **Get VP Approval**.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="b427b-108">So erstellen Sie das Beispiel</span><span class="sxs-lookup"><span data-stu-id="b427b-108">To build the sample</span></span>  
  
1.  <span data-ttu-id="b427b-109">Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b427b-109">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="b427b-110">Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="b427b-110">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b427b-111">Führen Sie die Projektmappe ohne Debuggen aus, indem Sie STRG+F5 drücken.</span><span class="sxs-lookup"><span data-stu-id="b427b-111">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="b427b-112">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="b427b-112">To run the sample</span></span>  
  
-   <span data-ttu-id="b427b-113">Führen Sie im Eingabeaufforderungsfenster des SDKs die EXE-Datei im Ordner "IfElseWithRules\bin\debug" aus (bzw. im Ordner "IfElseWithRules\bin" für die Visual Basic-Version des Beispiels), der sich unter dem Hauptordner des Beispiels befindet.</span><span class="sxs-lookup"><span data-stu-id="b427b-113">In the SDK Command Prompt window, run the .exe file in the IfElseWithRules\bin\debug folder (or the IfElseWithRules\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b427b-114">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b427b-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b427b-115">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="b427b-115">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b427b-116">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="b427b-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b427b-117">Dieses Beispiel befindet sich im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="b427b-117">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a><span data-ttu-id="b427b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b427b-118">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
