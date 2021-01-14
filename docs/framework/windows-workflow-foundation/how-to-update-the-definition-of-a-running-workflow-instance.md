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
# <a name="how-to-update-the-definition-of-a-running-workflow-instance"></a>Vorgehensweise: Aktualisieren der Definition einer ausgeführten Workflowinstanz

Dynamische Updates bieten Entwicklern von Workflowanwendungen die Möglichkeit, die Workflowdefinition einer persistenten Workflowinstanz zu aktualisieren, beispielsweise um eine Fehlerkorrektur oder neue Anforderungen zu implementieren oder um unerwartete Änderungen zu berücksichtigen. In diesem Schritt des Lernprogramms wird veranschaulicht, wie Sie mit dem dynamischen Update persistente Instanzen des `v1` Workflows für die Zahlen Schätzung ändern, um die neuen Funktionen zu verwenden, die in Gewusst [wie: paralleles Hosten mehrerer Workflow Versionen](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)eingeführt wurden.

## <a name="in-this-topic"></a>In diesem Thema

- [So erstellen Sie das CreateUpdateMaps-Projekt](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateProject)

- [So aktualisieren Sie StateMachineNumberGuessWorkflow](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StateMachine)

- [So aktualisieren Sie FlowchartNumberGuessWorkflow](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Flowchart)

- [So aktualisieren Sie SequentialNumberGuessWorkflow](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Sequential)

- [So erstellen und führen Sie die CreateUpdateMaps-Anwendung aus](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateUpdateMaps)

- [So erstellen Sie die aktualisierte Workflowassembly](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAssembly)

- [So aktualisieren Sie WorkflowVersionMap anhand der neuen Versionen](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_UpdateWorkflowVersionMap)

- [So wenden Sie die dynamischen Updates an](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_ApplyUpdate)

- [So führen Sie die Anwendung anhand der aktualisierten Workflows aus](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAndRun)

- [So aktivieren Sie das Starten von Vorgängerversionen der Workflows](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StartPreviousVersions)

### <a name="to-create-the-createupdatemaps-project"></a><a name="BKMK_CreateProject"></a> So erstellen Sie das Projekt "Projekt erstellen"

1. Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf **WF45GettingStartedTutorial** , und wählen Sie **Hinzufügen**, **Neues Projekt** aus.

2. Wählen Sie im Knoten **installiert** die Option **Visual c#**, **Windows** (oder **Visual Basic**, **Windows**) aus.

    > [!NOTE]
    > Abhängig davon, welche Programmiersprache als primäre Sprache in Visual Studio konfiguriert ist, kann sich der Knoten **Visual C#** oder **Visual Basic** unter dem Knoten **Andere Sprachen** im Knoten **Installiert** befinden.

     Stellen Sie sicher, dass **.NET Framework 4.5** in der Dropdownliste für die .NET Framework-Version ausgewählt ist. Wählen Sie in der Liste **Windows** die Option **Konsolenanwendung** aus. Geben Sie im Feld **Name den Namen** " **kreateupdatemaps** " ein, und klicken Sie auf **OK**

3. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **kreateupdatemaps** " und wählen Sie **Verweis hinzufügen**

4. Wählen Sie **Framework** aus **dem Knoten Assemblys in der Liste** **Verweis hinzufügen** aus. Geben Sie **System. Activities** in das Feld Assemblys **Suchen** ein, um die Assemblys zu filtern und die Auswahl der gewünschten Verweise zu vereinfachen.

5. Aktivieren Sie das Kontrollkästchen neben **System. Activities** in der Liste **Suchergebnisse** .

6. Geben Sie **Serialisierung** in das Feld Assemblys **Durchsuchen** ein, und aktivieren Sie in der Liste **Suchergebnisse** das Kontrollkästchen neben **System. Runtime. Serialization** .

7. Geben Sie **System. XAML** in das Feld Assemblys **Durchsuchen** ein, und aktivieren Sie das Kontrollkästchen neben **System. XAML** in der Liste **Suchergebnisse** .

8. Klicken Sie auf **OK** , um den **Verweis-Manager** zu schließen.

9. Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.

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

10. Fügen Sie der `Program`-Klasse (bzw. `Module1`) die folgenden beiden Zeichenfolgenmember hinzu.

    ```vb
    Const mapPath = "..\..\..\PreviousVersions"
    Const definitionPath = "..\..\..\NumberGuessWorkflowActivities_du"
    ```

    ```csharp
    const string mapPath = @"..\..\..\PreviousVersions";
    const string definitionPath = @"..\..\..\NumberGuessWorkflowActivities_du";
    ```

11. Fügen Sie der `StartUpdate`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu. Durch diese Methode wird die angegebene XAML-Workflowdefinition in einen `ActivityBuilder` geladen und dann `DynamicUpdate.PrepareForUpdate` aufgerufen. `PrepareForUpdate` erstellt eine Kopie der Workflowdefinition in `ActivityBuilder`. Nachdem die Workflowdefinition geändert wurde, wird diese Kopie zusammen mit der geänderten Workflowdefinition verwendet, um die Updatezuordnung zu erstellen.

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

12. Als Nächstes fügen Sie der `CreateUpdateMethod`-Klasse (bzw. `Program`) die folgende `Module1` hinzu. Dadurch wird durch Aufrufen von DynamicUpdateServices.CreateUpdateMap eine dynamische Updatezuordnung erstellt und unter dem angegebenen Namen gespeichert. Diese Updatezuordnung enthält die Informationen, die von der Workflowlaufzeit zur Aktualisierung einer persistenten Workflowinstanz benötigt werden, die mithilfe der ursprünglichen, in `ActivityBuilder` enthaltenen Workflowdefinition gestartet wurde. Die Instanz kann so mithilfe der aktualisierten Workflowdefinition abgeschlossen werden.

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

13. Fügen Sie der `SaveUpdatedDefinition`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu. Durch diese Methode wird die aktualisierte Workflowdefinition gespeichert, nachdem die Updatezuordnung erstellt wurde.

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

### <a name="to-update-statemachinenumberguessworkflow"></a><a name="BKMK_StateMachine"></a> So aktualisieren Sie statemachinenumberguess Workflow

1. Fügen Sie der `CreateStateMachineUpdateMap`-Klasse (bzw. `Program`) eine `Module1` hinzu.

    ```vb
    Private Sub CreateStateMachineUpdateMap()

    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
    }
    ```

2. Rufen Sie `StartUpdate` auf, und rufen Sie anschließend einen Verweis auf die `StateMachine`-Stammaktivität des Workflows ab.

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

3. Aktualisieren Sie als nächstes die Ausdrücke der beiden `WriteLine` Aktivitäten, in denen angezeigt wird, ob der Schätzwert des Benutzers zu hoch oder zu niedrig ist, damit Sie mit den Aktualisierungen in Gewusst [wie: paralleles Hosten mehrerer Workflow Versionen](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)identisch sind.

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

4. Als Nächstes fügen Sie die neue `WriteLine`-Aktivität hinzu, durch die die abschließende Meldung angezeigt wird.

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

5. Nach der Aktualisierung des Workflows rufen Sie `CreateUpdateMaps` und `SaveUpdatedDefinition` auf. Durch `CreateUpdateMaps` wird `DynamicUpdateMap` erstellt und gespeichert, und durch `SaveUpdatedDefinition` wird die aktualisierte Workflowdefinition gespeichert.

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

    Im folgenden Beispiel ist die abgeschlossene `CreateStateMachineUpdateMap`-Methode dargestellt.

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

### <a name="to-update-flowchartnumberguessworkflow"></a><a name="BKMK_Flowchart"></a> So aktualisieren Sie flowchartnumguess Workflow

1. Fügen Sie der `CreateFlowchartUpdateMethod`-Klasse (bzw. `Program`) die folgende `Module1` hinzu. Diese Methode ist vergleichbar mit `CreateStateMachineUpdateMap`. Sie beginnt mit einem Aufruf von `StartUpdate`, aktualisiert die Definition des Flussdiagrammworkflows und endet mit dem Speichern der Updatezuordnung und der aktualisierten Workflowdefinition.

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

### <a name="to-update-sequentialnumberguessworkflow"></a><a name="BKMK_Sequential"></a> So aktualisieren Sie sequentialnumguess Workflow

1. Fügen Sie der `CreateSequentialUpdateMethod`-Klasse (bzw. `Program`) die folgende `Module1` hinzu. Diese Methode ist vergleichbar mit den anderen beiden Methoden. Sie beginnt mit einem Aufruf von `StartUpdate`, aktualisiert die Definition des sequenziellen Workflows und endet mit dem Speichern der Updatezuordnung und der aktualisierten Workflowdefinition.

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

### <a name="to-build-and-run-the-createupdatemaps-application"></a><a name="BKMK_CreateUpdateMaps"></a> So erstellen Sie die Anwendung "| ateupdatemaps" und führen Sie aus

1. Aktualisieren Sie die `Main`-Methode, und fügen Sie die folgenden drei Methodenaufrufe hinzu. Diese Methoden werden in den folgenden Abschnitten hinzugefügt. Durch jede Methode wird der entsprechende Workflow für das Schätzen von Zahlen aktualisiert und eine `DynamicUpdateMap` erstellt, die die Updates beschreibt.

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

2. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **kreateupdatemaps** " und dann auf **als Startprojekt festlegen**.

3. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und dann STRG+F5, um die `CreateUpdateMaps`-Anwendung auszuführen.

    > [!NOTE]
    > Die `CreateUpdateMaps` Anwendung zeigt keine Statusinformationen an, während Sie ausgeführt wird. Wenn Sie jedoch im Ordner " **NumberGuessWorkflowActivities_du** " und im Ordner " **previousversions** " nachschauen, werden die aktualisierten Workflow Definitions Dateien und die Update Zuordnungen angezeigt.

    Sobald die Updatezuordnungen erstellt und die Workflowdefinitionen aktualisiert sind, besteht der nächste Schritt darin, eine aktualisierte Workflowassembly zu erstellen, in der die aktualisierten Definitionen enthalten sind.

### <a name="to-build-the-updated-workflow-assembly"></a><a name="BKMK_BuildAssembly"></a> So erstellen Sie die aktualisierte Workflowassembly

1. Öffnen Sie eine zweite Instanz von Visual Studio 2012.

2. Wählen Sie im Menü Datei die Option **Öffnen**, **Projekt/Projekt** **Mappe** aus.

3. Navigieren Sie zu dem Ordner, **NumberGuessWorkflowActivities_du** den Sie in Gewusst [wie: Hosten mehrerer Versionen eines Workflows nebeneinander](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)erstellt haben, wählen Sie " **numguess workflowactivities. csproj** " (oder **vbproj**) aus, und klicken Sie auf **Öffnen**.

4. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **sequentialnummeriguess Workflow. XAML** , und wählen Sie **aus Projekt ausschließen aus**. Führen Sie die gleichen Schritte für **flowchartnumguess Workflow. XAML** und **statemachinenumberguess Workflow. XAML** aus. Durch diesen Schritt werden die Vorgängerversionen der Workflowdefinitionen aus dem Projekt entfernt.

5. Wählen Sie im Menü **Projekt** die Option **Vorhandenes Element hinzufügen** aus.

6. Navigieren Sie zu dem **NumberGuessWorkflowActivities_du** Ordner, den Sie unter Gewusst [wie: Hosten mehrerer Versionen eines Workflows nebeneinander](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)erstellt haben.

7. Wählen Sie **XAML-Dateien ( \* . XAML; aus \* . XOML)** aus der Dropdown Liste **Dateityp** .

8. Wählen Sie **SequentialNumberGuessWorkflow_du. XAML**, **FlowchartNumberGuessWorkflow_du. XAML** und **StateMachineNumberGuessWorkflow_du. XAML** aus, und klicken Sie auf **Hinzufügen**.

    > [!NOTE]
    > Klicken Sie mit gedrückter STRG-TASTE, um mehrere Elemente gleichzeitig auszuwählen.

    Durch diesen Schritt werden dem Projekt die aktualisierten Versionen der Workflowdefinitionen hinzugefügt.

9. Drücken Sie STRG+UMSCHALT+B, um das Projekt zu erstellen.

10. Wählen Sie im Menü Datei die Option Projekt **Mappe** **Schließen** aus. Eine Projektmappendatei für das Projekt ist nicht erforderlich. Klicken Sie auf **Nein** , um Visual Studio zu schließen, ohne eine Projektmappendatei zu speichern. Wählen Sie im Menü **Datei** die Option **Beenden** aus, um Visual Studio zu schließen.

11. Öffnen Sie Windows-Explorer, und navigieren Sie zum Ordner " **NumberGuessWorkflowActivities_du \bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen).

12. Benennen Sie **NumberGuessWorkflowActivities.dll** in **NumberGuessWorkflowActivities_v15.dll** um, und kopieren Sie die Datei in den Ordner **previousversions** , den Sie in Gewusst [wie: Hosten mehrerer Versionen eines Workflows nebeneinander](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)erstellt haben.

### <a name="to-update-workflowversionmap-with-the-new-versions"></a><a name="BKMK_UpdateWorkflowVersionMap"></a> So aktualisieren Sie workflowversionmap mit den neuen Versionen

1. Wechseln Sie zurück zur ersten Instanz von Visual Studio 2012.

2. Doppelklicken Sie unter dem Projekt " **numguess Workflowhost** " auf **WorkflowVersionMap.cs** (oder **workflowversionmap. vb**), um es zu öffnen.

3. Fügen Sie direkt unterhalb der sechs vorhandenen Deklarationen für Workflowidentitäten drei neue Workflowidentitäten hinzu. In diesem Lernprogramm wird `1.5.0.0` als `WorkflowIdentity.Version` für die dynamischen Updateidentitäten verwendet. Diese neuen `v15`-Workflowidentitäten werden verwendet, um die richtige Workflowdefinition für die dynamisch aktualisierten, persistenten Workflowinstanzen bereitzustellen.

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

4. Fügen Sie den folgenden Code am Ende des Konstruktors hinzu. Durch diesen Code werden die Workflowidentitäten für dynamische Updates initialisiert, die entsprechenden Workflowdefinitionen geladen und dem Wörterbuch der Workflowversionen hinzugefügt.

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

     Im folgenden Beispiel ist die abgeschlossene `WorkflowVersionMap`-Klasse dargestellt.

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

5. Drücken Sie STRG+UMSCHALT+B, um das Projekt zu erstellen.

### <a name="to-apply-the-dynamic-updates"></a><a name="BKMK_ApplyUpdate"></a> So wenden Sie die dynamischen Updates an

1. Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf **WF45GettingStartedTutorial** , und wählen Sie **Hinzufügen**, **Neues Projekt** aus.

2. Wählen Sie im Knoten **installiert** die Option **Visual c#**, **Windows** (oder **Visual Basic**, **Windows**) aus.

    > [!NOTE]
    > Abhängig davon, welche Programmiersprache als primäre Sprache in Visual Studio konfiguriert ist, kann sich der Knoten **Visual C#** oder **Visual Basic** unter dem Knoten **Andere Sprachen** im Knoten **Installiert** befinden.

    Stellen Sie sicher, dass **.NET Framework 4.5** in der Dropdownliste für die .NET Framework-Version ausgewählt ist. Wählen Sie in der Liste **Windows** die Option **Konsolenanwendung** aus. Geben Sie **applydynamicupdate** in das Feld **Name** ein, und klicken Sie auf **OK**.

3. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **applydynamicupdate** , und wählen Sie **Verweis hinzufügen**.

4. Klicken Sie auf Projekt Mappe, und **Aktivieren Sie das** Kontrollkästchen neben " **numguess Workflowhost**". Dieser Verweis ist erforderlich, damit `ApplyDynamicUpdate` die `NumberGuessWorkflowHost.WorkflowVersionMap`-Klasse verwenden kann.

5. Wählen Sie **Framework** aus **dem Knoten Assemblys in der Liste** **Verweis hinzufügen** aus. Geben Sie **System. Activities** in das Feld Assemblys **Suchen** ein. Dadurch werden die Assemblys gefiltert, sodass die gewünschten Verweise einfacher auszuwählen sind.

6. Aktivieren Sie das Kontrollkästchen neben **System. Activities** in der Liste **Suchergebnisse** .

7. Geben Sie **Serialisierung** in das Feld Assemblys **Durchsuchen** ein, und aktivieren Sie in der Liste **Suchergebnisse** das Kontrollkästchen neben **System. Runtime. Serialization** .

8. Geben Sie **DurableInstancing** in das Feld Assemblys **Durchsuchen** ein, und aktivieren Sie das Kontrollkästchen neben **System. Activities. DurableInstancing** und **System. Runtime. DurableInstancing** in der Liste **Suchergebnisse** .

9. Klicken Sie auf **OK** , um den **Verweis-Manager** zu schließen.

10. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **applydynamicupdate** , und wählen Sie **Hinzufügen**, **Klasse**. Geben `DynamicUpdateInfo` Sie im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.

11. Fügen Sie der `DynamicUpdateInfo`-Klasse die beiden folgenden Member hinzu. Im folgenden Beispiel ist die abgeschlossene `DynamicUpdateInfo`-Klasse dargestellt. Diese Klasse enthält Informationen über die Updatezuordnung und die neue Workflowidentität, die zur Aktualisierung einer Workflowinstanz verwendet wird.

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

12. Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.

    ```vb
    Imports System.Activities
    Imports System.Activities.DynamicUpdate
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DynamicUpdate;
    ```

13. Doppelklicken Sie in Projektmappen-Explorer auf **Program.cs** (oder **Module1. vb**).

14. Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.

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

15. Fügen Sie der `Program`-Klasse (bzw. `Module1`) den folgenden Verbindungszeichenfolgen-Member hinzu.

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    ```

    > [!NOTE]
    > Abhängig von der SQL Server-Version kann der Servername der Verbindungszeichenfolge abweichen.

16. Fügen Sie der `GetIDs`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu. Durch diese Methode wird eine Liste der persistenten Workflowinstanz-IDs zurückgegeben.

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

17. Fügen Sie der `LoadMap`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu. Durch diese Methode wird ein Wörterbuch erstellt, durch das `v1`-Workflowidentitäten den Updatezuordnungen und neuen Workflowidentitäten zugeordnet werden, die zum Aktualisieren der entsprechenden persistenten Workflowinstanzen verwendet werden.

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

18. Fügen Sie der `LoadMaps`-Klasse (bzw. `Program`) die folgende `Module1`-Methode hinzu. Durch diese Methode werden die drei Updatezuordnungen geladen und ein Wörterbuch erstellt, das den Updatezuordnungen `v1`-Workflowidentitäten zuordnet.

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

19. Fügen Sie `Main` den folgenden Code hinzu. Der Code durchläuft die persistenten Workflowinstanzen und überprüft jede `WorkflowIdentity`. Wenn `WorkflowIdentity` einer `v1`-Workflowinstanz entspricht, wird eine `WorkflowApplication` mit der aktualisierten Workflowdefinition und einer aktualisierten Workflowidentität konfiguriert. Anschließend wird `WorkflowApplication.Load` mit der Instanz und der Updatezuordnung aufgerufen, durch die die dynamische Updatezuordnung angewendet wird. Nachdem das Update angewendet wurde, wird die aktualisierte Instanz mit einem Aufruf von `Unload` persistent gespeichert.

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

20. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **applydynamicupdate** , und wählen Sie **als Startprojekt festlegen** aus.

21. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und STRG+F5, um die `ApplyDynamicUpdate`-Anwendung auszuführen und die persistenten Workflowinstanzen zu aktualisieren. Eine Ausgabe ähnlich der folgenden sollte angezeigt werden. Die Workflows der Version 1.0.0.0 werden auf die Version 1.5.0.0 aktualisiert, während die Workflows der Version 2.0.0.0 nicht aktualisiert werden.

    **Überprüfen: statemachinenumberguess Workflow; Version = 1.0.0.0**\
    **Aktualisiert in: statemachinenumberguess Workflow; Version = 1.5.0.0**\
    **Überprüfen: statemachinenumberguess Workflow; Version = 1.0.0.0**\
    **Aktualisiert in: statemachinenumberguess Workflow; Version = 1.5.0.0**\
    **Überprüfung: flowchartnumguess Workflow; Version = 1.0.0.0**\
    **Aktualisiert in: flowchartnumguess Workflow; Version = 1.5.0.0**\
    **Überprüfung: flowchartnumguess Workflow; Version = 1.0.0.0**\
    **Aktualisiert in: flowchartnumguess Workflow; Version = 1.5.0.0**\
    **Überprüfung: sequentialnummeriguess Workflow; Version = 1.0.0.0**\
    **Aktualisiert in: sequentialnumguess Workflow; Version = 1.5.0.0**\
    **Überprüfung: sequentialnummeriguess Workflow; Version = 1.0.0.0**\
    **Aktualisiert in: sequentialnumguess Workflow; Version = 1.5.0.0**\
    **Überprüfung: sequentialnummeriguess Workflow; Version = 1.0.0.0**\
    **Aktualisiert in: sequentialnumguess Workflow; Version = 1.5.0.0**\
    **Überprüfen: statemachinenumberguess Workflow; Version = 1.0.0.0**\
    **Aktualisiert in: statemachinenumberguess Workflow; Version = 1.5.0.0**\
    **Überprüfung: flowchartnumguess Workflow; Version = 1.0.0.0**\
    **Aktualisiert in: flowchartnumguess Workflow; Version = 1.5.0.0**\
    **Überprüfen: statemachinenumberguess Workflow; Version = 2.0.0.0**\
    **Überprüfen: statemachinenumberguess Workflow; Version = 2.0.0.0**\
    **Überprüfung: flowchartnumguess Workflow; Version = 2.0.0.0**\
    **Überprüfung: flowchartnumguess Workflow; Version = 2.0.0.0**\
    **Überprüfung: sequentialnummeriguess Workflow; Version = 2.0.0.0**\
    **Überprüfung: sequentialnummeriguess Workflow; Version = 2.0.0.0**\
    **Drücken Sie eine beliebige Taste, um fortzufahren...**

### <a name="to-run-the-application-with-the-updated-workflows"></a><a name="BKMK_BuildAndRun"></a> So führen Sie die Anwendung mit den aktualisierten Workflows aus

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflowhost** ", und wählen Sie **als Startprojekt festlegen**.

2. Drücken Sie STRG+F5, um die Anwendung auszuführen.

3. Klicken Sie auf **Neues Spiel** , um einen neuen Workflow zu starten, und notieren Sie die Versionsinformationen unter dem Statusfenster, das angibt, dass der Workflow ein `v2` Workflow ist.

4. Wählen Sie einen der `v1` Workflows aus, die Sie am Anfang der [Seite "Gewusst wie: Hosten mehrerer Versionen eines Workflows](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) " gestartet haben. Beachten Sie, dass die Versionsinformationen unter dem Statusfenster angeben, dass es sich bei dem Workflow um einen Workflow der Version **1.5.0.0** handelt. Beachten Sie, dass abgesehen von der Meldung, dass die Schätzung zu hoch oder zu niedrig war, keine Informationen zu früheren Schätzungen angezeigt werden.

    **Geben Sie eine Zahl zwischen 1 und 10 ein.**\
    **Your guess is too low.**

5. Notieren Sie die `InstanceId`, und geben Sie dann Schätzungen ein, bis der Workflow beendet ist. Das Statusfenster zeigt Informationen über den Inhalt der Schätzung an, da die `WriteLine`-Aktivitäten durch das dynamische Update aktualisiert wurden.

    **Geben Sie eine Zahl zwischen 1 und 10 ein.**\
    **Der Schätzwert ist zu niedrig.**\
    **Geben Sie eine Zahl zwischen 1 und 10 ein.**\
    **5 ist zu niedrig.**\
    **Geben Sie eine Zahl zwischen 1 und 10 ein.**\
    **7 ist zu hoch.**\
    **Geben Sie eine Zahl zwischen 1 und 10 ein.**\
    **Congratulations, you guessed the number in 4 turns.**

6. Öffnen Sie Windows-Explorer, und navigieren Sie zum Ordner " **infogustinworkflowhost\bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen), und öffnen Sie die nach Verfolgungs Datei mit dem Editor, der dem abgeschlossenen Workflow entspricht. Wenn Sie das nicht notiert haben `InstanceId` , können Sie die richtige nach Verfolgungs Datei unter Verwendung der **geänderten Datums** Informationen in Windows-Explorer identifizieren. Die letzte Zeile der Nachverfolgungsinformationen enthält die Ausgabe der neu hinzugefügten `WriteLine`-Aktivität.

    **Geben Sie eine Zahl zwischen 1 und 10 ein.**\
    **Der Schätzwert ist zu niedrig.**\
    **Geben Sie eine Zahl zwischen 1 und 10 ein.**\
    **5 ist zu niedrig.**\
    **Geben Sie eine Zahl zwischen 1 und 10 ein.**\
    **7 ist zu hoch.**\
    **Geben Sie eine Zahl zwischen 1 und 10 ein.**\
    **6 ist richtig. Sie haben es in 4 sich verwandelt.**

### <a name="to-enable-starting-previous-versions-of-the-workflows"></a><a name="BKMK_StartPreviousVersions"></a> So aktivieren Sie das Starten vorheriger Versionen der Workflows

Wenn keine zu aktualisierenden Workflows mehr verfügbar sind, können Sie die `NumberGuessWorkflowHost`-Anwendung ändern, um das Starten früherer Workflowversionen zu aktivieren.

1. Doppelklicken Sie in **Projektmappen-Explorer** auf **workflowhostform** , und wählen Sie das Kombinations Feld **WorkflowType** aus.

2. Wählen Sie im Fenster **Eigenschaften** die Eigenschaft **Items** aus, und klicken Sie auf die Schaltfläche mit den Auslassungs Punkten, um die Sammlung **Elemente** zu bearbeiten

3. Fügen Sie der Auflistung die folgenden drei Elemente hinzu.

    ```
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

    Die abgeschlossene `Items`-Auflistung verfügt über sechs Elemente.

    ```
    StateMachineNumberGuessWorkflow
    FlowchartNumberGuessWorkflow
    SequentialNumberGuessWorkflow
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

4. Doppelklicken Sie in **Projektmappen-Explorer** auf **workflowhostform** , und wählen Sie **Code anzeigen** aus.

5. Fügen Sie der- `switch` Anweisung (oder) drei neue Fälle `Select Case` im-Handler hinzu `NewGame_Click` , um die neuen Elemente im Kombinations Feld **WorkflowType** den übereinstimmenden Workflow Identitäten zuzuordnen.

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

    Im folgenden Beispiel ist die gesamte `switch`-Anweisung (bzw. `Select Case`-Anweisung) enthalten.

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

6. Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen. Sie können jetzt die `v1`-Versionen des Workflows sowie die aktuellen Versionen starten. Um diese neuen Instanzen dynamisch zu aktualisieren, führen Sie die Anwendung **applydynamicupdate** aus.
