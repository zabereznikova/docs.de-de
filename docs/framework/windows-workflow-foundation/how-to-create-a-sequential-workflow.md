---
title: 'Vorgehensweise: Erstellen eines sequenziellen Workflows'
description: In diesem Artikel wird ein Workflow erstellt, der integrierte Aktivitäten verwendet, wie z. b. die Sequence-Aktivität und benutzerdefinierte Aktivitäten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: f80ac471fdcc425504b11b5fb17effa888aa9590
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419693"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="3beb7-103">Vorgehensweise: Erstellen eines sequenziellen Workflows</span><span class="sxs-lookup"><span data-stu-id="3beb7-103">How to: Create a Sequential Workflow</span></span>

<span data-ttu-id="3beb7-104">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3beb7-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="3beb7-105">In diesem Thema wird Schritt für Schritt beschrieben, wie Sie einen Workflow erstellen, der integrierte Aktivitäten wie die <xref:System.Activities.Statements.Sequence> -Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen Thema Gewusst [wie: Erstellen einer Aktivität](how-to-create-an-activity.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="3beb7-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="3beb7-106">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="3beb7-106">The workflow models a number guessing game.</span></span>

> [!NOTE]
> <span data-ttu-id="3beb7-107">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="3beb7-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="3beb7-108">Um dieses Thema abzuschließen, müssen Sie zunächst Gewusst [wie: Erstellen einer Aktivität durchführen](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="3beb7-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3beb7-109">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3beb7-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-workflow"></a><span data-ttu-id="3beb7-110">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="3beb7-110">To create the workflow</span></span>

1. <span data-ttu-id="3beb7-111">Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf " **numguess Workflow Activities** ", und wählen Sie **Hinzufügen**, **Neues Element**aus.</span><span class="sxs-lookup"><span data-stu-id="3beb7-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>

2. <span data-ttu-id="3beb7-112">Wählen Sie im Knoten **installierte**, **Allgemeine Elemente** die Option **Workflow**aus.</span><span class="sxs-lookup"><span data-stu-id="3beb7-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="3beb7-113">Wählen Sie **Aktivität** aus der Liste **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="3beb7-113">Select **Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="3beb7-114">Geben `SequentialNumberGuessWorkflow` Sie im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3beb7-114">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>

4. <span data-ttu-id="3beb7-115">Ziehen Sie eine **Sequence** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie diese auf der Bezeichnung **Aktivität hier ablegen** auf der Workflow Entwurfs Oberfläche ab.</span><span class="sxs-lookup"><span data-stu-id="3beb7-115">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>

## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="3beb7-116">So erstellen Sie die Workflowvariablen und -argumente</span><span class="sxs-lookup"><span data-stu-id="3beb7-116">To create the workflow variables and arguments</span></span>

1. <span data-ttu-id="3beb7-117">Doppelklicken Sie in **Projektmappen-Explorer** auf **sequentialnumguess Workflow. XAML** , um den Workflow im Designer anzuzeigen, falls er nicht bereits angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3beb7-117">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>

2. <span data-ttu-id="3beb7-118">Klicken Sie Links unten im Workflow-Designer auf **Argumente** , um den Bereich **Argumente** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3beb7-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>

3. <span data-ttu-id="3beb7-119">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3beb7-119">Click **Create Argument**.</span></span>

4. <span data-ttu-id="3beb7-120">Geben `MaxNumber` Sie in das Feld **Name** ein, wählen Sie in der Dropdown Liste **Richtung** die Option **in** aus, wählen Sie **Int32** aus der Dropdown Liste **Argumenttyp** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3beb7-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>

5. <span data-ttu-id="3beb7-121">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3beb7-121">Click **Create Argument**.</span></span>

6. <span data-ttu-id="3beb7-122">Geben `Turns` Sie in das Feld **Name** unter dem neu hinzugefügten `MaxNumber` Argument ein, wählen Sie aus der Dropdown Liste **Richtung** die Option **aus** , wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="3beb7-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>

7. <span data-ttu-id="3beb7-123">Klicken Sie unten links im Aktivitäts-Designer auf **Argumente**, um den Bereich **Argumente** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="3beb7-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

8. <span data-ttu-id="3beb7-124">Klicken Sie Links unten im Workflow-Designer auf **Variablen** , um den Bereich **Variablen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3beb7-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>

9. <span data-ttu-id="3beb7-125">Klicken Sie auf **Variable erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3beb7-125">Click **Create Variable**.</span></span>

    > [!TIP]
    > <span data-ttu-id="3beb7-126">Wenn das Feld **Variable erstellen** nicht angezeigt wird, klicken Sie auf der Oberfläche des Workflow-Designers auf die **Sequenz** Aktivität, um Sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3beb7-126">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>

10. <span data-ttu-id="3beb7-127">Geben `Guess` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern</span><span class="sxs-lookup"><span data-stu-id="3beb7-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

11. <span data-ttu-id="3beb7-128">Klicken Sie auf **Variable erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3beb7-128">Click **Create Variable**.</span></span>

12. <span data-ttu-id="3beb7-129">Geben `Target` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern</span><span class="sxs-lookup"><span data-stu-id="3beb7-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

13. <span data-ttu-id="3beb7-130">Klicken Sie unten links im Aktivitäts-Designer auf **Variablen**, um den Bereich **Variablen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="3beb7-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>

## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="3beb7-131">So fügen Sie die Workflowaktivitäten hinzu</span><span class="sxs-lookup"><span data-stu-id="3beb7-131">To add the workflow activities</span></span>

1. <span data-ttu-id="3beb7-132">Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf der **Sequence** -Aktivität ab.</span><span class="sxs-lookup"><span data-stu-id="3beb7-132">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="3beb7-133">Geben Sie in das Feld `Target` **an** und den folgenden Ausdruck im Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .</span><span class="sxs-lookup"><span data-stu-id="3beb7-133">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > <span data-ttu-id="3beb7-134">Wird das Fenster **Toolbox** nicht angezeigt, wählen Sie **Toolbox** im Menü **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="3beb7-134">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

2. <span data-ttu-id="3beb7-135">Ziehen Sie eine **DoWhile** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie Sie auf dem Workflow ab, sodass Sie sich unterhalb der **assign** -Aktivität befindet.</span><span class="sxs-lookup"><span data-stu-id="3beb7-135">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>

3. <span data-ttu-id="3beb7-136">Geben Sie den folgenden Ausdruck **in das Feld Bedingungs Eigenschafts Wert** der **DoWhile** -Aktivität ein.</span><span class="sxs-lookup"><span data-stu-id="3beb7-136">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     <span data-ttu-id="3beb7-137">Eine <xref:System.Activities.Statements.DoWhile>-Aktivität führt ihre untergeordneten Aktivitäten aus und wertet dann <xref:System.Activities.Statements.DoWhile.Condition%2A> aus.</span><span class="sxs-lookup"><span data-stu-id="3beb7-137">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="3beb7-138">Wenn <xref:System.Activities.Statements.DoWhile.Condition%2A>`True` ergibt, dann werden die Aktivitäten in <xref:System.Activities.Statements.DoWhile> erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3beb7-138">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="3beb7-139">In diesem Beispiel wird der Schätzwert des Benutzers ausgewertet und <xref:System.Activities.Statements.DoWhile> fortgesetzt, bis die Schätzung richtig ist.</span><span class="sxs-lookup"><span data-stu-id="3beb7-139">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>

4. <span data-ttu-id="3beb7-140">Ziehen Sie eine **prompt** -Aktivität aus dem Abschnitt " **nummeriguess Workflow Activities** " der **Toolbox** , und legen Sie Sie aus dem vorherigen Schritt in der **DoWhile** -Aktivität ab.</span><span class="sxs-lookup"><span data-stu-id="3beb7-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>

5. <span data-ttu-id="3beb7-141">Geben Sie im **Eigenschaften Fenster** `"EnterGuess"` die Anführungszeichen in das Feld **BookmarkName** -Eigenschafts Wert für die **prompt** -Aktivität ein.</span><span class="sxs-lookup"><span data-stu-id="3beb7-141">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="3beb7-142">Geben Sie `Guess` in das Feld **Ergebnis** Eigenschafts Wert ein, und geben Sie den folgenden Ausdruck in das Eigenschaften Feld **Text** ein.</span><span class="sxs-lookup"><span data-stu-id="3beb7-142">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > <span data-ttu-id="3beb7-143">Wenn das **Fenster Eigenschaften** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Eigenschaften Fenster** aus.</span><span class="sxs-lookup"><span data-stu-id="3beb7-143">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

6. <span data-ttu-id="3beb7-144">Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie in der **DoWhile** -Aktivität ab, sodass Sie der **prompt** -Aktivität folgt.</span><span class="sxs-lookup"><span data-stu-id="3beb7-144">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3beb7-145">Beachten Sie beim Löschen der **assign** -Aktivität, wie der Workflow-Designer automatisch eine **Sequence** -Aktivität hinzufügt, die sowohl die **prompt** -Aktivität als auch die neu hinzugefügte **assign** -Aktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="3beb7-145">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>

7. <span data-ttu-id="3beb7-146">Geben `Turns` Sie im Feld **an** und `Turns + 1` im Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .</span><span class="sxs-lookup"><span data-stu-id="3beb7-146">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

8. <span data-ttu-id="3beb7-147">Ziehen Sie eine **if** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie Sie in der **Sequence** -Aktivität ab, sodass Sie auf die neu hinzugefügte **assign** -Aktivität folgt.</span><span class="sxs-lookup"><span data-stu-id="3beb7-147">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>

9. <span data-ttu-id="3beb7-148">Geben Sie den folgenden Ausdruck in das Feld Bedingungs **Eigenschafts Wert** der **if** -Aktivität ein.</span><span class="sxs-lookup"><span data-stu-id="3beb7-148">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. <span data-ttu-id="3beb7-149">Ziehen Sie eine weitere **if** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie Sie im Abschnitt **Then** der ersten **if** -Aktivität ab.</span><span class="sxs-lookup"><span data-stu-id="3beb7-149">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>

11. <span data-ttu-id="3beb7-150">Geben Sie den folgenden Ausdruck in das **Feldeigenschaften Wert der neu** hinzugefügten **if** -Aktivität ein.</span><span class="sxs-lookup"><span data-stu-id="3beb7-150">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>

    ```text
    Guess < Target
    ```

12. <span data-ttu-id="3beb7-151">Ziehen Sie **zwei schreiben** -Aktivitäten aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie diese so ab, dass Sie sich im **Then** -Abschnitt der neu hinzugefügten **if** -Aktivität befinden und eine im Abschnitt **else** .</span><span class="sxs-lookup"><span data-stu-id="3beb7-151">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>

13. <span data-ttu-id="3beb7-152">Klicken Sie im Abschnitt **Then** auf die Aktivität **Write** -Aktivität, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert ein.</span><span class="sxs-lookup"><span data-stu-id="3beb7-152">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too low."
    ```

14. <span data-ttu-id="3beb7-153">Klicken Sie im Abschnitt **else** auf die Aktivität **Write** -Aktivität, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert ein.</span><span class="sxs-lookup"><span data-stu-id="3beb7-153">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too high."
    ```

     <span data-ttu-id="3beb7-154">Im folgenden Beispiel wird der abgeschlossene Workflow veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="3beb7-154">The following example illustrates the completed workflow:</span></span>

     ![Screenshot, der den abgeschlossenen sequenziellen Workflow anzeigt.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a><span data-ttu-id="3beb7-156">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="3beb7-156">To build the workflow</span></span>

1. <span data-ttu-id="3beb7-157">Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3beb7-157">Press CTRL+SHIFT+B to build the solution.</span></span>

     <span data-ttu-id="3beb7-158">Anweisungen zum Ausführen des Workflows finden Sie im nächsten Thema Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="3beb7-158">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="3beb7-159">Wenn Sie den Schritt Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md) mit einem anderen Workflow Workflow abgeschlossen haben und ihn mit dem sequenziellen Workflow aus diesem Schritt ausführen möchten, fahren Sie mit dem Abschnitt so [Erstellen und führen Sie den Anwendungs](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) Abschnitt "Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md)" fort.</span><span class="sxs-lookup"><span data-stu-id="3beb7-159">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3beb7-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3beb7-160">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="3beb7-161">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="3beb7-161">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="3beb7-162">Entwerfen von Workflows</span><span class="sxs-lookup"><span data-stu-id="3beb7-162">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="3beb7-163">Tutorial zu den ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="3beb7-163">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="3beb7-164">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="3beb7-164">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="3beb7-165">Vorgehensweise: Ausführen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="3beb7-165">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
