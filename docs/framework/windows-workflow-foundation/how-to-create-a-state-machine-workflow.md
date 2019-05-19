---
title: 'Vorgehensweise: Erstellen eines Zustandsautomatworkflows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 84d2355a78c7d33bf712baf158f28861e59e75d1
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881939"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="b917a-102">Vorgehensweise: Erstellen eines Zustandsautomatworkflows</span><span class="sxs-lookup"><span data-stu-id="b917a-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="b917a-103">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b917a-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="b917a-104">Dieses Thema führt durch Erstellen eines Workflows, der integrierten Aktivitäten, wie z. B. verwendet die <xref:System.Activities.Statements.StateMachine> Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen [Vorgehensweise: Erstellen einer Aktivität](how-to-create-an-activity.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="b917a-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="b917a-105">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="b917a-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b917a-106">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="b917a-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="b917a-107">Um dieses Thema abzuschließen, müssen Sie zuerst abschließen [Vorgehensweise: Erstellen einer Aktivität](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="b917a-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b917a-108">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b917a-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="b917a-109">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="b917a-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="b917a-110">Mit der rechten Maustaste **NumberGuessWorkflowActivities** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="b917a-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="b917a-111">In der **installiert**, **gemeinsame Elemente** Knoten **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="b917a-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="b917a-112">Wählen Sie **Aktivität** aus der **Workflow** Liste.</span><span class="sxs-lookup"><span data-stu-id="b917a-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="b917a-113">Typ `StateMachineNumberGuessWorkflow` in die **Namen** ein, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b917a-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="b917a-114">Ziehen Sie eine **StateMachine** Aktivität aus der **State Machine** Teil der **Toolbox** und legen ihn auf die **Aktivität hier ablegen** Beschriftung im die Workflow-Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="b917a-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="b917a-115">So erstellen Sie die Workflowvariablen und -argumente</span><span class="sxs-lookup"><span data-stu-id="b917a-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="b917a-116">Doppelklicken Sie auf **StateMachineNumberGuessWorkflow.xaml** in **Projektmappen-Explorer** um den Workflow im Designer anzuzeigen, wenn er nicht bereits angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b917a-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="b917a-117">Klicken Sie auf **Argumente** in der unteren linken Seite des Workflow-Designers zum Anzeigen der **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="b917a-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="b917a-118">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b917a-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="b917a-119">Typ `MaxNumber` in die **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b917a-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="b917a-120">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b917a-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="b917a-121">Typ `Turns` in die **Namen** Feld unterhalb des neu erstellten `MaxNumber` Argument die Option **Out** aus der **Richtung** Dropdown-Liste  **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="b917a-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="b917a-122">Klicken Sie auf **Argumente** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="b917a-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="b917a-123">Klicken Sie auf **Variablen** in der unteren linken Seite des Workflow-Designers zum Anzeigen der **Variablen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="b917a-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="b917a-124">Klicken Sie auf **erstellen Variable**.</span><span class="sxs-lookup"><span data-stu-id="b917a-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b917a-125">Wenn kein **Variable erstellen** angezeigt wird, klicken Sie auf die <xref:System.Activities.Statements.StateMachine> Aktivität auf der workflowdesigneroberfläche, um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b917a-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="b917a-126">Typ `Guess` in die **Namen** Kontrollkästchen **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b917a-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="b917a-127">Klicken Sie auf **erstellen Variable**.</span><span class="sxs-lookup"><span data-stu-id="b917a-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="b917a-128">Typ `Target` in die **Namen** Kontrollkästchen **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b917a-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="b917a-129">Klicken Sie auf **Variablen** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Variablen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="b917a-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="b917a-130">So fügen Sie die Workflowaktivitäten hinzu</span><span class="sxs-lookup"><span data-stu-id="b917a-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="b917a-131">Klicken Sie auf **State1** um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b917a-131">Click **State1** to select it.</span></span> <span data-ttu-id="b917a-132">In der **Fenster "Eigenschaften"**, ändern Sie die **"DisplayName"** zu `Initialize Target`.</span><span class="sxs-lookup"><span data-stu-id="b917a-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b917a-133">Wenn die **Fenster "Eigenschaften"** als nicht angezeigt, aktivieren **Fenster "Eigenschaften"** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="b917a-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="b917a-134">Doppelklicken Sie auf das gerade umbenannte **Ziel initialisieren** Zustand im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b917a-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="b917a-135">Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und legen ihn auf die **Eintrag** -Abschnitt des Zustands.</span><span class="sxs-lookup"><span data-stu-id="b917a-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="b917a-136">Typ `Target` in die **zu** Feld und den folgenden Ausdruck in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.</span><span class="sxs-lookup"><span data-stu-id="b917a-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="b917a-137">Wenn die **Toolbox** Fenster nicht angezeigt wird, wählen Sie **Toolbox** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="b917a-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="b917a-138">Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Brotkrümelnavigation angezeigt werden soll, am oberen Rand der Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="b917a-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="b917a-139">Ziehen Sie eine **Zustand** Aktivität aus der **Zustandsautomat** im Abschnitt der **Toolbox** im Workflow-Designer und zeigen sie die **Ziel initialisieren** Zustand.</span><span class="sxs-lookup"><span data-stu-id="b917a-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="b917a-140">Beachten Sie, dass vier Dreiecke, um angezeigt werden die **Ziel initialisieren** Status, wenn der neue Zustand darüber befindet.</span><span class="sxs-lookup"><span data-stu-id="b917a-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="b917a-141">Löschen Sie den neuen Zustand auf dem Dreieck ab, direkt unterhalb der **Ziel initialisieren** Zustand.</span><span class="sxs-lookup"><span data-stu-id="b917a-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="b917a-142">Dadurch wird der neuen Zustand im Workflow, und erstellt einen Übergang von der **Ziel initialisieren** -Zustand in den neuen Zustand.</span><span class="sxs-lookup"><span data-stu-id="b917a-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="b917a-143">Klicken Sie auf **State1** ändern, um ihn auszuwählen, die **"DisplayName"** zu `Enter Guess`, und doppelklicken Sie dann auf den Zustand im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b917a-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="b917a-144">Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** Teil der **Toolbox** und legen ihn auf die **Eintrag** -Abschnitt des Zustands.</span><span class="sxs-lookup"><span data-stu-id="b917a-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="b917a-145">Geben Sie den folgenden Ausdruck in der **Text** Eigenschaftenfeld die **WriteLine**.</span><span class="sxs-lookup"><span data-stu-id="b917a-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="b917a-146">Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und legen Sie auf die **beenden** -Abschnitt des Zustands.</span><span class="sxs-lookup"><span data-stu-id="b917a-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="b917a-147">Typ `Turns` in die **zu** Feld und `Turns + 1` in die **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.</span><span class="sxs-lookup"><span data-stu-id="b917a-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="b917a-148">Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Brotkrümelnavigation angezeigt werden soll, am oberen Rand der Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="b917a-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="b917a-149">Ziehen Sie eine **FinalState** Aktivität aus der **Zustandsautomat** im Abschnitt der **Toolbox**, zeigen sie die **Enter Guess** Zustand, und legen sie auf das Dreieck, das rechts von der **Enter Guess** versetzt, sodass ein Übergang zwischen erstellt wird **Enter Guess** und **FinalState**.</span><span class="sxs-lookup"><span data-stu-id="b917a-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="b917a-150">Der Standardname des Übergangs lautet **T2**.</span><span class="sxs-lookup"><span data-stu-id="b917a-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="b917a-151">Klicken Sie auf den Übergang im Workflow-Designer, um ihn auszuwählen, und legen Sie dessen **"DisplayName"** zu **Guess Correct**.</span><span class="sxs-lookup"><span data-stu-id="b917a-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="b917a-152">Klicken Sie dann auf, und wählen Sie die **FinalState**, und ziehen Sie es auf der rechten Seite, damit genügend Platz für den vollständigen Namen des Übergangs angezeigt werden, ohne einen der beiden Zustände zu überlagern vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b917a-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="b917a-153">Das vereinfacht die Ausführung der verbleibenden Schritte im Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="b917a-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="b917a-154">Doppelklicken Sie auf das gerade umbenannte **Guess Correct** Übergang im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b917a-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="b917a-155">Ziehen Sie eine **ReadInt** Aktivität aus der **NumberGuessWorkflowActivities** im Abschnitt der **Toolbox** und legen Sie sie in der **Trigger** Abschnitt des Übergangs.</span><span class="sxs-lookup"><span data-stu-id="b917a-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="b917a-156">In der **Fenster "Eigenschaften"** für die **ReadInt** Aktivität, Typ `"EnterGuess"` einschließlich der Anführungszeichen der **BookmarkName** Wertefeld der Eigenschaft, und geben `Guess`in die **Ergebnis** Wertefeld der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b917a-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="b917a-157">Geben Sie den folgenden Ausdruck in der **Guess Correct** des Übergangs **Bedingung** Wertefeld der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b917a-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="b917a-158">Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Brotkrümelnavigation angezeigt werden soll, am oberen Rand der Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="b917a-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b917a-159">Ein Übergang erfolgt, wenn das Triggerereignis empfangen wird und <xref:System.Activities.Statements.Transition.Condition%2A>, falls vorhanden, `True` ergibt.</span><span class="sxs-lookup"><span data-stu-id="b917a-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="b917a-160">Für diesen Übergang Wenn des Benutzers `Guess` entspricht dem zufällig generierten `Target`, übergibt die Kontrolle an die **FinalState** und der Workflow abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b917a-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="b917a-161">Je nachdem, ob die Schätzung richtig ist, sollte der Workflow Übergang entweder auf die **FinalState** oder an der **Enter Guess** Zustand versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="b917a-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="b917a-162">Beide Übergänge verwenden den gleichen Trigger warten Sie, bis der Schätzwert des Benutzers für den Empfang über den **ReadInt** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b917a-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="b917a-163">Dies wird als gemeinsamer Übergang bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b917a-163">This is called a shared transition.</span></span> <span data-ttu-id="b917a-164">Um einen gemeinsamen Übergang zu erstellen, klicken Sie auf den Kreis, der den Anfang des Zustands der **Guess Correct** Übergang aus, und ziehen Sie es auf den gewünschten Zustand.</span><span class="sxs-lookup"><span data-stu-id="b917a-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="b917a-165">In diesem Fall ist des Übergangs ein, ziehen Sie den Ausgangspunkt der **Guess Correct** übertragen, und legen diesen wieder auf den unteren Rand der **Enter Guess** Zustand.</span><span class="sxs-lookup"><span data-stu-id="b917a-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="b917a-166">Klicken Sie nach dem Erstellen des Übergangs an, wählen Sie ihn im Workflow-Designer, und legen dessen **"DisplayName"** Eigenschaft **Guess Incorrect**.</span><span class="sxs-lookup"><span data-stu-id="b917a-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b917a-167">Gemeinsame Übergänge können auch erstellt werden von innerhalb des Übergangs-Designers durch Klicken auf **gemeinsamen triggerübergang hinzufügen** am unteren Rand des Übergangs-Designers, und wählen Sie dann den gewünschten Zielzustand aus der  **Verfügbare Zustände für Verbindung** Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="b917a-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b917a-168">Wenn die <xref:System.Activities.Statements.Transition.Condition%2A>-Aktivität eines Übergangs mit `false` ausgewertet wird (oder alle Bedingungen eines Übergangs mit freigegebenem Trigger mit `false` ausgewertet werden), erfolgt der Übergang nicht, und die Trigger aller Übergänge aus dem Zustand werden neu geplant.</span><span class="sxs-lookup"><span data-stu-id="b917a-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="b917a-169">In diesem Lernprogramm kann diese Situation aufgrund der Konfigurationsmethode für die Bedingungen (es gibt spezielle Aktionen für richtige oder falsche Schätzungen) nicht auftreten.</span><span class="sxs-lookup"><span data-stu-id="b917a-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="b917a-170">Doppelklicken Sie auf die **Guess Incorrect** Übergang im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b917a-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="b917a-171">Beachten Sie, dass die **Trigger** bereits festgelegt ist, auf die gleiche **ReadInt** Aktivität, die verwendet wurde, indem die **Guess Correct** Übergang.</span><span class="sxs-lookup"><span data-stu-id="b917a-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="b917a-172">Geben Sie den folgenden Ausdruck in der **Bedingung** Wertefeld der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b917a-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="b917a-173">Ziehen Sie ein **Wenn** Aktivität aus der **Ablaufsteuerung** im Abschnitt der **Toolbox** und legen Sie sie in der **Aktion** Abschnitt des Übergangs.</span><span class="sxs-lookup"><span data-stu-id="b917a-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="b917a-174">Geben Sie den folgenden Ausdruck in der **Wenn** Aktivität **Bedingung** Wertefeld der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b917a-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="b917a-175">Ziehen Sie zwei **WriteLine** Aktivitäten aus der **primitive** Teil der **Toolbox** und legen Sie sie, dass sich eine in der **klicken Sie dann** Teil die **Wenn** -Aktivität, und eine hat die **Else** Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b917a-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="b917a-176">Klicken Sie auf die **WriteLine** -Aktivität in der **dann** Abschnitt, um es auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Wertefeld der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b917a-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="b917a-177">Klicken Sie auf die **WriteLine** -Aktivität in der **Else** Abschnitt, um es auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Wertefeld der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b917a-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="b917a-178">Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Brotkrümelnavigation angezeigt werden soll, am oberen Rand der Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="b917a-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="b917a-179">Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b917a-179">The following example illustrates the completed workflow.</span></span>  
  
     ![Abbildung der abgeschlossenen Zustandsautomatworkflow.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="b917a-181">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="b917a-181">To build the workflow</span></span>  
  
1. <span data-ttu-id="b917a-182">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b917a-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="b917a-183">Informationen zum Ausführen des Workflows finden Sie im nächste Thema, [Vorgehensweise: Ausführen eines Workflows](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b917a-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="b917a-184">Wenn Sie bereits abgeschlossen haben die [Vorgehensweise: Ausführen eines Workflows](how-to-run-a-workflow.md) Schritt mit einer anderen workflowart und ihn mithilfe der Zustandsautomatworkflows aus diesem Schritt ausführen möchten, fahren Sie mit der [erstellen und Ausführen der Anwendungs](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) Abschnitt [Vorgehensweise: Ausführen eines Workflows](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b917a-184">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b917a-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b917a-185">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="b917a-186">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="b917a-186">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="b917a-187">Entwerfen von Workflows</span><span class="sxs-lookup"><span data-stu-id="b917a-187">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="b917a-188">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="b917a-188">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="b917a-189">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="b917a-189">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="b917a-190">Vorgehensweise: Ausführen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="b917a-190">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
