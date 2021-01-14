---
title: 'Vorgehensweise: Erstellen eines Zustandsautomatworkflows'
description: In diesem Artikel wird ein Workflow erstellt, der integrierte Aktivitäten verwendet, z. b. die StateMachine-Aktivität und benutzerdefinierte Aktivitäten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8e977a182d55143f8d877d61a0f0345bbe6bded4
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190467"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="2d17d-103">Vorgehensweise: Erstellen eines Zustandsautomatworkflows</span><span class="sxs-lookup"><span data-stu-id="2d17d-103">How to: Create a State Machine Workflow</span></span>

<span data-ttu-id="2d17d-104">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2d17d-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="2d17d-105">In diesem Thema wird Schritt für Schritt beschrieben, wie Sie einen Workflow erstellen, der integrierte Aktivitäten wie die <xref:System.Activities.Statements.StateMachine> -Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen Thema Gewusst [wie: Erstellen einer Aktivität](how-to-create-an-activity.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d17d-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="2d17d-106">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="2d17d-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d17d-107">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="2d17d-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="2d17d-108">Um dieses Thema abzuschließen, müssen Sie zunächst Gewusst [wie: Erstellen einer Aktivität durchführen](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="2d17d-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="2d17d-109">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="2d17d-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="2d17d-110">Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf " **numguess Workflow Activities** ", und wählen Sie **Hinzufügen**, **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="2d17d-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="2d17d-111">Wählen Sie im Knoten **installierte**, **Allgemeine Elemente** die Option **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="2d17d-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="2d17d-112">Wählen Sie **Aktivität** aus der Liste **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="2d17d-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="2d17d-113">Geben `StateMachineNumberGuessWorkflow` Sie im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2d17d-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="2d17d-114">Ziehen Sie eine **StateMachine** -Aktivität aus dem Abschnitt **Zustands Automat** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** auf der Workflow Entwurfs Oberfläche ab.</span><span class="sxs-lookup"><span data-stu-id="2d17d-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="2d17d-115">So erstellen Sie die Workflowvariablen und -argumente</span><span class="sxs-lookup"><span data-stu-id="2d17d-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="2d17d-116">Doppelklicken Sie in **Projektmappen-Explorer** auf **statemachinenumberguess Workflow. XAML** , um den Workflow im Designer anzuzeigen, falls er nicht bereits angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2d17d-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="2d17d-117">Klicken Sie Links unten im Workflow-Designer auf **Argumente** , um den Bereich **Argumente** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d17d-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="2d17d-118">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2d17d-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="2d17d-119">Geben `MaxNumber` Sie in das Feld **Name** ein, wählen Sie in der Dropdown Liste **Richtung** die Option **in** aus, wählen Sie **Int32** aus der Dropdown Liste **Argumenttyp** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d17d-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="2d17d-120">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2d17d-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="2d17d-121">Geben `Turns` Sie in das Feld **Name** unter dem neu hinzugefügten `MaxNumber` Argument ein, wählen Sie aus der Dropdown Liste **Richtung** die Option **aus** , wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="2d17d-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="2d17d-122">Klicken Sie unten links im Aktivitäts-Designer auf **Argumente**, um den Bereich **Argumente** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2d17d-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="2d17d-123">Klicken Sie Links unten im Workflow-Designer auf **Variablen** , um den Bereich **Variablen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d17d-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="2d17d-124">Klicken Sie auf **Variable erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2d17d-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="2d17d-125">Wenn das Feld **Variable erstellen** nicht angezeigt wird, klicken Sie auf der Oberfläche des Workflow-Designers auf die- <xref:System.Activities.Statements.StateMachine> Aktivität, um Sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2d17d-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="2d17d-126">Geben `Guess` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern</span><span class="sxs-lookup"><span data-stu-id="2d17d-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="2d17d-127">Klicken Sie auf **Variable erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2d17d-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="2d17d-128">Geben `Target` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern</span><span class="sxs-lookup"><span data-stu-id="2d17d-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="2d17d-129">Klicken Sie unten links im Aktivitäts-Designer auf **Variablen**, um den Bereich **Variablen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2d17d-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="2d17d-130">So fügen Sie die Workflowaktivitäten hinzu</span><span class="sxs-lookup"><span data-stu-id="2d17d-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="2d17d-131">Klicken Sie auf **state1** , um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2d17d-131">Click **State1** to select it.</span></span> <span data-ttu-id="2d17d-132">Ändern Sie im **Fenster Eigenschaften** den **Display Name** in `Initialize Target` .</span><span class="sxs-lookup"><span data-stu-id="2d17d-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="2d17d-133">Wenn das **Fenster Eigenschaften** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Eigenschaften Fenster** aus.</span><span class="sxs-lookup"><span data-stu-id="2d17d-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="2d17d-134">Doppelklicken Sie auf den neu umbenannten Zustand **Ziel initialisieren** im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2d17d-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="2d17d-135">Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf dem Abschnitt **Entry** des Zustands ab.</span><span class="sxs-lookup"><span data-stu-id="2d17d-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="2d17d-136">Geben Sie in das Feld `Target` **an** und den folgenden Ausdruck im Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .</span><span class="sxs-lookup"><span data-stu-id="2d17d-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="2d17d-137">Wird das Fenster **Toolbox** nicht angezeigt, wählen Sie **Toolbox** im Menü **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="2d17d-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="2d17d-138">Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.</span><span class="sxs-lookup"><span data-stu-id="2d17d-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="2d17d-139">Ziehen Sie eine **State** -Aktivität aus dem Abschnitt **Zustands Automat** der **Toolbox** auf den Workflow-Designer, und bewegen Sie den Mauszeiger über den Zustand **Ziel initialisieren** .</span><span class="sxs-lookup"><span data-stu-id="2d17d-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="2d17d-140">Beachten Sie, dass vier Dreiecke um den **Initialisierungs Ziel** Status angezeigt werden, wenn sich der neue Status darüber befindet.</span><span class="sxs-lookup"><span data-stu-id="2d17d-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="2d17d-141">Legen Sie den neuen Zustand auf dem Dreieck ab, das sich direkt unterhalb des **Ziel Zustands initialisieren** befindet.</span><span class="sxs-lookup"><span data-stu-id="2d17d-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="2d17d-142">Dadurch wird der neue Zustand auf dem Workflow platziert, und es wird ein Übergang vom Zustand " **Initialize Target** " in den neuen Zustand erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d17d-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="2d17d-143">Klicken Sie auf **state1** , um es auszuwählen, ändern Sie **Display Name** in `Enter Guess` , und doppelklicken Sie dann auf den Zustand im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2d17d-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="2d17d-144">Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf dem Abschnitt **Entry** des Zustands ab.</span><span class="sxs-lookup"><span data-stu-id="2d17d-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="2d17d-145">Geben Sie den folgenden Ausdruck in das **Text** -Eigenschaften Feld von " **Write teline**" ein.</span><span class="sxs-lookup"><span data-stu-id="2d17d-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="2d17d-146">Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf dem **Exit** -Abschnitt des Zustands ab.</span><span class="sxs-lookup"><span data-stu-id="2d17d-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="2d17d-147">Geben `Turns` Sie im Feld **an** und `Turns + 1` im Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .</span><span class="sxs-lookup"><span data-stu-id="2d17d-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="2d17d-148">Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.</span><span class="sxs-lookup"><span data-stu-id="2d17d-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="2d17d-149">Ziehen Sie eine **FinalState** -Aktivität aus dem Abschnitt **Zustands Automat** der **Toolbox**, zeigen Sie mit dem Mauszeiger auf den Status **Enter Guess** , und legen Sie ihn auf dem Dreieck ab, das rechts neben dem Status **Eingabe Raten** angezeigt wird, sodass ein Übergang zwischen **Enter Guess** und **FinalState** erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2d17d-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="2d17d-150">Der Standardname des Übergangs ist **T2**.</span><span class="sxs-lookup"><span data-stu-id="2d17d-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="2d17d-151">Klicken Sie auf den Übergang im Workflow-Designer, um ihn auszuwählen, und legen Sie dessen **Display Name** auf **Guess correct** fest.</span><span class="sxs-lookup"><span data-stu-id="2d17d-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="2d17d-152">Klicken Sie anschließend auf **FinalState**, und ziehen Sie ihn nach rechts, damit genügend Platz vorhanden ist, damit der vollständige Übergangs Name angezeigt wird, ohne einen der beiden Zustände zu überlagern.</span><span class="sxs-lookup"><span data-stu-id="2d17d-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="2d17d-153">Das vereinfacht die Ausführung der verbleibenden Schritte im Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="2d17d-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="2d17d-154">Doppelklicken Sie im Workflow-Designer auf den neu umbenannten Abschnitt " **Guess correct** ", um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2d17d-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="2d17d-155">Ziehen Sie eine Aktivität "read **int** " aus dem Abschnitt " **nummeriguess Workflow Activities** " der **Toolbox** , und legen Sie Sie im **triggerabschnitt** des Übergangs ab.</span><span class="sxs-lookup"><span data-stu-id="2d17d-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="2d17d-156">Geben Sie im **Eigenschaften Fenster** für die Aktivität "read **int** " `"EnterGuess"` die Anführungszeichen in das Feld **BookmarkName** -Eigenschafts Wert ein, und geben Sie `Guess` in das Feld **Ergebnis** Eigenschafts Wert ein.</span><span class="sxs-lookup"><span data-stu-id="2d17d-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="2d17d-157">Geben Sie den folgenden Ausdruck in das Feld **Eigenschafts Wert des Bedingungs** Werts des Übergangs **erraten** ein.</span><span class="sxs-lookup"><span data-stu-id="2d17d-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="2d17d-158">Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.</span><span class="sxs-lookup"><span data-stu-id="2d17d-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2d17d-159">Ein Übergang erfolgt, wenn das Triggerereignis empfangen wird und <xref:System.Activities.Statements.Transition.Condition%2A>, falls vorhanden, `True` ergibt.</span><span class="sxs-lookup"><span data-stu-id="2d17d-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="2d17d-160">Wenn der Benutzer für diesen Übergang `Guess` mit dem zufällig generierten übereinstimmt `Target` , übergibt die Steuerung an den **FinalState** , und der Workflow wird beendet.</span><span class="sxs-lookup"><span data-stu-id="2d17d-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="2d17d-161">Abhängig davon, ob der Schätzwert richtig ist, sollte der Workflow für einen anderen Versuch entweder in den **FinalState** oder zurück in den Zustand " **Enter Guess** " übergehen.</span><span class="sxs-lookup"><span data-stu-id="2d17d-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="2d17d-162">Beide Übergänge verwenden denselben-Triggern, der darauf wartet, dass die Schätzung des Benutzers über die Read **int** -Aktivität empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="2d17d-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="2d17d-163">Dies wird als gemeinsamer Übergang bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2d17d-163">This is called a shared transition.</span></span> <span data-ttu-id="2d17d-164">Um einen freigegebenen Übergang zu erstellen, klicken Sie auf den Kreis, der den Anfang des **korrekten Guess** -Übergangs angibt, und ziehen Sie ihn in den gewünschten Zustand.</span><span class="sxs-lookup"><span data-stu-id="2d17d-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="2d17d-165">In diesem Fall handelt es sich bei dem Übergang um einen selbst Übergang. ziehen Sie daher den Startpunkt des über-/Unterbrechungs **-Übergangs,** und legen Sie ihn wieder am unteren Ende des Zustands für die **Eingabe Vermutung** ab</span><span class="sxs-lookup"><span data-stu-id="2d17d-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="2d17d-166">Nachdem Sie den Übergang erstellt haben, wählen Sie ihn im Workflow-Designer aus, und legen Sie dessen Eigenschaft **Display Name** auf nicht **richtig** fest.</span><span class="sxs-lookup"><span data-stu-id="2d17d-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2d17d-167">Freigegebene Übergänge können auch aus dem Übergangs-Designer erstellt werden, indem Sie im unteren Bereich des Übergangs-Designers auf frei **gegebenen triggerübergang hinzufügen** klicken und dann den gewünschten Ziel Status aus der Dropdown Liste **Verfügbare Zustände zum Verbinden** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2d17d-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="2d17d-168">Wenn die <xref:System.Activities.Statements.Transition.Condition%2A>-Aktivität eines Übergangs mit `false` ausgewertet wird (oder alle Bedingungen eines Übergangs mit freigegebenem Trigger mit `false` ausgewertet werden), erfolgt der Übergang nicht, und die Trigger aller Übergänge aus dem Zustand werden neu geplant.</span><span class="sxs-lookup"><span data-stu-id="2d17d-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="2d17d-169">In diesem Lernprogramm kann diese Situation aufgrund der Konfigurationsmethode für die Bedingungen (es gibt spezielle Aktionen für richtige oder falsche Schätzungen) nicht auftreten.</span><span class="sxs-lookup"><span data-stu-id="2d17d-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="2d17d-170">Doppelklicken Sie im Workflow-Designer auf den Übergang **erraten** , um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2d17d-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="2d17d-171">Beachten Sie, dass der- **Triggerwert** bereits auf die gleiche Read **int** -Aktivität festgelegt ist **, die von der falschen** Übertragung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2d17d-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="2d17d-172">Geben **Sie im Feld Bedingungs Eigenschaften Wert** den folgenden Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="2d17d-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="2d17d-173">Ziehen Sie eine **if** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie Sie im Abschnitt **Aktion** des Übergangs ab.</span><span class="sxs-lookup"><span data-stu-id="2d17d-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="2d17d-174">Geben Sie den folgenden Ausdruck in das Feld Bedingungs **Eigenschafts Wert** der **if** -Aktivität ein.</span><span class="sxs-lookup"><span data-stu-id="2d17d-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
24. <span data-ttu-id="2d17d-175">Ziehen Sie zwei **Write** -Aktivitäten aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie diese so ab, dass Sie sich im **Then** -Abschnitt der **if** -Aktivität befinden und eine im Abschnitt **else** .</span><span class="sxs-lookup"><span data-stu-id="2d17d-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="2d17d-176">Klicken Sie im Abschnitt **Then** auf die Aktivität **Write** -Aktivität, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert ein.</span><span class="sxs-lookup"><span data-stu-id="2d17d-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="2d17d-177">Klicken Sie im Abschnitt **else** auf die Aktivität **Write** -Aktivität, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert ein.</span><span class="sxs-lookup"><span data-stu-id="2d17d-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="2d17d-178">Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.</span><span class="sxs-lookup"><span data-stu-id="2d17d-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="2d17d-179">Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2d17d-179">The following example illustrates the completed workflow.</span></span>  
  
     ![Die Abbildung zeigt den abgeschlossenen Zustandsautomatworkflow.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="2d17d-181">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="2d17d-181">To build the workflow</span></span>  
  
1. <span data-ttu-id="2d17d-182">Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d17d-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="2d17d-183">Anweisungen zum Ausführen des Workflows finden Sie im nächsten Thema Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="2d17d-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="2d17d-184">Wenn Sie den Schritt Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md) mit einem anderen Workflow Workflow abgeschlossen haben und ihn mit dem Zustandsautomatworkflow aus diesem Schritt ausführen möchten, fahren Sie mit dem Abschnitt so [Erstellen und führen Sie den Anwendungs](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) Abschnitt "Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md)" fort.</span><span class="sxs-lookup"><span data-stu-id="2d17d-184">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d17d-185">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d17d-185">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="2d17d-186">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="2d17d-186">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="2d17d-187">Entwerfen von Workflows</span><span class="sxs-lookup"><span data-stu-id="2d17d-187">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="2d17d-188">Lernprogramm 'Erste Schritte'</span><span class="sxs-lookup"><span data-stu-id="2d17d-188">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="2d17d-189">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="2d17d-189">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="2d17d-190">Vorgehensweise: Ausführen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="2d17d-190">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
