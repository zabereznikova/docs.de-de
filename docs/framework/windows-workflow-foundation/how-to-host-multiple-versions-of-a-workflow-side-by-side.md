---
title: 'Vorgehensweise: Paralleles Hosten mehrerer Workflowversionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: e47440110215d8e60744c26c6351211a2ac08f3a
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98191156"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="6d20b-102">Vorgehensweise: Paralleles Hosten mehrerer Workflowversionen</span><span class="sxs-lookup"><span data-stu-id="6d20b-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>

<span data-ttu-id="6d20b-103">`WorkflowIdentity` bietet Entwicklern von Workflowanwendungen die Möglichkeit, einer Worfklowdefinition einen Namen und eine Version zuzuordnen und diese Informationen mit einer persistenten Workflowinstanz zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="6d20b-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="6d20b-104">Entwickler von Workflowanwendungen können diese Identitätsinformationen verwenden, um Szenarien wie die parallele Ausführung mehrerer Versionen einer Workflowdefinition umzusetzen. Darüber hinaus bilden sie die Grundlage für andere Funktionen wie dynamische Updates.</span><span class="sxs-lookup"><span data-stu-id="6d20b-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="6d20b-105">In diesem Schritt des Lernprogramms wird veranschaulicht, wie mit `WorkflowIdentity` mehrere Versionen eines Workflows gleichzeitig gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="6d20b-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="6d20b-106">In diesem Thema</span><span class="sxs-lookup"><span data-stu-id="6d20b-106">In this topic</span></span>

<span data-ttu-id="6d20b-107">In diesem Schritt des Lernprogramms werden die `WriteLine`-Aktivitäten im Workflow geändert, um zusätzliche Informationen bereitzustellen. Außerdem wird eine neue `WriteLine`-Aktivität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6d20b-107">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="6d20b-108">Eine Kopie der ursprünglichen Workflowassembly wird gespeichert, und die Hostanwendung wird aktualisiert, sodass der ursprüngliche und der aktualisierte Workflow gleichzeitig ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="6d20b-108">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>

- [<span data-ttu-id="6d20b-109">So erstellen Sie eine Kopie des NumberGuessWorkflowActivities-Projekts</span><span class="sxs-lookup"><span data-stu-id="6d20b-109">To make a copy of the NumberGuessWorkflowActivities project</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)

- [<span data-ttu-id="6d20b-110">So aktualisieren Sie die Workflows</span><span class="sxs-lookup"><span data-stu-id="6d20b-110">To update the workflows</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)

  - [<span data-ttu-id="6d20b-111">So aktualisieren Sie den StateMachine-Workflow</span><span class="sxs-lookup"><span data-stu-id="6d20b-111">To update the StateMachine workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)

  - [<span data-ttu-id="6d20b-112">So aktualisieren Sie den Flowchart-Workflow</span><span class="sxs-lookup"><span data-stu-id="6d20b-112">To update the Flowchart workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)

  - [<span data-ttu-id="6d20b-113">So aktualisieren Sie den Sequential-Workflow</span><span class="sxs-lookup"><span data-stu-id="6d20b-113">To update the Sequential workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)

- [<span data-ttu-id="6d20b-114">So aktualisieren Sie WorkflowVersionMap, um die vorherigen Workflowversionen einzuschließen</span><span class="sxs-lookup"><span data-stu-id="6d20b-114">To update WorkflowVersionMap to include the previous workflow versions</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)

- [<span data-ttu-id="6d20b-115">So erstellen Sie die Anwendung und führen sie aus</span><span class="sxs-lookup"><span data-stu-id="6d20b-115">To build and run the application</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)

> [!NOTE]
> <span data-ttu-id="6d20b-116">Bevor Sie die Schritte in diesem Thema ausführen, führen Sie die Anwendung aus, starten mehrere Workflows jedes Typs und geben einen oder zwei Schätzwerte für jeden Typ an.</span><span class="sxs-lookup"><span data-stu-id="6d20b-116">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="6d20b-117">Diese beibehaltenen Workflows werden in diesem Schritt und im folgenden Schritt erläutert [: Gewusst wie: Aktualisieren der Definition einer Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md), die ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d20b-117">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

### <a name="to-make-a-copy-of-the-numberguessworkflowactivities-project"></a><a name="BKMK_BackupCopy"></a> <span data-ttu-id="6d20b-118">So erstellen Sie eine Kopie des Projekts "numguess workflowactivities"</span><span class="sxs-lookup"><span data-stu-id="6d20b-118">To make a copy of the NumberGuessWorkflowActivities project</span></span>

1. <span data-ttu-id="6d20b-119">Öffnen Sie die Projekt Mappe **WF45GettingStartedTutorial** in Visual Studio 2012, wenn Sie nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="6d20b-119">Open the **WF45GettingStartedTutorial** solution in Visual Studio 2012 if it is not open.</span></span>

2. <span data-ttu-id="6d20b-120">Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d20b-120">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="6d20b-121">Schließen Sie die **WF45GettingStartedTutorial** -Lösung.</span><span class="sxs-lookup"><span data-stu-id="6d20b-121">Close the **WF45GettingStartedTutorial** solution.</span></span>

4. <span data-ttu-id="6d20b-122">Öffnen Sie Windows-Explorer, und navigieren Sie zu dem Ordner, in dem sich die Projektmappendatei und die Projektordner des Lernprogramms befinden.</span><span class="sxs-lookup"><span data-stu-id="6d20b-122">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>

5. <span data-ttu-id="6d20b-123">Erstellen Sie einen neuen Ordner mit dem Namen **previousversions** im gleichen Ordner wie " **numguess Workflowhost** " und " **numguess workflowactivities**".</span><span class="sxs-lookup"><span data-stu-id="6d20b-123">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="6d20b-124">In diesem Ordner werden die Assemblys gespeichert, die die verschiedenen Versionen der in den folgenden Lernprogrammschritten verwendeten Workflows enthalten.</span><span class="sxs-lookup"><span data-stu-id="6d20b-124">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>

6. <span data-ttu-id="6d20b-125">Navigieren Sie zum Ordner " **numguess workflowactivities\bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen).</span><span class="sxs-lookup"><span data-stu-id="6d20b-125">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="6d20b-126">Kopieren Sie **NumberGuessWorkflowActivities.dll** , und fügen Sie ihn in den Ordner **previousversions** ein.</span><span class="sxs-lookup"><span data-stu-id="6d20b-126">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>

7. <span data-ttu-id="6d20b-127">Benennen Sie **NumberGuessWorkflowActivities.dll** im Ordner **previousversions** in **NumberGuessWorkflowActivities_v1.dll** um.</span><span class="sxs-lookup"><span data-stu-id="6d20b-127">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6d20b-128">Die Schritte in diesem Thema zeigen eine Möglichkeit zur Verwaltung der Assemblys, in denen mehrere Versionen der Workflows enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="6d20b-128">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="6d20b-129">Andere Methoden, wie starke Namen für die Assemblys und das Registrieren der Assemblys im globalen Assemblycache, können ebenfalls verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d20b-129">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>

8. <span data-ttu-id="6d20b-130">Erstellen Sie einen neuen Ordner mit dem Namen **NumberGuessWorkflowActivities_du** im selben Ordner wie " **numguess Workflowhost**", " **numguess workflowactivities**" und dem neu hinzugefügten Ordner " **previousversions** ", und kopieren Sie alle Dateien und Unterordner aus dem Ordner " **zahleresworkflowactivities** " in den neuen Ordner " **NumberGuessWorkflowActivities_du** ".</span><span class="sxs-lookup"><span data-stu-id="6d20b-130">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="6d20b-131">Diese Sicherungskopie des Projekts für die anfängliche Version der Aktivitäten wird in Gewusst [wie: Aktualisieren der Definition einer laufenden Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d20b-131">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

9. <span data-ttu-id="6d20b-132">Öffnen Sie die **WF45GettingStartedTutorial** -Projekt Mappe in Visual Studio 2012 erneut.</span><span class="sxs-lookup"><span data-stu-id="6d20b-132">Re-open the **WF45GettingStartedTutorial** solution in Visual Studio 2012.</span></span>

### <a name="to-update-the-workflows"></a><a name="BKMK_UpdateWorkflows"></a> <span data-ttu-id="6d20b-133">So aktualisieren Sie die Workflows</span><span class="sxs-lookup"><span data-stu-id="6d20b-133">To update the workflows</span></span>

<span data-ttu-id="6d20b-134">In diesem Abschnitt werden die Workflowdefinitionen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6d20b-134">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="6d20b-135">Die beiden `WriteLine`-Aktivitäten, die Feedback zum Schätzwert des Benutzers geben, werden aktualisiert, und es wird eine neue `WriteLine`-Aktivität hinzugefügt, die zusätzliche Informationen zum Spiel bereitstellt, nachdem die Zahl geschätzt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d20b-135">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>

#### <a name="to-update-the-statemachine-workflow"></a><a name="BKMK_UpdateStateMachine"></a> <span data-ttu-id="6d20b-136">So aktualisieren Sie den StateMachine-Workflow</span><span class="sxs-lookup"><span data-stu-id="6d20b-136">To update the StateMachine workflow</span></span>

1. <span data-ttu-id="6d20b-137">Doppelklicken Sie in **Projektmappen-Explorer** unter dem Projekt " **numguess Workflow Activities** " auf **statemachinenumberguess Workflow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="6d20b-137">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="6d20b-138">Doppelklicken Sie auf den **fehlerhaften** Übergang auf dem Zustands Automaten.</span><span class="sxs-lookup"><span data-stu-id="6d20b-138">Double-click the **Guess Incorrect** transition on the state machine.</span></span>

3. <span data-ttu-id="6d20b-139">Aktualisieren Sie `Text` der äußersten linken `WriteLine` in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6d20b-139">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4. <span data-ttu-id="6d20b-140">Aktualisieren Sie `Text` der äußersten rechten `WriteLine` in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6d20b-140">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5. <span data-ttu-id="6d20b-141">Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.</span><span class="sxs-lookup"><span data-stu-id="6d20b-141">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>

6. <span data-ttu-id="6d20b-142">Doppelklicken Sie auf den Übergang **Guess correct** auf dem Zustands Automaten.</span><span class="sxs-lookup"><span data-stu-id="6d20b-142">Double-click the **Guess Correct** transition on the state machine.</span></span>

7. <span data-ttu-id="6d20b-143">Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** des Übergangs ab.</span><span class="sxs-lookup"><span data-stu-id="6d20b-143">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>

8. <span data-ttu-id="6d20b-144">Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.</span><span class="sxs-lookup"><span data-stu-id="6d20b-144">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="to-update-the-flowchart-workflow"></a><a name="BKMK_UpdateFlowchart"></a> <span data-ttu-id="6d20b-145">So aktualisieren Sie den Flussdiagramm Workflow</span><span class="sxs-lookup"><span data-stu-id="6d20b-145">To update the Flowchart workflow</span></span>

1. <span data-ttu-id="6d20b-146">Doppelklicken Sie in **Projektmappen-Explorer** unter dem Projekt " **numguess Workflow Activities** " auf **flowchartnumguess Workflow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="6d20b-146">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="6d20b-147">Aktualisieren Sie `Text` der äußersten linken `WriteLine`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6d20b-147">Update the `Text` of the left-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="6d20b-148">Aktualisieren Sie `Text` der äußersten rechten `WriteLine`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6d20b-148">Update the `Text` of the right-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="6d20b-149">Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf dem Ablage Punkt der `True` obersten Aktion ab `FlowDecision` .</span><span class="sxs-lookup"><span data-stu-id="6d20b-149">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="6d20b-150">Die `WriteLine`-Aktivität wird dem Flussdiagramm hinzugefügt und mit der `True`-Aktion von `FlowDecision` verknüpft.</span><span class="sxs-lookup"><span data-stu-id="6d20b-150">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>

5. <span data-ttu-id="6d20b-151">Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.</span><span class="sxs-lookup"><span data-stu-id="6d20b-151">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="to-update-the-sequential-workflow"></a><a name="BKMK_UpdateSequential"></a> <span data-ttu-id="6d20b-152">So aktualisieren Sie den sequenziellen Workflow</span><span class="sxs-lookup"><span data-stu-id="6d20b-152">To update the Sequential workflow</span></span>

1. <span data-ttu-id="6d20b-153">Doppelklicken Sie in **Projektmappen-Explorer** unter dem Projekt " **numguess Workflow Activities** " auf **sequentialnumguess Workflow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="6d20b-153">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="6d20b-154">Aktualisieren Sie `Text` der äußersten linken `WriteLine` in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6d20b-154">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="6d20b-155">Aktualisieren Sie `Text` der äußersten rechten `WriteLine`-Aktivität in der `If`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6d20b-155">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="6d20b-156">Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie hinter der **DoWhile** -Aktivität ab, sodass die **Schreib** Weise die letzte Aktivität in der Stamm `Sequence` Aktivität ist.</span><span class="sxs-lookup"><span data-stu-id="6d20b-156">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>

5. <span data-ttu-id="6d20b-157">Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.</span><span class="sxs-lookup"><span data-stu-id="6d20b-157">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

### <a name="to-update-workflowversionmap-to-include-the-previous-workflow-versions"></a><a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="6d20b-158">So aktualisieren Sie workflowversionmap, um die vorherigen Workflow Versionen einzuschließen</span><span class="sxs-lookup"><span data-stu-id="6d20b-158">To update WorkflowVersionMap to include the previous workflow versions</span></span>

1. <span data-ttu-id="6d20b-159">Doppelklicken Sie unter dem Projekt " **numguess Workflowhost** " auf **WorkflowVersionMap.cs** (oder **workflowversionmap. vb**), um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6d20b-159">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

2. <span data-ttu-id="6d20b-160">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d20b-160">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3. <span data-ttu-id="6d20b-161">Fügen Sie drei neue Workflowidentitäten direkt unterhalb der drei vorhandenen Deklarationen für Workflowidentitäten hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d20b-161">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="6d20b-162">Über diese neuen `v1`-Workflowidentitäten wird den Workflows, die vor den Updates gestartet wurden, die richtige Workflowdefinition bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6d20b-162">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>

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

4. <span data-ttu-id="6d20b-163">Aktualisieren Sie im `WorkflowVersionMap`-Konstruktor die `Version`-Eigenschaft der drei aktuellen Workflowidentitäten auf `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="6d20b-163">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>

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

    <span data-ttu-id="6d20b-164">Durch den darin enthaltenen Code werden dem Wörterbuch die aktuellen Workflowversionen hinzugefügt. Der Code verwendet die aktuellen Versionen, auf die im Projekt verwiesen wird. Aus diesem Grund muss der Code, durch den die Workflowdefinitionen initialisiert werden, nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6d20b-164">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>

5. <span data-ttu-id="6d20b-165">Fügen Sie den folgenden Code im Konstruktor unmittelbar nach dem Code hinzu, durch den dem Wörterbuch die aktuellen Versionen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6d20b-165">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>

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

    <span data-ttu-id="6d20b-166">Diese Workflowidentitäten werden den ursprünglichen Versionen der entsprechenden Workflowdefinitionen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6d20b-166">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>

6. <span data-ttu-id="6d20b-167">Als Nächstes laden Sie die Assembly, die die ursprüngliche Version der Workflowdefinitionen enthält, und erstellen die entsprechenden Workflowdefinitionen und fügen sie dem Wörterbuch hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d20b-167">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>

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

    <span data-ttu-id="6d20b-168">Das folgende Beispiel enthält die vollständige Auflistung für die aktualisierte `WorkflowVersionMap`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6d20b-168">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>

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

### <a name="to-build-and-run-the-application"></a><a name="BKMK_BuildAndRun"></a> <span data-ttu-id="6d20b-169">So erstellen Sie die Anwendung und führen Sie aus</span><span class="sxs-lookup"><span data-stu-id="6d20b-169">To build and run the application</span></span>

1. <span data-ttu-id="6d20b-170">Drücken Sie STRG+UMSCHALT+B, um die Anwendung zu erstellen, und dann STRG+F5, um sie zu starten.</span><span class="sxs-lookup"><span data-stu-id="6d20b-170">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>

2. <span data-ttu-id="6d20b-171">Starten Sie einen neuen Workflow, indem Sie auf **Neues Spiel** klicken.</span><span class="sxs-lookup"><span data-stu-id="6d20b-171">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="6d20b-172">Die Version des Workflows wird unter dem Statusfenster angezeigt und gibt die aktualisierte Version der zugeordneten `WorkflowIdentity` an.</span><span class="sxs-lookup"><span data-stu-id="6d20b-172">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="6d20b-173">Notieren Sie die `InstanceId`, sodass Sie beim Abschluss des Workflows dessen Nachverfolgungsdatei anzeigen können. Geben Sie dann Schätzwerte ein, bis das Spiel abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6d20b-173">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="6d20b-174">Beachten Sie, wie sich der Schätzwert des Benutzers gemäß den Updates der `WriteLine`-Aktivitäten in den Informationen im Statusfenster verändert.</span><span class="sxs-lookup"><span data-stu-id="6d20b-174">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>

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
    > <span data-ttu-id="6d20b-175">Der aktualisierte Text aus den `WriteLine`-Aktivitäten wird angezeigt, die Ausgabe der endgültigen, in diesem Thema hinzugefügten `WriteLine`-Aktivität jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="6d20b-175">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="6d20b-176">Das liegt daran, dass das Statusfenster vom `PersistableIdle`-Handler aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6d20b-176">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="6d20b-177">Da der Workflow abgeschlossen wird, statt nach der letzten Aktivität in den Leerlauf zu wechseln, wird der `PersistableIdle`-Handler nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6d20b-177">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="6d20b-178">Im Statusfenster wird jedoch eine ähnliche Meldung vom `Completed`-Handler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d20b-178">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="6d20b-179">Bei Bedarf kann Code dem `Completed`-Handler hinzugefügt werden, um den Text aus `StringWriter` zu extrahieren und ihn im Statusfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6d20b-179">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>

3. <span data-ttu-id="6d20b-180">Öffnen Sie Windows-Explorer, und navigieren Sie zum Ordner " **infogustinworkflowhost\bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen), und öffnen Sie die nach Verfolgungs Datei mit dem Editor, der dem abgeschlossenen Workflow entspricht.</span><span class="sxs-lookup"><span data-stu-id="6d20b-180">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="6d20b-181">Wenn Sie den nicht notiert haben `InstanceId` , können Sie die richtige nach Verfolgungs Datei mithilfe der **geänderten Datums** Informationen in Windows-Explorer identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d20b-181">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>

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

    <span data-ttu-id="6d20b-182">Die aktualisierte `WriteLine`-Ausgabe ist in der Nachverfolgungsdatei enthalten, einschließlich der Ausgabe der `WriteLine`-Aktivität, die diesem Thema hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d20b-182">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>

4. <span data-ttu-id="6d20b-183">Wechseln Sie zurück zur Anwendung zum Schätzen der Zahl, und wählen Sie einen der Workflows aus, die vor den Updates gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="6d20b-183">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="6d20b-184">Sie können die Version des aktuell ausgewählten Workflows anhand der Versionsinformationen identifizieren, die unter dem Statusfenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d20b-184">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="6d20b-185">Geben Sie mehrere Schätzwerte ein. Sie werden feststellen, dass die Statusupdates mit der Ausgabe der `WriteLine`-Aktivität aus der vorherigen Version übereinstimmen und keine Schätzwerte des Benutzers enthalten.</span><span class="sxs-lookup"><span data-stu-id="6d20b-185">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="6d20b-186">Das liegt daran, dass diese Workflows die vorherige Workflowdefinition verwenden, die nicht über die `WriteLine`-Updates verfügt.</span><span class="sxs-lookup"><span data-stu-id="6d20b-186">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>

    <span data-ttu-id="6d20b-187">Im nächsten Schritt, Vorgehens [Weise: Aktualisieren der Definition einer Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md), die ausgeführt wird, werden die laufenden `v1` Workflow Instanzen so aktualisiert, dass Sie die neuen Funktionen als `v2` Instanzen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6d20b-187">In the next step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
