---
title: Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 42eb660aff01c7e29227c28a6ad0d47d4370eb91
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70016015"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="fbd2d-102">Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch</span><span class="sxs-lookup"><span data-stu-id="fbd2d-102">Fault Handling in a Flowchart Activity Using TryCatch</span></span>

<span data-ttu-id="fbd2d-103">In diesem Beispiel wird gezeigt, wie die <xref:System.Activities.Statements.TryCatch>-Aktivität innerhalb einer komplexen Ablaufsteuerungsaktivität verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-103">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>

<span data-ttu-id="fbd2d-104">In diesem Beispiel werden ein Promotionscode und eine Anzahl von Kindern als Variablen an eine <xref:System.Activities.Statements.Flowchart>-Aktivität übergeben, die einen Rabatt auf Grundlage von Formeln berechnet, die dem Promotioncode entsprechen.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-104">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="fbd2d-105">Zum Beispiel gehören obligatorischer Code und Workflow-Designer-Versionen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-105">The sample includes imperative code and workflow designer versions of the sample.</span></span>

<span data-ttu-id="fbd2d-106">In der folgenden Tabelle werden die Variablen für die `CreateFlowchartWithFaults`-Aktivität aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-106">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>

|<span data-ttu-id="fbd2d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="fbd2d-107">Parameters</span></span>|<span data-ttu-id="fbd2d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbd2d-108">Description</span></span>|
|----------------|-----------------|
|<span data-ttu-id="fbd2d-109">promoCode</span><span class="sxs-lookup"><span data-stu-id="fbd2d-109">promoCode</span></span>|<span data-ttu-id="fbd2d-110">Der Promotionscode.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-110">The promotion code.</span></span> <span data-ttu-id="fbd2d-111">Typ: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fbd2d-111">Type: String</span></span><br /><br /> <span data-ttu-id="fbd2d-112">Die möglichen Werte mit einer Beschreibung in Klammern:</span><span class="sxs-lookup"><span data-stu-id="fbd2d-112">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="fbd2d-113">-Single (Single)</span><span class="sxs-lookup"><span data-stu-id="fbd2d-113">-   Single (Single)</span></span><br /><span data-ttu-id="fbd2d-114">-MNK (ohne Kinder verheiratet)</span><span class="sxs-lookup"><span data-stu-id="fbd2d-114">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="fbd2d-115">-MWK (mit Kindern verheiratet)</span><span class="sxs-lookup"><span data-stu-id="fbd2d-115">-   MWK (Married with kids.)</span></span>|
|<span data-ttu-id="fbd2d-116">numKids</span><span class="sxs-lookup"><span data-stu-id="fbd2d-116">numKids</span></span>|<span data-ttu-id="fbd2d-117">Die Anzahl der Kinder.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-117">The number of children.</span></span> <span data-ttu-id="fbd2d-118">Typ: int</span><span class="sxs-lookup"><span data-stu-id="fbd2d-118">Type: int</span></span>|

<span data-ttu-id="fbd2d-119">Die `CreateFlowchartWithFaults`-Aktivität verwendet eine <xref:System.Activities.Statements.FlowSwitch%601>-Aktivität, die auf das `promoCode`-Argument umschaltet und den Rabatt mit der folgenden Formel berechnet.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-119">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>

|<span data-ttu-id="fbd2d-120">Wert von `promoCode`</span><span class="sxs-lookup"><span data-stu-id="fbd2d-120">Value of `promoCode`</span></span>|<span data-ttu-id="fbd2d-121">Rabatt (%)</span><span class="sxs-lookup"><span data-stu-id="fbd2d-121">Discount (%)</span></span>|
|--------------------------|--------------------|
|<span data-ttu-id="fbd2d-122">Single</span><span class="sxs-lookup"><span data-stu-id="fbd2d-122">Single</span></span>|<span data-ttu-id="fbd2d-123">10</span><span class="sxs-lookup"><span data-stu-id="fbd2d-123">10</span></span>|
|<span data-ttu-id="fbd2d-124">MNK</span><span class="sxs-lookup"><span data-stu-id="fbd2d-124">MNK</span></span>|<span data-ttu-id="fbd2d-125">15</span><span class="sxs-lookup"><span data-stu-id="fbd2d-125">15</span></span>|
|<span data-ttu-id="fbd2d-126">MWK</span><span class="sxs-lookup"><span data-stu-id="fbd2d-126">MWK</span></span>|<span data-ttu-id="fbd2d-127">15 + (1 – 1/`numberOfKids`)\*10 **Hinweis:**  Potenziell kann diese Berechnung eine <xref:System.DivideByZeroException> auslösen.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-127">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="fbd2d-128">Deshalb wird die Rabattberechnung in eine <xref:System.Activities.Statements.TryCatch>-Aktivität eingeschlossen, die die <xref:System.DivideByZeroException>-Ausnahme abfängt und den Rabatt auf 0 (null) festlegt.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-128">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|

#### <a name="to-use-this-sample"></a><span data-ttu-id="fbd2d-129">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbd2d-129">To use this sample</span></span>

1. <span data-ttu-id="fbd2d-130">Öffnen Sie mit Visual Studio 2010 die Projektmappendatei flowchartwithfaulthandult. sln.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-130">Using Visual Studio 2010, open the FlowchartWithFaultHandling.sln solution file.</span></span>

2. <span data-ttu-id="fbd2d-131">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-131">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="fbd2d-132">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-132">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fbd2d-133">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fbd2d-134">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-134">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="fbd2d-135">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fbd2d-136">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fbd2d-136">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`

## <a name="see-also"></a><span data-ttu-id="fbd2d-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbd2d-137">See also</span></span>

- [<span data-ttu-id="fbd2d-138">Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="fbd2d-138">Flowchart Workflows</span></span>](../flowchart-workflows.md)
- [<span data-ttu-id="fbd2d-139">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="fbd2d-139">Exceptions</span></span>](../exceptions.md)
