---
title: 'Vorgehensweise: Ausführen eines Workflows'
description: In diesem Artikel erfahren Sie, wie Sie einen Workflow Host erstellen und den Workflow ausführen, der in einem vorherigen Artikel dieser Windows Workflow Foundation tutorialreihe definiert wurde.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 7f76ed5ad1a76a155489339a9febf12eefd64ae8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279986"
---
# <a name="how-to-run-a-workflow"></a><span data-ttu-id="e717d-103">Vorgehensweise: Ausführen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="e717d-103">How to: Run a Workflow</span></span>

<span data-ttu-id="e717d-104">Dieses Thema ist eine Fortsetzung des Tutorials „Windows Workflow Foundation: Erste Schritte“. Hierin wird beschrieben, wie Sie einen Workflowhost erstellen und den im vorherigen Thema [How to: Create a Workflow](how-to-create-a-workflow.md) definierten Workflow ausführen.</span><span class="sxs-lookup"><span data-stu-id="e717d-104">This topic is a continuation of the Windows Workflow Foundation Getting Started tutorial and discusses how to create a workflow host and run the workflow defined in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="e717d-105">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="e717d-105">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="e717d-106">Um dieses Thema verwenden zu können, müssen Sie zuerst [How to: Create an Activity](how-to-create-an-activity.md) und [How to: Create a Workflow](how-to-create-a-workflow.md)durcharbeiten und abschließen.</span><span class="sxs-lookup"><span data-stu-id="e717d-106">To complete this topic you must first complete [How to: Create an Activity](how-to-create-an-activity.md) and [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e717d-107">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e717d-107">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow-host-project"></a><span data-ttu-id="e717d-108">So erstellen Sie das Workflowhostprojekt</span><span class="sxs-lookup"><span data-stu-id="e717d-108">To create the workflow host project</span></span>  
  
1. <span data-ttu-id="e717d-109">Öffnen Sie die Projekt Mappe aus dem vorherigen Thema Gewusst [wie: Erstellen einer Aktivität](how-to-create-an-activity.md) mithilfe von Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="e717d-109">Open the solution from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic by using Visual Studio 2012.</span></span>  
  
2. <span data-ttu-id="e717d-110">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **WF45GettingStartedTutorial** , zeigen Sie auf **Hinzufügen**, und wählen Sie **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="e717d-110">Right-click the **WF45GettingStartedTutorial** solution in **Solution Explorer** and select **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="e717d-111">Wird das Fenster **Projektmappen-Explorer** nicht angezeigt, wählen Sie **Projektmappen-Explorer** im Menü **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="e717d-111">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="e717d-112">Wählen Sie im Knoten **Installiert** die Option **Visual C#** und anschließend **Workflow** (oder **Visual Basic**, **Workflow**) aus.</span><span class="sxs-lookup"><span data-stu-id="e717d-112">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e717d-113">Abhängig davon, welche Programmiersprache als primäre Sprache in Visual Studio konfiguriert ist, kann sich der Knoten **Visual C#** oder **Visual Basic** unter dem Knoten **Andere Sprachen** im Knoten **Installiert** befinden.</span><span class="sxs-lookup"><span data-stu-id="e717d-113">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="e717d-114">Stellen Sie sicher, dass **.NET Framework 4.5** in der Dropdownliste für die .NET Framework-Version ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e717d-114">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="e717d-115">Wählen Sie in der Liste **Workflow** die Option **Konsolenanwendung für Workflows** aus.</span><span class="sxs-lookup"><span data-stu-id="e717d-115">Select **Workflow Console Application** from the **Workflow** list.</span></span> <span data-ttu-id="e717d-116">Geben Sie im Feld `NumberGuessWorkflowHost` Name **die Bezeichnung** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e717d-116">Type `NumberGuessWorkflowHost` into the **Name** box and click **OK**.</span></span> <span data-ttu-id="e717d-117">Auf diese Weise wird eine Start-Workflowanwendung mit grundlegender Unterstützung von Workflowhosting erstellt.</span><span class="sxs-lookup"><span data-stu-id="e717d-117">This creates a starter workflow application with basic workflow hosting support.</span></span> <span data-ttu-id="e717d-118">Dieser grundlegende Hostingcode wird geändert und zum Ausführen der Workflowanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e717d-118">This basic hosting code is modified and used to run the workflow application.</span></span>

4. <span data-ttu-id="e717d-119">Klicken Sie im Projektmappen-Explorer  mit der rechten Maustaste auf das neu hinzugefügte Projekt **NumberGuessWorkflowHost** , und wählen Sie **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="e717d-119">Right-click the newly added **NumberGuessWorkflowHost** project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="e717d-120">Wählen Sie in der Liste **Verweis hinzufügen** den Eintrag **Projektmappe** aus, aktivieren Sie das Kontrollkästchen neben **NumberGuessWorkflowActivities**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e717d-120">Select **Solution** from the **Add Reference** list, check the checkbox beside **NumberGuessWorkflowActivities**, and then click **OK**.</span></span>

5. <span data-ttu-id="e717d-121">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Workflow1.xaml** , und wählen Sie **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="e717d-121">Right-click **Workflow1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="e717d-122">Klicken Sie auf **OK** , um zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="e717d-122">Click **OK** to confirm.</span></span>

### <a name="to-modify-the-workflow-hosting-code"></a><span data-ttu-id="e717d-123">So ändern Sie den Code zum Hosten von Workflows</span><span class="sxs-lookup"><span data-stu-id="e717d-123">To modify the workflow hosting code</span></span>

1. <span data-ttu-id="e717d-124">Doppelklicken Sie im **Projektmappen-Explorer** auf **Program.cs** oder **Module1.vb** , um den Code anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e717d-124">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to display the code.</span></span>

    > [!TIP]
    > <span data-ttu-id="e717d-125">Wird das Fenster **Projektmappen-Explorer** nicht angezeigt, wählen Sie **Projektmappen-Explorer** im Menü **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="e717d-125">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

     <span data-ttu-id="e717d-126">Da dieses Projekt mit der Vorlage **Konsolenanwendung für Workflows** erstellt wurde, enthält **Program.cs** oder **Module1.vb** den folgenden grundlegenden Code zum Hosten von Workflows.</span><span class="sxs-lookup"><span data-stu-id="e717d-126">Because this project was created by using the **Workflow Console Application** template, **Program.cs** or **Module1.vb** contains the following basic workflow hosting code.</span></span>

    ```vb
    ' Create and cache the workflow definition.
    Dim workflow1 As Activity = New Workflow1()
    WorkflowInvoker.Invoke(workflow1)
    ```

    ```csharp
    // Create and cache the workflow definition.
    Activity workflow1 = new Workflow1();
    WorkflowInvoker.Invoke(workflow1);
    ```

     <span data-ttu-id="e717d-127">Der generierte Hostingcode verwendet <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="e717d-127">This generated hosting code uses <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="e717d-128"><xref:System.Activities.WorkflowInvoker> stellt eine einfache Möglichkeit zum Aufrufen eines Workflows bereit, so als handelte es sich um einen Methodenaufruf, und kann nur für Workflows verwendet werden, die keine Persistenz verwenden.</span><span class="sxs-lookup"><span data-stu-id="e717d-128"><xref:System.Activities.WorkflowInvoker> provides a simple way for invoking a workflow as if it were a method call and can be used only for workflows that do not use persistence.</span></span> <span data-ttu-id="e717d-129"><xref:System.Activities.WorkflowApplication> bietet ein umfangreicheres Modell zum Ausführen von Workflows, die Benachrichtigungen über Lebenszyklusereignisse, Ausführungssteuerung, Wiederaufnahme von Lesezeichen und Persistenz enthalten.</span><span class="sxs-lookup"><span data-stu-id="e717d-129"><xref:System.Activities.WorkflowApplication> provides a richer model for executing workflows that includes notification of life-cycle events, execution control, bookmark resumption, and persistence.</span></span> <span data-ttu-id="e717d-130">In diesem Beispiel werden Lesezeichen verwendet, und <xref:System.Activities.WorkflowApplication> wird zum Hosten des Workflows genutzt.</span><span class="sxs-lookup"><span data-stu-id="e717d-130">This example uses bookmarks and <xref:System.Activities.WorkflowApplication> is used for hosting the workflow.</span></span> <span data-ttu-id="e717d-131">Fügen Sie die folgende `using` - oder **Imports** -Anweisung am Anfang von **Program.cs** oder **Module1.vb** unter der vorhandenen **using** - oder **Imports** -Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e717d-131">Add the following `using` or **Imports** statement at the top of **Program.cs** or **Module1.vb** below the existing **using** or **Imports** statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     <span data-ttu-id="e717d-132">Ersetzen Sie die Codezeilen, in denen <xref:System.Activities.WorkflowInvoker> mit dem folgenden grundlegenden <xref:System.Activities.WorkflowApplication> -Hostingcode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e717d-132">Replace the lines of code that use <xref:System.Activities.WorkflowInvoker> with the following basic <xref:System.Activities.WorkflowApplication> hosting code.</span></span> <span data-ttu-id="e717d-133">In diesem Beispielhostingcode werden die grundlegenden Schritte zum Hosten und das Aufrufen eines Workflows veranschaulicht, das Beispiel enthält jedoch noch nicht die Funktionalität zum erfolgreichen Ausführen des Workflows aus diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="e717d-133">This sample hosting code demonstrates the basic steps for hosting and invoking a workflow, but does not yet contain the functionality to successfully run the workflow from this topic.</span></span> <span data-ttu-id="e717d-134">In den folgenden Schritten wird der grundlegende Code geändert, und es werden zusätzliche Funktionen hinzugefügt, bis die Anwendung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e717d-134">In the following steps, this basic code is modified and additional features are added until the application is complete.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e717d-135">Ersetzen Sie `Workflow1` in diesen Beispielen durch `FlowchartNumberGuessWorkflow`, und wählen Sie `SequentialNumberGuessWorkflow`, und wählen Sie or `StateMachineNumberGuessWorkflow`, und wählen Sie depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="e717d-135">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="e717d-136">Wenn Sie `Workflow1` nicht ersetzen, erhalten Sie Buildfehler, wenn Sie versuchen, den Workflow zu erstellen oder auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e717d-136">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     <span data-ttu-id="e717d-137">In diesem Code wird ein <xref:System.Activities.WorkflowApplication>-Element erstellt, es werden drei Lebenszyklusereignisse des Workflows abonniert, der Workflow wird per Aufruf von <xref:System.Activities.WorkflowApplication.Run%2A>gestartet, und dann wird auf den Abschluss des Workflows gewartet.</span><span class="sxs-lookup"><span data-stu-id="e717d-137">This code creates a <xref:System.Activities.WorkflowApplication>, subscribes to three workflow life-cycle events, starts the workflow with a call to <xref:System.Activities.WorkflowApplication.Run%2A>, and then waits for the workflow to complete.</span></span> <span data-ttu-id="e717d-138">Nach Abschluss des Workflows wird <xref:System.Threading.AutoResetEvent> festgelegt, und die Hostanwendung wird abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e717d-138">When the workflow completes, the <xref:System.Threading.AutoResetEvent> is set and the host application completes.</span></span>

### <a name="to-set-input-arguments-of-a-workflow"></a><span data-ttu-id="e717d-139">So legen Sie die Eingabeargumente eines Workflows fest</span><span class="sxs-lookup"><span data-stu-id="e717d-139">To set input arguments of a workflow</span></span>

1. <span data-ttu-id="e717d-140">Fügen Sie oben in der Datei **Program.cs** oder **Module1.vb** unter den vorhandenen `using` - oder `Imports` -Anweisung die folgende Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e717d-140">Add the following statement at the top of **Program.cs** or **Module1.vb** below the existing `using` or `Imports` statements.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. <span data-ttu-id="e717d-141">Ersetzen Sie die Codezeile, die das neue <xref:System.Activities.WorkflowApplication> -Element erstellt, durch den folgenden Code, der ein Wörterbuch mit Parametern erstellt und dieses nach seiner Erstellung an den Workflow übergibt.</span><span class="sxs-lookup"><span data-stu-id="e717d-141">Replace the line of code that creates the new <xref:System.Activities.WorkflowApplication> with the following code that creates and passes a dictionary of parameters to the workflow when it is created.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e717d-142">Ersetzen Sie `Workflow1` in diesen Beispielen durch `FlowchartNumberGuessWorkflow`, und wählen Sie `SequentialNumberGuessWorkflow`, und wählen Sie or `StateMachineNumberGuessWorkflow`, und wählen Sie depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="e717d-142">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="e717d-143">Wenn Sie `Workflow1` nicht ersetzen, erhalten Sie Buildfehler, wenn Sie versuchen, den Workflow zu erstellen oder auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e717d-143">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="e717d-144">Dieses Wörterbuch enthält ein Element mit dem Schlüssel `MaxNumber`.</span><span class="sxs-lookup"><span data-stu-id="e717d-144">This dictionary contains one element with a key of `MaxNumber`.</span></span> <span data-ttu-id="e717d-145">Schlüssel im Eingabewörterbuch entsprechen Eingabeargumenten in der Stammaktivität des Workflows.</span><span class="sxs-lookup"><span data-stu-id="e717d-145">Keys in the input dictionary correspond to input arguments on the root activity of the workflow.</span></span> <span data-ttu-id="e717d-146">`MaxNumber` wird vom Workflow verwendet, um die Obergrenze für die zufällig generierte Zahl zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e717d-146">`MaxNumber` is used by the workflow to determine the upper bound for the randomly generated number.</span></span>

### <a name="to-retrieve-output-arguments-of-a-workflow"></a><span data-ttu-id="e717d-147">So rufen Sie die Ausgabeargumente eines Workflows ab</span><span class="sxs-lookup"><span data-stu-id="e717d-147">To retrieve output arguments of a workflow</span></span>

1. <span data-ttu-id="e717d-148">Ändern Sie den <xref:System.Activities.WorkflowApplication.Completed%2A> -Handler, um die Anzahl der vom Workflow verwendeten Durchgänge (turns) abzurufen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e717d-148">Modify the <xref:System.Activities.WorkflowApplication.Completed%2A> handler to retrieve and display the number of turns used by the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a><span data-ttu-id="e717d-149">So nehmen Sie ein Lesezeichen wieder auf</span><span class="sxs-lookup"><span data-stu-id="e717d-149">To resume a bookmark</span></span>

1. <span data-ttu-id="e717d-150">Fügen Sie oben in der `Main` -Methode direkt nach der bestehenden <xref:System.Threading.AutoResetEvent> -Deklaration den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="e717d-150">Add the following code at the top of the `Main` method just after the existing <xref:System.Threading.AutoResetEvent> declaration.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. <span data-ttu-id="e717d-151">Fügen Sie direkt unterhalb der drei bestehenden Lebenszyklushandler des Workflows im Abschnitt <xref:System.Activities.WorkflowApplication.Idle%2A> den folgenden `Main`-Handler hinzu.</span><span class="sxs-lookup"><span data-stu-id="e717d-151">Add the following <xref:System.Activities.WorkflowApplication.Idle%2A> handler just below the existing three workflow life-cycle handlers in `Main`.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     <span data-ttu-id="e717d-152">Jedes Mal, wenn der Workflow in den Leerlauf wechselt und auf die nächste Vermutung wartet, wird dieser Handler aufgerufen, und der `idleAction` <xref:System.Threading.AutoResetEvent> wird festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e717d-152">Each time the workflow becomes idle waiting for the next guess, this handler is called and the `idleAction` <xref:System.Threading.AutoResetEvent> is set.</span></span> <span data-ttu-id="e717d-153">Der Code im folgenden Schritt verwendet `idleEvent` und `syncEvent` , um zu ermitteln, ob der Workflow auf den nächsten Lösungsversuch wartet oder abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e717d-153">The code in the following step uses `idleEvent` and `syncEvent` to determine whether the workflow is waiting for the next guess or is complete.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e717d-154">In diesem Beispiel verwendet die Hostanwendung AutoReset-Ereignisse in den Handlern <xref:System.Activities.WorkflowApplication.Completed%2A> und <xref:System.Activities.WorkflowApplication.Idle%2A> , um die Hostanwendung mit dem Status des Workflows zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="e717d-154">In this example, the host application uses auto-reset events in the <xref:System.Activities.WorkflowApplication.Completed%2A> and <xref:System.Activities.WorkflowApplication.Idle%2A> handlers to synchronize the host application with the progress of the workflow.</span></span> <span data-ttu-id="e717d-155">Das Blockieren und das Warten auf den Eintritt des Workflows in den Leerlaufzustand ist nicht erforderlich, bevor ein Lesezeichen wiederaufgenommen wird. In diesem Beispiel sind die Synchronisierungsereignisse jedoch erforderlich, damit der Host weiß, ob der Workflow abgeschlossen ist oder ob dieser mithilfe von <xref:System.Activities.Bookmark>auf weitere Benutzereingaben wartet.</span><span class="sxs-lookup"><span data-stu-id="e717d-155">It is not necessary to block and wait for the workflow to become idle before resuming a bookmark, but in this example the synchronization events are required so the host knows whether the workflow is complete or whether it is waiting on more user input by using the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="e717d-156">Weitere Informationen finden Sie unter [Lesezeichen](bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="e717d-156">For more information, see [Bookmarks](bookmarks.md).</span></span>

3. <span data-ttu-id="e717d-157">Entfernen Sie den Aufruf von `WaitOne`, und ersetzen Sie diesen durch Code zum Erfassen der Eingabe des Benutzers und zum Wiederaufnehmen von <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="e717d-157">Remove the call to `WaitOne`, and replace it with code to gather input from the user and resume the <xref:System.Activities.Bookmark>.</span></span>

     <span data-ttu-id="e717d-158">Entfernen Sie die folgende Codezeile.</span><span class="sxs-lookup"><span data-stu-id="e717d-158">Remove the following line of code.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     <span data-ttu-id="e717d-159">Ersetzen Sie diese durch den folgenden Beispielcode.</span><span class="sxs-lookup"><span data-stu-id="e717d-159">Replace it with the following example.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="to-build-and-run-the-application"></a><a name="BKMK_ToRunTheApplication"></a> <span data-ttu-id="e717d-160">So erstellen Sie die Anwendung und führen Sie aus</span><span class="sxs-lookup"><span data-stu-id="e717d-160">To build and run the application</span></span>

1. <span data-ttu-id="e717d-161">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **NumberGuessWorkflowHost** , und wählen Sie **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="e717d-161">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="e717d-162">Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e717d-162">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="e717d-163">Versuchen Sie, die Zahl in möglichst wenigen Durchgängen zu erraten.</span><span class="sxs-lookup"><span data-stu-id="e717d-163">Try to guess the number in as few turns as possible.</span></span>

     <span data-ttu-id="e717d-164">Um die Anwendung mit einem der anderen Workflowtypen auszuprobieren, ersetzen Sie `Workflow1` im Code, durch den <xref:System.Activities.WorkflowApplication> erstellt wird, durch `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`oder `StateMachineNumberGuessWorkflow`, je nachdem, welcher Workflowtyp gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="e717d-164">To try the application with one of the other styles of workflow, replace `Workflow1` in the code that creates the <xref:System.Activities.WorkflowApplication> with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow style you desire.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="e717d-165">Eine Anleitung dazu, wie Sie einer Workflowanwendung Persistenz hinzufügen, finden Sie im nächsten Thema: [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="e717d-165">For instructions about how to add persistence to a workflow application, see the next topic, [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).</span></span>

## <a name="example"></a><span data-ttu-id="e717d-166">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e717d-166">Example</span></span>

 <span data-ttu-id="e717d-167">Das folgende Beispiel ist die vollständige Codeauflistung für die `Main` -Methode.</span><span class="sxs-lookup"><span data-stu-id="e717d-167">The following example is the complete code listing for the `Main` method.</span></span>

> [!NOTE]
> <span data-ttu-id="e717d-168">Ersetzen Sie `Workflow1` in diesen Beispielen durch `FlowchartNumberGuessWorkflow`, und wählen Sie `SequentialNumberGuessWorkflow`, und wählen Sie or `StateMachineNumberGuessWorkflow`, und wählen Sie depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="e717d-168">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="e717d-169">Wenn Sie `Workflow1` nicht ersetzen, erhalten Sie Buildfehler, wenn Sie versuchen, den Workflow zu erstellen oder auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e717d-169">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a><span data-ttu-id="e717d-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e717d-170">See also</span></span>

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [<span data-ttu-id="e717d-171">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="e717d-171">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="e717d-172">Lernprogramm 'Erste Schritte'</span><span class="sxs-lookup"><span data-stu-id="e717d-172">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="e717d-173">Vorgehensweise: Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="e717d-173">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="e717d-174">Vorgehensweise: Erstellen und Ausführen eines Workflows mit langer Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e717d-174">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)
- [<span data-ttu-id="e717d-175">Warten auf Eingabe in einem Workflow</span><span class="sxs-lookup"><span data-stu-id="e717d-175">Waiting for Input in a Workflow</span></span>](waiting-for-input-in-a-workflow.md)
- [<span data-ttu-id="e717d-176">Hosten von Workflows</span><span class="sxs-lookup"><span data-stu-id="e717d-176">Hosting Workflows</span></span>](hosting-workflows.md)
