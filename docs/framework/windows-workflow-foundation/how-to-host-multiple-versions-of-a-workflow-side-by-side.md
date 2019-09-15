---
title: 'Vorgehensweise: Paralleles Hosten mehrerer Workflowversionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: 820ed324c8095e2f9f2823513a37965099f42c48
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989651"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="2550f-102">Vorgehensweise: Paralleles Hosten mehrerer Workflowversionen</span><span class="sxs-lookup"><span data-stu-id="2550f-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>

<span data-ttu-id="2550f-103">`WorkflowIdentity` bietet Entwicklern von Workflowanwendungen die Möglichkeit, einer Worfklowdefinition einen Namen und eine Version zuzuordnen und diese Informationen mit einer persistenten Workflowinstanz zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="2550f-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="2550f-104">Entwickler von Workflowanwendungen können diese Identitätsinformationen verwenden, um Szenarien wie die parallele Ausführung mehrerer Versionen einer Workflowdefinition umzusetzen. Darüber hinaus bilden sie die Grundlage für andere Funktionen wie dynamische Updates.</span><span class="sxs-lookup"><span data-stu-id="2550f-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="2550f-105">In diesem Schritt des Lernprogramms wird veranschaulicht, wie mit `WorkflowIdentity` mehrere Versionen eines Workflows gleichzeitig gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="2550f-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>

> [!NOTE]
> <span data-ttu-id="2550f-106">Informationen zum Herunterladen einer abgeschlossenen Version oder zum Anzeigen einer exemplarischen Vorgehensweise für das Tutorial finden Sie unter [Windows Workflow Foundation (WF45)-Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)für die ersten Schritte.</span><span class="sxs-lookup"><span data-stu-id="2550f-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="2550f-107">In diesem Thema</span><span class="sxs-lookup"><span data-stu-id="2550f-107">In this topic</span></span>

<span data-ttu-id="2550f-108">In diesem Schritt des Lernprogramms werden die `WriteLine`-Aktivitäten im Workflow geändert, um zusätzliche Informationen bereitzustellen. Außerdem wird eine neue `WriteLine`-Aktivität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2550f-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="2550f-109">Eine Kopie der ursprünglichen Workflowassembly wird gespeichert, und die Hostanwendung wird aktualisiert, sodass der ursprüngliche und der aktualisierte Workflow gleichzeitig ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2550f-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>

- [<span data-ttu-id="2550f-110">So erstellen Sie eine Kopie des Projekts "numguess workflowactivities"</span><span class="sxs-lookup"><span data-stu-id="2550f-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)

- [<span data-ttu-id="2550f-111">So aktualisieren Sie die Workflows</span><span class="sxs-lookup"><span data-stu-id="2550f-111">To update the workflows</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)

  - [<span data-ttu-id="2550f-112">So aktualisieren Sie den StateMachine-Workflow</span><span class="sxs-lookup"><span data-stu-id="2550f-112">To update the StateMachine workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)

  - [<span data-ttu-id="2550f-113">So aktualisieren Sie den Flussdiagramm Workflow</span><span class="sxs-lookup"><span data-stu-id="2550f-113">To update the Flowchart workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)

  - [<span data-ttu-id="2550f-114">So aktualisieren Sie den sequenziellen Workflow</span><span class="sxs-lookup"><span data-stu-id="2550f-114">To update the Sequential workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)

- [<span data-ttu-id="2550f-115">So aktualisieren Sie workflowversionmap, um die vorherigen Workflow Versionen einzuschließen</span><span class="sxs-lookup"><span data-stu-id="2550f-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)

- [<span data-ttu-id="2550f-116">So erstellen Sie die Anwendung und führen Sie aus</span><span class="sxs-lookup"><span data-stu-id="2550f-116">To build and run the application</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)

> [!NOTE]
> <span data-ttu-id="2550f-117">Bevor Sie die Schritte in diesem Thema ausführen, führen Sie die Anwendung aus, starten mehrere Workflows jedes Typs und geben einen oder zwei Schätzwerte für jeden Typ an.</span><span class="sxs-lookup"><span data-stu-id="2550f-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="2550f-118">Diese beibehaltenen Workflows werden in diesem Schritt und im folgenden Schritt [verwendet: Aktualisieren Sie die Definition einer Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md), die ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2550f-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2550f-119">Jeder Schritt im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Schritten ab.</span><span class="sxs-lookup"><span data-stu-id="2550f-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="2550f-120">Wenn Sie die vorherigen Schritte nicht ausgeführt haben, können Sie eine abgeschlossene Version des Tutorials aus [Windows Workflow Foundation (WF45)-Tutorial "Getting Started](https://go.microsoft.com/fwlink/?LinkID=248976)" herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2550f-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

### <a name="BKMK_BackupCopy"></a><span data-ttu-id="2550f-121">So erstellen Sie eine Kopie des Projekts "numguess workflowactivities"</span><span class="sxs-lookup"><span data-stu-id="2550f-121">To make a copy of the NumberGuessWorkflowActivities project</span></span>

1. <span data-ttu-id="2550f-122">Öffnen Sie die Projekt Mappe **WF45GettingStartedTutorial** in Visual Studio 2012, wenn Sie nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="2550f-122">Open the **WF45GettingStartedTutorial** solution in Visual Studio 2012 if it is not open.</span></span>

2. <span data-ttu-id="2550f-123">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2550f-123">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="2550f-124">Schließen Sie die **WF45GettingStartedTutorial** -Lösung.</span><span class="sxs-lookup"><span data-stu-id="2550f-124">Close the **WF45GettingStartedTutorial** solution.</span></span>

4. <span data-ttu-id="2550f-125">Öffnen Sie Windows-Explorer, und navigieren Sie zu dem Ordner, in dem sich die Projektmappendatei und die Projektordner des Lernprogramms befinden.</span><span class="sxs-lookup"><span data-stu-id="2550f-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>

5. <span data-ttu-id="2550f-126">Erstellen Sie einen neuen Ordner mit dem Namen **previousversions** im gleichen Ordner wie " **numguess Workflowhost** " und " **numguess workflowactivities**".</span><span class="sxs-lookup"><span data-stu-id="2550f-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="2550f-127">In diesem Ordner werden die Assemblys gespeichert, die die verschiedenen Versionen der in den folgenden Lernprogrammschritten verwendeten Workflows enthalten.</span><span class="sxs-lookup"><span data-stu-id="2550f-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>

6. <span data-ttu-id="2550f-128">Navigieren Sie zum Ordner " **numguess workflowactivities\bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen).</span><span class="sxs-lookup"><span data-stu-id="2550f-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="2550f-129">Kopieren Sie die Datei " **numguess Workflow Activities. dll** ", und fügen Sie Sie in den Ordner **previousversions** ein.</span><span class="sxs-lookup"><span data-stu-id="2550f-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>

7. <span data-ttu-id="2550f-130">Benennen Sie die Datei " **numguess Workflow Activities. dll** " im Ordner " **previousversions** " in **NumberGuessWorkflowActivities_v1. dll**um.</span><span class="sxs-lookup"><span data-stu-id="2550f-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2550f-131">Die Schritte in diesem Thema zeigen eine Möglichkeit zur Verwaltung der Assemblys, in denen mehrere Versionen der Workflows enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2550f-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="2550f-132">Andere Methoden, wie starke Namen für die Assemblys und das Registrieren der Assemblys im globalen Assemblycache, können ebenfalls verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2550f-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>

8. <span data-ttu-id="2550f-133">Erstellen Sie einen neuen Ordner mit dem Namen **NumberGuessWorkflowActivities_du** im selben Ordner wie " **numguess Workflowhost**", " **numguess workflowactivities**" und dem neu hinzugefügten Ordner " **previousversions** ", und kopieren Sie alle Dateien. Unterordner aus dem Ordner " **numguess workflowactivities** " in den neuen Ordner " **NumberGuessWorkflowActivities_du** ".</span><span class="sxs-lookup"><span data-stu-id="2550f-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="2550f-134">Diese Sicherungskopie des Projekts für die anfängliche Version der Aktivitäten wird in [Gewusst wie: Aktualisieren Sie die Definition einer Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md), die ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2550f-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

9. <span data-ttu-id="2550f-135">Öffnen Sie die **WF45GettingStartedTutorial** -Projekt Mappe in Visual Studio 2012 erneut.</span><span class="sxs-lookup"><span data-stu-id="2550f-135">Re-open the **WF45GettingStartedTutorial** solution in Visual Studio 2012.</span></span>

### <a name="BKMK_UpdateWorkflows"></a><span data-ttu-id="2550f-136">So aktualisieren Sie die Workflows</span><span class="sxs-lookup"><span data-stu-id="2550f-136">To update the workflows</span></span>

<span data-ttu-id="2550f-137">In diesem Abschnitt werden die Workflowdefinitionen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2550f-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="2550f-138">Die beiden `WriteLine`-Aktivitäten, die Feedback zum Schätzwert des Benutzers geben, werden aktualisiert, und es wird eine neue `WriteLine`-Aktivität hinzugefügt, die zusätzliche Informationen zum Spiel bereitstellt, nachdem die Zahl geschätzt wurde.</span><span class="sxs-lookup"><span data-stu-id="2550f-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>

#### <a name="BKMK_UpdateStateMachine"></a><span data-ttu-id="2550f-139">So aktualisieren Sie den StateMachine-Workflow</span><span class="sxs-lookup"><span data-stu-id="2550f-139">To update the StateMachine workflow</span></span>

1. <span data-ttu-id="2550f-140">Doppelklicken Sie in **Projektmappen-Explorer**unter dem Projekt " **numguess Workflow Activities** " auf **statemachinenumberguess Workflow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="2550f-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="2550f-141">Doppelklicken Sie auf den **fehlerhaften** Übergang auf dem Zustands Automaten.</span><span class="sxs-lookup"><span data-stu-id="2550f-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>

3. <span data-ttu-id="2550f-142">Aktualisieren Sie `Text` der äußersten linken `WriteLine` in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2550f-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4. <span data-ttu-id="2550f-143">Aktualisieren Sie `Text` der äußersten rechten `WriteLine` in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2550f-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5. <span data-ttu-id="2550f-144">Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.</span><span class="sxs-lookup"><span data-stu-id="2550f-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>

6. <span data-ttu-id="2550f-145">Doppelklicken Sie auf den Übergang **Guess correct** auf dem Zustands Automaten.</span><span class="sxs-lookup"><span data-stu-id="2550f-145">Double-click the **Guess Correct** transition on the state machine.</span></span>

7. <span data-ttu-id="2550f-146">Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** des Übergangs ab.</span><span class="sxs-lookup"><span data-stu-id="2550f-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>

8. <span data-ttu-id="2550f-147">Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.</span><span class="sxs-lookup"><span data-stu-id="2550f-147">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateFlowchart"></a><span data-ttu-id="2550f-148">So aktualisieren Sie den Flussdiagramm Workflow</span><span class="sxs-lookup"><span data-stu-id="2550f-148">To update the Flowchart workflow</span></span>

1. <span data-ttu-id="2550f-149">Doppelklicken Sie in **Projektmappen-Explorer**unter dem Projekt " **numguess Workflow Activities** " auf **flowchartnumguess Workflow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="2550f-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="2550f-150">Aktualisieren Sie `Text` der äußersten linken `WriteLine`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2550f-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="2550f-151">Aktualisieren Sie `Text` der äußersten rechten `WriteLine`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2550f-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="2550f-152">Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf `True` dem Ablage Punkt der obersten `FlowDecision`Aktion ab.</span><span class="sxs-lookup"><span data-stu-id="2550f-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="2550f-153">Die `WriteLine`-Aktivität wird dem Flussdiagramm hinzugefügt und mit der `True`-Aktion von `FlowDecision` verknüpft.</span><span class="sxs-lookup"><span data-stu-id="2550f-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>

5. <span data-ttu-id="2550f-154">Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.</span><span class="sxs-lookup"><span data-stu-id="2550f-154">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateSequential"></a><span data-ttu-id="2550f-155">So aktualisieren Sie den sequenziellen Workflow</span><span class="sxs-lookup"><span data-stu-id="2550f-155">To update the Sequential workflow</span></span>

1. <span data-ttu-id="2550f-156">Doppelklicken Sie in **Projektmappen-Explorer**unter dem Projekt " **numguess Workflow Activities** " auf **sequentialnumguess Workflow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="2550f-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="2550f-157">Aktualisieren Sie `Text` der äußersten linken `WriteLine` in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2550f-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="2550f-158">Aktualisieren Sie `Text` der äußersten rechten `WriteLine`-Aktivität in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2550f-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="2550f-159">Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie hinter der **DoWhile** -Aktivität ab, sodass die **Schreib** Weise die letzte `Sequence` Aktivität in der Stamm Aktivität ist.</span><span class="sxs-lookup"><span data-stu-id="2550f-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>

5. <span data-ttu-id="2550f-160">Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.</span><span class="sxs-lookup"><span data-stu-id="2550f-160">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

### <a name="BKMK_UpdateWorkflowVersionMap"></a><span data-ttu-id="2550f-161">So aktualisieren Sie workflowversionmap, um die vorherigen Workflow Versionen einzuschließen</span><span class="sxs-lookup"><span data-stu-id="2550f-161">To update WorkflowVersionMap to include the previous workflow versions</span></span>

1. <span data-ttu-id="2550f-162">Doppelklicken Sie unter dem Projekt " **numguess Workflowhost** " auf **WorkflowVersionMap.cs** (oder **workflowversionmap. vb**), um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2550f-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

2. <span data-ttu-id="2550f-163">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="2550f-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3. <span data-ttu-id="2550f-164">Fügen Sie drei neue Workflowidentitäten direkt unterhalb der drei vorhandenen Deklarationen für Workflowidentitäten hinzu.</span><span class="sxs-lookup"><span data-stu-id="2550f-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="2550f-165">Über diese neuen `v1`-Workflowidentitäten wird den Workflows, die vor den Updates gestartet wurden, die richtige Workflowdefinition bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2550f-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>

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

4. <span data-ttu-id="2550f-166">Aktualisieren Sie im `WorkflowVersionMap`-Konstruktor die `Version`-Eigenschaft der drei aktuellen Workflowidentitäten auf `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="2550f-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>

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

    <span data-ttu-id="2550f-167">Durch den darin enthaltenen Code werden dem Wörterbuch die aktuellen Workflowversionen hinzugefügt. Der Code verwendet die aktuellen Versionen, auf die im Projekt verwiesen wird. Aus diesem Grund muss der Code, durch den die Workflowdefinitionen initialisiert werden, nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2550f-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>

5. <span data-ttu-id="2550f-168">Fügen Sie den folgenden Code im Konstruktor unmittelbar nach dem Code hinzu, durch den dem Wörterbuch die aktuellen Versionen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2550f-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>

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

    <span data-ttu-id="2550f-169">Diese Workflowidentitäten werden den ursprünglichen Versionen der entsprechenden Workflowdefinitionen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2550f-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>

6. <span data-ttu-id="2550f-170">Als Nächstes laden Sie die Assembly, die die ursprüngliche Version der Workflowdefinitionen enthält, und erstellen die entsprechenden Workflowdefinitionen und fügen sie dem Wörterbuch hinzu.</span><span class="sxs-lookup"><span data-stu-id="2550f-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>

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

    <span data-ttu-id="2550f-171">Das folgende Beispiel enthält die vollständige Auflistung für die aktualisierte `WorkflowVersionMap`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2550f-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>

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

### <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="2550f-172">So erstellen und führen Sie die Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="2550f-172">To build and run the application</span></span>

1. <span data-ttu-id="2550f-173">Drücken Sie STRG+UMSCHALT+B, um die Anwendung zu erstellen, und dann STRG+F5, um sie zu starten.</span><span class="sxs-lookup"><span data-stu-id="2550f-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>

2. <span data-ttu-id="2550f-174">Starten Sie einen neuen Workflow, indem Sie auf **Neues Spiel**klicken.</span><span class="sxs-lookup"><span data-stu-id="2550f-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="2550f-175">Die Version des Workflows wird unter dem Statusfenster angezeigt und gibt die aktualisierte Version der zugeordneten `WorkflowIdentity` an.</span><span class="sxs-lookup"><span data-stu-id="2550f-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="2550f-176">Notieren Sie die `InstanceId`, sodass Sie beim Abschluss des Workflows dessen Nachverfolgungsdatei anzeigen können. Geben Sie dann Schätzwerte ein, bis das Spiel abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2550f-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="2550f-177">Beachten Sie, wie sich der Schätzwert des Benutzers gemäß den Updates der `WriteLine`-Aktivitäten in den Informationen im Statusfenster verändert.</span><span class="sxs-lookup"><span data-stu-id="2550f-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>

    ```console
    Please enter a number between 1 and 10
    5 is too high.
    Please enter a number between 1 and 10
    3 is too high.
    Please enter a number between 1 and 10
    1 is too low.
    Please enter a number between 1 and 10
    Congratulations, you guessed the number in 4 turns.
    ```

    > [!NOTE]
    > <span data-ttu-id="2550f-178">Der aktualisierte Text aus den `WriteLine`-Aktivitäten wird angezeigt, die Ausgabe der endgültigen, in diesem Thema hinzugefügten `WriteLine`-Aktivität jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="2550f-178">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="2550f-179">Das liegt daran, dass das Statusfenster vom `PersistableIdle`-Handler aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2550f-179">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="2550f-180">Da der Workflow abgeschlossen wird, statt nach der letzten Aktivität in den Leerlauf zu wechseln, wird der `PersistableIdle`-Handler nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2550f-180">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="2550f-181">Im Statusfenster wird jedoch eine ähnliche Meldung vom `Completed`-Handler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2550f-181">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="2550f-182">Bei Bedarf kann Code dem `Completed`-Handler hinzugefügt werden, um den Text aus `StringWriter` zu extrahieren und ihn im Statusfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2550f-182">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>

3. <span data-ttu-id="2550f-183">Öffnen Sie Windows-Explorer, und navigieren Sie zum Ordner " **infogustinworkflowhost\bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen), und öffnen Sie die nach Verfolgungs Datei mit dem Editor, der dem abgeschlossenen Workflow entspricht.</span><span class="sxs-lookup"><span data-stu-id="2550f-183">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="2550f-184">Wenn Sie den `InstanceId`nicht notiert haben, können Sie die richtige nach Verfolgungs Datei mithilfe der **geänderten Datums** Informationen in Windows-Explorer identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2550f-184">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>

    ```console
    Please enter a number between 1 and 10
    5 is too high.
    Please enter a number between 1 and 10
    3 is too high.
    Please enter a number between 1 and 10
    1 is too low.
    Please enter a number between 1 and 10
    2 is correct. You guessed it in 4 turns.
    ```

    <span data-ttu-id="2550f-185">Die aktualisierte `WriteLine`-Ausgabe ist in der Nachverfolgungsdatei enthalten, einschließlich der Ausgabe der `WriteLine`-Aktivität, die diesem Thema hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="2550f-185">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>

4. <span data-ttu-id="2550f-186">Wechseln Sie zurück zur Anwendung zum Schätzen der Zahl, und wählen Sie einen der Workflows aus, die vor den Updates gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="2550f-186">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="2550f-187">Sie können die Version des aktuell ausgewählten Workflows anhand der Versionsinformationen identifizieren, die unter dem Statusfenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2550f-187">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="2550f-188">Geben Sie mehrere Schätzwerte ein. Sie werden feststellen, dass die Statusupdates mit der Ausgabe der `WriteLine`-Aktivität aus der vorherigen Version übereinstimmen und keine Schätzwerte des Benutzers enthalten.</span><span class="sxs-lookup"><span data-stu-id="2550f-188">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="2550f-189">Das liegt daran, dass diese Workflows die vorherige Workflowdefinition verwenden, die nicht über die `WriteLine`-Updates verfügt.</span><span class="sxs-lookup"><span data-stu-id="2550f-189">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>

    <span data-ttu-id="2550f-190">Im nächsten Schritt wird [Folgendes erläutert: Aktualisieren Sie die Definition einer Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md), die ausgeführt wird, und die laufenden `v1` Workflow Instanzen werden so aktualisiert, dass Sie `v2` die neuen Funktionen als Instanzen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2550f-190">In the next step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
