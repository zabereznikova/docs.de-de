---
title: 'Gewusst wie: Erstellen eines Zustandsautomatenworkflows'
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
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 95ba37b123b57ba9f86fefb55a860fb2122ccd3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="f61ab-102">Gewusst wie: Erstellen eines Zustandsautomatenworkflows</span><span class="sxs-lookup"><span data-stu-id="f61ab-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="f61ab-103">Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f61ab-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="f61ab-104">Dieses Thema führt Sie durch Erstellen eines Workflows, die sowohl integrierten Aktivitäten, wie z. B. verwendet die <xref:System.Activities.Statements.StateMachine> Aktivität und den benutzerdefinierten Aktivitäten aus dem vorherigen [Vorgehensweise: Erstellen Sie eine Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="f61ab-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="f61ab-105">Der Workflow erstellt ein Spiel, das Zahlen errät.</span><span class="sxs-lookup"><span data-stu-id="f61ab-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f61ab-106">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="f61ab-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="f61ab-107">Um dieses Thema abzuschließen, müssen Sie zuerst ausführen [Vorgehensweise: Erstellen Sie eine Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="f61ab-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f61ab-108">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f61ab-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="f61ab-109">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="f61ab-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="f61ab-110">Mit der rechten Maustaste **NumberGuessWorkflowActivities** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="f61ab-111">In der **installiert**, **gemeinsame Elemente** Knoten **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="f61ab-112">Wählen Sie **Aktivität** aus der **Workflow** Liste.</span><span class="sxs-lookup"><span data-stu-id="f61ab-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="f61ab-113">Typ `StateMachineNumberGuessWorkflow` in der **Namen** Feld, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="f61ab-114">Ziehen Sie eine **StateMachine** Aktivität aus der **Zustandsautomat** Teil der **Toolbox** und legen ihn auf die **Aktivität hier ablegen** Beschriftung im die Entwurfsoberfläche des Workflows.</span><span class="sxs-lookup"><span data-stu-id="f61ab-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="f61ab-115">So erstellen Sie die Workflowvariablen und -argumente</span><span class="sxs-lookup"><span data-stu-id="f61ab-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="f61ab-116">Doppelklicken Sie auf **StateMachineNumberGuessWorkflow.xaml** in **Projektmappen-Explorer** um den Workflow im Designer anzuzeigen, wenn er nicht bereits angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f61ab-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="f61ab-117">Klicken Sie auf **Argumente** in der unteren linken Seite im Workflow-Designer zum Anzeigen der **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="f61ab-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="f61ab-118">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="f61ab-119">Typ `MaxNumber` in der **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f61ab-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="f61ab-120">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="f61ab-121">Typ `Turns` in der **Namen** Feld, das unterhalb der neu hinzugefügten `MaxNumber` Argument die Option **Out** aus der **Richtung** Dropdown-Liste  **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="f61ab-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="f61ab-122">Klicken Sie auf **Argumente** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="f61ab-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="f61ab-123">Klicken Sie auf **Variablen** in der unteren linken Seite im Workflow-Designer zum Anzeigen der **Variablen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="f61ab-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="f61ab-124">Klicken Sie auf **erstellen Variable**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="f61ab-125">Wenn kein **Variable erstellen** angezeigt wird, klicken Sie auf die <xref:System.Activities.Statements.StateMachine> Aktivität auf der workflowdesigneroberfläche, um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f61ab-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="f61ab-126">Typ `Guess` in der **Namen** wählen Sie im **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f61ab-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="f61ab-127">Klicken Sie auf **erstellen Variable**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="f61ab-128">Typ `Target` in der **Namen** wählen Sie im **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f61ab-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="f61ab-129">Klicken Sie auf **Variablen** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Variablen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="f61ab-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="f61ab-130">So fügen Sie die Workflowaktivitäten hinzu</span><span class="sxs-lookup"><span data-stu-id="f61ab-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="f61ab-131">Klicken Sie auf **State1** um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f61ab-131">Click **State1** to select it.</span></span> <span data-ttu-id="f61ab-132">In der **Fenster "Eigenschaften"**, ändern Sie die **DisplayName** auf `Initialize Target`.</span><span class="sxs-lookup"><span data-stu-id="f61ab-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="f61ab-133">Wenn die **Fenster "Eigenschaften"** wird nicht angezeigt werden, wählen Sie **Fenster "Eigenschaften"** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="f61ab-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="f61ab-134">Doppelklicken Sie auf den umbenannten **Ziel initialisieren** Zustand im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f61ab-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3.  <span data-ttu-id="f61ab-135">Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und legen ihn auf die **Eintrag** -Abschnitt des Zustands.</span><span class="sxs-lookup"><span data-stu-id="f61ab-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="f61ab-136">Typ `Target` in der **auf** Feld und den folgenden Ausdruck in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.</span><span class="sxs-lookup"><span data-stu-id="f61ab-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="f61ab-137">Wenn die **Toolbox** Fenster nicht angezeigt wird, wählen Sie **Toolbox** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="f61ab-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4.  <span data-ttu-id="f61ab-138">Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers.</span><span class="sxs-lookup"><span data-stu-id="f61ab-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5.  <span data-ttu-id="f61ab-139">Ziehen Sie eine **Zustand** Aktivität aus der **Zustandsautomat** Teil der **Toolbox** auf die Workflow-Designer und zeigen sie auf die **Ziel initialisieren** Zustand.</span><span class="sxs-lookup"><span data-stu-id="f61ab-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="f61ab-140">Beachten Sie, dass vier Dreiecke, um angezeigt werden die **Ziel initialisieren** Zustand, wenn der neue Zustand darüber befindet.</span><span class="sxs-lookup"><span data-stu-id="f61ab-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="f61ab-141">Legen Sie den neuen Zustand auf dem Dreieck ab, das unmittelbar unterhalb der **Ziel initialisieren** Zustand.</span><span class="sxs-lookup"><span data-stu-id="f61ab-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="f61ab-142">Dadurch wird der neue Zustand auf dem Workflow, und erstellt einen Übergang von der **Ziel initialisieren** Zustands, in dem Zustand "Neu".</span><span class="sxs-lookup"><span data-stu-id="f61ab-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6.  <span data-ttu-id="f61ab-143">Klicken Sie auf **State1** ändern, um ihn auszuwählen, die **DisplayName** auf `Enter Guess`, und doppelklicken Sie dann auf den Zustand im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f61ab-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7.  <span data-ttu-id="f61ab-144">Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** Teil der **Toolbox** und legen ihn auf die **Eintrag** -Abschnitt des Zustands.</span><span class="sxs-lookup"><span data-stu-id="f61ab-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8.  <span data-ttu-id="f61ab-145">Geben Sie den folgenden Ausdruck in der **Text** Eigenschaftenfeld der **WriteLine**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="f61ab-146">Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und legen Sie auf der **beenden** -Abschnitt des Zustands.</span><span class="sxs-lookup"><span data-stu-id="f61ab-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="f61ab-147">Typ `Turns` in der **auf** Feld und `Turns + 1` in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.</span><span class="sxs-lookup"><span data-stu-id="f61ab-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="f61ab-148">Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers.</span><span class="sxs-lookup"><span data-stu-id="f61ab-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="f61ab-149">Ziehen Sie eine **FinalState** Aktivität aus der **Zustandsautomat** im Abschnitt der **Toolbox**, zeigen sie auf die **Enter Guess** Status, und legen Sie sie auf dem Dreieck ab, die rechts neben der **Enter Guess** versetzt, sodass ein Übergang zwischen erstellt ist **Enter Guess** und **FinalState**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="f61ab-150">Der Standardname des Übergangs lautet **T2**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="f61ab-151">Klicken Sie auf den Übergang im Workflowdesigner, um auszuwählen, und legen Sie dessen **DisplayName** auf **Guess Correct**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="f61ab-152">Klicken Sie dann auf, und wählen Sie die **FinalState**, und ziehen Sie es auf der rechten Seite, damit genügend Platz für den vollständigen Namen des Übergangs angezeigt werden, ohne einen der beiden Zustände zu überlagern vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f61ab-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="f61ab-153">Das vereinfacht die Ausführung der verbleibenden Schritte im Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="f61ab-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="f61ab-154">Doppelklicken Sie auf den umbenannten **Guess Correct** Übergang im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f61ab-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="f61ab-155">Ziehen Sie eine **ReadInt** Aktivität aus der **NumberGuessWorkflowActivities** Teil der **Toolbox** und legen Sie sie in der **Trigger** Abschnitt des Übergangs.</span><span class="sxs-lookup"><span data-stu-id="f61ab-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="f61ab-156">In der **Fenster "Eigenschaften"** für die **ReadInt** -Aktivität `"EnterGuess"` einschließlich der Anführungszeichen in der **BookmarkName** Feld mit dem Eigenschaftswert ein, und geben `Guess`in der **Ergebnis** Feld mit dem Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="f61ab-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="f61ab-157">Geben Sie den folgenden Ausdruck in der **Guess Correct** des Übergangs **Bedingung** Feld mit dem Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="f61ab-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="f61ab-158">Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers.</span><span class="sxs-lookup"><span data-stu-id="f61ab-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f61ab-159">Ein Übergang erfolgt, wenn das Triggerereignis empfangen wird und <xref:System.Activities.Statements.Transition.Condition%2A>, falls vorhanden, `True` ergibt.</span><span class="sxs-lookup"><span data-stu-id="f61ab-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="f61ab-160">Bei diesem Übergang Wenn des Benutzers `Guess` entspricht, die nach dem Zufallsprinzip generierte `Target`, übergibt die Steuerung an die **FinalState** und der Workflow abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f61ab-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="f61ab-161">Je nachdem, ob die Schätzung richtig ist, sollte der Workflow Übergang entweder auf die **FinalState** oder wieder auf die **Enter Guess** Zustand versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="f61ab-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="f61ab-162">Beide Übergänge verwenden den gleichen Trigger warten Schätzwert des Benutzers über empfangen werden die **ReadInt** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f61ab-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="f61ab-163">Dies wird als gemeinsamer Übergang bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f61ab-163">This is called a shared transition.</span></span> <span data-ttu-id="f61ab-164">Um einen gemeinsamen Übergang zu erstellen, klicken Sie auf den Kreis, der den Anfang des Zustands der **Guess Correct** Übergang erfolgt, und ziehen Sie es auf den gewünschten Zustand.</span><span class="sxs-lookup"><span data-stu-id="f61ab-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="f61ab-165">In diesem Fall wird des Übergangs ein Übergang, ziehen Sie daher den Ausgangspunkt der **Guess Correct** darstellt, und legen diesen wieder auf den unteren Rand der **Enter Guess** Zustand.</span><span class="sxs-lookup"><span data-stu-id="f61ab-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="f61ab-166">Nachdem der Übergang erstellt haben, wählen sie im Workflow-Designer, und legen seine **DisplayName** Eigenschaft **Guess Incorrect**.</span><span class="sxs-lookup"><span data-stu-id="f61ab-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f61ab-167">Gemeinsame Übergänge können auch aus erstellt werden innerhalb des Übergangs-Designers durch Klicken auf **gemeinsamen triggerübergang hinzufügen** am unteren Rand des Übergangs-Designers, und wählen Sie dann den gewünschten Zielzustand aus der  **Verfügbare Zustände für Verbindung** Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="f61ab-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f61ab-168">Wenn die <xref:System.Activities.Statements.Transition.Condition%2A>-Aktivität eines Übergangs mit `false` ausgewertet wird (oder alle Bedingungen eines Übergangs mit freigegebenem Trigger mit `false` ausgewertet werden), erfolgt der Übergang nicht, und die Trigger aller Übergänge aus dem Zustand werden neu geplant.</span><span class="sxs-lookup"><span data-stu-id="f61ab-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="f61ab-169">In diesem Lernprogramm kann diese Situation aufgrund der Konfigurationsmethode für die Bedingungen (es gibt spezielle Aktionen für richtige oder falsche Schätzungen) nicht auftreten.</span><span class="sxs-lookup"><span data-stu-id="f61ab-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="f61ab-170">Doppelklicken Sie auf die **Guess Incorrect** Übergang im Workflow-Designer, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f61ab-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="f61ab-171">Beachten Sie, dass die **Trigger** bereits festgelegt ist, auf das gleiche **ReadInt** Aktivität, die verwendet wurde, indem die **Guess Correct** Übergang.</span><span class="sxs-lookup"><span data-stu-id="f61ab-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="f61ab-172">Geben Sie den folgenden Ausdruck in der **Bedingung** Feld mit dem Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="f61ab-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="f61ab-173">Ziehen Sie ein **Wenn** Aktivität aus der **Control Flow** Teil der **Toolbox** und legen Sie sie in der **Aktion** Abschnitt des Übergangs.</span><span class="sxs-lookup"><span data-stu-id="f61ab-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="f61ab-174">Geben Sie den folgenden Ausdruck in der **Wenn** Aktivität **Bedingung** Feld mit dem Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="f61ab-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="f61ab-175">Ziehen Sie zwei **WriteLine** Aktivitäten aus der **primitive** im Abschnitt der **Toolbox** und ablegen, sodass ist die **dann** im Abschnitt die **Wenn** Aktivität, und eine befindet sich in der **Else** Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f61ab-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="f61ab-176">Klicken Sie auf die **WriteLine** Aktivität in der **dann** Abschnitt, um ihn auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Feld mit dem Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="f61ab-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="f61ab-177">Klicken Sie auf die **WriteLine** Aktivität in der **Else** Abschnitt, um ihn auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Feld mit dem Eigenschaftswert.</span><span class="sxs-lookup"><span data-stu-id="f61ab-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="f61ab-178">Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers.</span><span class="sxs-lookup"><span data-stu-id="f61ab-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="f61ab-179">Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f61ab-179">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="f61ab-180">![Abgeschlossener Zustandsautomatworkflow](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="f61ab-180">![Completed State Machine Workflow](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="f61ab-181">So erstellen Sie den Workflow</span><span class="sxs-lookup"><span data-stu-id="f61ab-181">To build the workflow</span></span>  
  
1.  <span data-ttu-id="f61ab-182">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f61ab-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="f61ab-183">Anweisungen zum Ausführen des Workflows finden Sie unter dem nächsten Thema [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f61ab-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="f61ab-184">Wenn Sie bereits abgeschlossen haben die [wie: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) Schritt mit einem anderen Format des Workflows und sie mit den Zustandsautomat-Workflow aus diesen Schritt ausführen möchten, fahren Sie mit der [zum Erstellen und Ausführen der Anwendung](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) Abschnitt [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f61ab-184">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f61ab-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f61ab-185">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="f61ab-186">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="f61ab-186">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="f61ab-187">Entwerfen von Workflows</span><span class="sxs-lookup"><span data-stu-id="f61ab-187">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="f61ab-188">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="f61ab-188">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="f61ab-189">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="f61ab-189">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="f61ab-190">Vorgehensweise: Ausführen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="f61ab-190">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
