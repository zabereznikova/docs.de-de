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
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a>Vorgehensweise: Paralleles Hosten mehrerer Workflowversionen

`WorkflowIdentity` bietet Entwicklern von Workflowanwendungen die Möglichkeit, einer Worfklowdefinition einen Namen und eine Version zuzuordnen und diese Informationen mit einer persistenten Workflowinstanz zu verknüpfen. Entwickler von Workflowanwendungen können diese Identitätsinformationen verwenden, um Szenarien wie die parallele Ausführung mehrerer Versionen einer Workflowdefinition umzusetzen. Darüber hinaus bilden sie die Grundlage für andere Funktionen wie dynamische Updates. In diesem Schritt des Lernprogramms wird veranschaulicht, wie mit `WorkflowIdentity` mehrere Versionen eines Workflows gleichzeitig gehostet werden.

## <a name="in-this-topic"></a>In diesem Thema

In diesem Schritt des Lernprogramms werden die `WriteLine`-Aktivitäten im Workflow geändert, um zusätzliche Informationen bereitzustellen. Außerdem wird eine neue `WriteLine`-Aktivität hinzugefügt. Eine Kopie der ursprünglichen Workflowassembly wird gespeichert, und die Hostanwendung wird aktualisiert, sodass der ursprüngliche und der aktualisierte Workflow gleichzeitig ausgeführt werden können.

- [So erstellen Sie eine Kopie des NumberGuessWorkflowActivities-Projekts](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)

- [So aktualisieren Sie die Workflows](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)

  - [So aktualisieren Sie den StateMachine-Workflow](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)

  - [So aktualisieren Sie den Flowchart-Workflow](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)

  - [So aktualisieren Sie den Sequential-Workflow](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)

- [So aktualisieren Sie WorkflowVersionMap, um die vorherigen Workflowversionen einzuschließen](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)

- [So erstellen Sie die Anwendung und führen sie aus](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)

> [!NOTE]
> Bevor Sie die Schritte in diesem Thema ausführen, führen Sie die Anwendung aus, starten mehrere Workflows jedes Typs und geben einen oder zwei Schätzwerte für jeden Typ an. Diese beibehaltenen Workflows werden in diesem Schritt und im folgenden Schritt erläutert [: Gewusst wie: Aktualisieren der Definition einer Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md), die ausgeführt wird.

### <a name="to-make-a-copy-of-the-numberguessworkflowactivities-project"></a><a name="BKMK_BackupCopy"></a> So erstellen Sie eine Kopie des Projekts "numguess workflowactivities"

1. Öffnen Sie die Projekt Mappe **WF45GettingStartedTutorial** in Visual Studio 2012, wenn Sie nicht geöffnet ist.

2. Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.

3. Schließen Sie die **WF45GettingStartedTutorial** -Lösung.

4. Öffnen Sie Windows-Explorer, und navigieren Sie zu dem Ordner, in dem sich die Projektmappendatei und die Projektordner des Lernprogramms befinden.

5. Erstellen Sie einen neuen Ordner mit dem Namen **previousversions** im gleichen Ordner wie " **numguess Workflowhost** " und " **numguess workflowactivities**". In diesem Ordner werden die Assemblys gespeichert, die die verschiedenen Versionen der in den folgenden Lernprogrammschritten verwendeten Workflows enthalten.

6. Navigieren Sie zum Ordner " **numguess workflowactivities\bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen). Kopieren Sie **NumberGuessWorkflowActivities.dll** , und fügen Sie ihn in den Ordner **previousversions** ein.

7. Benennen Sie **NumberGuessWorkflowActivities.dll** im Ordner **previousversions** in **NumberGuessWorkflowActivities_v1.dll** um.

    > [!NOTE]
    > Die Schritte in diesem Thema zeigen eine Möglichkeit zur Verwaltung der Assemblys, in denen mehrere Versionen der Workflows enthalten sind. Andere Methoden, wie starke Namen für die Assemblys und das Registrieren der Assemblys im globalen Assemblycache, können ebenfalls verwendet werden.

8. Erstellen Sie einen neuen Ordner mit dem Namen **NumberGuessWorkflowActivities_du** im selben Ordner wie " **numguess Workflowhost**", " **numguess workflowactivities**" und dem neu hinzugefügten Ordner " **previousversions** ", und kopieren Sie alle Dateien und Unterordner aus dem Ordner " **zahleresworkflowactivities** " in den neuen Ordner " **NumberGuessWorkflowActivities_du** ". Diese Sicherungskopie des Projekts für die anfängliche Version der Aktivitäten wird in Gewusst [wie: Aktualisieren der Definition einer laufenden Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md)verwendet.

9. Öffnen Sie die **WF45GettingStartedTutorial** -Projekt Mappe in Visual Studio 2012 erneut.

### <a name="to-update-the-workflows"></a><a name="BKMK_UpdateWorkflows"></a> So aktualisieren Sie die Workflows

In diesem Abschnitt werden die Workflowdefinitionen aktualisiert. Die beiden `WriteLine`-Aktivitäten, die Feedback zum Schätzwert des Benutzers geben, werden aktualisiert, und es wird eine neue `WriteLine`-Aktivität hinzugefügt, die zusätzliche Informationen zum Spiel bereitstellt, nachdem die Zahl geschätzt wurde.

#### <a name="to-update-the-statemachine-workflow"></a><a name="BKMK_UpdateStateMachine"></a> So aktualisieren Sie den StateMachine-Workflow

1. Doppelklicken Sie in **Projektmappen-Explorer** unter dem Projekt " **numguess Workflow Activities** " auf **statemachinenumberguess Workflow. XAML**.

2. Doppelklicken Sie auf den **fehlerhaften** Übergang auf dem Zustands Automaten.

3. Aktualisieren Sie `Text` der äußersten linken `WriteLine` in der `If`-Aktivität.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4. Aktualisieren Sie `Text` der äußersten rechten `WriteLine` in der `If`-Aktivität.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5. Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.

6. Doppelklicken Sie auf den Übergang **Guess correct** auf dem Zustands Automaten.

7. Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** des Übergangs ab.

8. Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="to-update-the-flowchart-workflow"></a><a name="BKMK_UpdateFlowchart"></a> So aktualisieren Sie den Flussdiagramm Workflow

1. Doppelklicken Sie in **Projektmappen-Explorer** unter dem Projekt " **numguess Workflow Activities** " auf **flowchartnumguess Workflow. XAML**.

2. Aktualisieren Sie `Text` der äußersten linken `WriteLine`-Aktivität.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. Aktualisieren Sie `Text` der äußersten rechten `WriteLine`-Aktivität.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf dem Ablage Punkt der `True` obersten Aktion ab `FlowDecision` . Die `WriteLine`-Aktivität wird dem Flussdiagramm hinzugefügt und mit der `True`-Aktion von `FlowDecision` verknüpft.

5. Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="to-update-the-sequential-workflow"></a><a name="BKMK_UpdateSequential"></a> So aktualisieren Sie den sequenziellen Workflow

1. Doppelklicken Sie in **Projektmappen-Explorer** unter dem Projekt " **numguess Workflow Activities** " auf **sequentialnumguess Workflow. XAML**.

2. Aktualisieren Sie `Text` der äußersten linken `WriteLine` in der `If`-Aktivität.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. Aktualisieren Sie `Text` der äußersten rechten `WriteLine`-Aktivität in der `If`-Aktivität.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie hinter der **DoWhile** -Aktivität ab, sodass die **Schreib** Weise die letzte Aktivität in der Stamm `Sequence` Aktivität ist.

5. Geben Sie den folgenden Ausdruck in das Eigenschaftsfeld `Text` ein.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

### <a name="to-update-workflowversionmap-to-include-the-previous-workflow-versions"></a><a name="BKMK_UpdateWorkflowVersionMap"></a> So aktualisieren Sie workflowversionmap, um die vorherigen Workflow Versionen einzuschließen

1. Doppelklicken Sie unter dem Projekt " **numguess Workflowhost** " auf **WorkflowVersionMap.cs** (oder **workflowversionmap. vb**), um es zu öffnen.

2. Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3. Fügen Sie drei neue Workflowidentitäten direkt unterhalb der drei vorhandenen Deklarationen für Workflowidentitäten hinzu. Über diese neuen `v1`-Workflowidentitäten wird den Workflows, die vor den Updates gestartet wurden, die richtige Workflowdefinition bereitgestellt.

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

4. Aktualisieren Sie im `WorkflowVersionMap`-Konstruktor die `Version`-Eigenschaft der drei aktuellen Workflowidentitäten auf `2.0.0.0`.

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

    Durch den darin enthaltenen Code werden dem Wörterbuch die aktuellen Workflowversionen hinzugefügt. Der Code verwendet die aktuellen Versionen, auf die im Projekt verwiesen wird. Aus diesem Grund muss der Code, durch den die Workflowdefinitionen initialisiert werden, nicht aktualisiert werden.

5. Fügen Sie den folgenden Code im Konstruktor unmittelbar nach dem Code hinzu, durch den dem Wörterbuch die aktuellen Versionen hinzugefügt werden.

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

    Diese Workflowidentitäten werden den ursprünglichen Versionen der entsprechenden Workflowdefinitionen zugeordnet.

6. Als Nächstes laden Sie die Assembly, die die ursprüngliche Version der Workflowdefinitionen enthält, und erstellen die entsprechenden Workflowdefinitionen und fügen sie dem Wörterbuch hinzu.

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

    Das folgende Beispiel enthält die vollständige Auflistung für die aktualisierte `WorkflowVersionMap`-Klasse.

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

### <a name="to-build-and-run-the-application"></a><a name="BKMK_BuildAndRun"></a> So erstellen Sie die Anwendung und führen Sie aus

1. Drücken Sie STRG+UMSCHALT+B, um die Anwendung zu erstellen, und dann STRG+F5, um sie zu starten.

2. Starten Sie einen neuen Workflow, indem Sie auf **Neues Spiel** klicken. Die Version des Workflows wird unter dem Statusfenster angezeigt und gibt die aktualisierte Version der zugeordneten `WorkflowIdentity` an. Notieren Sie die `InstanceId`, sodass Sie beim Abschluss des Workflows dessen Nachverfolgungsdatei anzeigen können. Geben Sie dann Schätzwerte ein, bis das Spiel abgeschlossen ist. Beachten Sie, wie sich der Schätzwert des Benutzers gemäß den Updates der `WriteLine`-Aktivitäten in den Informationen im Statusfenster verändert.

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
    > Der aktualisierte Text aus den `WriteLine`-Aktivitäten wird angezeigt, die Ausgabe der endgültigen, in diesem Thema hinzugefügten `WriteLine`-Aktivität jedoch nicht. Das liegt daran, dass das Statusfenster vom `PersistableIdle`-Handler aktualisiert wird. Da der Workflow abgeschlossen wird, statt nach der letzten Aktivität in den Leerlauf zu wechseln, wird der `PersistableIdle`-Handler nicht aufgerufen. Im Statusfenster wird jedoch eine ähnliche Meldung vom `Completed`-Handler angezeigt. Bei Bedarf kann Code dem `Completed`-Handler hinzugefügt werden, um den Text aus `StringWriter` zu extrahieren und ihn im Statusfenster anzuzeigen.

3. Öffnen Sie Windows-Explorer, und navigieren Sie zum Ordner " **infogustinworkflowhost\bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen), und öffnen Sie die nach Verfolgungs Datei mit dem Editor, der dem abgeschlossenen Workflow entspricht. Wenn Sie den nicht notiert haben `InstanceId` , können Sie die richtige nach Verfolgungs Datei mithilfe der **geänderten Datums** Informationen in Windows-Explorer identifizieren.

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

    Die aktualisierte `WriteLine`-Ausgabe ist in der Nachverfolgungsdatei enthalten, einschließlich der Ausgabe der `WriteLine`-Aktivität, die diesem Thema hinzugefügt wurde.

4. Wechseln Sie zurück zur Anwendung zum Schätzen der Zahl, und wählen Sie einen der Workflows aus, die vor den Updates gestartet wurden. Sie können die Version des aktuell ausgewählten Workflows anhand der Versionsinformationen identifizieren, die unter dem Statusfenster angezeigt werden. Geben Sie mehrere Schätzwerte ein. Sie werden feststellen, dass die Statusupdates mit der Ausgabe der `WriteLine`-Aktivität aus der vorherigen Version übereinstimmen und keine Schätzwerte des Benutzers enthalten. Das liegt daran, dass diese Workflows die vorherige Workflowdefinition verwenden, die nicht über die `WriteLine`-Updates verfügt.

    Im nächsten Schritt, Vorgehens [Weise: Aktualisieren der Definition einer Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md), die ausgeführt wird, werden die laufenden `v1` Workflow Instanzen so aktualisiert, dass Sie die neuen Funktionen als `v2` Instanzen enthalten.
