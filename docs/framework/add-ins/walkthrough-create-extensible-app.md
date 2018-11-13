---
title: 'Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63780583d035d6fab6b3a79424857b82a910ef09
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2018
ms.locfileid: "50744612"
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="d8041-102">Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d8041-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="d8041-103">In dieser exemplarischen Vorgehensweise wird beschrieben, wie Sie eine Pipeline für ein Add-in erstellen, die einfachen Taschenrechner Funktionen ausführt.</span><span class="sxs-lookup"><span data-stu-id="d8041-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="d8041-104">Es wird nicht auf einem realen Szenario veranschaulicht; Stattdessen zeigt es die grundlegende Funktionen einer Pipeline und wie ein Add-In-Dienste für einen Host bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="d8041-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="d8041-105">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben:</span><span class="sxs-lookup"><span data-stu-id="d8041-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="d8041-106">Visual Studio-Projektmappe wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="d8041-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="d8041-107">Erstellen der Pipelineverzeichnisstruktur.</span><span class="sxs-lookup"><span data-stu-id="d8041-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="d8041-108">Erstellen den Vertrag und Ansichten.</span><span class="sxs-lookup"><span data-stu-id="d8041-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="d8041-109">Erstellen des Add-In-seitige Adapters an.</span><span class="sxs-lookup"><span data-stu-id="d8041-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="d8041-110">Den hostseitige Adapter wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="d8041-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="d8041-111">Erstellen des Hosts.</span><span class="sxs-lookup"><span data-stu-id="d8041-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="d8041-112">Erstellen das Add-in.</span><span class="sxs-lookup"><span data-stu-id="d8041-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="d8041-113">Bereitstellen der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="d8041-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="d8041-114">Die hostanwendung wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d8041-114">Running the host application.</span></span>  
  
 <span data-ttu-id="d8041-115">Diese Pipeline übergibt nur serialisierbare Typen (<xref:System.Double> und <xref:System.String>), zwischen dem Host und das Add-in.</span><span class="sxs-lookup"><span data-stu-id="d8041-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="d8041-116">Ein Beispiel, wie Auflistungen von komplexen Datentypen übergeben werden, finden Sie unter [Exemplarische Vorgehensweise: Übergeben von Auflistungen zwischen Hosts und Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span><span class="sxs-lookup"><span data-stu-id="d8041-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="d8041-117">Der Vertrag für die Pipeline definiert ein Objektmodell der vier arithmetischen Operationen: hinzufügen, subtrahieren, Multiplizieren und Dividieren.</span><span class="sxs-lookup"><span data-stu-id="d8041-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="d8041-118">Der Host stellt das Add-in mit einer Formel zum Berechnen, wie z. B. 2 + 2, und gibt Sie das Ergebnis des Add-Ins auf den Host zurück.</span><span class="sxs-lookup"><span data-stu-id="d8041-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="d8041-119">Version 2 von der Rechner-add-in bietet mehr berechnen Möglichkeiten und versionsverwaltung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d8041-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="d8041-120">Es wird beschrieben, [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als der Host-Änderungen](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="d8041-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d8041-121">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d8041-121">Prerequisites</span></span>  
 <span data-ttu-id="d8041-122">Für diese exemplarische Vorgehensweise wird Folgendes benötigt:</span><span class="sxs-lookup"><span data-stu-id="d8041-122">You need the following to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="d8041-123">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d8041-123">Visual Studio.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="d8041-124">Erstellen eine Visual Studio-Projektmappe</span><span class="sxs-lookup"><span data-stu-id="d8041-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="d8041-125">Verwenden Sie eine Lösung in Visual Studio, um die Projekte der Pipelinesegmente enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8041-125">Use a solution in Visual Studio to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="d8041-126">Zum Erstellen der Pipeline-Lösung</span><span class="sxs-lookup"><span data-stu-id="d8041-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="d8041-127">Erstellen Sie in Visual Studio ein neues Projekt namens `Calc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="d8041-127">In Visual Studio, create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="d8041-128">Basierend auf den **Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d8041-129">Nennen Sie die Projektmappe `CalculatorV1`.</span><span class="sxs-lookup"><span data-stu-id="d8041-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="d8041-130">Erstellen der Pipelineverzeichnisstruktur</span><span class="sxs-lookup"><span data-stu-id="d8041-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="d8041-131">Das Add-In Modell erfordert, dass die Pipeline Segment Assemblys in einer angegebenen Verzeichnisstruktur platziert werden.</span><span class="sxs-lookup"><span data-stu-id="d8041-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="d8041-132">Weitere Informationen über die Pipelinestruktur finden Sie unter [Anforderungen für die Pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="d8041-132">For more information about the pipeline structure, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="d8041-133">Zum Erstellen der Pipeline-Verzeichnisstruktur</span><span class="sxs-lookup"><span data-stu-id="d8041-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="d8041-134">Erstellen Sie einen Anwendungsordner an einer beliebigen Stelle auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="d8041-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="d8041-135">Erstellen Sie in diesem Ordner die folgende Struktur:</span><span class="sxs-lookup"><span data-stu-id="d8041-135">In that folder, create the following structure:</span></span>  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     <span data-ttu-id="d8041-136">Es ist nicht erforderlich, platzieren Sie die Ordnerstruktur für die Pipeline in Ihrem Anwendungsordner; Diese erfolgt hier nur aus praktischen Gründen.</span><span class="sxs-lookup"><span data-stu-id="d8041-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="d8041-137">Zu gegebener Zeit wird in der exemplarischen Vorgehensweise erläutert, wie den Code ändern, ist die Ordnerstruktur für die Pipeline an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="d8041-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="d8041-138">Finden Sie in den Ausführungen der Pipeline verzeichnisanforderungen in [Anforderungen für die Pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="d8041-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8041-139">Die `CalcV2` Ordner wird in dieser exemplarischen Vorgehensweise nicht verwendet; es ist ein Platzhalter für [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als der Host-Änderungen](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="d8041-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="d8041-140">Erstellen des Vertrags und Ansichten</span><span class="sxs-lookup"><span data-stu-id="d8041-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="d8041-141">Das Vertragssegment für diese Pipeline definiert die `ICalc1Contract` -Schnittstelle, die vier Methoden definiert: `add`, `subtract`, `multiply`, und `divide`.</span><span class="sxs-lookup"><span data-stu-id="d8041-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="d8041-142">Um den Vertrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8041-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="d8041-143">In der Visual Studio-Projektmappe, die mit dem Namen `CalculatorV1`öffnen die `Calc1Contract` Projekt.</span><span class="sxs-lookup"><span data-stu-id="d8041-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="d8041-144">In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1Contract` Projekt:</span><span class="sxs-lookup"><span data-stu-id="d8041-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="d8041-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="d8041-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="d8041-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="d8041-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="d8041-147">In **Projektmappen-Explorer**, schließen Sie die Standardklasse, die hinzugefügt werden, neue **Klassenbibliothek** Projekte.</span><span class="sxs-lookup"><span data-stu-id="d8041-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="d8041-148">In **Projektmappen-Explorer**, fügen Sie dem Projekt ein neues Element mit dem **Schnittstelle** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="d8041-149">In der **neues Element hinzufügen** klicken Sie im Dialogfeld die Namen der Schnittstelle `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="d8041-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="d8041-150">Fügen Sie Namespaceverweise hinzu, in der Schnittstellendatei <xref:System.AddIn.Contract> und <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="d8041-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="d8041-151">Verwenden Sie den folgenden Code zum Abschließen dieses Vertragssegment an.</span><span class="sxs-lookup"><span data-stu-id="d8041-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="d8041-152">Beachten Sie, dass diese Schnittstelle muss die <xref:System.AddIn.Pipeline.AddInContractAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="d8041-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="d8041-153">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="d8041-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="d8041-154">Die Lösung kann nicht ausgeführt werden, bis nach jeder Prozedur stellt sicher, dass jedes Projekt erstellen, aber im letzten Schritt korrigieren.</span><span class="sxs-lookup"><span data-stu-id="d8041-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="d8041-155">Da das Add-In-Ansicht und dem Host angezeigt das Add-in den gleichen Code, besonders in der ersten Version von einem Add-in in der Regel verfügen, können Sie problemlos die Ansichten zur gleichen Zeit erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8041-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="d8041-156">Sie unterscheiden sich nur ein Aspekt: die View-Add-in erfordert die <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut, während die Hostansicht des Add-in-Attribute nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="d8041-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="d8041-157">So erstellen Sie die Ansicht-Add-in</span><span class="sxs-lookup"><span data-stu-id="d8041-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="d8041-158">Hinzufügen eines neuen Projekts mit dem Namen `Calc1AddInView` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="d8041-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d8041-159">Basierend auf den **Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d8041-160">In **Projektmappen-Explorer**, fügen Sie einen Verweis auf System.AddIn.dll, um die `Calc1AddInView` Projekt.</span><span class="sxs-lookup"><span data-stu-id="d8041-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="d8041-161">In **Projektmappen-Explorer**, schließen Sie die Standardklasse, die hinzugefügt werden, neue **Klassenbibliothek** projiziert, und fügen Sie dem Projekt ein neues Element mit der **Schnittstelle** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="d8041-162">In der **neues Element hinzufügen** klicken Sie im Dialogfeld die Namen der Schnittstelle `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="d8041-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="d8041-163">Fügen Sie in der Schnittstellendatei einen Namespaceverweis hinzu <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="d8041-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="d8041-164">Verwenden Sie den folgenden Code in dieser Ansicht-add-in ausführen.</span><span class="sxs-lookup"><span data-stu-id="d8041-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="d8041-165">Beachten Sie, dass diese Schnittstelle muss die <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="d8041-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="d8041-166">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="d8041-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="d8041-167">Um die Hostansicht des Add-Ins zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8041-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="d8041-168">Hinzufügen eines neuen Projekts mit dem Namen `Calc1HVA` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="d8041-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d8041-169">Basierend auf den **Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d8041-170">In **Projektmappen-Explorer**, schließen Sie die Standardklasse, die hinzugefügt werden, neue **Klassenbibliothek** projiziert, und fügen Sie dem Projekt ein neues Element mit der **Schnittstelle** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="d8041-171">In der **neues Element hinzufügen** klicken Sie im Dialogfeld die Namen der Schnittstelle `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="d8041-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="d8041-172">Verwenden Sie in der Schnittstellendatei den folgenden Code, der die Hostansicht des Add-Ins abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d8041-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="d8041-173">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="d8041-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="d8041-174">Den Add-In-seitige Adapter erstellen</span><span class="sxs-lookup"><span data-stu-id="d8041-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="d8041-175">Dieses Add-In-seitige Adapter besteht aus einem Ansicht-zu-Vertrag-Adapter.</span><span class="sxs-lookup"><span data-stu-id="d8041-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="d8041-176">Dieses Pipelinesegment konvertiert die Typen aus der Add-In-Ansicht des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="d8041-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="d8041-177">In dieser Pipeline das Add-in bietet einen Dienst an dem Host, und die Typen, die aus dem Add-in auf den Host fließen.</span><span class="sxs-lookup"><span data-stu-id="d8041-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="d8041-178">Da keine Typen zwischen dem Host und Add-In-fließen, müssen Sie keinen Vertrag-zu-Ansicht-Adapter auf der Seite-Add-in dieser Pipeline aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="d8041-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="d8041-179">Den Add-In-seitige Adapter erstellen</span><span class="sxs-lookup"><span data-stu-id="d8041-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="d8041-180">Hinzufügen eines neuen Projekts mit dem Namen `Calc1AddInSideAdapter` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="d8041-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d8041-181">Basierend auf den **Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d8041-182">In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1AddInSideAdapter` Projekt:</span><span class="sxs-lookup"><span data-stu-id="d8041-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="d8041-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="d8041-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="d8041-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="d8041-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="d8041-185">Fügen Sie Projektverweise auf die Projekte für die benachbarten Pipelinesegmente hinzu:</span><span class="sxs-lookup"><span data-stu-id="d8041-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="d8041-186">Wählen Sie jeden Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** zu **"false"**.</span><span class="sxs-lookup"><span data-stu-id="d8041-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="d8041-187">Verwenden Sie in Visual Basic die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** zu **"false"** für die beiden Verweise Projekt.</span><span class="sxs-lookup"><span data-stu-id="d8041-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="d8041-188">Benennen Sie die Standardklasse des Projekts `CalculatorViewToContractAddInSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="d8041-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="d8041-189">Fügen Sie Namespaceverweise hinzu, in der Klassendatei <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="d8041-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="d8041-190">Fügen Sie in der Klassendatei Namespaceverweise für die benachbarten Segmente: `CalcAddInViews` und `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="d8041-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="d8041-191">(In Visual Basic sind diese Namespaceverweise `Calc1AddInView.CalcAddInViews` und `Calc1Contract.CalculatorContracts`, es sei denn, Sie die Standardnamespaces in Visual Basic-Projekte deaktiviert haben.)</span><span class="sxs-lookup"><span data-stu-id="d8041-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="d8041-192">Anwenden der <xref:System.AddIn.Pipeline.AddInAdapterAttribute> -Attribut auf die `CalculatorViewToContractAddInSideAdapter` -Klasse, um den Add-In-seitige Adapter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d8041-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="d8041-193">Stellen die `CalculatorViewToContractAddInSideAdapter` Klasse erben <xref:System.AddIn.Pipeline.ContractBase>, die bietet einer Standardimplementierung von der <xref:System.AddIn.Contract.IContract> Schnittstelle, und implementieren Sie die Vertragsschnittstelle für die Pipeline `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="d8041-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="d8041-194">Fügen Sie einen öffentlichen Konstruktor, die akzeptiert eine `ICalculator`, speichert es in einem privaten Feld und den Basisklassenkonstruktor aufruft.</span><span class="sxs-lookup"><span data-stu-id="d8041-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="d8041-195">Das Implementieren von `ICalc1Contract`, rufen Sie einfach die entsprechenden Membern von der `ICalculator` -Instanz, die an den Konstruktor übergeben wird, und die Ergebnisse zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d8041-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="d8041-196">Dadurch wird die Ansicht (`ICalculator`) für den Vertrag (`ICalc1Contract`).</span><span class="sxs-lookup"><span data-stu-id="d8041-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="d8041-197">Der folgende Code zeigt die vollständige Add-In-seitige Adapter.</span><span class="sxs-lookup"><span data-stu-id="d8041-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="d8041-198">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="d8041-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="d8041-199">Den hostseitige Adapter erstellen</span><span class="sxs-lookup"><span data-stu-id="d8041-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="d8041-200">Diese hostseitiger Adapter besteht aus einem Vertrag-zu-Ansicht-Adapter.</span><span class="sxs-lookup"><span data-stu-id="d8041-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="d8041-201">Dieses Segment passt sich an den Vertrag, der die Hostansicht des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="d8041-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="d8041-202">In dieser Pipeline bietet das Add-in einen Dienst auf dem Host und den Fluss von Typen aus dem Add-in auf den Host.</span><span class="sxs-lookup"><span data-stu-id="d8041-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="d8041-203">Da keine Typen zwischen dem Host und Add-In-fließen, müssen Sie keinen Ansicht-zu-Vertrag-Adapter enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8041-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="d8041-204">Verwenden Sie zum Implementieren der Verwaltung der Lebensdauer einer <xref:System.AddIn.Pipeline.ContractHandle> Lebensdauertoken für den Vertrag anzufügendes Objekt.</span><span class="sxs-lookup"><span data-stu-id="d8041-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="d8041-205">Sie müssen einen Verweis auf dieses Handle in der Reihenfolge für die Verwaltung der Prozesslebensdauer funktioniert beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d8041-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="d8041-206">Nachdem das Token angewendet wird, ist keine zusätzliche Programmierung erforderlich, da es sich bei der Add-in-System Objekte freigeben kann, wenn sie nicht mehr verwendet werden und für die Garbagecollection zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="d8041-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="d8041-207">Weitere Informationen finden Sie unter [Verwaltung der Lebensdauer](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="d8041-207">For more information, see [Lifetime Management](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="d8041-208">Den hostseitige Adapter erstellen</span><span class="sxs-lookup"><span data-stu-id="d8041-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="d8041-209">Hinzufügen eines neuen Projekts mit dem Namen `Calc1HostSideAdapter` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="d8041-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d8041-210">Basierend auf den **Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d8041-211">In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1HostSideAdapter` Projekt:</span><span class="sxs-lookup"><span data-stu-id="d8041-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="d8041-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="d8041-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="d8041-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="d8041-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="d8041-214">Fügen Sie Projektverweise auf die Projekte für die benachbarten Segmente hinzu:</span><span class="sxs-lookup"><span data-stu-id="d8041-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="d8041-215">Wählen Sie jeden Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** zu **"false"**.</span><span class="sxs-lookup"><span data-stu-id="d8041-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="d8041-216">Verwenden Sie in Visual Basic die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** zu **"false"** für die beiden Verweise Projekt.</span><span class="sxs-lookup"><span data-stu-id="d8041-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="d8041-217">Benennen Sie die Standardklasse des Projekts `CalculatorContractToViewHostSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="d8041-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="d8041-218">Fügen Sie Namespaceverweise hinzu, in der Klassendatei <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="d8041-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="d8041-219">Fügen Sie in der Klassendatei Namespaceverweise für die benachbarten Segmente: `CalcHVAs` und `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="d8041-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="d8041-220">(In Visual Basic sind diese Namespaceverweise `Calc1HVA.CalcHVAs` und `Calc1Contract.CalculatorContracts`, es sei denn, Sie die Standardnamespaces in Visual Basic-Projekte deaktiviert haben.)</span><span class="sxs-lookup"><span data-stu-id="d8041-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="d8041-221">Anwenden der <xref:System.AddIn.Pipeline.HostAdapterAttribute> -Attribut auf die `CalculatorContractToViewHostSideAdapter` -Klasse, um das Segment der hostseitige Adapter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d8041-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="d8041-222">Stellen Sie die `CalculatorContractToViewHostSideAdapter` Klasse implementiert die Schnittstelle, der die Hostansicht des Add-Ins darstellt: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d8041-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="d8041-223">Fügen Sie einen öffentlichen Konstruktor, die den Vertragstyp der Pipeline akzeptiert `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="d8041-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="d8041-224">Der Konstruktor muss den Verweis auf den Vertrag zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="d8041-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="d8041-225">Sie müssen auch erstellen und einen neuen cache <xref:System.AddIn.Pipeline.ContractHandle> für den Vertrag, zum Verwalten der Lebensdauer des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="d8041-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d8041-226">Die <xref:System.AddIn.Pipeline.ContractHandle> ist entscheidend für die Verwaltung der Lebensdauer.</span><span class="sxs-lookup"><span data-stu-id="d8041-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="d8041-227">Wenn Sie nicht behalten Sie einen Verweis auf die <xref:System.AddIn.Pipeline.ContractHandle> -Objekts können Garbagecollection freigegeben wird, und die Pipeline wird heruntergefahren, wenn das Programm nicht erwartet wurden.</span><span class="sxs-lookup"><span data-stu-id="d8041-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="d8041-228">Dies kann zu Fehlern führen, die schwer zu diagnostizieren, z. B. <xref:System.AppDomainUnloadedException>.</span><span class="sxs-lookup"><span data-stu-id="d8041-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="d8041-229">Das Herunterfahren ist eine normale Phase im Lebenszyklus einer Pipeline, daher keine Möglichkeit für die Lebensdauer Management Code besteht erkennen, dass diese Bedingung ein Fehler ist.</span><span class="sxs-lookup"><span data-stu-id="d8041-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="d8041-230">Das Implementieren von `ICalculator`, rufen Sie einfach die entsprechenden Membern von der `ICalc1Contract` -Instanz, die an den Konstruktor übergeben wird, und die Ergebnisse zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d8041-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="d8041-231">Dadurch wird der Vertrag (`ICalc1Contract`) an die Ansicht (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="d8041-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="d8041-232">Der folgende Code zeigt die abgeschlossenen hostseitiger Adapter.</span><span class="sxs-lookup"><span data-stu-id="d8041-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="d8041-233">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="d8041-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="d8041-234">Erstellen des Hosts</span><span class="sxs-lookup"><span data-stu-id="d8041-234">Creating the Host</span></span>  
 <span data-ttu-id="d8041-235">Eine hostanwendung interagiert mit dem Add-in durch die Hostansicht des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="d8041-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="d8041-236">Er verwendet die Add-In-Suche und Aktivierung von bereitgestellte Methoden die <xref:System.AddIn.Hosting.AddInStore> und <xref:System.AddIn.Hosting.AddInToken> Klassen die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="d8041-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="d8041-237">Aktualisieren Sie den Cache der Pipeline- und Add-in-Informationen.</span><span class="sxs-lookup"><span data-stu-id="d8041-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="d8041-238">Finden Sie Add-Ins den Hosttyp Ansicht `ICalculator`, unter dem Stammverzeichnis für die angegebene Pipeline.</span><span class="sxs-lookup"><span data-stu-id="d8041-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="d8041-239">Der Benutzer aufgefordert, geben Sie die-add-in verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8041-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="d8041-240">Aktivieren Sie das ausgewählte Add-in in einer neuen Anwendungsdomäne mit einer angegebenen Sicherheitsvertrauensebene.</span><span class="sxs-lookup"><span data-stu-id="d8041-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="d8041-241">Führen Sie die benutzerdefinierte `RunCalculator` -Methode, die das Add-in-Methoden gemäß die Hostansicht des Add-Ins aufruft.</span><span class="sxs-lookup"><span data-stu-id="d8041-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="d8041-242">Zum Erstellen des Hosts</span><span class="sxs-lookup"><span data-stu-id="d8041-242">To create the host</span></span>  
  
1.  <span data-ttu-id="d8041-243">Hinzufügen eines neuen Projekts mit dem Namen `Calc1Host` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="d8041-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d8041-244">Basierend auf den **Konsolenanwendung** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="d8041-245">In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die Assembly System.AddIn.dll, um die `Calc1Host` Projekt.</span><span class="sxs-lookup"><span data-stu-id="d8041-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="d8041-246">Fügen Sie einen Projektverweis auf die `Calc1HVA` Projekt.</span><span class="sxs-lookup"><span data-stu-id="d8041-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="d8041-247">Wählen Sie den Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** zu **"false"**.</span><span class="sxs-lookup"><span data-stu-id="d8041-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="d8041-248">Verwenden Sie in Visual Basic die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** zu **"false"**.</span><span class="sxs-lookup"><span data-stu-id="d8041-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="d8041-249">Benennen Sie die Klassendatei (Modul in Visual Basic) `MathHost1`.</span><span class="sxs-lookup"><span data-stu-id="d8041-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="d8041-250">Verwenden Sie in Visual Basic die **Anwendung** Registerkarte die **Projekteigenschaften** Dialogfeld **Startobjekt** zu **Sub Main**.</span><span class="sxs-lookup"><span data-stu-id="d8041-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="d8041-251">Fügen Sie in der Klasse oder das Modul-Datei einen Namespaceverweis hinzu <xref:System.AddIn.Hosting>.</span><span class="sxs-lookup"><span data-stu-id="d8041-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="d8041-252">Fügen Sie in der Klasse oder das Modul-Datei einen Namespaceverweis für die Hostansicht des Add-Ins: `CalcHVAs`.</span><span class="sxs-lookup"><span data-stu-id="d8041-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="d8041-253">(In Visual Basic wird dieser Namespaceverweis ist `Calc1HVA.CalcHVAs`, es sei denn, Sie die Standardnamespaces in Visual Basic-Projekte deaktiviert haben.)</span><span class="sxs-lookup"><span data-stu-id="d8041-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="d8041-254">In **Projektmappen-Explorer**, wählen Sie die Projektmappe und aus der **Projekt** Menü **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d8041-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="d8041-255">In der **Eigenschaftenseiten für Projektmappen** (Dialogfeld), legen die **einzelnes Startprojekt** dieser Hostanwendungsprojekt sein.</span><span class="sxs-lookup"><span data-stu-id="d8041-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="d8041-256">Verwenden Sie in der Datei Klasse oder das Modul die <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> Methode, um den Cache zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d8041-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="d8041-257">Verwenden Sie die <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> Methode, um eine Auflistung von Token abrufen und Verwenden der <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> Methode, um ein Add-in zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d8041-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="d8041-258">Der folgende Code zeigt die abgeschlossene hostanwendung.</span><span class="sxs-lookup"><span data-stu-id="d8041-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="d8041-259">Dieser Code wird davon ausgegangen, dass die Pipeline-Ordnerstruktur im Ordner Anwendung befindet.</span><span class="sxs-lookup"><span data-stu-id="d8041-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="d8041-260">Ändern Sie die Zeile von Code, der festlegt, wenn Sie sie an anderer Stelle befindet, die `addInRoot` -Variablen so, dass die Variable den Pfad zu der Pipelineverzeichnisstruktur enthält.</span><span class="sxs-lookup"><span data-stu-id="d8041-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="d8041-261">Der Code verwendet ein `ChooseCalculator` Methode, die Token aufgeführt und fordert den Benutzer auf ein Add-in auswählen.</span><span class="sxs-lookup"><span data-stu-id="d8041-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="d8041-262">Die `RunCalculator` Methode fordert den Benutzer einfache mathematische Ausdrücke, analysiert die Ausdrücke mithilfe der `Parser` -Klasse, und zeigt die Ergebnisse zurückgegeben werden, indem Sie das Add-in.</span><span class="sxs-lookup"><span data-stu-id="d8041-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="d8041-263">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="d8041-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="d8041-264">Erstellen das Add-In</span><span class="sxs-lookup"><span data-stu-id="d8041-264">Creating the Add-In</span></span>  
 <span data-ttu-id="d8041-265">Ein Add-in implementiert die Methoden, die von der Add-In-Ansicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="d8041-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="d8041-266">Dieses add-in implementiert die `Add`, `Subtract`, `Multiply`, und `Divide` Vorgänge und gibt die Ergebnisse an den Host zurück.</span><span class="sxs-lookup"><span data-stu-id="d8041-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="d8041-267">Um das Add-in zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8041-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="d8041-268">Hinzufügen eines neuen Projekts mit dem Namen `AddInCalcV1` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="d8041-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="d8041-269">Basierend auf den **Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d8041-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="d8041-270">In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die System.AddIn.dll-Assembly zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="d8041-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="d8041-271">Fügen Sie einen Projektverweis auf die `Calc1AddInView` Projekt.</span><span class="sxs-lookup"><span data-stu-id="d8041-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="d8041-272">Wählen Sie den Projektverweis, und klicken Sie in **Eigenschaften**legen **lokale Kopie** zu **"false"**.</span><span class="sxs-lookup"><span data-stu-id="d8041-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="d8041-273">Verwenden Sie in Visual Basic die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** zu **"false"** für den Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="d8041-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="d8041-274">Benennen Sie die Klasse `AddInCalcV1`.</span><span class="sxs-lookup"><span data-stu-id="d8041-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="d8041-275">Fügen Sie in der Klassendatei einen Namespaceverweis hinzu <xref:System.AddIn> und das Add-In-Ansichtssegment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d8041-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="d8041-276">Anwenden der <xref:System.AddIn.AddInAttribute> -Attribut auf die `AddInCalcV1` -Klasse, um die Klasse als ein Add-in zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d8041-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="d8041-277">Stellen Sie die `AddInCalcV1` Klasse implementiert die Schnittstelle, die die Add-In-Ansicht darstellt: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d8041-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="d8041-278">Implementieren Sie die Mitglieder der `ICalculator` werden die Ergebnisse der entsprechenden Berechnungen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d8041-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="d8041-279">Der folgende Code zeigt die abgeschlossene-add-in.</span><span class="sxs-lookup"><span data-stu-id="d8041-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="d8041-280">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="d8041-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="d8041-281">Bereitstellen der Pipeline</span><span class="sxs-lookup"><span data-stu-id="d8041-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="d8041-282">Sie können nun zum Erstellen und Bereitstellen von Add-in-Segmente in der Pipelineverzeichnisstruktur erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d8041-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="d8041-283">Die Segmente an die Pipeline bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d8041-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="d8041-284">Verwenden Sie für jedes Projekt in der Projektmappe, die **erstellen** Registerkarte **Projekteigenschaften** (die **Kompilieren** Registerkarte in Visual Basic) zum Festlegen des Werts von der **Ausgabepfad**  (die **Buildausgabepfad** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d8041-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="d8041-285">Wenn Sie den Anwendungsordner Namen `MyApp`, z. B. würden Ihre Projekte erstellen, in den folgenden Ordnern:</span><span class="sxs-lookup"><span data-stu-id="d8041-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="d8041-286">Projekt</span><span class="sxs-lookup"><span data-stu-id="d8041-286">Project</span></span>|<span data-ttu-id="d8041-287">Pfad</span><span class="sxs-lookup"><span data-stu-id="d8041-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="d8041-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="d8041-288">AddInCalcV1</span></span>|<span data-ttu-id="d8041-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="d8041-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="d8041-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="d8041-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="d8041-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="d8041-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="d8041-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="d8041-292">Calc1AddInView</span></span>|<span data-ttu-id="d8041-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="d8041-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="d8041-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="d8041-294">Calc1Contract</span></span>|<span data-ttu-id="d8041-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="d8041-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="d8041-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="d8041-296">Calc1Host</span></span>|<span data-ttu-id="d8041-297">"MyApp"</span><span class="sxs-lookup"><span data-stu-id="d8041-297">MyApp</span></span>|  
    |<span data-ttu-id="d8041-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="d8041-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="d8041-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="d8041-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="d8041-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="d8041-300">Calc1HVA</span></span>|<span data-ttu-id="d8041-301">"MyApp"</span><span class="sxs-lookup"><span data-stu-id="d8041-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d8041-302">Wenn Sie sich entschieden, die Ordnerstruktur für die Pipeline in einem anderen Speicherort als den Anwendungsordner, müssen Sie die Pfade in der Tabelle aufgeführt sind, entsprechend ändern.</span><span class="sxs-lookup"><span data-stu-id="d8041-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="d8041-303">Finden Sie in den Ausführungen der Pipeline verzeichnisanforderungen in [Anforderungen für die Pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="d8041-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="d8041-304">Erstellen Sie die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="d8041-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="d8041-305">Überprüfen Sie die Anwendung und die Pipeline Verzeichnisse, um sicherzustellen, dass die Assemblys in den richtigen Verzeichnissen kopiert wurden und keine zusätzlichen Kopien der Assemblys in den falschen Ordnern installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d8041-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8041-306">Wenn Sie nicht geändert haben **lokale Kopie** zu **"false"** für die `Calc1AddInView` Projektverweise in der `AddInCalcV1` Projekt Ladeprogramm Kontext Probleme verhindert das Add-in gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d8041-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="d8041-307">Informationen zum Bereitstellen von für die Pipeline finden Sie unter [Anforderungen für die Pipelineentwicklung](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="d8041-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="d8041-308">Die Hostanwendung ausführen</span><span class="sxs-lookup"><span data-stu-id="d8041-308">Running the Host Application</span></span>  
 <span data-ttu-id="d8041-309">Sie können nun führen Sie den Host aus, und interagieren mit der Add-in.</span><span class="sxs-lookup"><span data-stu-id="d8041-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="d8041-310">Die hostanwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d8041-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="d8041-311">Klicken Sie an der Eingabeaufforderung, wechseln Sie zum Verzeichnis Anwendung, und führen Sie die hostanwendung, `Calc1Host.exe`.</span><span class="sxs-lookup"><span data-stu-id="d8041-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="d8041-312">Der Host alle verfügbare Add-Ins dieses Typs sucht und fordert Sie zum Auswählen eines Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="d8041-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="d8041-313">Geben Sie **1** für das nur verfügbar, add-in.</span><span class="sxs-lookup"><span data-stu-id="d8041-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="d8041-314">Geben Sie eine Formel für den Rechner, z. B. **2 + 2**.</span><span class="sxs-lookup"><span data-stu-id="d8041-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="d8041-315">Leerzeichen zwischen den Zahlen und den Operator muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d8041-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="d8041-316">Typ **beenden** , und drücken Sie die **EINGABETASTE** Taste, um die Anwendung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="d8041-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8041-317">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8041-317">See Also</span></span>  
- [<span data-ttu-id="d8041-318">Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität bei geändertem Host</span><span class="sxs-lookup"><span data-stu-id="d8041-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
-  [<span data-ttu-id="d8041-319">Exemplarische Vorgehensweise: Übergeben von Auflistungen zwischen Hosts und -Add-Ins</span><span class="sxs-lookup"><span data-stu-id="d8041-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
-  [<span data-ttu-id="d8041-320">Anforderungen für die pipelineentwicklung</span><span class="sxs-lookup"><span data-stu-id="d8041-320">Pipeline Development Requirements</span></span>](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
-  [<span data-ttu-id="d8041-321">Verträge, Ansichten und Adapter</span><span class="sxs-lookup"><span data-stu-id="d8041-321">Contracts, Views, and Adapters</span></span>](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
-  [<span data-ttu-id="d8041-322">Pipelineentwicklung</span><span class="sxs-lookup"><span data-stu-id="d8041-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)
