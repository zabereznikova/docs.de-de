---
title: "Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a179ae5aaca959383a88105b96cbba2cebd1919
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="6e167-102">Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch</span><span class="sxs-lookup"><span data-stu-id="6e167-102">Fault Handling in a Flowchart Activity Using TryCatch</span></span>
<span data-ttu-id="6e167-103">In diesem Beispiel wird gezeigt, wie die <xref:System.Activities.Statements.TryCatch>-Aktivität innerhalb einer komplexen Ablaufsteuerungsaktivität verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e167-103">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>  
  
 <span data-ttu-id="6e167-104">In diesem Beispiel werden ein Promotionscode und eine Anzahl von Kindern als Variablen an eine <xref:System.Activities.Statements.Flowchart>-Aktivität übergeben, die einen Rabatt auf Grundlage von Formeln berechnet, die dem Promotioncode entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6e167-104">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="6e167-105">Zum Beispiel gehören obligatorischer Code und Workflow-Designer-Versionen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="6e167-105">The sample includes imperative code and workflow designer versions of the sample.</span></span>  
  
 <span data-ttu-id="6e167-106">In der folgenden Tabelle werden die Variablen für die `CreateFlowchartWithFaults`-Aktivität aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6e167-106">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>  
  
|<span data-ttu-id="6e167-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e167-107">Parameters</span></span>|<span data-ttu-id="6e167-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e167-108">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="6e167-109">promoCode</span><span class="sxs-lookup"><span data-stu-id="6e167-109">promoCode</span></span>|<span data-ttu-id="6e167-110">Der Promotionscode.</span><span class="sxs-lookup"><span data-stu-id="6e167-110">The promotion code.</span></span> <span data-ttu-id="6e167-111">Typ: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6e167-111">Type: String</span></span><br /><br /> <span data-ttu-id="6e167-112">Die möglichen Werte mit einer Beschreibung in Klammern:</span><span class="sxs-lookup"><span data-stu-id="6e167-112">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="6e167-113">-Einzelne (einfach)</span><span class="sxs-lookup"><span data-stu-id="6e167-113">-   Single (Single)</span></span><br /><span data-ttu-id="6e167-114">-MNK (Verheiratet ohne Kinder).</span><span class="sxs-lookup"><span data-stu-id="6e167-114">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="6e167-115">-MWK (Verheiratet mit Kindern).</span><span class="sxs-lookup"><span data-stu-id="6e167-115">-   MWK (Married with kids.)</span></span>|  
|<span data-ttu-id="6e167-116">numKids</span><span class="sxs-lookup"><span data-stu-id="6e167-116">numKids</span></span>|<span data-ttu-id="6e167-117">Die Anzahl der Kinder.</span><span class="sxs-lookup"><span data-stu-id="6e167-117">The number of children.</span></span> <span data-ttu-id="6e167-118">Typ: int</span><span class="sxs-lookup"><span data-stu-id="6e167-118">Type: int</span></span>|  
  
 <span data-ttu-id="6e167-119">Die `CreateFlowchartWithFaults`-Aktivität verwendet eine <xref:System.Activities.Statements.FlowSwitch%601>-Aktivität, die auf das `promoCode`-Argument umschaltet und den Rabatt mit der folgenden Formel berechnet.</span><span class="sxs-lookup"><span data-stu-id="6e167-119">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>  
  
|<span data-ttu-id="6e167-120">Wert von `promoCode`</span><span class="sxs-lookup"><span data-stu-id="6e167-120">Value of `promoCode`</span></span>|<span data-ttu-id="6e167-121">Rabatt (%)</span><span class="sxs-lookup"><span data-stu-id="6e167-121">Discount (%)</span></span>|  
|--------------------------|--------------------|  
|<span data-ttu-id="6e167-122">Single</span><span class="sxs-lookup"><span data-stu-id="6e167-122">Single</span></span>|<span data-ttu-id="6e167-123">10</span><span class="sxs-lookup"><span data-stu-id="6e167-123">10</span></span>|  
|<span data-ttu-id="6e167-124">MNK</span><span class="sxs-lookup"><span data-stu-id="6e167-124">MNK</span></span>|<span data-ttu-id="6e167-125">15</span><span class="sxs-lookup"><span data-stu-id="6e167-125">15</span></span>|  
|<span data-ttu-id="6e167-126">MWK</span><span class="sxs-lookup"><span data-stu-id="6e167-126">MWK</span></span>|<span data-ttu-id="6e167-127">15 + (1 – 1 /`numberOfKids`)\*10 **Hinweis:** potenziell kann diese Berechnung Auslösen einer <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="6e167-127">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="6e167-128">Deshalb wird die Rabattberechnung in eine <xref:System.Activities.Statements.TryCatch>-Aktivität eingeschlossen, die die <xref:System.DivideByZeroException>-Ausnahme abfängt und den Rabatt auf 0 (null) festlegt.</span><span class="sxs-lookup"><span data-stu-id="6e167-128">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6e167-129">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e167-129">To use this sample</span></span>  
  
1.  <span data-ttu-id="6e167-130">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "FlowchartWithFaultHandling.sln".</span><span class="sxs-lookup"><span data-stu-id="6e167-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the FlowchartWithFaultHandling.sln solution file.</span></span>  
  
2.  <span data-ttu-id="6e167-131">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e167-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6e167-132">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6e167-132">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6e167-133">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="6e167-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="6e167-134">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6e167-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6e167-135">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="6e167-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6e167-136">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6e167-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a><span data-ttu-id="6e167-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e167-137">See Also</span></span>  
 [<span data-ttu-id="6e167-138">Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="6e167-138">Flowchart Workflows</span></span>](../../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)  
 [<span data-ttu-id="6e167-139">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="6e167-139">Exceptions</span></span>](../../../../docs/framework/windows-workflow-foundation/exceptions.md)
