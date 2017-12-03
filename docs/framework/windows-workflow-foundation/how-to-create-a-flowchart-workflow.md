---
title: 'Vorgehensweise: Erstellen eines Flussdiagrammworkflows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3df93a876522ccdc001bc3f6bc8c780bc80dc21b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="6a246-102">Vorgehensweise: Erstellen eines Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="6a246-102">How to: Create a Flowchart Workflow</span></span>
<span data-ttu-id="6a246-103">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6a246-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="6a246-104">Dieses Thema führt Sie durch Erstellen eines Workflows, die sowohl integrierten Aktivitäten, wie z. B. verwendet die <xref:System.Activities.Statements.Flowchart> Aktivität und den benutzerdefinierten Aktivitäten aus dem vorherigen [Vorgehensweise: Erstellen Sie eine Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="6a246-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="6a246-105">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="6a246-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a246-106">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="6a246-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="6a246-107">Um dieses Thema abzuschließen, müssen Sie zuerst ausführen [Vorgehensweise: Erstellen Sie eine Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="6a246-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a246-108">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="6a246-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="6a246-109">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="6a246-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="6a246-110">Mit der rechten Maustaste **NumberGuessWorkflowActivities** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="6a246-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="6a246-111">In der **installiert**, **gemeinsame Elemente** Knoten **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="6a246-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="6a246-112">Wählen Sie **Aktivität** aus der **Workflow** Liste.</span><span class="sxs-lookup"><span data-stu-id="6a246-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="6a246-113">Typ `FlowchartNumberGuessWorkflow` in der **Namen** Feld, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6a246-113">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="6a246-114">Ziehen Sie eine **Flussdiagramm** Aktivität aus der **Flussdiagramm** im Abschnitt der **Toolbox** und legen ihn auf die **Aktivität hier ablegen** Bezeichnung auf die die Entwurfsoberfläche des Workflows.</span><span class="sxs-lookup"><span data-stu-id="6a246-114">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="6a246-115">So erstellen Sie die Workflowvariablen und -argumente</span><span class="sxs-lookup"><span data-stu-id="6a246-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="6a246-116">Doppelklicken Sie auf **FlowchartNumberGuessWorkflow.xaml** in **Projektmappen-Explorer** um den Workflow im Designer anzuzeigen, wenn er nicht bereits angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6a246-116">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="6a246-117">Klicken Sie auf **Argumente** in der unteren linken Seite im Workflow-Designer zum Anzeigen der **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="6a246-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="6a246-118">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="6a246-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="6a246-119">Typ `MaxNumber` in der **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6a246-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="6a246-120">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="6a246-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="6a246-121">Typ `Turns` in der **Namen** Feld, das unterhalb der neu hinzugefügten `MaxNumber` Argument die Option **Out** aus der **Richtung** Dropdown-Liste  **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="6a246-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="6a246-122">Klicken Sie auf **Argumente** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="6a246-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="6a246-123">Klicken Sie auf **Variablen** in der unteren linken Seite im Workflow-Designer zum Anzeigen der **Variablen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="6a246-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="6a246-124">Klicken Sie auf **erstellen Variable**.</span><span class="sxs-lookup"><span data-stu-id="6a246-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="6a246-125">Wenn kein **Variable erstellen** angezeigt wird, klicken Sie auf die <xref:System.Activities.Statements.Flowchart> Aktivität auf der workflowdesigneroberfläche, um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6a246-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="6a246-126">Typ `Guess` in der **Namen** wählen Sie im **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6a246-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="6a246-127">Klicken Sie auf **erstellen Variable**.</span><span class="sxs-lookup"><span data-stu-id="6a246-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="6a246-128">Typ `Target` in der **Namen** wählen Sie im **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6a246-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="6a246-129">Klicken Sie auf **Variablen** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Variablen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="6a246-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="6a246-130">So fügen Sie die Workflowaktivitäten hinzu</span><span class="sxs-lookup"><span data-stu-id="6a246-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="6a246-131">Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und zeigen sie auf die **starten** Knoten, die am oberen Rand ist die Flussdiagramm.</span><span class="sxs-lookup"><span data-stu-id="6a246-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="6a246-132">Wenn die **zuweisen** Aktivität liegt über der **starten** Knoten drei Dreiecke um den **starten** Knoten.</span><span class="sxs-lookup"><span data-stu-id="6a246-132">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="6a246-133">Löschen der **zuweisen** Aktivität auf dem Dreieck ab, das direkt unterhalb der **starten** Knoten.</span><span class="sxs-lookup"><span data-stu-id="6a246-133">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="6a246-134">Dadurch werden die beiden Elemente miteinander verknüpfen und bezieht sich auf die **zuweisen** Aktivität als erste Aktivität im Flussdiagramm.</span><span class="sxs-lookup"><span data-stu-id="6a246-134">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6a246-135">Aktivitäten können auch als Startaktivität im Workflow angegeben werden, indem Sie die Aktivität manuell mit dem Startknoten verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="6a246-135">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="6a246-136">Zeigen Sie dazu mit der Maus auf die **starten** Knoten, klicken Sie auf eines der Rechtecke, die angezeigt werden, wenn sich der Mauszeiger die **starten** Knoten, und ziehen Sie die Verbindungslinie auf die gewünschte Aktivität herunter und legen es auf einem der der angezeigten Rechtecke ab.</span><span class="sxs-lookup"><span data-stu-id="6a246-136">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="6a246-137">Sie können auch festlegen, und die Aktivität als Startaktivität durch Rechtsklick auf die It und Auswahl **als Startknoten festlegen**.</span><span class="sxs-lookup"><span data-stu-id="6a246-137">You can also designate and activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2.  <span data-ttu-id="6a246-138">Typ `Target` in der **auf** Feld und den folgenden Ausdruck in der **Geben Sie eine C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.</span><span class="sxs-lookup"><span data-stu-id="6a246-138">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="6a246-139">Wenn die **Toolbox** Fenster nicht angezeigt wird, wählen Sie **Toolbox** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="6a246-139">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="6a246-140">Ziehen Sie eine **Prompt** Aktivität aus der **NumberGuessWorkflowActivities** im Abschnitt der **Toolbox**, legen Sie sie unterhalb der **zuweisen** Aktivität aus dem vorherigen Schritt ab, und verbinden die **Prompt** Aktivität, um die **zuweisen** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a246-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="6a246-141">Es gibt drei Möglichkeiten, die beiden Aktivitäten zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="6a246-141">There are three ways to connect the two activities.</span></span> <span data-ttu-id="6a246-142">Die erste Möglichkeit besteht, um sie zu verbinden, wie Sie löschen die **Prompt** -Aktivität im Workflow.</span><span class="sxs-lookup"><span data-stu-id="6a246-142">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="6a246-143">Wie Sie ziehen die **Prompt** Aktivität für den Workflow, zeigen sie auf die **zuweisen** Aktivität, und legen ihn auf einem der vier Dreiecke ab, die angezeigt werden die **Prompt** Aktivität liegt über dem **zuweisen** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a246-143">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="6a246-144">Die zweite Möglichkeit ist zum Löschen der **Prompt** -Aktivität auf dem Workflow am gewünschten Ort.</span><span class="sxs-lookup"><span data-stu-id="6a246-144">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="6a246-145">Klicken Sie dann den Mauszeiger über die **zuweisen** Aktivität, und ziehen Sie eines der Rechtecke, die nach unten, um die **Prompt** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a246-145">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="6a246-146">Ziehen Sie die Maus, sodass die Verbindungslinie von der **zuweisen** Aktivität eine Verbindung mit einem der Rechtecke der der **Prompt** Aktivität, und lassen Sie die Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="6a246-146">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="6a246-147">Der dritte Weg ist vergleichbar mit der ersten Methode, außer dass ziehen die **Prompt** Aktivität aus der **Toolbox**, ziehen Sie es von ihrer Position auf der Workflowentwurfsoberfläche, zeigen sie auf die  **Weisen Sie** Aktivität, und auf einem der angezeigten Dreiecke ablegen.</span><span class="sxs-lookup"><span data-stu-id="6a246-147">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4.  <span data-ttu-id="6a246-148">In der **Fenster "Eigenschaften"** für die **Prompt** -Aktivität `"EnterGuess"` einschließlich der Anführungszeichen in der **BookmarkName** Feld mit dem Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="6a246-148">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="6a246-149">Typ `Guess` in der **Ergebnis** Eigenschaft Wert im Feld, und geben Sie den folgenden Ausdruck in der **Text** Eigenschaftenfeld.</span><span class="sxs-lookup"><span data-stu-id="6a246-149">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="6a246-150">Wenn die **Fenster "Eigenschaften"** wird nicht angezeigt werden, wählen Sie **Fenster "Eigenschaften"** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="6a246-150">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="6a246-151">Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und verbinden Sie diese mit einer der Methoden, die im vorherigen Schritt beschrieben wird, sodass sie sich unterhalb der befindet **Prompt** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a246-151">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6.  <span data-ttu-id="6a246-152">Typ `Turns` in der **auf** Feld und `Turns + 1` in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.</span><span class="sxs-lookup"><span data-stu-id="6a246-152">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7.  <span data-ttu-id="6a246-153">Ziehen Sie eine **FlowDecision** aus der **Flussdiagramm** Teil der **Toolbox** und verbinden Sie ihn unten die **zuweisen** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a246-153">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="6a246-154">In der **Fenster "Eigenschaften"**, geben Sie den folgenden Ausdruck in der **Bedingung** Feld mit dem Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="6a246-154">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  <span data-ttu-id="6a246-155">Ziehen Sie ein weiteres **FlowDecision** Aktivität aus der **Toolbox** und legen Sie es unterhalb der ersten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a246-155">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="6a246-156">Verbinden Sie die beiden Aktivitäten durch Ziehen zwischen dem Rechteck mit der Bezeichnung **"false"** am oberen Rand **FlowDecision** -Aktivität zum Rechteck am oberen Rand der zweiten **FlowDecision**Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a246-156">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="6a246-157">Wenn Sie nicht sehen die **"true"** und **"false"** "Bezeichnungen" auf die **FlowDecision**, zeigen Sie mit der Maus auf die **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="6a246-157">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="6a246-158">Klicken Sie auf die zweite **FlowDecision** Aktivität, um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6a246-158">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="6a246-159">In der **Fenster "Eigenschaften"**, geben Sie den folgenden Ausdruck in der **Bedingung** Feld mit dem Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="6a246-159">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
10. <span data-ttu-id="6a246-160">Ziehen Sie zwei **WriteLine** Aktivitäten aus der **primitive** Teil der **Toolbox** und ablegen, damit sie nebeneinander unter den zwei sind **FlowDecision**  Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="6a246-160">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="6a246-161">Verbinden der **"true"** -Aktion der untersten **FlowDecision** Aktivität, um die am weitesten links stehende **WriteLine** Aktivität, und die **"false"** Aktion aus, um die ganz rechts **WriteLine** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6a246-161">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="6a246-162">Klicken Sie auf die am weitesten links stehende **WriteLine** Aktivität, um es auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Eigenschaftswert Feld der **Fenster "Eigenschaften"**.</span><span class="sxs-lookup"><span data-stu-id="6a246-162">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="6a246-163">Verbinden der **WriteLine** auf der linken Seite des der **Prompt** Aktivität, die jeweils darüber liegt.</span><span class="sxs-lookup"><span data-stu-id="6a246-163">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="6a246-164">Klicken Sie auf der äußersten rechten **WriteLine** Aktivität, um es auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Eigenschaftswert Feld der **Fenster "Eigenschaften"**.</span><span class="sxs-lookup"><span data-stu-id="6a246-164">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="6a246-165">Verbinden der **WriteLine** Aktivität rechts neben der **Prompt** Aktivität darüber.</span><span class="sxs-lookup"><span data-stu-id="6a246-165">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="6a246-166">Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6a246-166">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="6a246-167">![Windows Workflow Foundation abgeschlossen](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")</span><span class="sxs-lookup"><span data-stu-id="6a246-167">![Completed Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="6a246-168">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="6a246-168">To build the workflow</span></span>  
  
1.  <span data-ttu-id="6a246-169">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6a246-169">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="6a246-170">Anweisungen zum Ausführen des Workflows finden Sie unter dem nächsten Thema [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="6a246-170">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="6a246-171">Wenn Sie bereits abgeschlossen haben die [wie: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) Schritt mit einem anderen Format des Workflows und möchten sie mit dem Flussdiagramm-Workflow aus diesen Schritt ausführen, fahren Sie mit der [zum Erstellen und Ausführen der Anwendung](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)Abschnitt [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="6a246-171">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a246-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a246-172">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="6a246-173">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="6a246-173">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="6a246-174">Entwerfen von Workflows</span><span class="sxs-lookup"><span data-stu-id="6a246-174">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="6a246-175">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="6a246-175">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="6a246-176">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="6a246-176">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="6a246-177">Vorgehensweise: Ausführen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="6a246-177">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
