---
title: "Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 85fe8dcbd0ef5e774ab81ed167ff937ec2e09d83
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="b9f1f-102">Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="b9f1f-102">Using the ExpressionTextBox in a Custom Activity Designer</span></span>
<span data-ttu-id="b9f1f-103">In diesem Beispiel wird gezeigt, wie das <xref:System.Activities.Presentation.View.ExpressionTextBox> in einem benutzerdefinierten Aktivitätsdesigner verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-103">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="b9f1f-104">Die benutzerdefinierte Aktivität, `MultiAssign`, weist zwei Zeichenfolgenvariablen zwei Zeichenfolgenwerten zu.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-104">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="b9f1f-105">Einige <xref:System.Activities.Presentation.View.ExpressionTextBox>-Steuerelemente werden an <xref:System.Activities.InArgument>e gebunden, und einige werden an <xref:System.Activities.OutArgument>e gebunden.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-105">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="b9f1f-106">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="b9f1f-106">Sample details</span></span>  
 <span data-ttu-id="b9f1f-107">Der `ArgumentToExpressionConverter` ist der verwendete Typkonverter, wenn Bindungsausdrücke an Argumente gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-107">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="b9f1f-108">`ConverterParameter` muss ggf. auf `In` oder `Out` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-108">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> <span data-ttu-id="b9f1f-109">`InOut` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-109">`InOut` is not supported.</span></span>  
  
 <span data-ttu-id="b9f1f-110">Die `UseLocationExpression` Attribut wird verwendet, auf `OutArgument`s, um anzugeben, dass der Ausdruck einen Ausdruck ein L-Wert ("Linker Wert" oder "Location-Wert") werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-110">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="b9f1f-111">In den meisten Fällen ist ein L-Wert-Ausdruck ein gültiger Visual Basic-Bezeichner, der verwendet wird, um anzugeben, dass das zurückgegebene `OutArgument` eine Variable oder ein Argumentname ist.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-111">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>  
  
 <span data-ttu-id="b9f1f-112">Das `MaxLines`-Attribut wird in diesem Beispiel auf 1 festgelegt, und `MinLines` wird nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-112">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="b9f1f-113">Dadurch wird angegeben, dass das <xref:System.Activities.Presentation.View.ExpressionTextBox> eine feste Größe von einer Zeile hat, unabhängig von der Menge von Text, die vom Benutzer eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-113">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="b9f1f-114">Damit das <xref:System.Activities.Presentation.View.ExpressionTextBox> an die Benutzereingabe angepasst werden kann, legen Sie `MaxLines` größer als `MinLines` fest.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-114">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>  
  
 <span data-ttu-id="b9f1f-115">Ein ExpressionTextBox kann nur an Argumente gebunden werden und nicht an CLR-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-115">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b9f1f-116">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9f1f-116">To use this sample</span></span>  
  
1.  <span data-ttu-id="b9f1f-117">Öffnen Sie die Datei "ExpressionTextBoxSample.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9f1f-117">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ExpressionTextBoxSample.sln file.</span></span>  
  
2.  <span data-ttu-id="b9f1f-118">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-118">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="b9f1f-119">So führen Sie dieses Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="b9f1f-119">To run this sample</span></span>  
  
1.  <span data-ttu-id="b9f1f-120">Fügen Sie der Projektmappe eine neue Konsolenanwendung für Workflows hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-120">Add a new Workflow Console Application to the solution.</span></span>  
  
2.  <span data-ttu-id="b9f1f-121">Hinzufügen eines Verweises auf die **ExpressionTextBoxSample** Projekt aus der neue Workflow-Konsolenanwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-121">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>  
  
3.  <span data-ttu-id="b9f1f-122">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-122">Build the solution.</span></span>  
  
4.  <span data-ttu-id="b9f1f-123">Ziehen Sie die **MultiAssign** Aktivität aus der Toolbox, und legen Sie sie in den Workflow.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-123">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b9f1f-124">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b9f1f-125">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b9f1f-126">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b9f1f-127">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b9f1f-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="b9f1f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9f1f-128">See Also</span></span>  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
 [<span data-ttu-id="b9f1f-129">Entwickeln von Anwendungen mit dem Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="b9f1f-129">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
