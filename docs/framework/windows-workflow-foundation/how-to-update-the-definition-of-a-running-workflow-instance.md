---
title: 'Vorgehensweise: Aktualisieren der Definition einer ausgeführten Workflowinstanz'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26dfac36-ae23-4909-9867-62495b55fb5e
ms.openlocfilehash: b94c7564b1ce87695f82f28eb6daf7686203b41f
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190428"
---
# <a name="how-to-update-the-definition-of-a-running-workflow-instance"></a><span data-ttu-id="dc0d3-102">Vorgehensweise: Aktualisieren der Definition einer ausgeführten Workflowinstanz</span><span class="sxs-lookup"><span data-stu-id="dc0d3-102">How to: Update the Definition of a Running Workflow Instance</span></span>

<span data-ttu-id="dc0d3-103">Dynamische Updates bieten Entwicklern von Workflowanwendungen die Möglichkeit, die Workflowdefinition einer persistenten Workflowinstanz zu aktualisieren,</span><span class="sxs-lookup"><span data-stu-id="dc0d3-103">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="dc0d3-104">beispielsweise um eine Fehlerkorrektur oder neue Anforderungen zu implementieren oder um unerwartete Änderungen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-104">The required change can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="dc0d3-105">In diesem Schritt des Lernprogramms wird veranschaulicht, wie Sie mit dem dynamischen Update persistente Instanzen des `v1` Workflows für die Zahlen Schätzung ändern, um die neuen Funktionen zu verwenden, die in Gewusst [wie: paralleles Hosten mehrerer Workflow Versionen](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-105">This step in the tutorial demonstrates how to use dynamic update to modify  persisted instances of the `v1` number guessing workflow to match the new functionality introduced in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="dc0d3-106">In diesem Thema</span><span class="sxs-lookup"><span data-stu-id="dc0d3-106">In this topic</span></span>

- [<span data-ttu-id="dc0d3-107">So erstellen Sie das CreateUpdateMaps-Projekt</span><span class="sxs-lookup"><span data-stu-id="dc0d3-107">To create the CreateUpdateMaps project</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateProject)

- [<span data-ttu-id="dc0d3-108">So aktualisieren Sie StateMachineNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="dc0d3-108">To update StateMachineNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StateMachine)

- [<span data-ttu-id="dc0d3-109">So aktualisieren Sie FlowchartNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="dc0d3-109">To update FlowchartNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Flowchart)

- [<span data-ttu-id="dc0d3-110">So aktualisieren Sie SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="dc0d3-110">To update SequentialNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Sequential)

- [<span data-ttu-id="dc0d3-111">So erstellen und führen Sie die CreateUpdateMaps-Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="dc0d3-111">To build and run the CreateUpdateMaps application</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateUpdateMaps)

- [<span data-ttu-id="dc0d3-112">So erstellen Sie die aktualisierte Workflowassembly</span><span class="sxs-lookup"><span data-stu-id="dc0d3-112">To build the updated workflow assembly</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAssembly)

- [<span data-ttu-id="dc0d3-113">So aktualisieren Sie WorkflowVersionMap anhand der neuen Versionen</span><span class="sxs-lookup"><span data-stu-id="dc0d3-113">To update WorkflowVersionMap with the new versions</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_UpdateWorkflowVersionMap)

- [<span data-ttu-id="dc0d3-114">So wenden Sie die dynamischen Updates an</span><span class="sxs-lookup"><span data-stu-id="dc0d3-114">To apply the dynamic updates</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_ApplyUpdate)

- [<span data-ttu-id="dc0d3-115">So führen Sie die Anwendung anhand der aktualisierten Workflows aus</span><span class="sxs-lookup"><span data-stu-id="dc0d3-115">To run the application with the updated workflows</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAndRun)

- [<span data-ttu-id="dc0d3-116">So aktivieren Sie das Starten von Vorgängerversionen der Workflows</span><span class="sxs-lookup"><span data-stu-id="dc0d3-116">To enable starting previous versions of the workflows</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StartPreviousVersions)

### <a name="to-create-the-createupdatemaps-project"></a><a name="BKMK_CreateProject"></a> <span data-ttu-id="dc0d3-117">So erstellen Sie das Projekt "Projekt erstellen"</span><span class="sxs-lookup"><span data-stu-id="dc0d3-117">To create the CreateUpdateMaps project</span></span>

1. <span data-ttu-id="dc0d3-118">Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf **WF45GettingStartedTutorial** , und wählen Sie **Hinzufügen**, **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-118">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>

2. <span data-ttu-id="dc0d3-119">Wählen Sie im Knoten **installiert** die Option **Visual c#**, **Windows** (oder **Visual Basic**, **Windows**) aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-119">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc0d3-120">Abhängig davon, welche Programmiersprache als primäre Sprache in Visual Studio konfiguriert ist, kann sich der Knoten **Visual C#** oder **Visual Basic** unter dem Knoten **Andere Sprachen** im Knoten **Installiert** befinden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-120">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="dc0d3-121">Stellen Sie sicher, dass **.NET Framework 4.5** in der Dropdownliste für die .NET Framework-Version ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-121">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="dc0d3-122">Wählen Sie in der Liste **Windows** die Option **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-122">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="dc0d3-123">Geben Sie im Feld **Name den Namen** " **kreateupdatemaps** " ein, und klicken Sie auf **OK**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-123">Type **CreateUpdateMaps** into the **Name** box and click **OK**.</span></span>

3. <span data-ttu-id="dc0d3-124">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **kreateupdatemaps** " und wählen Sie **Verweis hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-124">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Add Reference**.</span></span>

4. <span data-ttu-id="dc0d3-125">Wählen Sie **Framework** aus **dem Knoten Assemblys in der Liste** **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-125">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="dc0d3-126">Geben Sie **System. Activities** in das Feld Assemblys **Suchen** ein, um die Assemblys zu filtern und die Auswahl der gewünschten Verweise zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-126">Type **System.Activities** into the **Search Assemblies** box to filter the assemblies and make the desired references easier to select.</span></span>

5. <span data-ttu-id="dc0d3-127">Aktivieren Sie das Kontrollkästchen neben **System. Activities** in der Liste **Suchergebnisse** .</span><span class="sxs-lookup"><span data-stu-id="dc0d3-127">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

6. <span data-ttu-id="dc0d3-128">Geben Sie **Serialisierung** in das Feld Assemblys **Durchsuchen** ein, und aktivieren Sie in der Liste **Suchergebnisse** das Kontrollkästchen neben **System. Runtime. Serialization** .</span><span class="sxs-lookup"><span data-stu-id="dc0d3-128">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

7. <span data-ttu-id="dc0d3-129">Geben Sie **System. XAML** in das Feld Assemblys **Durchsuchen** ein, und aktivieren Sie das Kontrollkästchen neben **System. XAML** in der Liste **Suchergebnisse** .</span><span class="sxs-lookup"><span data-stu-id="dc0d3-129">Type **System.Xaml** into the **Search Assemblies** box, and check the checkbox beside **System.Xaml** from the **Search Results** list.</span></span>

8. <span data-ttu-id="dc0d3-130">Klicken Sie auf **OK** , um den **Verweis-Manager** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-130">Click **OK** to close **Reference Manager** and add the references.</span></span>

9. <span data-ttu-id="dc0d3-131">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-131">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.Statements
    Imports System.Xaml
    Imports System.Reflection
    Imports System.IO
    Imports System.Activities.XamlIntegration
    Imports System.Activities.DynamicUpdate
    Imports System.Runtime.Serialization
    Imports Microsoft.VisualBasic.Activities
    ```

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    using System.IO;
    using System.Xaml;
    using System.Reflection;
    using System.Activities.XamlIntegration;
    using System.Activities.DynamicUpdate;
    using System.Runtime.Serialization;
    using Microsoft.CSharp.Activities;
    ```

10. <span data-ttu-id="dc0d3-132">Fügen Sie der `Program`-Klasse (bzw. `Module1`) die folgenden beiden Zeichenfolgenmember hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-132">Add the following two string members to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const mapPath = "..\..\..\PreviousVersions"
    Const definitionPath = "..\..\..\NumberGuessWorkflowActivities_du"
    ```

    ```csharp
    const string mapPath = @"..\..\..\PreviousVersions";
    const string definitionPath = @"..\..\..\NumberGuessWorkflowActivities_du";
    ```

11. <span data-ttu-id="dc0d3-133">Fügen Sie der `StartUpdate`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-133">Add the following `StartUpdate` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="dc0d3-134">Durch diese Methode wird die angegebene XAML-Workflowdefinition in einen `ActivityBuilder` geladen und dann `DynamicUpdate.PrepareForUpdate` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-134">This method loads up the specified xaml workflow definition into an `ActivityBuilder`, and then calls `DynamicUpdate.PrepareForUpdate`.</span></span> <span data-ttu-id="dc0d3-135">`PrepareForUpdate` erstellt eine Kopie der Workflowdefinition in `ActivityBuilder`.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-135">`PrepareForUpdate` makes a copy of the workflow definition inside the `ActivityBuilder`.</span></span> <span data-ttu-id="dc0d3-136">Nachdem die Workflowdefinition geändert wurde, wird diese Kopie zusammen mit der geänderten Workflowdefinition verwendet, um die Updatezuordnung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-136">After the workflow definition is modified, this copy is used along with the modified workflow definition to create the update map.</span></span>

    ```vb
    Private Function StartUpdate(name As String) As ActivityBuilder
        'Create the XamlXmlReaderSettings.
        Dim readerSettings As XamlReaderSettings = New XamlXmlReaderSettings()
        'In the XAML the "local" namespace refers to artifacts that come from
        'the same project as the XAML. When loading XAML if the currently executing
        'assembly is not the same assembly that was referred to as "local" in the XAML
        'LocalAssembly must be set to the assembly containing the artifacts.
        'Assembly.LoadFile requires an absolute path so convert this relative path
        'to an absolute path.
        readerSettings.LocalAssembly = Assembly.LoadFile(
            Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))

        Dim fullPath As String = Path.Combine(definitionPath, name)
        Dim xamlReader As XamlXmlReader = New XamlXmlReader(fullPath, readerSettings)

        'Load the workflow definition into an ActivityBuilder.
        Dim wf As ActivityBuilder = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))

        'PrepareForUpdate makes a copy of the workflow definition in the
        'ActivityBuilder that is used for comparison when the update
        'map is created.
        DynamicUpdateServices.PrepareForUpdate(wf)

        Return wf
    End Function
    ```

    ```csharp
    private static ActivityBuilder StartUpdate(string name)
    {
        // Create the XamlXmlReaderSettings.
        XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()
        {
            // In the XAML the "local" namespace refers to artifacts that come from
            // the same project as the XAML. When loading XAML if the currently executing
            // assembly is not the same assembly that was referred to as "local" in the XAML
            // LocalAssembly must be set to the assembly containing the artifacts.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            LocalAssembly = Assembly.LoadFile(
                Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))
        };

        string path = Path.Combine(definitionPath, name);
        XamlXmlReader xamlReader = new XamlXmlReader(path, readerSettings);

        // Load the workflow definition into an ActivityBuilder.
        ActivityBuilder wf = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))
            as ActivityBuilder;

        // PrepareForUpdate makes a copy of the workflow definition in the
        // ActivityBuilder that is used for comparison when the update
        // map is created.
        DynamicUpdateServices.PrepareForUpdate(wf);

        return wf;
    }
    ```

12. <span data-ttu-id="dc0d3-137">Als Nächstes fügen Sie der `CreateUpdateMethod`-Klasse (bzw. `Program`) die folgende `Module1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-137">Next, add the following `CreateUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="dc0d3-138">Dadurch wird durch Aufrufen von DynamicUpdateServices.CreateUpdateMap eine dynamische Updatezuordnung erstellt und unter dem angegebenen Namen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-138">This creates a dynamic update map by calling DynamicUpdateServices.CreateUpdateMap, and then saves the update map using the specified name.</span></span> <span data-ttu-id="dc0d3-139">Diese Updatezuordnung enthält die Informationen, die von der Workflowlaufzeit zur Aktualisierung einer persistenten Workflowinstanz benötigt werden, die mithilfe der ursprünglichen, in `ActivityBuilder` enthaltenen Workflowdefinition gestartet wurde. Die Instanz kann so mithilfe der aktualisierten Workflowdefinition abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-139">This update map contains the information needed by the workflow runtime to update a persisted workflow instance that was started using the original workflow definition contained in the `ActivityBuilder` so that it completes using the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateUpdateMaps(wf As ActivityBuilder, name As String)
        'Create the UpdateMap.
        Dim map As DynamicUpdateMap =
            DynamicUpdateServices.CreateUpdateMap(wf)

        'Serialize it to a file.
        Dim mapFullPath As String = Path.Combine(mapPath, name)
        Dim sz As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
        Using fs As FileStream = File.Open(mapFullPath, FileMode.Create)
            sz.WriteObject(fs, map)
        End Using
    End Sub
    ```

    ```csharp
    private static void CreateUpdateMaps(ActivityBuilder wf, string name)
    {
        // Create the UpdateMap.
        DynamicUpdateMap map =
            DynamicUpdateServices.CreateUpdateMap(wf);

        // Serialize it to a file.
        string path = Path.Combine(mapPath, name);
        DataContractSerializer sz = new DataContractSerializer(typeof(DynamicUpdateMap));
        using (FileStream fs = System.IO.File.Open(path, FileMode.Create))
        {
            sz.WriteObject(fs, map);
        }
    }
    ```

13. <span data-ttu-id="dc0d3-140">Fügen Sie der `SaveUpdatedDefinition`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-140">Add the following `SaveUpdatedDefinition` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="dc0d3-141">Durch diese Methode wird die aktualisierte Workflowdefinition gespeichert, nachdem die Updatezuordnung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-141">This method saves the updated workflow definition once the update map is created.</span></span>

    ```vb
    Private Sub SaveUpdatedDefinition(wf As ActivityBuilder, name As String)
        Dim xamlPath As String = Path.Combine(definitionPath, name)
        Dim sw As StreamWriter = File.CreateText(xamlPath)
        Dim xw As XamlWriter = ActivityXamlServices.CreateBuilderWriter(
            New XamlXmlWriter(sw, New XamlSchemaContext()))
        XamlServices.Save(xw, wf)
        sw.Close()
    End Sub
    ```

    ```csharp
    private static void SaveUpdatedDefinition(ActivityBuilder wf, string name)
    {
        string xamlPath = Path.Combine(definitionPath, name);
        StreamWriter sw = File.CreateText(xamlPath);
        XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(
            new XamlXmlWriter(sw, new XamlSchemaContext()));
        XamlServices.Save(xw, wf);
        sw.Close();
    }
    ```

### <a name="to-update-statemachinenumberguessworkflow"></a><a name="BKMK_StateMachine"></a> <span data-ttu-id="dc0d3-142">So aktualisieren Sie statemachinenumberguess Workflow</span><span class="sxs-lookup"><span data-stu-id="dc0d3-142">To update StateMachineNumberGuessWorkflow</span></span>

1. <span data-ttu-id="dc0d3-143">Fügen Sie der `CreateStateMachineUpdateMap`-Klasse (bzw. `Program`) eine `Module1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-143">Add a `CreateStateMachineUpdateMap` to the `Program` class (or `Module1`).</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()

    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
    }
    ```

2. <span data-ttu-id="dc0d3-144">Rufen Sie `StartUpdate` auf, und rufen Sie anschließend einen Verweis auf die `StateMachine`-Stammaktivität des Workflows ab.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-144">Make a call to `StartUpdate` and then get a reference to the root `StateMachine` activity of the workflow.</span></span>

    ```vb
    Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

    'Get a reference to the root StateMachine activity.
    Dim sm As StateMachine = wf.Implementation
    ```

    ```csharp
    ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

    // Get a reference to the root StateMachine activity.
    StateMachine sm = wf.Implementation as StateMachine;
    ```

3. <span data-ttu-id="dc0d3-145">Aktualisieren Sie als nächstes die Ausdrücke der beiden `WriteLine` Aktivitäten, in denen angezeigt wird, ob der Schätzwert des Benutzers zu hoch oder zu niedrig ist, damit Sie mit den Aktualisierungen in Gewusst [wie: paralleles Hosten mehrerer Workflow Versionen](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)identisch sind.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-145">Next, update the expressions of the two `WriteLine` activities that display whether the user's guess is too high or too low so that they match the updates made in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

    ```vb
    'Update the Text of the two WriteLine activities that write the
    'results of the user's guess. They are contained in the workflow as the
    'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

    'Update the "too low" message.
    Dim tooLow As WriteLine = guessLow.Then
    tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

    'Update the "too high" message.
    Dim tooHigh As WriteLine = guessLow.Else
    tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")
    ```

    ```csharp
    // Update the Text of the two WriteLine activities that write the
    // results of the user's guess. They are contained in the workflow as the
    // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    If guessLow = sm.States[1].Transitions[1].Action as If;

    // Update the "too low" message.
    WriteLine tooLow = guessLow.Then as WriteLine;
    tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

    // Update the "too high" message.
    WriteLine tooHigh = guessLow.Else as WriteLine;
    tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");
    ```

4. <span data-ttu-id="dc0d3-146">Als Nächstes fügen Sie die neue `WriteLine`-Aktivität hinzu, durch die die abschließende Meldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-146">Next, add the new `WriteLine` activity that displays the closing message.</span></span>

    ```vb
    'Create the new WriteLine that displays the closing message.
    Dim wl As New WriteLine() With
    {
        .Text = New VisualBasicValue(Of String) _
            ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
    }

    'Add it as the Action for the Guess Correct transition. The Guess Correct
    'transition is the first transition of States[1]. The transitions are listed
    'at the bottom of the State activity designer.
    sm.States(1).Transitions(0).Action = wl
    ```

    ```csharp
    // Create the new WriteLine that displays the closing message.
    WriteLine wl = new WriteLine
    {
        Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
    };

    // Add it as the Action for the Guess Correct transition. The Guess Correct
    // transition is the first transition of States[1]. The transitions are listed
    // at the bottom of the State activity designer.
    sm.States[1].Transitions[0].Action = wl;
    ```

5. <span data-ttu-id="dc0d3-147">Nach der Aktualisierung des Workflows rufen Sie `CreateUpdateMaps` und `SaveUpdatedDefinition` auf.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-147">After the workflow is updated, call `CreateUpdateMaps` and `SaveUpdatedDefinition`.</span></span> <span data-ttu-id="dc0d3-148">Durch `CreateUpdateMaps` wird `DynamicUpdateMap` erstellt und gespeichert, und durch `SaveUpdatedDefinition` wird die aktualisierte Workflowdefinition gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-148">`CreateUpdateMaps` creates and saves the `DynamicUpdateMap`, and `SaveUpdatedDefinition` saves the updated workflow definition.</span></span>

    ```vb
    'Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

    'Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    ```

    ```csharp
    // Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

    // Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    ```

    <span data-ttu-id="dc0d3-149">Im folgenden Beispiel ist die abgeschlossene `CreateStateMachineUpdateMap`-Methode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-149">The following example is the completed `CreateStateMachineUpdateMap` method.</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

        'Get a reference to the root StateMachine activity.
        Dim sm As StateMachine = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

        'Update the "too low" message.
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Add it as the Action for the Guess Correct transition. The Guess Correct
        'transition is the first transition of States[1]. The transitions are listed
        'at the bottom of the State activity designer.
        sm.States(1).Transitions(0).Action = wl

        'Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

        // Get a reference to the root StateMachine activity.
        StateMachine sm = wf.Implementation as StateMachine;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        If guessLow = sm.States[1].Transitions[1].Action as If;

        // Update the "too low" message.
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Create the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Add it as the Action for the Guess Correct transition. The Guess Correct
        // transition is the first transition of States[1]. The transitions are listed
        // at the bottom of the State activity designer.
        sm.States[1].Transitions[0].Action = wl;

        // Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="to-update-flowchartnumberguessworkflow"></a><a name="BKMK_Flowchart"></a> <span data-ttu-id="dc0d3-150">So aktualisieren Sie flowchartnumguess Workflow</span><span class="sxs-lookup"><span data-stu-id="dc0d3-150">To update FlowchartNumberGuessWorkflow</span></span>

1. <span data-ttu-id="dc0d3-151">Fügen Sie der `CreateFlowchartUpdateMethod`-Klasse (bzw. `Program`) die folgende `Module1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-151">Add the following `CreateFlowchartUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="dc0d3-152">Diese Methode ist vergleichbar mit `CreateStateMachineUpdateMap`.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-152">This method is similar to `CreateStateMachineUpdateMap`.</span></span> <span data-ttu-id="dc0d3-153">Sie beginnt mit einem Aufruf von `StartUpdate`, aktualisiert die Definition des Flussdiagrammworkflows und endet mit dem Speichern der Updatezuordnung und der aktualisierten Workflowdefinition.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-153">It starts with a call to `StartUpdate`, updates the flowchart workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateFlowchartUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("FlowchartNumberGuessWorkflow.xaml")

        'Get a reference to the root Flowchart activity.
        Dim fc As Flowchart = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'True and False action of the "Guess < Target" FlowDecision, which is
        'Nodes[4].
        Dim guessLow As FlowDecision = fc.Nodes(4)

        'Update the "too low" message.
        Dim trueStep As FlowStep = guessLow.True
        Dim tooLow As WriteLine = trueStep.Action
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim falseStep As FlowStep = guessLow.False
        Dim tooHigh As WriteLine = falseStep.Action
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Create a FlowStep to hold the WriteLine.
        Dim closingStep As New FlowStep() With
        {
            .Action = wl
        }

        'Add this new FlowStep to the True action of the
        '"Guess = Guess" FlowDecision
        Dim guessCorrect As FlowDecision = fc.Nodes(3)
        guessCorrect.True = closingStep

        'Add the new FlowStep to the Nodes collection.
        'If closingStep was replacing an existing node then
        'we would need to remove that Step from the collection.
        'In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep)

        'Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateFlowchartUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("FlowchartNumberGuessWorkflow.xaml");

        // Get a reference to the root Flowchart activity.
        Flowchart fc = wf.Implementation as Flowchart;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // True and False action of the "Guess < Target" FlowDecision, which is
        // Nodes[4].
        FlowDecision guessLow = fc.Nodes[4] as FlowDecision;

        // Update the "too low" message.
        FlowStep trueStep = guessLow.True as FlowStep;
        WriteLine tooLow = trueStep.Action as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        FlowStep falseStep = guessLow.False as FlowStep;
        WriteLine tooHigh = falseStep.Action as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Create a FlowStep to hold the WriteLine.
        FlowStep closingStep = new FlowStep
        {
            Action = wl
        };

        // Add this new FlowStep to the True action of the
        // "Guess == Guess" FlowDecision
        FlowDecision guessCorrect = fc.Nodes[3] as FlowDecision;
        guessCorrect.True = closingStep;

        // Add the new FlowStep to the Nodes collection.
        // If closingStep was replacing an existing node then
        // we would need to remove that Step from the collection.
        // In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep);

        // Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map");

        //  Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="to-update-sequentialnumberguessworkflow"></a><a name="BKMK_Sequential"></a> <span data-ttu-id="dc0d3-154">So aktualisieren Sie sequentialnumguess Workflow</span><span class="sxs-lookup"><span data-stu-id="dc0d3-154">To update SequentialNumberGuessWorkflow</span></span>

1. <span data-ttu-id="dc0d3-155">Fügen Sie der `CreateSequentialUpdateMethod`-Klasse (bzw. `Program`) die folgende `Module1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-155">Add the following `CreateSequentialUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="dc0d3-156">Diese Methode ist vergleichbar mit den anderen beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-156">This method is similar to the other two methods.</span></span> <span data-ttu-id="dc0d3-157">Sie beginnt mit einem Aufruf von `StartUpdate`, aktualisiert die Definition des sequenziellen Workflows und endet mit dem Speichern der Updatezuordnung und der aktualisierten Workflowdefinition.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-157">It starts with a call to `StartUpdate`, updates the sequential workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateSequentialUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("SequentialNumberGuessWorkflow.xaml")

        'Get a reference to the root activity in the workflow.
        Dim rootSequence As Sequence = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the "Guess < Target" If activity.
        'Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        Dim gameLoop As Statements.DoWhile = rootSequence.Activities(1)
        Dim gameBody As Sequence = gameLoop.Body
        Dim guessCorrect As Statements.If = gameBody.Activities(2)
        Dim guessLow As Statements.If = guessCorrect.Then
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl)

        'Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateSequentialUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("SequentialNumberGuessWorkflow.xaml");

        // Get a reference to the root activity in the workflow.
        Sequence rootSequence = wf.Implementation as Sequence;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the "Guess < Target" If activity.
        // Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        DoWhile gameLoop = rootSequence.Activities[1] as DoWhile;
        Sequence gameBody = gameLoop.Body as Sequence;
        If guessCorrect = gameBody.Activities[2] as If;
        If guessLow = guessCorrect.Then as If;
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl);

        // Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="to-build-and-run-the-createupdatemaps-application"></a><a name="BKMK_CreateUpdateMaps"></a> <span data-ttu-id="dc0d3-158">So erstellen Sie die Anwendung "| ateupdatemaps" und führen Sie aus</span><span class="sxs-lookup"><span data-stu-id="dc0d3-158">To build and run the CreateUpdateMaps application</span></span>

1. <span data-ttu-id="dc0d3-159">Aktualisieren Sie die `Main`-Methode, und fügen Sie die folgenden drei Methodenaufrufe hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-159">Update the `Main` method and add the following three method calls.</span></span> <span data-ttu-id="dc0d3-160">Diese Methoden werden in den folgenden Abschnitten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-160">These methods are added in the following sections.</span></span> <span data-ttu-id="dc0d3-161">Durch jede Methode wird der entsprechende Workflow für das Schätzen von Zahlen aktualisiert und eine `DynamicUpdateMap` erstellt, die die Updates beschreibt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-161">Each method updates the corresponding number guess workflow and creates a `DynamicUpdateMap` that describes the updates.</span></span>

    ```vb
    Sub Main()
        'Create the update maps for the changes needed to the v1 activities
        'so they match the v2 activities.
        CreateSequentialUpdateMap()
        CreateFlowchartUpdateMap()
        CreateStateMachineUpdateMap()
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        // Create the update maps for the changes needed to the v1 activities
        // so they match the v2 activities.
        CreateSequentialUpdateMap();
        CreateFlowchartUpdateMap();
        CreateStateMachineUpdateMap();
    }
    ```

2. <span data-ttu-id="dc0d3-162">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **kreateupdatemaps** " und dann auf **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-162">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

3. <span data-ttu-id="dc0d3-163">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und dann STRG+F5, um die `CreateUpdateMaps`-Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-163">Press CTRL+SHIFT+B to build the solution, and then CTRL+F5 to run the `CreateUpdateMaps` application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc0d3-164">Die `CreateUpdateMaps` Anwendung zeigt keine Statusinformationen an, während Sie ausgeführt wird. Wenn Sie jedoch im Ordner " **NumberGuessWorkflowActivities_du** " und im Ordner " **previousversions** " nachschauen, werden die aktualisierten Workflow Definitions Dateien und die Update Zuordnungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-164">The `CreateUpdateMaps` application does not display any status information while running, but if you look in the **NumberGuessWorkflowActivities_du** folder and the **PreviousVersions** folder you will see the updated workflow definition files and the update maps.</span></span>

    <span data-ttu-id="dc0d3-165">Sobald die Updatezuordnungen erstellt und die Workflowdefinitionen aktualisiert sind, besteht der nächste Schritt darin, eine aktualisierte Workflowassembly zu erstellen, in der die aktualisierten Definitionen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-165">Once the update maps are created and the workflow definitions updated, the next step is to build an updated workflow assembly containing the updated definitions.</span></span>

### <a name="to-build-the-updated-workflow-assembly"></a><a name="BKMK_BuildAssembly"></a> <span data-ttu-id="dc0d3-166">So erstellen Sie die aktualisierte Workflowassembly</span><span class="sxs-lookup"><span data-stu-id="dc0d3-166">To build the updated workflow assembly</span></span>

1. <span data-ttu-id="dc0d3-167">Öffnen Sie eine zweite Instanz von Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-167">Open a second instance of Visual Studio 2012.</span></span>

2. <span data-ttu-id="dc0d3-168">Wählen Sie im Menü Datei die Option **Öffnen**, **Projekt/Projekt** **Mappe** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-168">Choose **Open**, **Project/Solution** from the **File** menu.</span></span>

3. <span data-ttu-id="dc0d3-169">Navigieren Sie zu dem Ordner, **NumberGuessWorkflowActivities_du** den Sie in Gewusst [wie: Hosten mehrerer Versionen eines Workflows nebeneinander](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)erstellt haben, wählen Sie " **numguess workflowactivities. csproj** " (oder **vbproj**) aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-169">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), select **NumberGuessWorkflowActivities.csproj** (or **vbproj**), and click **Open**.</span></span>

4. <span data-ttu-id="dc0d3-170">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **sequentialnummeriguess Workflow. XAML** , und wählen Sie **aus Projekt ausschließen aus**.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-170">In **Solution Explorer**, right click **SequentialNumberGuessWorkflow.xaml** and choose **Exclude From Project**.</span></span> <span data-ttu-id="dc0d3-171">Führen Sie die gleichen Schritte für **flowchartnumguess Workflow. XAML** und **statemachinenumberguess Workflow. XAML** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-171">Do the same thing for **FlowchartNumberGuessWorkflow.xaml** and **StateMachineNumberGuessWorkflow.xaml**.</span></span> <span data-ttu-id="dc0d3-172">Durch diesen Schritt werden die Vorgängerversionen der Workflowdefinitionen aus dem Projekt entfernt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-172">This step removes the previous versions of the workflow definitions from the project.</span></span>

5. <span data-ttu-id="dc0d3-173">Wählen Sie im Menü **Projekt** die Option **Vorhandenes Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-173">Choose **Add Existing Item** from the **Project** menu.</span></span>

6. <span data-ttu-id="dc0d3-174">Navigieren Sie zu dem **NumberGuessWorkflowActivities_du** Ordner, den Sie unter Gewusst [wie: Hosten mehrerer Versionen eines Workflows nebeneinander](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-174">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

7. <span data-ttu-id="dc0d3-175">Wählen Sie **XAML-Dateien ( \* . XAML; aus \* . XOML)** aus der Dropdown Liste **Dateityp** .</span><span class="sxs-lookup"><span data-stu-id="dc0d3-175">Choose **XAML Files (\*.xaml;\*.xoml)** from the **Files of type** drop-down list.</span></span>

8. <span data-ttu-id="dc0d3-176">Wählen Sie **SequentialNumberGuessWorkflow_du. XAML**, **FlowchartNumberGuessWorkflow_du. XAML** und **StateMachineNumberGuessWorkflow_du. XAML** aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-176">Select **SequentialNumberGuessWorkflow_du.xaml**, **FlowchartNumberGuessWorkflow_du.xaml**, and **StateMachineNumberGuessWorkflow_du.xaml** and click **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc0d3-177">Klicken Sie mit gedrückter STRG-TASTE, um mehrere Elemente gleichzeitig auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-177">CTRL+Click to select multiple items at a time.</span></span>

    <span data-ttu-id="dc0d3-178">Durch diesen Schritt werden dem Projekt die aktualisierten Versionen der Workflowdefinitionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-178">This step adds the updated versions of the workflow definitions to the project.</span></span>

9. <span data-ttu-id="dc0d3-179">Drücken Sie STRG+UMSCHALT+B, um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-179">Press CTRL+SHIFT+B to build the project.</span></span>

10. <span data-ttu-id="dc0d3-180">Wählen Sie im Menü Datei die Option Projekt **Mappe** **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-180">Choose **Close Solution** from the **File** menu.</span></span> <span data-ttu-id="dc0d3-181">Eine Projektmappendatei für das Projekt ist nicht erforderlich. Klicken Sie auf **Nein** , um Visual Studio zu schließen, ohne eine Projektmappendatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-181">A solution file for the project is not required, so click **No** to close Visual Studio without saving a solution file.</span></span> <span data-ttu-id="dc0d3-182">Wählen Sie im Menü **Datei** die Option **Beenden** aus, um Visual Studio zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-182">Choose **Exit** from the **File** menu to close Visual Studio.</span></span>

11. <span data-ttu-id="dc0d3-183">Öffnen Sie Windows-Explorer, und navigieren Sie zum Ordner " **NumberGuessWorkflowActivities_du \bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen).</span><span class="sxs-lookup"><span data-stu-id="dc0d3-183">Open Windows Explorer and navigate to the **NumberGuessWorkflowActivities_du\bin\Debug** folder (or **bin\Release** depending on your project settings).</span></span>

12. <span data-ttu-id="dc0d3-184">Benennen Sie **NumberGuessWorkflowActivities.dll** in **NumberGuessWorkflowActivities_v15.dll** um, und kopieren Sie die Datei in den Ordner **previousversions** , den Sie in Gewusst [wie: Hosten mehrerer Versionen eines Workflows nebeneinander](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-184">Rename **NumberGuessWorkflowActivities.dll** to **NumberGuessWorkflowActivities_v15.dll**, and copy it to the **PreviousVersions** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

### <a name="to-update-workflowversionmap-with-the-new-versions"></a><a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="dc0d3-185">So aktualisieren Sie workflowversionmap mit den neuen Versionen</span><span class="sxs-lookup"><span data-stu-id="dc0d3-185">To update WorkflowVersionMap with the new versions</span></span>

1. <span data-ttu-id="dc0d3-186">Wechseln Sie zurück zur ersten Instanz von Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-186">Switch back to the initial instance of Visual Studio 2012.</span></span>

2. <span data-ttu-id="dc0d3-187">Doppelklicken Sie unter dem Projekt " **numguess Workflowhost** " auf **WorkflowVersionMap.cs** (oder **workflowversionmap. vb**), um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-187">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

3. <span data-ttu-id="dc0d3-188">Fügen Sie direkt unterhalb der sechs vorhandenen Deklarationen für Workflowidentitäten drei neue Workflowidentitäten hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-188">Add three new workflow identities just below the six existing workflow identity declarations.</span></span> <span data-ttu-id="dc0d3-189">In diesem Lernprogramm wird `1.5.0.0` als `WorkflowIdentity.Version` für die dynamischen Updateidentitäten verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-189">In this tutorial, `1.5.0.0` is used as the `WorkflowIdentity.Version` for the dynamic update identities.</span></span> <span data-ttu-id="dc0d3-190">Diese neuen `v15`-Workflowidentitäten werden verwendet, um die richtige Workflowdefinition für die dynamisch aktualisierten, persistenten Workflowinstanzen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-190">These new `v15` workflow identities will be used provide the correct workflow definition for the dynamically updated persisted workflow instances.</span></span>

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

    'v1.5 (Dynamic Update) identities.
    Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity
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

    // v1.5 (Dynamic Update) identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v15;
    ```

4. <span data-ttu-id="dc0d3-191">Fügen Sie den folgenden Code am Ende des Konstruktors hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-191">Add the following code at the end of the constructor.</span></span> <span data-ttu-id="dc0d3-192">Durch diesen Code werden die Workflowidentitäten für dynamische Updates initialisiert, die entsprechenden Workflowdefinitionen geladen und dem Wörterbuch der Workflowversionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-192">This code initializes the dynamic update workflow identities, loads the corresponding workflow definitions, and adds them to the workflow version dictionary.</span></span>

    ```vb
    'Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    'Add the dynamic update workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v15 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
    Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    // Add the dynamic update workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v15 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
    Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

     <span data-ttu-id="dc0d3-193">Im folgenden Beispiel ist die abgeschlossene `WorkflowVersionMap`-Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-193">The following example is the completed `WorkflowVersionMap` class.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        'v1.5 (Dynamic Update) identities.
        Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity

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

            'Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            'Add the dynamic update workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v15 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
            Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
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

        // v1.5 (Dynamic Update) identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v15;

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

            // Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            // Add the dynamic update workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v15 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
            Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
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

5. <span data-ttu-id="dc0d3-194">Drücken Sie STRG+UMSCHALT+B, um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-194">Press CTRL+SHIFT+B to build the project.</span></span>

### <a name="to-apply-the-dynamic-updates"></a><a name="BKMK_ApplyUpdate"></a> <span data-ttu-id="dc0d3-195">So wenden Sie die dynamischen Updates an</span><span class="sxs-lookup"><span data-stu-id="dc0d3-195">To apply the dynamic updates</span></span>

1. <span data-ttu-id="dc0d3-196">Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf **WF45GettingStartedTutorial** , und wählen Sie **Hinzufügen**, **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-196">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>

2. <span data-ttu-id="dc0d3-197">Wählen Sie im Knoten **installiert** die Option **Visual c#**, **Windows** (oder **Visual Basic**, **Windows**) aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-197">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc0d3-198">Abhängig davon, welche Programmiersprache als primäre Sprache in Visual Studio konfiguriert ist, kann sich der Knoten **Visual C#** oder **Visual Basic** unter dem Knoten **Andere Sprachen** im Knoten **Installiert** befinden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-198">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

    <span data-ttu-id="dc0d3-199">Stellen Sie sicher, dass **.NET Framework 4.5** in der Dropdownliste für die .NET Framework-Version ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-199">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="dc0d3-200">Wählen Sie in der Liste **Windows** die Option **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-200">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="dc0d3-201">Geben Sie **applydynamicupdate** in das Feld **Name** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-201">Type **ApplyDynamicUpdate** into the **Name** box and click **OK**.</span></span>

3. <span data-ttu-id="dc0d3-202">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **applydynamicupdate** , und wählen Sie **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-202">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Add Reference**.</span></span>

4. <span data-ttu-id="dc0d3-203">Klicken Sie auf Projekt Mappe, und **Aktivieren Sie das** Kontrollkästchen neben " **numguess Workflowhost**".</span><span class="sxs-lookup"><span data-stu-id="dc0d3-203">Click **Solution** and check the box next to **NumberGuessWorkflowHost**.</span></span> <span data-ttu-id="dc0d3-204">Dieser Verweis ist erforderlich, damit `ApplyDynamicUpdate` die `NumberGuessWorkflowHost.WorkflowVersionMap`-Klasse verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-204">This reference is needed so that `ApplyDynamicUpdate` can use the `NumberGuessWorkflowHost.WorkflowVersionMap` class.</span></span>

5. <span data-ttu-id="dc0d3-205">Wählen Sie **Framework** aus **dem Knoten Assemblys in der Liste** **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-205">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="dc0d3-206">Geben Sie **System. Activities** in das Feld Assemblys **Suchen** ein.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-206">Type **System.Activities** into the **Search Assemblies** box.</span></span> <span data-ttu-id="dc0d3-207">Dadurch werden die Assemblys gefiltert, sodass die gewünschten Verweise einfacher auszuwählen sind.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-207">This will filter the assemblies and make the desired references easier to select.</span></span>

6. <span data-ttu-id="dc0d3-208">Aktivieren Sie das Kontrollkästchen neben **System. Activities** in der Liste **Suchergebnisse** .</span><span class="sxs-lookup"><span data-stu-id="dc0d3-208">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

7. <span data-ttu-id="dc0d3-209">Geben Sie **Serialisierung** in das Feld Assemblys **Durchsuchen** ein, und aktivieren Sie in der Liste **Suchergebnisse** das Kontrollkästchen neben **System. Runtime. Serialization** .</span><span class="sxs-lookup"><span data-stu-id="dc0d3-209">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

8. <span data-ttu-id="dc0d3-210">Geben Sie **DurableInstancing** in das Feld Assemblys **Durchsuchen** ein, und aktivieren Sie das Kontrollkästchen neben **System. Activities. DurableInstancing** und **System. Runtime. DurableInstancing** in der Liste **Suchergebnisse** .</span><span class="sxs-lookup"><span data-stu-id="dc0d3-210">Type **DurableInstancing** into the **Search Assemblies** box, and check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list.</span></span>

9. <span data-ttu-id="dc0d3-211">Klicken Sie auf **OK** , um den **Verweis-Manager** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-211">Click **OK** to close **Reference Manager** and add the references.</span></span>

10. <span data-ttu-id="dc0d3-212">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **applydynamicupdate** , und wählen Sie **Hinzufügen**, **Klasse**.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-212">Right-click **ApplyDynamicUpdate** in Solution Explorer and choose **Add**, **Class**.</span></span> <span data-ttu-id="dc0d3-213">Geben `DynamicUpdateInfo` Sie im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-213">Type `DynamicUpdateInfo` into the **Name** box and click **Add**.</span></span>

11. <span data-ttu-id="dc0d3-214">Fügen Sie der `DynamicUpdateInfo`-Klasse die beiden folgenden Member hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-214">Add the following two members to the `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="dc0d3-215">Im folgenden Beispiel ist die abgeschlossene `DynamicUpdateInfo`-Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-215">The following example is the completed `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="dc0d3-216">Diese Klasse enthält Informationen über die Updatezuordnung und die neue Workflowidentität, die zur Aktualisierung einer Workflowinstanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-216">This class contains information on the update map and new workflow identity used when a workflow instance is updated.</span></span>

    ```vb
    Public Class DynamicUpdateInfo
        Public updateMap As DynamicUpdateMap
        Public newIdentity As WorkflowIdentity
    End Class
    ```

    ```csharp
    class DynamicUpdateInfo
    {
        public DynamicUpdateMap updateMap;
        public WorkflowIdentity newIdentity;
    }
    ```

12. <span data-ttu-id="dc0d3-217">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-217">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.DynamicUpdate
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DynamicUpdate;
    ```

13. <span data-ttu-id="dc0d3-218">Doppelklicken Sie in Projektmappen-Explorer auf **Program.cs** (oder **Module1. vb**).</span><span class="sxs-lookup"><span data-stu-id="dc0d3-218">Double-click **Program.cs** (or **Module1.vb**) in Solution Explorer.</span></span>

14. <span data-ttu-id="dc0d3-219">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-219">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowHost
    Imports System.Data.SqlClient
    Imports System.Activities.DynamicUpdate
    Imports System.IO
    Imports System.Runtime.Serialization
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    ```

    ```csharp
    using NumberGuessWorkflowHost;
    using System.Data;
    using System.Data.SqlClient;
    using System.Activities;
    using System.Activities.DynamicUpdate;
    using System.IO;
    using System.Runtime.Serialization;
    using System.Activities.DurableInstancing;
    ```

15. <span data-ttu-id="dc0d3-220">Fügen Sie der `Program`-Klasse (bzw. `Module1`) den folgenden Verbindungszeichenfolgen-Member hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-220">Add the following connection string member to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    ```

    > [!NOTE]
    > <span data-ttu-id="dc0d3-221">Abhängig von der SQL Server-Version kann der Servername der Verbindungszeichenfolge abweichen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-221">Depending on your edition of SQL Server, the connection string server name may be different.</span></span>

16. <span data-ttu-id="dc0d3-222">Fügen Sie der `GetIDs`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-222">Add the following `GetIDs` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="dc0d3-223">Durch diese Methode wird eine Liste der persistenten Workflowinstanz-IDs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-223">This method returns a list of persisted workflow instance ids.</span></span>

    ```vb
    Function GetIds() As IList(Of Guid)
        Dim Ids As New List(Of Guid)
        Dim localCmd = _
            String.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]")
        Using localCon = New SqlConnection(connectionString)
            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)
                While reader.Read()
                    'Get the InstanceId of the persisted Workflow
                    Dim id As Guid = Guid.Parse(reader(0).ToString())

                    'Add it to the list.
                    Ids.Add(id)
                End While
            End Using
        End Using

        Return Ids
    End Function
    ```

    ```csharp
    static IList<Guid> GetIds()
    {
        List<Guid> Ids = new List<Guid>();
        string localCmd = string.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]");
        using (SqlConnection localCon = new SqlConnection(connectionString))
        {
            SqlCommand cmd = localCon.CreateCommand();
            cmd.CommandText = localCmd;
            localCon.Open();
            using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
            {
                while (reader.Read())
                {
                    // Get the InstanceId of the persisted Workflow
                    Guid id = Guid.Parse(reader[0].ToString());

                    // Add it to the list.
                    Ids.Add(id);
                }
            }
        }

        return Ids;
    }
    ```

17. <span data-ttu-id="dc0d3-224">Fügen Sie der `LoadMap`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-224">Add the following `LoadMap` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="dc0d3-225">Durch diese Methode wird ein Wörterbuch erstellt, durch das `v1`-Workflowidentitäten den Updatezuordnungen und neuen Workflowidentitäten zugeordnet werden, die zum Aktualisieren der entsprechenden persistenten Workflowinstanzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-225">This method creates a dictionary that maps `v1` workflow identities to the update maps and new workflow identities used to update the corresponding persisted workflow instances.</span></span>

    ```vb
    Function LoadMap(mapName As String) As DynamicUpdateMap
        Dim mapPath As String = Path.Combine("..\..\..\PreviousVersions", mapName)

        Dim map As DynamicUpdateMap
        Using fs As FileStream = File.Open(mapPath, FileMode.Open)
            Dim serializer As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
            Dim updateMap = serializer.ReadObject(fs)
            If updateMap Is Nothing Then
                Throw New ApplicationException("DynamicUpdateMap is null.")
            End If

            map = updateMap
        End Using

        Return map
    End Function
    ```

    ```csharp
    static DynamicUpdateMap LoadMap(string mapName)
    {
        string path = Path.Combine(@"..\..\..\PreviousVersions", mapName);

        DynamicUpdateMap map;
        using (FileStream fs = File.Open(path, FileMode.Open))
        {
            DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
            object updateMap = serializer.ReadObject(fs);
            if (updateMap == null)
            {
                throw new ApplicationException("DynamicUpdateMap is null.");
            }

            map = updateMap as DynamicUpdateMap;
        }

        return map;
    }
    ```

18. <span data-ttu-id="dc0d3-226">Fügen Sie der `LoadMaps`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-226">Add the following `LoadMaps` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="dc0d3-227">Durch diese Methode werden die drei Updatezuordnungen geladen und ein Wörterbuch erstellt, das den Updatezuordnungen `v1`-Workflowidentitäten zuordnet.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-227">This method loads the three update maps and creates a dictionary that maps `v1` workflow identities to the update maps.</span></span>

    ```vb
    Function LoadMaps() As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo)
        'There are 3 update maps to describe the changes to update v1 workflows,
        'one for reach of the 3 workflow types in the tutorial.
        Dim maps = New Dictionary(Of WorkflowIdentity, DynamicUpdateInfo)()

        Dim sequentialMap As DynamicUpdateMap = LoadMap("SequentialNumberGuessWorkflow.map")
        Dim sequentialInfo = New DynamicUpdateInfo With
        {
            .updateMap = sequentialMap,
            .newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo)

        Dim stateMap As DynamicUpdateMap = LoadMap("StateMachineNumberGuessWorkflow.map")
        Dim stateInfo = New DynamicUpdateInfo With
        {
            .updateMap = stateMap,
            .newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo)

        Dim flowchartMap As DynamicUpdateMap = LoadMap("FlowchartNumberGuessWorkflow.map")
        Dim flowchartInfo = New DynamicUpdateInfo With
        {
            .updateMap = flowchartMap,
            .newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo)

        Return maps
    End Function
    ```

    ```csharp
    static IDictionary<WorkflowIdentity, DynamicUpdateInfo> LoadMaps()
    {
        // There are 3 update maps to describe the changes to update v1 workflows,
        // one for reach of the 3 workflow types in the tutorial.
        Dictionary<WorkflowIdentity, DynamicUpdateInfo> maps =
            new Dictionary<WorkflowIdentity, DynamicUpdateInfo>();

        DynamicUpdateMap sequentialMap = LoadMap("SequentialNumberGuessWorkflow.map");
        DynamicUpdateInfo sequentialInfo = new DynamicUpdateInfo
        {
            updateMap = sequentialMap,
            newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo);

        DynamicUpdateMap stateMap = LoadMap("StateMachineNumberGuessWorkflow.map");
        DynamicUpdateInfo stateInfo = new DynamicUpdateInfo
        {
            updateMap = stateMap,
            newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo);

        DynamicUpdateMap flowchartMap = LoadMap("FlowchartNumberGuessWorkflow.map");
        DynamicUpdateInfo flowchartInfo = new DynamicUpdateInfo
        {
            updateMap = flowchartMap,
            newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo);

        return maps;
    }
    ```

19. <span data-ttu-id="dc0d3-228">Fügen Sie `Main` den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-228">Add the following code to `Main`.</span></span> <span data-ttu-id="dc0d3-229">Der Code durchläuft die persistenten Workflowinstanzen und überprüft jede `WorkflowIdentity`.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-229">This code iterates the persisted workflow instances and examines each `WorkflowIdentity`.</span></span> <span data-ttu-id="dc0d3-230">Wenn `WorkflowIdentity` einer `v1`-Workflowinstanz entspricht, wird eine `WorkflowApplication` mit der aktualisierten Workflowdefinition und einer aktualisierten Workflowidentität konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-230">If the `WorkflowIdentity` maps to a `v1` workflow instance, a `WorkflowApplication` is configured with the updated workflow definition and an updated workflow identity.</span></span> <span data-ttu-id="dc0d3-231">Anschließend wird `WorkflowApplication.Load` mit der Instanz und der Updatezuordnung aufgerufen, durch die die dynamische Updatezuordnung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-231">Next, `WorkflowApplication.Load` is called with the instance and the update map, which applies the dynamic update map.</span></span> <span data-ttu-id="dc0d3-232">Nachdem das Update angewendet wurde, wird die aktualisierte Instanz mit einem Aufruf von `Unload` persistent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-232">Once the update is applied, the updated instance is persisted with a call to `Unload`.</span></span>

    ```vb
    Dim store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    Dim updateMaps As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo) = LoadMaps()

    For Each id As Guid In GetIds()
        'Get a proxy to the instance.
        Dim instance As WorkflowApplicationInstance = WorkflowApplication.GetInstance(id, store)

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity)

        'Only update v1 workflows.
        If Not instance.DefinitionIdentity Is Nothing AndAlso _
            instance.DefinitionIdentity.Version.Equals(New Version(1, 0, 0, 0)) Then

            Dim info As DynamicUpdateInfo = updateMaps(instance.DefinitionIdentity)

            'Associate the persisted WorkflowApplicationInstance with
            'a WorkflowApplication that is configured with the updated
            'definition and updated WorkflowIdentity.
            Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity)
            Dim wfApp = New WorkflowApplication(wf, info.newIdentity)

            'Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap)

            'Persist the updated instance.
            wfApp.Unload()

            Console.WriteLine("Updated to: {0}", info.newIdentity)
        Else
            'Not updating this instance, so unload it.
            instance.Abandon()
        End If
    Next
    ```

    ```csharp
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    IDictionary<WorkflowIdentity, DynamicUpdateInfo> updateMaps = LoadMaps();

    foreach (Guid id in GetIds())
    {
        // Get a proxy to the instance.
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(id, store);

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity);

        // Only update v1 workflows.
        if (instance.DefinitionIdentity != null &&
            instance.DefinitionIdentity.Version.Equals(new Version(1, 0, 0, 0)))
        {
            DynamicUpdateInfo info = updateMaps[instance.DefinitionIdentity];

            // Associate the persisted WorkflowApplicationInstance with
            // a WorkflowApplication that is configured with the updated
            // definition and updated WorkflowIdentity.
            Activity wf = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity);
            WorkflowApplication wfApp =
                new WorkflowApplication(wf, info.newIdentity);

            // Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap);

            // Persist the updated instance.
            wfApp.Unload();

            Console.WriteLine("Updated to: {0}", info.newIdentity);
        }
        else
        {
            // Not updating this instance, so unload it.
            instance.Abandon();
        }
    }
    ```

20. <span data-ttu-id="dc0d3-233">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **applydynamicupdate** , und wählen Sie **als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-233">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

21. <span data-ttu-id="dc0d3-234">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und STRG+F5, um die `ApplyDynamicUpdate`-Anwendung auszuführen und die persistenten Workflowinstanzen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-234">Press CTRL+SHIFT+B to build the solution, and then press CTRL+F5 to run the `ApplyDynamicUpdate` application and update the persisted workflow instances.</span></span> <span data-ttu-id="dc0d3-235">Eine Ausgabe ähnlich der folgenden sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-235">You should see output similar to the following.</span></span> <span data-ttu-id="dc0d3-236">Die Workflows der Version 1.0.0.0 werden auf die Version 1.5.0.0 aktualisiert, während die Workflows der Version 2.0.0.0 nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-236">The version 1.0.0.0 workflows are updated to version 1.5.0.0, while the version 2.0.0.0 workflows are not updated.</span></span>

    <span data-ttu-id="dc0d3-237">**Überprüfen: statemachinenumberguess Workflow; Version = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-237">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-238">**Aktualisiert in: statemachinenumberguess Workflow; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-238">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="dc0d3-239">**Überprüfen: statemachinenumberguess Workflow; Version = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-239">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-240">**Aktualisiert in: statemachinenumberguess Workflow; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-240">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="dc0d3-241">**Überprüfung: flowchartnumguess Workflow; Version = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-241">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-242">**Aktualisiert in: flowchartnumguess Workflow; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-242">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="dc0d3-243">**Überprüfung: flowchartnumguess Workflow; Version = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-243">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-244">**Aktualisiert in: flowchartnumguess Workflow; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-244">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="dc0d3-245">**Überprüfung: sequentialnummeriguess Workflow; Version = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-245">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-246">**Aktualisiert in: sequentialnumguess Workflow; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-246">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="dc0d3-247">**Überprüfung: sequentialnummeriguess Workflow; Version = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-247">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-248">**Aktualisiert in: sequentialnumguess Workflow; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-248">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="dc0d3-249">**Überprüfung: sequentialnummeriguess Workflow; Version = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-249">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-250">**Aktualisiert in: sequentialnumguess Workflow; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-250">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="dc0d3-251">**Überprüfen: statemachinenumberguess Workflow; Version = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-251">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-252">**Aktualisiert in: statemachinenumberguess Workflow; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-252">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="dc0d3-253">**Überprüfung: flowchartnumguess Workflow; Version = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-253">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-254">**Aktualisiert in: flowchartnumguess Workflow; Version = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-254">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="dc0d3-255">**Überprüfen: statemachinenumberguess Workflow; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-255">**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-256">**Überprüfen: statemachinenumberguess Workflow; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-256">**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-257">**Überprüfung: flowchartnumguess Workflow; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-257">**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-258">**Überprüfung: flowchartnumguess Workflow; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-258">**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-259">**Überprüfung: sequentialnummeriguess Workflow; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-259">**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-260">**Überprüfung: sequentialnummeriguess Workflow; Version = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-260">**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="dc0d3-261">**Drücken Sie eine beliebige Taste, um fortzufahren...**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-261">**Press any key to continue . . .**</span></span>

### <a name="to-run-the-application-with-the-updated-workflows"></a><a name="BKMK_BuildAndRun"></a> <span data-ttu-id="dc0d3-262">So führen Sie die Anwendung mit den aktualisierten Workflows aus</span><span class="sxs-lookup"><span data-stu-id="dc0d3-262">To run the application with the updated workflows</span></span>

1. <span data-ttu-id="dc0d3-263">Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflowhost** ", und wählen Sie **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-263">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="dc0d3-264">Drücken Sie STRG+F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-264">Press CTRL+F5 to run the application.</span></span>

3. <span data-ttu-id="dc0d3-265">Klicken Sie auf **Neues Spiel** , um einen neuen Workflow zu starten, und notieren Sie die Versionsinformationen unter dem Statusfenster, das angibt, dass der Workflow ein `v2` Workflow ist.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-265">Click **New Game** to start a new workflow and note the version information below the status window that indicates the workflow is a `v2` workflow.</span></span>

4. <span data-ttu-id="dc0d3-266">Wählen Sie einen der `v1` Workflows aus, die Sie am Anfang der [Seite "Gewusst wie: Hosten mehrerer Versionen eines Workflows](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) " gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-266">Select one of the `v1` workflows you started at the beginning of the [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) topic.</span></span> <span data-ttu-id="dc0d3-267">Beachten Sie, dass die Versionsinformationen unter dem Statusfenster angeben, dass es sich bei dem Workflow um einen Workflow der Version **1.5.0.0** handelt.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-267">Note that the version information under the status window indicates that the workflow is a version **1.5.0.0** workflow.</span></span> <span data-ttu-id="dc0d3-268">Beachten Sie, dass abgesehen von der Meldung, dass die Schätzung zu hoch oder zu niedrig war, keine Informationen zu früheren Schätzungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-268">Note that there is no information indicated about previous guesses other than whether they were too high or too low.</span></span>

    <span data-ttu-id="dc0d3-269">**Geben Sie eine Zahl zwischen 1 und 10 ein.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-269">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="dc0d3-270">**Your guess is too low.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-270">**Your guess is too low.**</span></span>

5. <span data-ttu-id="dc0d3-271">Notieren Sie die `InstanceId`, und geben Sie dann Schätzungen ein, bis der Workflow beendet ist.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-271">Make a note of the `InstanceId` and then enter guesses until the workflow completes.</span></span> <span data-ttu-id="dc0d3-272">Das Statusfenster zeigt Informationen über den Inhalt der Schätzung an, da die `WriteLine`-Aktivitäten durch das dynamische Update aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-272">The status window displays information about the content of the guess because the `WriteLine` activities were updated by the dynamic update.</span></span>

    <span data-ttu-id="dc0d3-273">**Geben Sie eine Zahl zwischen 1 und 10 ein.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-273">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="dc0d3-274">**Der Schätzwert ist zu niedrig.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-274">**Your guess is too low.**</span></span>\
    <span data-ttu-id="dc0d3-275">**Geben Sie eine Zahl zwischen 1 und 10 ein.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-275">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="dc0d3-276">**5 ist zu niedrig.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-276">**5 is too low.**</span></span>\
    <span data-ttu-id="dc0d3-277">**Geben Sie eine Zahl zwischen 1 und 10 ein.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-277">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="dc0d3-278">**7 ist zu hoch.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-278">**7 is too high.**</span></span>\
    <span data-ttu-id="dc0d3-279">**Geben Sie eine Zahl zwischen 1 und 10 ein.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-279">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="dc0d3-280">**Congratulations, you guessed the number in 4 turns.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-280">**Congratulations, you guessed the number in 4 turns.**</span></span>

6. <span data-ttu-id="dc0d3-281">Öffnen Sie Windows-Explorer, und navigieren Sie zum Ordner " **infogustinworkflowhost\bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen), und öffnen Sie die nach Verfolgungs Datei mit dem Editor, der dem abgeschlossenen Workflow entspricht.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-281">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="dc0d3-282">Wenn Sie das nicht notiert haben `InstanceId` , können Sie die richtige nach Verfolgungs Datei unter Verwendung der **geänderten Datums** Informationen in Windows-Explorer identifizieren.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-282">If you did not make a note of the `InstanceId` you may be able to identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span> <span data-ttu-id="dc0d3-283">Die letzte Zeile der Nachverfolgungsinformationen enthält die Ausgabe der neu hinzugefügten `WriteLine`-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-283">The last line of the tracking information contains the output of the newly added `WriteLine` activity.</span></span>

    <span data-ttu-id="dc0d3-284">**Geben Sie eine Zahl zwischen 1 und 10 ein.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-284">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="dc0d3-285">**Der Schätzwert ist zu niedrig.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-285">**Your guess is too low.**</span></span>\
    <span data-ttu-id="dc0d3-286">**Geben Sie eine Zahl zwischen 1 und 10 ein.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-286">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="dc0d3-287">**5 ist zu niedrig.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-287">**5 is too low.**</span></span>\
    <span data-ttu-id="dc0d3-288">**Geben Sie eine Zahl zwischen 1 und 10 ein.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-288">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="dc0d3-289">**7 ist zu hoch.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-289">**7 is too high.**</span></span>\
    <span data-ttu-id="dc0d3-290">**Geben Sie eine Zahl zwischen 1 und 10 ein.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-290">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="dc0d3-291">**6 ist richtig. Sie haben es in 4 sich verwandelt.**</span><span class="sxs-lookup"><span data-stu-id="dc0d3-291">**6 is correct. You guessed it in 4 turns.**</span></span>

### <a name="to-enable-starting-previous-versions-of-the-workflows"></a><a name="BKMK_StartPreviousVersions"></a> <span data-ttu-id="dc0d3-292">So aktivieren Sie das Starten vorheriger Versionen der Workflows</span><span class="sxs-lookup"><span data-stu-id="dc0d3-292">To enable starting previous versions of the workflows</span></span>

<span data-ttu-id="dc0d3-293">Wenn keine zu aktualisierenden Workflows mehr verfügbar sind, können Sie die `NumberGuessWorkflowHost`-Anwendung ändern, um das Starten früherer Workflowversionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-293">If you run out of workflows to update, you can modify the `NumberGuessWorkflowHost` application to enable starting previous versions of the workflows.</span></span>

1. <span data-ttu-id="dc0d3-294">Doppelklicken Sie in **Projektmappen-Explorer** auf **workflowhostform** , und wählen Sie das Kombinations Feld **WorkflowType** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-294">Double-click **WorkflowHostForm** in **Solution Explorer**, and select the **WorkflowType** combo box.</span></span>

2. <span data-ttu-id="dc0d3-295">Wählen Sie im Fenster **Eigenschaften** die Eigenschaft **Items** aus, und klicken Sie auf die Schaltfläche mit den Auslassungs Punkten, um die Sammlung **Elemente** zu bearbeiten</span><span class="sxs-lookup"><span data-stu-id="dc0d3-295">In the **Properties** window, select the **Items** property and click the ellipsis button to edit the **Items** collection.</span></span>

3. <span data-ttu-id="dc0d3-296">Fügen Sie der Auflistung die folgenden drei Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-296">Add the following three items to the collection.</span></span>

    ```
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

    <span data-ttu-id="dc0d3-297">Die abgeschlossene `Items`-Auflistung verfügt über sechs Elemente.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-297">The completed `Items` collection will have six items.</span></span>

    ```
    StateMachineNumberGuessWorkflow
    FlowchartNumberGuessWorkflow
    SequentialNumberGuessWorkflow
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

4. <span data-ttu-id="dc0d3-298">Doppelklicken Sie in **Projektmappen-Explorer** auf **workflowhostform** , und wählen Sie **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-298">Double-click **WorkflowHostForm** in **Solution Explorer**, and select **View Code**.</span></span>

5. <span data-ttu-id="dc0d3-299">Fügen Sie der- `switch` Anweisung (oder) drei neue Fälle `Select Case` im-Handler hinzu `NewGame_Click` , um die neuen Elemente im Kombinations Feld **WorkflowType** den übereinstimmenden Workflow Identitäten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-299">Add three new cases to the `switch` (or `Select Case`) statement in the `NewGame_Click` handler to map the new items in the **WorkflowType** combo box to the matching workflow identities.</span></span>

    ```vb
    Case "SequentialNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

    Case "StateMachineNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

    Case "FlowchartNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    ```

    ```csharp
    case "SequentialNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
        break;

    case "StateMachineNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
        break;

    case "FlowchartNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
        break;
    ```

    <span data-ttu-id="dc0d3-300">Im folgenden Beispiel ist die gesamte `switch`-Anweisung (bzw. `Select Case`-Anweisung) enthalten.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-300">The following example contains the complete `switch` (or `Select Case`) statement.</span></span>

    ```vb
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity

        Case "SequentialNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

        Case "StateMachineNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

        Case "FlowchartNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    End Select
    ```

    ```csharp
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;

        case "SequentialNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
            break;

        case "StateMachineNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
            break;

        case "FlowchartNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
            break;
    };
    ```

6. <span data-ttu-id="dc0d3-301">Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-301">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="dc0d3-302">Sie können jetzt die `v1`-Versionen des Workflows sowie die aktuellen Versionen starten.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-302">You can now start the `v1` versions of the workflow as well as the current versions.</span></span> <span data-ttu-id="dc0d3-303">Um diese neuen Instanzen dynamisch zu aktualisieren, führen Sie die Anwendung **applydynamicupdate** aus.</span><span class="sxs-lookup"><span data-stu-id="dc0d3-303">To dynamically update these new instances, run the **ApplyDynamicUpdate** application.</span></span>
