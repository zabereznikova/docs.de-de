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
ms.openlocfilehash: 292447fa3cf2dbad70dbfef32b7c184b250ed25e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="50206-102">Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen</span><span class="sxs-lookup"><span data-stu-id="50206-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="50206-103">In dieser exemplarischen Vorgehensweise beschreibt, wie eine Pipeline für ein Add-in zu erstellen, das einfachen Rechnerfunktionen ausführt.</span><span class="sxs-lookup"><span data-stu-id="50206-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="50206-104">Es wird nicht auf einem realen Szenario veranschaulicht; Stattdessen stellt es die grundlegende Funktionalität eines einer Pipeline und wie ein Add-in Dienste für einen Host bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="50206-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="50206-105">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben beschrieben:</span><span class="sxs-lookup"><span data-stu-id="50206-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="50206-106">Erstellen eine Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50206-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="50206-107">Erstellen die Verzeichnisstruktur für die Pipeline an.</span><span class="sxs-lookup"><span data-stu-id="50206-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="50206-108">Der Vertrag und Ansichten werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="50206-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="50206-109">Erstellen die Add-In-seitiger Adapter.</span><span class="sxs-lookup"><span data-stu-id="50206-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="50206-110">Erstellen des hostseitige Adapters an.</span><span class="sxs-lookup"><span data-stu-id="50206-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="50206-111">Erstellen den Host.</span><span class="sxs-lookup"><span data-stu-id="50206-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="50206-112">Erstellen das Add-in.</span><span class="sxs-lookup"><span data-stu-id="50206-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="50206-113">Bereitstellen der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="50206-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="50206-114">Die hostanwendung wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="50206-114">Running the host application.</span></span>  
  
 <span data-ttu-id="50206-115">Diese Pipeline übergibt nur serialisierbare Typen (<xref:System.Double> und <xref:System.String>), zwischen dem Host und das Add-in.</span><span class="sxs-lookup"><span data-stu-id="50206-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="50206-116">Ein Beispiel, das zeigt, wie Auflistungen von komplexen Datentypen übergeben werden, finden Sie unter [Exemplarische Vorgehensweise: Übergeben von Sammlungen zwischen Hosts und -Add-Ins](http://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span><span class="sxs-lookup"><span data-stu-id="50206-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](http://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="50206-117">Der Vertrag für diese Pipeline definiert ein Objektmodell aus vier arithmetischen Operationen: hinzufügen, subtrahieren, Multiplizieren und Dividieren.</span><span class="sxs-lookup"><span data-stu-id="50206-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="50206-118">Der Host stellt das Add-in mit einer Formel zum Berechnen, wie z. B. 2 + 2, und das Add-in gibt das Ergebnis an den Host zurück.</span><span class="sxs-lookup"><span data-stu-id="50206-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="50206-119">Version 2 des Rechner-add-Ins bietet mehr berechnen Möglichkeiten und versionsverwaltung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="50206-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="50206-120">Es wird beschrieben, [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als der Host Änderungen](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="50206-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="50206-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="50206-121">Prerequisites</span></span>  
 <span data-ttu-id="50206-122">Für diese exemplarische Vorgehensweise wird Folgendes benötigt:</span><span class="sxs-lookup"><span data-stu-id="50206-122">You need the following to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="50206-123">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="50206-123">Visual Studio.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="50206-124">Erstellen einer Visual Studio-Projektmappe</span><span class="sxs-lookup"><span data-stu-id="50206-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="50206-125">Verwenden Sie eine Projektmappe in Visual Studio, um die Projekte der Pipelinesegmente enthalten.</span><span class="sxs-lookup"><span data-stu-id="50206-125">Use a solution in Visual Studio to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="50206-126">Zum Erstellen der Pipeline-Lösung</span><span class="sxs-lookup"><span data-stu-id="50206-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="50206-127">Erstellen Sie in Visual Studio ein neues Projekt mit dem Namen `Calc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="50206-127">In Visual Studio, create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="50206-128">Basierend auf den **-Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="50206-129">Nennen Sie die Projektmappe `CalculatorV1`.</span><span class="sxs-lookup"><span data-stu-id="50206-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="50206-130">Erstellen der Pipelineverzeichnisstruktur</span><span class="sxs-lookup"><span data-stu-id="50206-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="50206-131">Das Add-In Modell erfordert, dass die Pipeline Segment Assemblys in einer angegebenen Verzeichnisstruktur platziert werden.</span><span class="sxs-lookup"><span data-stu-id="50206-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="50206-132">Weitere Informationen über die Pipelinestruktur finden Sie unter [Pipelineentwicklung](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="50206-132">For more information about the pipeline structure, see [Pipeline Development Requirements](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="50206-133">Zum Erstellen der Pipeline-Verzeichnisstruktur</span><span class="sxs-lookup"><span data-stu-id="50206-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="50206-134">Erstellen Sie einen Anwendungsordner an einer beliebigen Stelle auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="50206-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="50206-135">Erstellen Sie in diesem Ordner die folgende Struktur:</span><span class="sxs-lookup"><span data-stu-id="50206-135">In that folder, create the following structure:</span></span>  
  
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
  
     <span data-ttu-id="50206-136">Es ist nicht erforderlich, platzieren die Ordnerstruktur für die Pipeline in Ihrem Anwendungsordner; Dies erfolgt hier nur zur Vereinfachung für.</span><span class="sxs-lookup"><span data-stu-id="50206-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="50206-137">Den entsprechenden Schritt wird die exemplarischen Vorgehensweise erläutert, wie den Code ändern, wenn die Ordnerstruktur für die Pipeline an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="50206-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="50206-138">Finden Sie in den Ausführungen des Pipeline-Directory-Anforderungen in [Pipelineentwicklung](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="50206-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50206-139">Die `CalcV2` Ordner wird in dieser exemplarischen Vorgehensweise nicht verwendet; es ist ein Platzhalter für [Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als der Host Änderungen](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="50206-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="50206-140">Der Vertrag und Ansichten werden erstellt</span><span class="sxs-lookup"><span data-stu-id="50206-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="50206-141">Das Vertragssegment für diese Pipeline definiert die `ICalc1Contract` -Schnittstelle, die vier Methoden definiert: `add`, `subtract`, `multiply`, und `divide`.</span><span class="sxs-lookup"><span data-stu-id="50206-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="50206-142">Um den Vertrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="50206-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="50206-143">In der Visual Studio-Projektmappe mit dem Namen `CalculatorV1`öffnen die `Calc1Contract` Projekt.</span><span class="sxs-lookup"><span data-stu-id="50206-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="50206-144">In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1Contract` Projekt:</span><span class="sxs-lookup"><span data-stu-id="50206-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="50206-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="50206-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="50206-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="50206-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="50206-147">In **Projektmappen-Explorer**, schließen Sie die Standardklasse, die hinzugefügt werden, neue **-Klassenbibliothek** Projekte.</span><span class="sxs-lookup"><span data-stu-id="50206-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="50206-148">In **Projektmappen-Explorer**, Hinzufügen eines neuen Elements zum Projekt mit der **Schnittstelle** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="50206-149">In der **neues Element hinzufügen** (Dialogfeld), Name der Schnittstelle `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="50206-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="50206-150">Fügen Sie Namespaceverweise hinzu, in der Schnittstellendatei <xref:System.AddIn.Contract> und <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="50206-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="50206-151">Verwenden Sie den folgenden Code, um dieses Vertragssegment abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="50206-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="50206-152">Beachten Sie, dass diese Schnittstelle muss das <xref:System.AddIn.Pipeline.AddInContractAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="50206-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="50206-153">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50206-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="50206-154">Die Lösung kann nicht ausgeführt werden, bis nach jeder Prozedur stellt sicher, dass jedes Projekt erstellen, aber mit dem abschließenden Verfahren korrigieren.</span><span class="sxs-lookup"><span data-stu-id="50206-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="50206-155">Da die Add-In-Ansicht und der Host des anzeigen das Add-in den gleichen Code, besonders in der ersten Version von einem Add-in in der Regel haben, können Sie problemlos Ansichten zur gleichen Zeit erstellt.</span><span class="sxs-lookup"><span data-stu-id="50206-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="50206-156">Sie unterscheiden sich nur eine einstufige: die View-Add-in erfordert die <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut, während die Hostansicht des Add-Ins keine Attribute erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="50206-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="50206-157">So erstellen Sie die Add-In-Ansicht</span><span class="sxs-lookup"><span data-stu-id="50206-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="50206-158">Fügen Sie ein neues Projekt mit dem Namen `Calc1AddInView` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="50206-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="50206-159">Basierend auf den **-Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="50206-160">In **Projektmappen-Explorer**, fügen Sie einen Verweis auf System.AddIn.dll auf die `Calc1AddInView` Projekt.</span><span class="sxs-lookup"><span data-stu-id="50206-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="50206-161">In **Projektmappen-Explorer**, schließen Sie die Standardklasse, das hinzugefügt wird, neu **-Klassenbibliothek** -Projekten und Hinzufügen eines neuen Elements zum Projekt mit der **Schnittstelle** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="50206-162">In der **neues Element hinzufügen** (Dialogfeld), Name der Schnittstelle `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="50206-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="50206-163">Fügen Sie in der Schnittstellendatei einen Namespaceverweis auf <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="50206-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="50206-164">Verwenden Sie den folgenden Code, um diese Add-In-Ansicht abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="50206-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="50206-165">Beachten Sie, dass diese Schnittstelle muss das <xref:System.AddIn.Pipeline.AddInBaseAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="50206-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="50206-166">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50206-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="50206-167">So erstellen die Hostansicht des Add-Ins</span><span class="sxs-lookup"><span data-stu-id="50206-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="50206-168">Fügen Sie ein neues Projekt mit dem Namen `Calc1HVA` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="50206-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="50206-169">Basierend auf den **-Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="50206-170">In **Projektmappen-Explorer**, schließen Sie die Standardklasse, das hinzugefügt wird, neu **-Klassenbibliothek** -Projekten und Hinzufügen eines neuen Elements zum Projekt mit der **Schnittstelle** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="50206-171">In der **neues Element hinzufügen** (Dialogfeld), Name der Schnittstelle `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="50206-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="50206-172">Verwenden Sie den folgenden Code in der Schnittstellendatei zum Abschließen der Hostansicht des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="50206-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="50206-173">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50206-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="50206-174">Erstellen die Add-In-seitiger Adapter</span><span class="sxs-lookup"><span data-stu-id="50206-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="50206-175">Dieses Add-In-seitiger Adapter besteht aus einem Ansicht-zu-Vertrag-Adapter.</span><span class="sxs-lookup"><span data-stu-id="50206-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="50206-176">Dieses Pipelinesegment konvertiert die Typen aus der Add-In-Ansicht mit dem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="50206-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="50206-177">In dieser Pipeline das Add-in bietet einen Dienst auf dem Host, und die Typen, die aus dem Add-in auf dem Host fließen.</span><span class="sxs-lookup"><span data-stu-id="50206-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="50206-178">Da keine Typen vom Host für die Add-in übergeben, müssen Sie keinen Vertrag-zu-Ansicht-Adapter auf der Add-in-Seite dieser Pipeline aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="50206-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="50206-179">Den Add-In-seitiger Adapter erstellen</span><span class="sxs-lookup"><span data-stu-id="50206-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="50206-180">Fügen Sie ein neues Projekt mit dem Namen `Calc1AddInSideAdapter` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="50206-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="50206-181">Basierend auf den **-Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="50206-182">In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1AddInSideAdapter` Projekt:</span><span class="sxs-lookup"><span data-stu-id="50206-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="50206-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="50206-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="50206-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="50206-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="50206-185">Fügen Sie Projektverweise die Projekte für die benachbarten Pipelinesegmente hinzu:</span><span class="sxs-lookup"><span data-stu-id="50206-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="50206-186">Wählen Sie jede Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** auf **"false"**.</span><span class="sxs-lookup"><span data-stu-id="50206-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="50206-187">In Visual Basic verwenden die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** auf **"false"** für die beiden Verweise Projekt.</span><span class="sxs-lookup"><span data-stu-id="50206-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="50206-188">Benennen Sie das Projekt Standardklasse `CalculatorViewToContractAddInSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="50206-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="50206-189">Fügen Sie Namespaceverweise hinzu, in der Klassendatei <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="50206-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="50206-190">Fügen Sie in der Klassendatei Namespaceverweise für die benachbarten Segmente: `CalcAddInViews` und `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="50206-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="50206-191">(In Visual Basic werden diese Namespaceverweise `Calc1AddInView.CalcAddInViews` und `Calc1Contract.CalculatorContracts`, es sei denn, Sie in Visual Basic-Projekte die Standardnamespaces deaktiviert haben.)</span><span class="sxs-lookup"><span data-stu-id="50206-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="50206-192">Anwenden der <xref:System.AddIn.Pipeline.AddInAdapterAttribute> -Attribut auf die `CalculatorViewToContractAddInSideAdapter` -Klasse, um es als die Add-In-seitiger Adapter zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="50206-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="50206-193">Stellen Sie die `CalculatorViewToContractAddInSideAdapter` Klasse erben <xref:System.AddIn.Pipeline.ContractBase>, stellt eine Standardimplementierung von der <xref:System.AddIn.Contract.IContract> Schnittstelle, und implementieren Sie die Vertragsschnittstelle für die Pipeline `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="50206-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="50206-194">Fügen Sie einen öffentlichen Konstruktor, das akzeptiert ein `ICalculator`, speichert es in einem privaten Feld und der Basisklassenkonstruktor aufruft.</span><span class="sxs-lookup"><span data-stu-id="50206-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="50206-195">Das Implementieren von `ICalc1Contract`, rufen Sie einfach die entsprechenden Mitgliedern von der `ICalculator` Instanz, die an den Konstruktor übergeben wird, und die Ergebnisse zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="50206-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="50206-196">Dadurch wird die Ansicht (`ICalculator`) mit dem Vertrag (`ICalc1Contract`).</span><span class="sxs-lookup"><span data-stu-id="50206-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="50206-197">Der folgende Code zeigt die vollständige Add-In-seitiger Adapter.</span><span class="sxs-lookup"><span data-stu-id="50206-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="50206-198">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50206-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="50206-199">Den hostseitige Adapter erstellen</span><span class="sxs-lookup"><span data-stu-id="50206-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="50206-200">Dieser hostseitige Adapter besteht aus einem Vertrag-zu-Ansicht-Adapter.</span><span class="sxs-lookup"><span data-stu-id="50206-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="50206-201">Dieses Segment wird der Vertrag, der die Hostansicht des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="50206-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="50206-202">In dieser Pipeline bietet das Add-in einen Dienst auf dem Host und den Fluss von Typen aus dem Add-in auf dem Host.</span><span class="sxs-lookup"><span data-stu-id="50206-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="50206-203">Da keine Typen vom Host für die Add-in übergeben, müssen Sie keinen Ansicht zu Vertrag-Adapter enthalten.</span><span class="sxs-lookup"><span data-stu-id="50206-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="50206-204">Verwenden Sie zum Implementieren der Verwaltung der Lebensdauer einer <xref:System.AddIn.Pipeline.ContractHandle> ein Lebensdauertoken der Vertrag anzufügende Objekt.</span><span class="sxs-lookup"><span data-stu-id="50206-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="50206-205">Sie müssen einen Verweis auf dieses Handle in der Reihenfolge für die Verwaltung der Objektlebensdauer zu behalten.</span><span class="sxs-lookup"><span data-stu-id="50206-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="50206-206">Nachdem das Token angewendet wird, ist keine zusätzliche Programmierung erforderlich, da das Add-in-System Objekte freigeben kann, wenn sie nicht mehr verwendet werden und für die Garbagecollection zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="50206-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="50206-207">Weitere Informationen finden Sie unter [Lebenszeitverwaltung](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="50206-207">For more information, see [Lifetime Management](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="50206-208">So erstellen Sie die hostseitige adapter</span><span class="sxs-lookup"><span data-stu-id="50206-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="50206-209">Fügen Sie ein neues Projekt mit dem Namen `Calc1HostSideAdapter` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="50206-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="50206-210">Basierend auf den **-Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="50206-211">In **Projektmappen-Explorer**, fügen Sie Verweise auf die folgenden Assemblys, die `Calc1HostSideAdapter` Projekt:</span><span class="sxs-lookup"><span data-stu-id="50206-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="50206-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="50206-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="50206-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="50206-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="50206-214">Fügen Sie Projektverweise für die Projekte für die benachbarten Segmente hinzu:</span><span class="sxs-lookup"><span data-stu-id="50206-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="50206-215">Wählen Sie jede Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** auf **"false"**.</span><span class="sxs-lookup"><span data-stu-id="50206-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="50206-216">In Visual Basic verwenden die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** auf **"false"** für die beiden Verweise Projekt.</span><span class="sxs-lookup"><span data-stu-id="50206-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="50206-217">Benennen Sie das Projekt Standardklasse `CalculatorContractToViewHostSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="50206-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="50206-218">Fügen Sie Namespaceverweise hinzu, in der Klassendatei <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="50206-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="50206-219">Fügen Sie in der Klassendatei Namespaceverweise für die benachbarten Segmente: `CalcHVAs` und `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="50206-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="50206-220">(In Visual Basic werden diese Namespaceverweise `Calc1HVA.CalcHVAs` und `Calc1Contract.CalculatorContracts`, es sei denn, Sie in Visual Basic-Projekte die Standardnamespaces deaktiviert haben.)</span><span class="sxs-lookup"><span data-stu-id="50206-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="50206-221">Anwenden der <xref:System.AddIn.Pipeline.HostAdapterAttribute> -Attribut auf die `CalculatorContractToViewHostSideAdapter` -Klasse, um es als das Adaptersegment hostseitige zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="50206-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="50206-222">Stellen Sie die `CalculatorContractToViewHostSideAdapter` Klasse implementiert die Schnittstelle, die die Hostansicht des Add-Ins darstellt: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="50206-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="50206-223">Fügen Sie einen öffentlichen Konstruktor, der den Typ des Pipeline-Vertrags akzeptiert `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="50206-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="50206-224">Der Konstruktor, muss den Verweis auf den Vertrag zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="50206-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="50206-225">Sie müssen auch erstellen und einen neuen cache <xref:System.AddIn.Pipeline.ContractHandle> für den Vertrag, zum Verwalten der Lebensdauer des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="50206-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="50206-226">Die <xref:System.AddIn.Pipeline.ContractHandle> für die Verwaltung der Lebensdauer von entscheidender Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="50206-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="50206-227">Wenn Sie ein Failover zu einem Verweis auf die <xref:System.AddIn.Pipeline.ContractHandle> -Objekts können Garbagecollection freigegeben, und die Pipeline wird heruntergefahren, wenn das Programm nicht erwartet.</span><span class="sxs-lookup"><span data-stu-id="50206-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="50206-228">Dies kann zu Fehlern, die schwer zu diagnostizieren, wie z. B. sind <xref:System.AppDomainUnloadedException>.</span><span class="sxs-lookup"><span data-stu-id="50206-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="50206-229">Shutdown ist eine normale Phase während der Lebensdauer einer Pipeline, daher keine Möglichkeit für die Lebensdauer Management Code besteht erkennen, dass diese Bedingung ein Fehler ist.</span><span class="sxs-lookup"><span data-stu-id="50206-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="50206-230">Das Implementieren von `ICalculator`, rufen Sie einfach die entsprechenden Mitgliedern von der `ICalc1Contract` Instanz, die an den Konstruktor übergeben wird, und die Ergebnisse zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="50206-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="50206-231">Dadurch wird der Vertrag (`ICalc1Contract`) zur Ansicht (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="50206-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="50206-232">Der folgende Code zeigt die vollständige hostseitige Adapter.</span><span class="sxs-lookup"><span data-stu-id="50206-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="50206-233">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50206-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="50206-234">Erstellen des Hosts</span><span class="sxs-lookup"><span data-stu-id="50206-234">Creating the Host</span></span>  
 <span data-ttu-id="50206-235">Eine hostanwendung interagiert mit dem Add-in über die Hostansicht des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="50206-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="50206-236">Add-In-Suche und Aktivierung von bereitgestellte Methoden verwendet die <xref:System.AddIn.Hosting.AddInStore> und <xref:System.AddIn.Hosting.AddInToken> Klassen, die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="50206-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="50206-237">Aktualisieren des Caches der Pipeline und Add-in-Informationen an.</span><span class="sxs-lookup"><span data-stu-id="50206-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="50206-238">Suchen-add-ins von den Hosttyp Ansicht `ICalculator`, unter dem Stammverzeichnis des angegebenen Pipeline.</span><span class="sxs-lookup"><span data-stu-id="50206-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="50206-239">Der Benutzer aufgefordert, geben Sie die add-in verwenden.</span><span class="sxs-lookup"><span data-stu-id="50206-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="50206-240">Aktivieren Sie die ausgewählten Add-Ins in eine neue Anwendungsdomäne mit der angegebenen Vertrauenswürdigkeit Sicherheitsstufe.</span><span class="sxs-lookup"><span data-stu-id="50206-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="50206-241">Führen Sie das benutzerdefinierte `RunCalculator` -Methode, die das Add-in Methoden gemäß der Hostansicht des Add-Ins aufruft.</span><span class="sxs-lookup"><span data-stu-id="50206-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="50206-242">Zum Erstellen des Hosts</span><span class="sxs-lookup"><span data-stu-id="50206-242">To create the host</span></span>  
  
1.  <span data-ttu-id="50206-243">Fügen Sie ein neues Projekt mit dem Namen `Calc1Host` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="50206-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="50206-244">Basierend auf den **Konsolenanwendung** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="50206-245">In **Projektmappen-Explorer**, fügen Sie einen Verweis auf die System.AddIn.dll-Assembly, auf die `Calc1Host` Projekt.</span><span class="sxs-lookup"><span data-stu-id="50206-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="50206-246">Fügen Sie einen Projektverweis auf die `Calc1HVA` Projekt.</span><span class="sxs-lookup"><span data-stu-id="50206-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="50206-247">Wählen Sie den Projektverweis, und klicken Sie in **Eigenschaften** festgelegt **lokale Kopie** auf **"false"**.</span><span class="sxs-lookup"><span data-stu-id="50206-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="50206-248">In Visual Basic verwenden die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** auf **"false"**.</span><span class="sxs-lookup"><span data-stu-id="50206-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="50206-249">Benennen Sie die Klassendatei (Modul in Visual Basic) `MathHost1`.</span><span class="sxs-lookup"><span data-stu-id="50206-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="50206-250">Verwenden Sie in Visual Basic die **Anwendung** auf der Registerkarte die **Projekteigenschaften** Dialogfeld **Startobjekt** auf **Sub Main**.</span><span class="sxs-lookup"><span data-stu-id="50206-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="50206-251">Fügen Sie in der Klasse oder des Moduls-Datei einen Namespaceverweis auf <xref:System.AddIn.Hosting>.</span><span class="sxs-lookup"><span data-stu-id="50206-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="50206-252">Fügen Sie in der Klasse oder des Moduls-Datei einen Namespaceverweis für die Hostansicht des Add-Ins: `CalcHVAs`.</span><span class="sxs-lookup"><span data-stu-id="50206-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="50206-253">(In Visual Basic wird diese Namespaceverweis `Calc1HVA.CalcHVAs`, es sei denn, Sie in Visual Basic-Projekte die Standardnamespaces deaktiviert haben.)</span><span class="sxs-lookup"><span data-stu-id="50206-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="50206-254">In **Projektmappen-Explorer**, wählen Sie die Projektmappe und aus der **Projekt** im Menü **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="50206-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="50206-255">In der **-Eigenschaftenseiten** (Dialogfeld), legen die **einzelnes Startprojekt** dieses Hostanwendungsprojekt sein.</span><span class="sxs-lookup"><span data-stu-id="50206-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="50206-256">Verwenden Sie in der Datei Klasse oder das Modul die <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> Methode, um den Cache aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="50206-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="50206-257">Verwenden Sie die <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> Methode zum Abrufen einer Auflistung der Token und zum Verwenden der <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> Methode, um ein Add-in aktivieren.</span><span class="sxs-lookup"><span data-stu-id="50206-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="50206-258">Der folgende Code zeigt den abgeschlossenen hostanwendung.</span><span class="sxs-lookup"><span data-stu-id="50206-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="50206-259">Mit diesem Code wird davon ausgegangen, dass die Ordnerstruktur für die Pipeline im Ordner Anwendung befindet.</span><span class="sxs-lookup"><span data-stu-id="50206-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="50206-260">Ändern Sie die Zeile des Codes, der festlegt, an anderer Stelle befindet, die `addInRoot` -Variablen so, dass die Variable den Pfad zur Pipelineverzeichnisstruktur enthält.</span><span class="sxs-lookup"><span data-stu-id="50206-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="50206-261">Der Code verwendet eine `ChooseCalculator` Methode, um die Token aufzulisten und fordert den Benutzer auf ein Add-in auswählen.</span><span class="sxs-lookup"><span data-stu-id="50206-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="50206-262">Die `RunCalculator` Methode fordert den Benutzer einfache mathematische Ausdrücke, analysiert die Ausdrücke mithilfe der `Parser` -Klasse, und zeigt die Ergebnisse zurückgegeben werden, indem Sie das Add-in.</span><span class="sxs-lookup"><span data-stu-id="50206-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="50206-263">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50206-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="50206-264">Erstellen das Add-In</span><span class="sxs-lookup"><span data-stu-id="50206-264">Creating the Add-In</span></span>  
 <span data-ttu-id="50206-265">Ein Add-In implementiert die Methoden, die von der Add-in-Sicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="50206-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="50206-266">Dieses Add-In implementiert die `Add`, `Subtract`, `Multiply`, und `Divide` Vorgänge und gibt die Ergebnisse an den Host zurück.</span><span class="sxs-lookup"><span data-stu-id="50206-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="50206-267">So erstellen das Add-in</span><span class="sxs-lookup"><span data-stu-id="50206-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="50206-268">Fügen Sie ein neues Projekt mit dem Namen `AddInCalcV1` auf die `CalculatorV1` Lösung.</span><span class="sxs-lookup"><span data-stu-id="50206-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="50206-269">Basierend auf den **-Klassenbibliothek** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="50206-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="50206-270">In **Projektmappen-Explorer**, dem Projekt einen Verweis auf die System.AddIn.dll-Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="50206-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="50206-271">Fügen Sie einen Projektverweis auf die `Calc1AddInView` Projekt.</span><span class="sxs-lookup"><span data-stu-id="50206-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="50206-272">Wählen Sie den Projektverweis, und klicken Sie in **Eigenschaften**legen **lokale Kopie** auf **"false"**.</span><span class="sxs-lookup"><span data-stu-id="50206-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="50206-273">In Visual Basic verwenden die **Verweise** Registerkarte **Projekteigenschaften** festzulegende **lokale Kopie** auf **"false"** für den Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="50206-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="50206-274">Benennen Sie die Klasse `AddInCalcV1`.</span><span class="sxs-lookup"><span data-stu-id="50206-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="50206-275">Fügen Sie in der Klassendatei einen Namespaceverweis auf <xref:System.AddIn> und das Anzeigen von Add-in-Segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="50206-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="50206-276">Anwenden der <xref:System.AddIn.AddInAttribute> -Attribut auf die `AddInCalcV1` -Klasse, um die Klasse als ein Add-in zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="50206-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="50206-277">Stellen Sie die `AddInCalcV1` Klasse implementiert die Schnittstelle, die die Add-In-Ansicht darstellt: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="50206-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="50206-278">Implementieren Sie die Mitglieder der `ICalculator` durch die Ergebnisse von den entsprechenden Berechnungen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="50206-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="50206-279">Der folgende Code zeigt den abgeschlossenen-add-in.</span><span class="sxs-lookup"><span data-stu-id="50206-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="50206-280">Erstellen Sie optional die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50206-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="50206-281">Bereitstellen der Pipeline</span><span class="sxs-lookup"><span data-stu-id="50206-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="50206-282">Sie können nun zum Erstellen und Bereitstellen der Add-in-Segmente an der Pipelineverzeichnisstruktur erforderlich.</span><span class="sxs-lookup"><span data-stu-id="50206-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="50206-283">Die Segmente in der Pipeline bereitstellen</span><span class="sxs-lookup"><span data-stu-id="50206-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="50206-284">Verwenden Sie für jedes Projekt in der Projektmappe, die **erstellen** Registerkarte **Projekteigenschaften** (die **Kompilieren** Registerkarte in Visual Basic) zum Festlegen des Werts von der **Ausgabepfad**  (die **Buildausgabepfad** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="50206-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="50206-285">Wenn Sie mit dem Namen Anwendungsordner `MyApp`, z. B. würde Ihre Projekte erstellen, in den folgenden Ordnern:</span><span class="sxs-lookup"><span data-stu-id="50206-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="50206-286">Projekt</span><span class="sxs-lookup"><span data-stu-id="50206-286">Project</span></span>|<span data-ttu-id="50206-287">Pfad</span><span class="sxs-lookup"><span data-stu-id="50206-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="50206-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="50206-288">AddInCalcV1</span></span>|<span data-ttu-id="50206-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="50206-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="50206-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="50206-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="50206-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="50206-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="50206-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="50206-292">Calc1AddInView</span></span>|<span data-ttu-id="50206-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="50206-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="50206-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="50206-294">Calc1Contract</span></span>|<span data-ttu-id="50206-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="50206-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="50206-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="50206-296">Calc1Host</span></span>|<span data-ttu-id="50206-297">"MyApp"</span><span class="sxs-lookup"><span data-stu-id="50206-297">MyApp</span></span>|  
    |<span data-ttu-id="50206-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="50206-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="50206-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="50206-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="50206-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="50206-300">Calc1HVA</span></span>|<span data-ttu-id="50206-301">"MyApp"</span><span class="sxs-lookup"><span data-stu-id="50206-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="50206-302">Wenn Sie sich entschieden, die Ordnerstruktur für die Pipeline in einem anderen Speicherort als den Anwendungsordner, müssen Sie die Pfade in der Tabelle aufgeführt sind, entsprechend ändern.</span><span class="sxs-lookup"><span data-stu-id="50206-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="50206-303">Finden Sie in den Ausführungen des Pipeline-Directory-Anforderungen in [Pipelineentwicklung](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="50206-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="50206-304">Erstellen Sie die Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50206-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="50206-305">Überprüfen Sie die Anwendung und die Pipeline Verzeichnisse, um sicherzustellen, dass die Assemblys in den richtigen Verzeichnissen kopiert wurden und keine zusätzlichen Kopien der Assemblys in der falschen Ordnern installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="50206-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50206-306">Wenn Sie nicht geändert hat **lokale Kopie** auf **"false"** für die `Calc1AddInView` Projektverweise in der `AddInCalcV1` Projekt Ladeprogramm Kontext Probleme verhindert das Add-in befindlich.</span><span class="sxs-lookup"><span data-stu-id="50206-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="50206-307">Informationen zur Bereitstellung in der Pipeline finden Sie unter [Pipelineentwicklung](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="50206-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="50206-308">Ausführen der Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="50206-308">Running the Host Application</span></span>  
 <span data-ttu-id="50206-309">Sie können nun den Host ausführen und interagieren mit dem Add-in.</span><span class="sxs-lookup"><span data-stu-id="50206-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="50206-310">Zum Ausführen der hostanwendung</span><span class="sxs-lookup"><span data-stu-id="50206-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="50206-311">An der Eingabeaufforderung, wechseln Sie zum Verzeichnis Anwendung, und führen Sie die hostanwendung `Calc1Host.exe`.</span><span class="sxs-lookup"><span data-stu-id="50206-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="50206-312">Der Host sucht alle verfügbaren Add-Ins dieses Typs und fordert Sie auf ein Add-in auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="50206-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="50206-313">Geben Sie **1** für die einzige verfügbare Add-in.</span><span class="sxs-lookup"><span data-stu-id="50206-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="50206-314">Geben Sie eine Formel für den Rechner, z. B. **2 + 2**.</span><span class="sxs-lookup"><span data-stu-id="50206-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="50206-315">Leerzeichen zwischen den Zahlen und der Operator muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="50206-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="50206-316">Typ **beenden** , und drücken Sie die **EINGABETASTE** Taste, um die Anwendung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="50206-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50206-317">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50206-317">See Also</span></span>  
 [<span data-ttu-id="50206-318">Exemplarische Vorgehensweise: Aktivieren der Abwärtskompatibilität als die Host-Änderungen</span><span class="sxs-lookup"><span data-stu-id="50206-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [<span data-ttu-id="50206-319">Exemplarische Vorgehensweise: Übergeben von Sammlungen zwischen Hosts und -Add-Ins</span><span class="sxs-lookup"><span data-stu-id="50206-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](http://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [<span data-ttu-id="50206-320">Pipelineentwicklung</span><span class="sxs-lookup"><span data-stu-id="50206-320">Pipeline Development Requirements</span></span>](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [<span data-ttu-id="50206-321">Verträge, Ansichten und Adapter</span><span class="sxs-lookup"><span data-stu-id="50206-321">Contracts, Views, and Adapters</span></span>](http://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [<span data-ttu-id="50206-322">Pipelineentwicklung</span><span class="sxs-lookup"><span data-stu-id="50206-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)
