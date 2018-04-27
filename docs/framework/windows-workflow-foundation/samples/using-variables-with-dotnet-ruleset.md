---
title: Verwenden von Variablen mit einem .NET Framework 3.5-Ruleset
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 216136ba084505947b5ab3c985284d704cb5872f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a><span data-ttu-id="e67d9-102">Verwenden von Variablen mit einem .NET Framework 3.5-Ruleset</span><span class="sxs-lookup"><span data-stu-id="e67d9-102">Using Variables with a .NET Framework 3.5 Ruleset</span></span>
<span data-ttu-id="e67d9-103">Dieses Beispiel veranschaulicht, wie ein Workflow erstellt wird, der mithilfe der <xref:System.Activities.Statements.Interop>-Aktivität eine in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] geschriebene benutzerdefinierte Aktivität integriert, die eine Richtlinie und Regeln verwendet.</span><span class="sxs-lookup"><span data-stu-id="e67d9-103">This sample demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span> <span data-ttu-id="e67d9-104">Der Workflow übergibt Daten an die benutzerdefinierte Aktivität, indem er Variablen an die von der benutzerdefinierten Aktivität verfügbar gemachten Abhängigkeitseigenschaften bindet.</span><span class="sxs-lookup"><span data-stu-id="e67d9-104">The workflow passes data to the custom activity by binding variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="sample-walkthrough"></a><span data-ttu-id="e67d9-105">Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="e67d9-105">Sample walkthrough</span></span>  
  
#### <a name="to-examine-travelrulelibrary"></a><span data-ttu-id="e67d9-106">So überprüfen Sie TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="e67d9-106">To examine TravelRuleLibrary</span></span>  
  
1.  <span data-ttu-id="e67d9-107">Öffnen Sie mit Visual Studio die Projektmappendatei "interopwith35ruleset.sln".</span><span class="sxs-lookup"><span data-stu-id="e67d9-107">Using Visual Studio, open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e67d9-108">Öffnen Sie "TravelRuleSet.cs" im Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="e67d9-108">Open the TravelRuleSet.cs in the workflow designer.</span></span>  
  
     <span data-ttu-id="e67d9-109">Es wird eine benutzerdefinierte sequenzielle Aktivität angezeigt, die eine <xref:System.Workflow.Activities.PolicyActivity> enthält.</span><span class="sxs-lookup"><span data-stu-id="e67d9-109">A custom sequential activity that contains a <xref:System.Workflow.Activities.PolicyActivity> is displayed.</span></span>  
  
3.  <span data-ttu-id="e67d9-110">Doppelklicken Sie auf die DiscountPolicy-Richtlinienaktivität, um die Regeln zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e67d9-110">Double-click the DiscountPolicy policy activity to examine the rules.</span></span>  
  
     <span data-ttu-id="e67d9-111">Die Regeln werden im Regel-Editor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e67d9-111">The Rules editor pops up to show the rules.</span></span>  
  
4.  <span data-ttu-id="e67d9-112">Klicken Sie mit der rechten Maustaste auf die `DiscountPolicy` , und wählen Sie die **Code anzeigen** Option aus, um die Code-beside-C#-Code für die Aktivität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e67d9-112">Right click the `DiscountPolicy` and select the **View Code** option to examine the code beside C# code for the activity.</span></span>  
  
     <span data-ttu-id="e67d9-113">Achten Sie auf die Einstellung der Abhängigkeitseigenschaft für `DiscountLevel`.</span><span class="sxs-lookup"><span data-stu-id="e67d9-113">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="e67d9-114">Diese entspricht den Argumenten in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e67d9-114">This is equivalent to arguments in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e67d9-115"> Argumente, finden Sie unter [Variablen und Argumente](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="e67d9-115"> arguments, see [Variables and Arguments](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="e67d9-116">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="e67d9-116">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="e67d9-117">Dies ist ein sequenzielles Workflowprojekt, das die <xref:System.Activities.Statements.Interop>-Aktivität für die Integration mit dem im `TravelRuleLibrary`-Projekt erstellten benutzerdefinierten Regelsatz verwendet.</span><span class="sxs-lookup"><span data-stu-id="e67d9-117">This is a sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom Rule set created in the `TravelRuleLibrary` project.</span></span> <span data-ttu-id="e67d9-118">Variablen werden in der <xref:System.Activities.Statements.Sequence>-Aktivität auf oberster Ebene erstellt.</span><span class="sxs-lookup"><span data-stu-id="e67d9-118">Variables are created on the top level <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="e67d9-119">Die <xref:System.Activities.Statements.Interop>-Aktivität wird zur Integration mit der `TravelRuleSet`-Aktivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="e67d9-119">The <xref:System.Activities.Statements.Interop> activity is used to integrate with the `TravelRuleSet` activity.</span></span> <span data-ttu-id="e67d9-120">Die Variablen in der <xref:System.Activities.Statements.Sequence> deklarierten Variablen werden zum Binden an die Abhängigkeitseigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="e67d9-120">The variables that are declared on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="e67d9-121">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="e67d9-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="e67d9-122">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "InteropWith35RuleSet.sln".</span><span class="sxs-lookup"><span data-stu-id="e67d9-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e67d9-123">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e67d9-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e67d9-124">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e67d9-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e67d9-125">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e67d9-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e67d9-126">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e67d9-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e67d9-127">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="e67d9-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e67d9-128">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e67d9-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`