---
title: 'Vorgehensweise: Erstellen eines Flussdiagrammworkflows'
description: In diesem Artikel wird beschrieben, wie Sie einen Workflow erstellen, der integrierte Aktivitäten und die benutzerdefinierten Aktivitäten aus dem vorherigen Artikel verwendet.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: eb30a3a21ffc4cffe64d2f5d0bc741728f1ea87d
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190480"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="9f3cc-103">Vorgehensweise: Erstellen eines Flussdiagrammworkflows</span><span class="sxs-lookup"><span data-stu-id="9f3cc-103">How to: Create a Flowchart Workflow</span></span>

<span data-ttu-id="9f3cc-104">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="9f3cc-105">In diesem Thema wird Schritt für Schritt beschrieben, wie Sie einen Workflow erstellen, der integrierte Aktivitäten wie die <xref:System.Activities.Statements.Flowchart> -Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen Thema Gewusst [wie: Erstellen einer Aktivität](how-to-create-an-activity.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="9f3cc-106">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9f3cc-107">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="9f3cc-108">Um dieses Thema abzuschließen, müssen Sie zunächst Gewusst [wie: Erstellen einer Aktivität durchführen](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="9f3cc-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="9f3cc-109">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="9f3cc-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="9f3cc-110">Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf " **numguess Workflow Activities** ", und wählen Sie **Hinzufügen**, **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="9f3cc-111">Wählen Sie im Knoten **installierte**, **Allgemeine Elemente** die Option **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="9f3cc-112">Wählen Sie **Aktivität** aus der Liste **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="9f3cc-113">Geben `FlowchartNumberGuessWorkflow` Sie im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-113">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="9f3cc-114">Ziehen Sie eine **Flowchart** -Aktivität aus dem Abschnitt **Flowchart** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** auf der Workflow Entwurfs Oberfläche ab.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-114">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="9f3cc-115">So erstellen Sie die Workflowvariablen und -argumente</span><span class="sxs-lookup"><span data-stu-id="9f3cc-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="9f3cc-116">Doppelklicken Sie in **Projektmappen-Explorer** auf **flowchartnumguess Workflow. XAML** , um den Workflow im Designer anzuzeigen, falls er nicht bereits angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-116">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="9f3cc-117">Klicken Sie Links unten im Workflow-Designer auf **Argumente** , um den Bereich **Argumente** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="9f3cc-118">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="9f3cc-119">Geben `MaxNumber` Sie in das Feld **Name** ein, wählen Sie in der Dropdown Liste **Richtung** die Option **in** aus, wählen Sie **Int32** aus der Dropdown Liste **Argumenttyp** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="9f3cc-120">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="9f3cc-121">Geben `Turns` Sie in das Feld **Name** unter dem neu hinzugefügten `MaxNumber` Argument ein, wählen Sie aus der Dropdown Liste **Richtung** die Option **aus** , wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="9f3cc-122">Klicken Sie unten links im Aktivitäts-Designer auf **Argumente**, um den Bereich **Argumente** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="9f3cc-123">Klicken Sie Links unten im Workflow-Designer auf **Variablen** , um den Bereich **Variablen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="9f3cc-124">Klicken Sie auf **Variable erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="9f3cc-125">Wenn das Feld **Variable erstellen** nicht angezeigt wird, klicken Sie auf der Oberfläche des Workflow-Designers auf die- <xref:System.Activities.Statements.Flowchart> Aktivität, um Sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="9f3cc-126">Geben `Guess` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern</span><span class="sxs-lookup"><span data-stu-id="9f3cc-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="9f3cc-127">Klicken Sie auf **Variable erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="9f3cc-128">Geben `Target` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern</span><span class="sxs-lookup"><span data-stu-id="9f3cc-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="9f3cc-129">Klicken Sie unten links im Aktivitäts-Designer auf **Variablen**, um den Bereich **Variablen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="9f3cc-130">So fügen Sie die Workflowaktivitäten hinzu</span><span class="sxs-lookup"><span data-stu-id="9f3cc-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="9f3cc-131">Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und zeigen Sie auf den Knoten **Start** , der sich am oberen Rand des Fluss Diagramms befindet.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="9f3cc-132">Wenn sich die **assign** -Aktivität über dem **Start** Knoten befindet, werden drei Dreiecke um den **Start** Knoten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-132">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="9f3cc-133">Legen Sie die **assign** -Aktivität auf dem Dreieck ab, das sich direkt unter dem **Start** Knoten befindet.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-133">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="9f3cc-134">Dadurch werden die beiden Elemente miteinander verknüpft, und die **assign** -Aktivität wird als erste Aktivität im Flussdiagramm bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-134">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9f3cc-135">Aktivitäten können auch als Startaktivität im Workflow angegeben werden, indem Sie die Aktivität manuell mit dem Startknoten verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-135">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="9f3cc-136">Zeigen Sie dazu mit dem Mauszeiger auf den Knoten **Start** , klicken Sie auf einen der Rechtecke, die angezeigt werden, wenn sich der Mauszeiger über dem Knoten **Start** befindet, und ziehen Sie die Verbindungslinie auf die gewünschte Aktivität, und legen Sie Sie auf einem der angezeigten Rechtecke ab.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-136">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="9f3cc-137">Sie können eine Aktivität auch als Start Aktivität festlegen, indem Sie mit der rechten Maustaste darauf klicken und **als Start Knoten festlegen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-137">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="9f3cc-138">Geben Sie in das Feld `Target` **an** und den folgenden Ausdruck im Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .</span><span class="sxs-lookup"><span data-stu-id="9f3cc-138">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="9f3cc-139">Wird das Fenster **Toolbox** nicht angezeigt, wählen Sie **Toolbox** im Menü **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-139">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="9f3cc-140">Ziehen Sie eine **prompt** -Aktivität aus dem Abschnitt " **nummeriguess Workflow Activities** " der **Toolbox**, legen Sie Sie unterhalb der **assign** -Aktivität aus dem vorherigen Schritt ab, und verbinden Sie die **prompt** -Aktivität mit der **assign** -Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="9f3cc-141">Es gibt drei Möglichkeiten, die beiden Aktivitäten zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-141">There are three ways to connect the two activities.</span></span> <span data-ttu-id="9f3cc-142">Die erste Möglichkeit besteht darin, Sie zu verbinden, während Sie die **prompt** -Aktivität für den Workflow ablegen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-142">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="9f3cc-143">Wenn Sie die **prompt** -Aktivität in den Workflow ziehen, zeigen Sie auf die **assign** -Aktivität, und legen Sie Sie auf einem der vier Dreiecke ab, die angezeigt werden, wenn die **prompt** -Aktivität über der **assign** -Aktivität ist.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-143">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="9f3cc-144">Die zweite Möglichkeit besteht darin, die **prompt** -Aktivität am gewünschten Speicherort auf dem Workflow abzulegen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-144">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="9f3cc-145">Zeigen Sie dann mit der Maus auf die **assign** -Aktivität, und ziehen Sie einen der unten angezeigten Rechtecke auf die Aktivität **prompt** .</span><span class="sxs-lookup"><span data-stu-id="9f3cc-145">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="9f3cc-146">Ziehen Sie die Maus, sodass sich die Verbindungslinie der **assign** -Aktivität mit einer der Rechtecke der **prompt** -Aktivität verbindet, und lassen Sie dann die Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-146">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="9f3cc-147">Die dritte Möglichkeit ähnelt der ersten Methode, mit dem Unterschied, dass Sie nicht die **prompt** -Aktivität aus der **Toolbox** ziehen, sondern von der Position auf der Workflow Entwurfs Oberfläche ziehen, mit der Maus auf die **assign** -Aktivität zeigen und Sie auf einem der angezeigten Dreiecke ablegen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-147">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="9f3cc-148">Geben Sie im **Eigenschaften Fenster** für die **prompt** -Aktivität im `"EnterGuess"` Feld **BookmarkName** -Eigenschafts Wert die Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-148">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="9f3cc-149">Geben Sie `Guess` in das Feld **Ergebnis** Eigenschafts Wert ein, und geben Sie den folgenden Ausdruck in das Eigenschaften Feld **Text** ein.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-149">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="9f3cc-150">Wenn das **Fenster Eigenschaften** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Eigenschaften Fenster** aus.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-150">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="9f3cc-151">Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und verbinden Sie Sie mit einer der im vorherigen Schritt beschriebenen Methoden, sodass Sie sich unterhalb der **prompt** -Aktivität befindet.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-151">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="9f3cc-152">Geben `Turns` Sie im Feld **an** und `Turns + 1` im Feld **c#-Ausdruck eingeben**  oder **VB-Ausdruck eingeben ein** .</span><span class="sxs-lookup"><span data-stu-id="9f3cc-152">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="9f3cc-153">Ziehen Sie eine **FlowDecision** aus dem Abschnitt **Flowchart** der **Toolbox** , und verbinden Sie Sie unter der **assign** -Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-153">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="9f3cc-154">Geben Sie im **Fenster Eigenschaften** den folgenden Ausdruck **in das Feld Bedingungs Eigenschaften Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-154">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="9f3cc-155">Ziehen Sie eine weitere **FlowDecision** -Aktivität aus der **Toolbox** , und legen Sie Sie unterhalb der ersten ab.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-155">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="9f3cc-156">Verbinden Sie die beiden Aktivitäten, indem Sie aus dem Rechteck mit der Bezeichnung **false** auf der Top- **FlowDecision** -Aktivität in das Rechteck am Anfang der zweiten **FlowDecision** -Aktivität ziehen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-156">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="9f3cc-157">Wenn die Bezeichnungen **true** und **false** bei **FlowDecision** nicht angezeigt werden, zeigen Sie mit der Maus auf die **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-157">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="9f3cc-158">Klicken Sie auf die zweite **FlowDecision** -Aktivität, um Sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-158">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="9f3cc-159">Geben Sie im **Fenster Eigenschaften** den folgenden Ausdruck **in das Feld Bedingungs Eigenschaften Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-159">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
10. <span data-ttu-id="9f3cc-160">Ziehen Sie **zwei schreiben** -Aktivitäten aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie diese so ab, dass Sie sich unter den zwei **FlowDecision** -Aktivitäten nebeneinander befinden.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-160">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="9f3cc-161">Verbinden Sie die " **true** "-Aktion der untersten **FlowDecision** -Aktivität mit **der Schreib** Schutz-Aktivität ganz links und der " **false** "-Aktion an die "äußersten rechten"-Aktivität " **WriteLine** ".</span><span class="sxs-lookup"><span data-stu-id="9f3cc-161">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="9f3cc-162">Klicken Sie zum auswählen auf die **Schreib** geschützte Aktivität ganz links, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert im **Eigenschaften Fenster** ein.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-162">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="9f3cc-163">Verbinden Sie die **Schreib** geschützte Seite mit der linken Seite der **prompt** -Aktivität, die sich darüber befindet.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-163">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="9f3cc-164">Klicken Sie auf die **WriteLine** -Aktivität ganz rechts, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert im **Fenster Eigenschaften** ein.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-164">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="9f3cc-165">Verbinden Sie die Aktivität " **Write teline** " mit der rechten Seite der **prompt** -Aktivität oberhalb der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-165">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="9f3cc-166">Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-166">The following example illustrates the completed workflow.</span></span>  
  
     ![Diagramm, das ein abgeschlossenes Windows Workflow Foundation Flussdiagramm anzeigt.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="9f3cc-168">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="9f3cc-168">To build the workflow</span></span>  
  
1. <span data-ttu-id="9f3cc-169">Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-169">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="9f3cc-170">Anweisungen zum Ausführen des Workflows finden Sie im nächsten Thema Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9f3cc-170">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="9f3cc-171">Wenn Sie den Schritt Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md) mit einem anderen Workflow Workflow abgeschlossen haben und ihn mit dem Flussdiagramm Workflow aus diesem Schritt ausführen möchten, fahren Sie mit dem Abschnitt so [Erstellen und führen Sie den Anwendungs](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) Abschnitt unter Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md)fort.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-171">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f3cc-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f3cc-172">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="9f3cc-173">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="9f3cc-173">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="9f3cc-174">Entwerfen von Workflows</span><span class="sxs-lookup"><span data-stu-id="9f3cc-174">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="9f3cc-175">Lernprogramm 'Erste Schritte'</span><span class="sxs-lookup"><span data-stu-id="9f3cc-175">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="9f3cc-176">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="9f3cc-176">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="9f3cc-177">Vorgehensweise: Ausführen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="9f3cc-177">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
