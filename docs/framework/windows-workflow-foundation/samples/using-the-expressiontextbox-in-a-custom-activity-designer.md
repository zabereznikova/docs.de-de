---
title: Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: bfac07d64cd5e30c3475d4e269c16597905ea829
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045351"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="a203b-102">Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="a203b-102">Using the ExpressionTextBox in a Custom Activity Designer</span></span>
<span data-ttu-id="a203b-103">In diesem Beispiel wird gezeigt, wie das <xref:System.Activities.Presentation.View.ExpressionTextBox> in einem benutzerdefinierten Aktivitätsdesigner verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a203b-103">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="a203b-104">Die benutzerdefinierte Aktivität, `MultiAssign`, weist zwei Zeichenfolgenvariablen zwei Zeichenfolgenwerten zu.</span><span class="sxs-lookup"><span data-stu-id="a203b-104">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="a203b-105">Einige <xref:System.Activities.Presentation.View.ExpressionTextBox>-Steuerelemente werden an <xref:System.Activities.InArgument>e gebunden, und einige werden an <xref:System.Activities.OutArgument>e gebunden.</span><span class="sxs-lookup"><span data-stu-id="a203b-105">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>

## <a name="sample-details"></a><span data-ttu-id="a203b-106">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="a203b-106">Sample details</span></span>
 <span data-ttu-id="a203b-107">Der `ArgumentToExpressionConverter` ist der verwendete Typkonverter, wenn Bindungsausdrücke an Argumente gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="a203b-107">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="a203b-108">`ConverterParameter` muss ggf. auf `In` oder `Out` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a203b-108">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> <span data-ttu-id="a203b-109">`InOut` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a203b-109">`InOut` is not supported.</span></span>

 <span data-ttu-id="a203b-110">Das `UseLocationExpression` -Attribut wird auf `OutArgument`s verwendet, um anzugeben, dass der Ausdruck ein L-Wert-Ausdruck ("Linker Wert" oder "Location Value") sein soll.</span><span class="sxs-lookup"><span data-stu-id="a203b-110">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="a203b-111">In den meisten Fällen ist ein L-Wert-Ausdruck ein gültiger Visual Basic-Bezeichner, der verwendet wird, um anzugeben, dass das zurückgegebene `OutArgument` eine Variable oder ein Argumentname ist.</span><span class="sxs-lookup"><span data-stu-id="a203b-111">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>

 <span data-ttu-id="a203b-112">Das `MaxLines`-Attribut wird in diesem Beispiel auf 1 festgelegt, und `MinLines` wird nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a203b-112">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="a203b-113">Dadurch wird angegeben, dass das <xref:System.Activities.Presentation.View.ExpressionTextBox> eine feste Größe von einer Zeile hat, unabhängig von der Menge von Text, die vom Benutzer eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a203b-113">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="a203b-114">Damit das <xref:System.Activities.Presentation.View.ExpressionTextBox> an die Benutzereingabe angepasst werden kann, legen Sie `MaxLines` größer als `MinLines` fest.</span><span class="sxs-lookup"><span data-stu-id="a203b-114">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>

 <span data-ttu-id="a203b-115">Ein ExpressionTextBox kann nur an Argumente gebunden werden und nicht an CLR-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a203b-115">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="a203b-116">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="a203b-116">To use this sample</span></span>

1. <span data-ttu-id="a203b-117">Öffnen Sie mit Visual Studio 2010 die Datei "expressiontextboxsample. sln".</span><span class="sxs-lookup"><span data-stu-id="a203b-117">Using Visual Studio 2010, open the ExpressionTextBoxSample.sln file.</span></span>

2. <span data-ttu-id="a203b-118">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a203b-118">To build the solution, press CTRL+SHIFT+B.</span></span>

#### <a name="to-run-this-sample"></a><span data-ttu-id="a203b-119">So führen Sie dieses Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="a203b-119">To run this sample</span></span>

1. <span data-ttu-id="a203b-120">Fügen Sie der Projektmappe eine neue Konsolenanwendung für Workflows hinzu.</span><span class="sxs-lookup"><span data-stu-id="a203b-120">Add a new Workflow Console Application to the solution.</span></span>

2. <span data-ttu-id="a203b-121">Fügen Sie dem Projekt " **expressiontextboxsample** " aus dem neuen Workflow Konsolen Anwendungsprojekt einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="a203b-121">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>

3. <span data-ttu-id="a203b-122">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="a203b-122">Build the solution.</span></span>

4. <span data-ttu-id="a203b-123">Ziehen Sie die **multiassign** -Aktivität aus der Toolbox, und legen Sie Sie im Workflow ab.</span><span class="sxs-lookup"><span data-stu-id="a203b-123">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a203b-124">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="a203b-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a203b-125">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a203b-125">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="a203b-126">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a203b-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a203b-127">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a203b-127">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="a203b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a203b-128">See also</span></span>

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [<span data-ttu-id="a203b-129">Entwickeln von Anwendungen mit dem Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="a203b-129">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
