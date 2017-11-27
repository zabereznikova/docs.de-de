---
title: 'Vorgehensweise: Paralleles Hosten mehrerer Workflowversionen'
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
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 713417131338dd683906eb2de56e615d4aa13c10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="028a5-102">Vorgehensweise: Paralleles Hosten mehrerer Workflowversionen</span><span class="sxs-lookup"><span data-stu-id="028a5-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>
<span data-ttu-id="028a5-103">`WorkflowIdentity` bietet Entwicklern von Workflowanwendungen die Möglichkeit, einer Worfklowdefinition einen Namen und eine Version zuzuordnen und diese Informationen mit einer persistenten Workflowinstanz zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="028a5-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="028a5-104">Entwickler von Workflowanwendungen können diese Identitätsinformationen verwenden, um Szenarien wie die parallele Ausführung mehrerer Versionen einer Workflowdefinition umzusetzen. Darüber hinaus bilden sie die Grundlage für andere Funktionen wie dynamische Updates.</span><span class="sxs-lookup"><span data-stu-id="028a5-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="028a5-105">In diesem Schritt des Lernprogramms wird veranschaulicht, wie mit `WorkflowIdentity` mehrere Versionen eines Workflows gleichzeitig gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="028a5-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="028a5-106">Um den download einer vervollständigten Version oder eine Videodemonstration des Lernprogramms anzuzeigen, finden Sie unter [Windows Workflow Foundation (WF45) – Lernprogramm für erste Schritte](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="028a5-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="028a5-107">In diesem Thema</span><span class="sxs-lookup"><span data-stu-id="028a5-107">In this topic</span></span>  
 <span data-ttu-id="028a5-108">In diesem Schritt des Lernprogramms werden die `WriteLine`-Aktivitäten im Workflow geändert, um zusätzliche Informationen bereitzustellen. Außerdem wird eine neue `WriteLine`-Aktivität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="028a5-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="028a5-109">Eine Kopie der ursprünglichen Workflowassembly wird gespeichert, und die Hostanwendung wird aktualisiert, sodass der ursprüngliche und der aktualisierte Workflow gleichzeitig ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="028a5-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>  
  
-   [<span data-ttu-id="028a5-110">Um eine Kopie des NumberGuessWorkflowActivities-Projekts</span><span class="sxs-lookup"><span data-stu-id="028a5-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [<span data-ttu-id="028a5-111">Um Workflows zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="028a5-111">To update the workflows</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [<span data-ttu-id="028a5-112">So aktualisieren Sie die StateMachine-workflow</span><span class="sxs-lookup"><span data-stu-id="028a5-112">To update the StateMachine workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [<span data-ttu-id="028a5-113">So aktualisieren Sie die Flussdiagramm-workflow</span><span class="sxs-lookup"><span data-stu-id="028a5-113">To update the Flowchart workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [<span data-ttu-id="028a5-114">So aktualisieren Sie die sequenziellen workflow</span><span class="sxs-lookup"><span data-stu-id="028a5-114">To update the Sequential workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [<span data-ttu-id="028a5-115">So aktualisieren Sie WorkflowVersionMap, um die vorherigen workflowversionen einzuschließen</span><span class="sxs-lookup"><span data-stu-id="028a5-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [<span data-ttu-id="028a5-116">So erstellen und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="028a5-116">To build and run the application</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  <span data-ttu-id="028a5-117">Bevor Sie die Schritte in diesem Thema ausführen, führen Sie die Anwendung aus, starten mehrere Workflows jedes Typs und geben einen oder zwei Schätzwerte für jeden Typ an.</span><span class="sxs-lookup"><span data-stu-id="028a5-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="028a5-118">Diese permanenten Workflows werden in diesem und den folgenden Schritt verwendet [Vorgehensweise: Aktualisieren Sie die Definition einer Workflowinstanz ausgeführt](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="028a5-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="028a5-119">Jeder Schritt im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Schritten ab.</span><span class="sxs-lookup"><span data-stu-id="028a5-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="028a5-120">Wenn Sie nicht die vorherigen Schritte abgeschlossen haben können Sie eine abgeschlossene Version des Lernprogramms von herunterladen [Windows Workflow Foundation (WF45) – Lernprogramm für erste Schritte](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="028a5-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
###  <span data-ttu-id="028a5-121"><a name="BKMK_BackupCopy"></a>Um eine Kopie des NumberGuessWorkflowActivities-Projekts</span><span class="sxs-lookup"><span data-stu-id="028a5-121"><a name="BKMK_BackupCopy"></a> To make a copy of the NumberGuessWorkflowActivities project</span></span>  
  
1.  <span data-ttu-id="028a5-122">Öffnen Sie die **WF45GettingStartedTutorial** -Lösung in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] , wenn er nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="028a5-122">Open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] if it is not open.</span></span>  
  
2.  <span data-ttu-id="028a5-123">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="028a5-123">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="028a5-124">Schließen der **WF45GettingStartedTutorial** Lösung.</span><span class="sxs-lookup"><span data-stu-id="028a5-124">Close the **WF45GettingStartedTutorial** solution.</span></span>  
  
4.  <span data-ttu-id="028a5-125">Öffnen Sie Windows-Explorer, und navigieren Sie zu dem Ordner, in dem sich die Projektmappendatei und die Projektordner des Lernprogramms befinden.</span><span class="sxs-lookup"><span data-stu-id="028a5-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>  
  
5.  <span data-ttu-id="028a5-126">Erstellen Sie einen neuen Ordner namens **PreviousVersions** im gleichen Ordner wie **NumberGuessWorkflowHost** und **NumberGuessWorkflowActivities**.</span><span class="sxs-lookup"><span data-stu-id="028a5-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="028a5-127">In diesem Ordner werden die Assemblys gespeichert, die die verschiedenen Versionen der in den folgenden Lernprogrammschritten verwendeten Workflows enthalten.</span><span class="sxs-lookup"><span data-stu-id="028a5-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>  
  
6.  <span data-ttu-id="028a5-128">Navigieren Sie zu der **NumberGuessWorkflowActivities\bin\debug** Ordner (oder **"bin\Release"** je nach den projekteinstellungen).</span><span class="sxs-lookup"><span data-stu-id="028a5-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="028a5-129">Kopie **NumberGuessWorkflowActivities.dll** und fügen Sie ihn in die **PreviousVersions** Ordner.</span><span class="sxs-lookup"><span data-stu-id="028a5-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>  
  
7.  <span data-ttu-id="028a5-130">Benennen Sie **NumberGuessWorkflowActivities.dll** in der **PreviousVersions** Ordner **NumberGuessWorkflowActivities_v1.dll**.</span><span class="sxs-lookup"><span data-stu-id="028a5-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="028a5-131">Die Schritte in diesem Thema zeigen eine Möglichkeit zur Verwaltung der Assemblys, in denen mehrere Versionen der Workflows enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="028a5-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="028a5-132">Andere Methoden, wie starke Namen für die Assemblys und das Registrieren der Assemblys im globalen Assemblycache, können ebenfalls verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="028a5-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>  
  
8.  <span data-ttu-id="028a5-133">Erstellen Sie einen neuen Ordner namens **NumberGuessWorkflowActivities_du** im gleichen Ordner wie **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, und die neu hinzugefügt **PreviousVersions** Ordner, und kopieren Sie alle Dateien und Unterordner aus dem **NumberGuessWorkflowActivities** Ordner in das neue  **NumberGuessWorkflowActivities_du** Ordner.</span><span class="sxs-lookup"><span data-stu-id="028a5-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="028a5-134">Dieser Sicherungskopie des Projekts für die erste Version der Aktivitäten werden in [Vorgehensweise: Aktualisieren Sie die Definition einer Workflowinstanz ausgeführt](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="028a5-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
9. <span data-ttu-id="028a5-135">Öffnen Sie erneut die **WF45GettingStartedTutorial** -Lösung in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="028a5-135">Re-open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
###  <span data-ttu-id="028a5-136"><a name="BKMK_UpdateWorkflows"></a>Um Workflows zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="028a5-136"><a name="BKMK_UpdateWorkflows"></a> To update the workflows</span></span>  
 <span data-ttu-id="028a5-137">In diesem Abschnitt werden die Workflowdefinitionen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="028a5-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="028a5-138">Die beiden `WriteLine`-Aktivitäten, die Feedback zum Schätzwert des Benutzers geben, werden aktualisiert, und es wird eine neue `WriteLine`-Aktivität hinzugefügt, die zusätzliche Informationen zum Spiel bereitstellt, nachdem die Zahl geschätzt wurde.</span><span class="sxs-lookup"><span data-stu-id="028a5-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>  
  
####  <span data-ttu-id="028a5-139"><a name="BKMK_UpdateStateMachine"></a>So aktualisieren Sie die StateMachine-workflow</span><span class="sxs-lookup"><span data-stu-id="028a5-139"><a name="BKMK_UpdateStateMachine"></a> To update the StateMachine workflow</span></span>  
  
1.  <span data-ttu-id="028a5-140">In **Projektmappen-Explorer**unter der **NumberGuessWorkflowActivities** Projekt, doppelklicken Sie auf **StateMachineNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="028a5-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="028a5-141">Doppelklicken Sie auf die **Guess Incorrect** Übergang für den Zustandsautomaten.</span><span class="sxs-lookup"><span data-stu-id="028a5-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>  
  
3.  <span data-ttu-id="028a5-142">Aktualisieren Sie `Text` der äußersten linken `WriteLine` in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="028a5-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
4.  <span data-ttu-id="028a5-143">Aktualisieren Sie `Text` der äußersten rechten `WriteLine` in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="028a5-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
5.  <span data-ttu-id="028a5-144">Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers.</span><span class="sxs-lookup"><span data-stu-id="028a5-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
6.  <span data-ttu-id="028a5-145">Doppelklicken Sie auf die **Guess Correct** Übergang für den Zustandsautomaten.</span><span class="sxs-lookup"><span data-stu-id="028a5-145">Double-click the **Guess Correct** transition on the state machine.</span></span>  
  
7.  <span data-ttu-id="028a5-146">Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** Teil der **Toolbox** und legen sie auf der **Drop Action-Aktivität hier** Bezeichnung des der Übergang.</span><span class="sxs-lookup"><span data-stu-id="028a5-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>  
  
8.  <span data-ttu-id="028a5-147">Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.</span><span class="sxs-lookup"><span data-stu-id="028a5-147">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <span data-ttu-id="028a5-148"><a name="BKMK_UpdateFlowchart"></a>So aktualisieren Sie die Flussdiagramm-workflow</span><span class="sxs-lookup"><span data-stu-id="028a5-148"><a name="BKMK_UpdateFlowchart"></a> To update the Flowchart workflow</span></span>  
  
1.  <span data-ttu-id="028a5-149">In **Projektmappen-Explorer**unter der **NumberGuessWorkflowActivities** Projekt, doppelklicken Sie auf **FlowchartNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="028a5-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="028a5-150">Aktualisieren Sie `Text` der äußersten linken `WriteLine`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="028a5-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="028a5-151">Aktualisieren Sie `Text` der äußersten rechten `WriteLine`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="028a5-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="028a5-152">Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** Teil der **Toolbox** und legen sie auf dem Ablagepunkt der `True` -Aktion der obersten `FlowDecision` .</span><span class="sxs-lookup"><span data-stu-id="028a5-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="028a5-153">Die `WriteLine`-Aktivität wird dem Flussdiagramm hinzugefügt und mit der `True`-Aktion von `FlowDecision` verknüpft.</span><span class="sxs-lookup"><span data-stu-id="028a5-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>  
  
5.  <span data-ttu-id="028a5-154">Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.</span><span class="sxs-lookup"><span data-stu-id="028a5-154">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <span data-ttu-id="028a5-155"><a name="BKMK_UpdateSequential"></a>So aktualisieren Sie die sequenziellen workflow</span><span class="sxs-lookup"><span data-stu-id="028a5-155"><a name="BKMK_UpdateSequential"></a> To update the Sequential workflow</span></span>  
  
1.  <span data-ttu-id="028a5-156">In **Projektmappen-Explorer**unter der **NumberGuessWorkflowActivities** Projekt, doppelklicken Sie auf **SequentialNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="028a5-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="028a5-157">Aktualisieren Sie `Text` der äußersten linken `WriteLine` in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="028a5-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="028a5-158">Aktualisieren Sie `Text` der äußersten rechten `WriteLine`-Aktivität in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="028a5-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="028a5-159">Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** Teil der **Toolbox** und legen Sie sie nach der **DoWhile** Aktivität, damit der  **WriteLine** ist die letzte Aktivität im Stammverzeichnis `Sequence` Aktivität.</span><span class="sxs-lookup"><span data-stu-id="028a5-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>  
  
5.  <span data-ttu-id="028a5-160">Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.</span><span class="sxs-lookup"><span data-stu-id="028a5-160">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
###  <span data-ttu-id="028a5-161"><a name="BKMK_UpdateWorkflowVersionMap"></a>So aktualisieren Sie WorkflowVersionMap, um die vorherigen workflowversionen einzuschließen</span><span class="sxs-lookup"><span data-stu-id="028a5-161"><a name="BKMK_UpdateWorkflowVersionMap"></a> To update WorkflowVersionMap to include the previous workflow versions</span></span>  
  
1.  <span data-ttu-id="028a5-162">Doppelklicken Sie auf **WorkflowVersionMap.cs** (oder **WorkflowVersionMap.vb**) unter der **NumberGuessWorkflowHost** aus, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="028a5-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>  
  
2.  <span data-ttu-id="028a5-163">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="028a5-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Reflection  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Reflection;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="028a5-164">Fügen Sie drei neue Workflowidentitäten direkt unterhalb der drei vorhandenen Deklarationen für Workflowidentitäten hinzu.</span><span class="sxs-lookup"><span data-stu-id="028a5-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="028a5-165">Über diese neuen `v1`-Workflowidentitäten wird den Workflows, die vor den Updates gestartet wurden, die richtige Workflowdefinition bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="028a5-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>  
  
    ```vb  
    'Current version identities.  
    Public StateMachineNumberGuessIdentity As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity As WorkflowIdentity  
    Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
    'v1 Identities.  
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
    ```  
  
    ```csharp  
    // Current version identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity;  
    static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
    // v1 identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
    ```  
  
4.  <span data-ttu-id="028a5-166">Aktualisieren Sie im `WorkflowVersionMap`-Konstruktor die `Version`-Eigenschaft der drei aktuellen Workflowidentitäten auf `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="028a5-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>  
  
    ```vb  
    'Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
    ```  
  
    ```csharp  
    // Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
    ```  
  
     <span data-ttu-id="028a5-167">Durch den darin enthaltenen Code werden dem Wörterbuch die aktuellen Workflowversionen hinzugefügt. Der Code verwendet die aktuellen Versionen, auf die im Projekt verwiesen wird. Aus diesem Grund muss der Code, durch den die Workflowdefinitionen initialisiert werden, nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="028a5-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>  
  
5.  <span data-ttu-id="028a5-168">Fügen Sie den folgenden Code im Konstruktor unmittelbar nach dem Code hinzu, durch den dem Wörterbuch die aktuellen Versionen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="028a5-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>  
  
    ```vb  
    'Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
    ```  
  
    ```csharp  
    // Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
    ```  
  
     <span data-ttu-id="028a5-169">Diese Workflowidentitäten werden den ursprünglichen Versionen der entsprechenden Workflowdefinitionen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="028a5-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>  
  
6.  <span data-ttu-id="028a5-170">Als Nächstes laden Sie die Assembly, die die ursprüngliche Version der Workflowdefinitionen enthält, und erstellen die entsprechenden Workflowdefinitionen und fügen sie dem Wörterbuch hinzu.</span><span class="sxs-lookup"><span data-stu-id="028a5-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>  
  
    ```vb  
    'Add the previous version workflow identities to the dictionary along with  
    'the corresponding workflow definitions loaded from the v1 assembly.  
    'Assembly.LoadFile requires an absolute path so convert this relative path  
    'to an absolute path.  
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
    ```  
  
    ```csharp  
    // Add the previous version workflow identities to the dictionary along with  
    // the corresponding workflow definitions loaded from the v1 assembly.  
    // Assembly.LoadFile requires an absolute path so convert this relative path  
    // to an absolute path.  
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
    ```  
  
     <span data-ttu-id="028a5-171">Das folgende Beispiel enthält die vollständige Auflistung für die aktualisierte `WorkflowVersionMap`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="028a5-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        'v1 Identities.  
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
  
            'Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            'Add the previous version workflow identities to the dictionary along with  
            'the corresponding workflow definitions loaded from the v1 assembly.  
            'Assembly.LoadFile requires an absolute path so convert this relative path  
            'to an absolute path.  
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
        End Sub  
  
        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity  
            Return map(identity)  
        End Function  
  
        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String  
            Return identity.ToString()  
        End Function  
    End Module  
    ```  
  
    ```csharp  
    public static class WorkflowVersionMap  
    {  
        static Dictionary<WorkflowIdentity, Activity> map;  
  
        // Current version identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity;  
        static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
        // v1 identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
  
            // Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            // Add the previous version workflow identities to the dictionary along with  
            // the corresponding workflow definitions loaded from the v1 assembly.  
            // Assembly.LoadFile requires an absolute path so convert this relative path  
            // to an absolute path.  
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
        }  
  
        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)  
        {  
            return map[identity];  
        }  
  
        public static string GetIdentityDescription(WorkflowIdentity identity)  
        {  
            return identity.ToString();  
        }  
    }  
    ```  
  
###  <span data-ttu-id="028a5-172"><a name="BKMK_BuildAndRun"></a>So erstellen und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="028a5-172"><a name="BKMK_BuildAndRun"></a> To build and run the application</span></span>  
  
1.  <span data-ttu-id="028a5-173">Drücken Sie STRG+UMSCHALT+B, um die Anwendung zu erstellen, und dann STRG+F5, um sie zu starten.</span><span class="sxs-lookup"><span data-stu-id="028a5-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>  
  
2.  <span data-ttu-id="028a5-174">Starten Sie einen neuen Workflow, indem Sie auf **New Game**.</span><span class="sxs-lookup"><span data-stu-id="028a5-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="028a5-175">Die Version des Workflows wird unter dem Statusfenster angezeigt und gibt die aktualisierte Version der zugeordneten `WorkflowIdentity` an.</span><span class="sxs-lookup"><span data-stu-id="028a5-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="028a5-176">Notieren Sie die `InstanceId`, sodass Sie beim Abschluss des Workflows dessen Nachverfolgungsdatei anzeigen können. Geben Sie dann Schätzwerte ein, bis das Spiel abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="028a5-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="028a5-177">Beachten Sie, wie sich der Schätzwert des Benutzers gemäß den Updates der `WriteLine`-Aktivitäten in den Informationen im Statusfenster verändert.</span><span class="sxs-lookup"><span data-stu-id="028a5-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>  
  
 <span data-ttu-id="028a5-178">**Bitte geben Sie eine Zahl zwischen 1 und 10**</span><span class="sxs-lookup"><span data-stu-id="028a5-178">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="028a5-179">**5 ist zu hoch.** </span><span class="sxs-lookup"><span data-stu-id="028a5-179">**5 is too high.** </span></span>  
<span data-ttu-id="028a5-180">**Bitte geben Sie eine Zahl zwischen 1 und 10** </span><span class="sxs-lookup"><span data-stu-id="028a5-180">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="028a5-181">**3 ist zu hoch.** </span><span class="sxs-lookup"><span data-stu-id="028a5-181">**3 is too high.** </span></span>  
<span data-ttu-id="028a5-182">**Bitte geben Sie eine Zahl zwischen 1 und 10** </span><span class="sxs-lookup"><span data-stu-id="028a5-182">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="028a5-183">**1 ist zu niedrig.** </span><span class="sxs-lookup"><span data-stu-id="028a5-183">**1 is too low.** </span></span>  
<span data-ttu-id="028a5-184">**Bitte geben Sie eine Zahl zwischen 1 und 10** </span><span class="sxs-lookup"><span data-stu-id="028a5-184">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="028a5-185">**Herzlichen Glückwunsch, Sie die Zahl 4 wiederum erraten.**</span><span class="sxs-lookup"><span data-stu-id="028a5-185">**Congratulations, you guessed the number in 4 turns.**</span></span>    
    > [!NOTE]
    >  <span data-ttu-id="028a5-186">Der aktualisierte Text aus den `WriteLine`-Aktivitäten wird angezeigt, die Ausgabe der endgültigen, in diesem Thema hinzugefügten `WriteLine`-Aktivität jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="028a5-186">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="028a5-187">Das liegt daran, dass das Statusfenster vom `PersistableIdle`-Handler aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="028a5-187">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="028a5-188">Da der Workflow abgeschlossen wird, statt nach der letzten Aktivität in den Leerlauf zu wechseln, wird der `PersistableIdle`-Handler nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="028a5-188">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="028a5-189">Im Statusfenster wird jedoch eine ähnliche Meldung vom `Completed`-Handler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="028a5-189">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="028a5-190">Bei Bedarf kann Code dem `Completed`-Handler hinzugefügt werden, um den Text aus `StringWriter` zu extrahieren und ihn im Statusfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="028a5-190">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>  
  
3.  <span data-ttu-id="028a5-191">Öffnen Sie Windows Explorer, und navigieren Sie zu der **NumberGuessWorkflowHost\bin\debug** Ordner (oder **"bin\Release"** je nach den projekteinstellungen), und öffnen Sie die Nachverfolgungsdatei, die mit dem Editor, der entspricht die dem abgeschlossenen Workflow.</span><span class="sxs-lookup"><span data-stu-id="028a5-191">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="028a5-192">Wenn Sie nicht notieren die `InstanceId`, bestimmen Sie die richtige Nachverfolgungsdatei mithilfe der **Änderungsdatum** Informationen im Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="028a5-192">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>  
  
 <span data-ttu-id="028a5-193">**Bitte geben Sie eine Zahl zwischen 1 und 10**</span><span class="sxs-lookup"><span data-stu-id="028a5-193">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="028a5-194">**5 ist zu hoch.** </span><span class="sxs-lookup"><span data-stu-id="028a5-194">**5 is too high.** </span></span>  
<span data-ttu-id="028a5-195">**Bitte geben Sie eine Zahl zwischen 1 und 10** </span><span class="sxs-lookup"><span data-stu-id="028a5-195">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="028a5-196">**3 ist zu hoch.** </span><span class="sxs-lookup"><span data-stu-id="028a5-196">**3 is too high.** </span></span>  
<span data-ttu-id="028a5-197">**Bitte geben Sie eine Zahl zwischen 1 und 10** </span><span class="sxs-lookup"><span data-stu-id="028a5-197">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="028a5-198">**1 ist zu niedrig.** </span><span class="sxs-lookup"><span data-stu-id="028a5-198">**1 is too low.** </span></span>  
<span data-ttu-id="028a5-199">**Bitte geben Sie eine Zahl zwischen 1 und 10** </span><span class="sxs-lookup"><span data-stu-id="028a5-199">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="028a5-200">**2 ist richtig. Sie können Sie erraten, 4 wiederum.**</span><span class="sxs-lookup"><span data-stu-id="028a5-200">**2 is correct. You guessed it in 4 turns.**</span></span>      <span data-ttu-id="028a5-201">Die aktualisierte `WriteLine`-Ausgabe ist in der Nachverfolgungsdatei enthalten, einschließlich der Ausgabe der `WriteLine`-Aktivität, die diesem Thema hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="028a5-201">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>  
  
4.  <span data-ttu-id="028a5-202">Wechseln Sie zurück zur Anwendung zum Schätzen der Zahl, und wählen Sie einen der Workflows aus, die vor den Updates gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="028a5-202">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="028a5-203">Sie können die Version des aktuell ausgewählten Workflows anhand der Versionsinformationen identifizieren, die unter dem Statusfenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="028a5-203">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="028a5-204">Geben Sie mehrere Schätzwerte ein. Sie werden feststellen, dass die Statusupdates mit der Ausgabe der `WriteLine`-Aktivität aus der vorherigen Version übereinstimmen und keine Schätzwerte des Benutzers enthalten.</span><span class="sxs-lookup"><span data-stu-id="028a5-204">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="028a5-205">Das liegt daran, dass diese Workflows die vorherige Workflowdefinition verwenden, die nicht über die `WriteLine`-Updates verfügt.</span><span class="sxs-lookup"><span data-stu-id="028a5-205">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>  
  
     <span data-ttu-id="028a5-206">Im nächsten Schritt [Vorgehensweise: Aktualisieren Sie die Definition einer Workflowinstanz ausgeführt](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), die Ausführung `v1` Workflowinstanzen werden aktualisiert, damit sie die neue Funktionalität wie enthalten die `v2` Instanzen.</span><span class="sxs-lookup"><span data-stu-id="028a5-206">In the next step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
