---
title: 'Vorgehensweise: Erstellen und Ausführen eines Workflows mit langer Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: e5083b3d12cecc395500ef13405effa7b7e51633
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420615"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a>Vorgehensweise: Erstellen und Ausführen eines Workflows mit langer Laufzeit

Eines der zentralen Features von Windows Workflow Foundation (WF) ist die Möglichkeit der Laufzeit, Workflows im Leerlauf dauerhaft in einer Datenbank zu speichern und zu entladen. Die Schritte in Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md) haben die Grundlagen des Workflow-Hosting mithilfe einer Konsolenanwendung veranschaulicht. Anhand von Beispielen wurde gezeigt, wie Workflows und Workflowlebenszyklus-Handler gestartet und Lesezeichen wiederaufgenommen werden. Um die Workflowpersistenz effektiv zu veranschaulichen, ist ein komplexerer Workflowhost erforderlich, der das Starten und Fortsetzen mehrerer Workflowinstanzen unterstützt. In diesem Schritt des Lernprogramms wird veranschaulicht, wie eine Windows-Formularhostanwendung erstellt wird, die das Starten und Fortsetzen mehrerer Workflowinstanzen und die Workflowpersistenz unterstützt sowie die Grundlage für erweiterte Funktionen wie Nachverfolgung und Versionsverwaltung bildet, die in den folgenden Schritten des Lernprogramms veranschaulicht werden.

> [!NOTE]
> In diesem Schritt des Tutorials und in den nachfolgenden Schritten werden alle drei Workflow Typen aus "Gewusst [wie: Erstellen eines Workflows](how-to-create-a-workflow.md)" verwendet. Wenn Sie nicht alle drei Typen abgeschlossen haben, können Sie eine abgeschlossene Version der Schritte aus [Windows Workflow Foundation (WF45)-Tutorial "Getting Started](https://go.microsoft.com/fwlink/?LinkID=248976)" herunterladen.

> [!NOTE]
> Informationen zum Herunterladen einer abgeschlossenen Version oder zum Anzeigen einer exemplarischen Vorgehensweise für das Tutorial finden Sie unter [Windows Workflow Foundation (WF45)-Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)für die ersten Schritte.

## <a name="in-this-topic"></a>In diesem Thema

- [So erstellen Sie die Persistenzdatenbank](how-to-create-and-run-a-long-running-workflow.md#BKMK_CreatePersistenceDatabase)

- [Hinzufügen des Verweises zu den DurableInstancing-Assemblys](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddReference)

- [So erstellen Sie das Workflow Host Formular](how-to-create-and-run-a-long-running-workflow.md#BKMK_CreateForm)

- [So fügen Sie die Eigenschaften und Hilfsmethoden des Formulars hinzu](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods)

- [So konfigurieren Sie den Instanzspeicher, die Workflow Lebenszyklus-Handler und Erweiterungen](how-to-create-and-run-a-long-running-workflow.md#BKMK_ConfigureWorkflowApplication)

- [So aktivieren Sie das Starten und fortsetzen mehrerer Workflow Typen](how-to-create-and-run-a-long-running-workflow.md#BKMK_WorkflowVersionMap)

- [So starten Sie einen neuen Workflow](how-to-create-and-run-a-long-running-workflow.md#BKMK_StartWorkflow)

- [So setzen Sie einen Workflow fort](how-to-create-and-run-a-long-running-workflow.md#BKMK_ResumeWorkflow)

- [So beenden Sie einen Workflow](how-to-create-and-run-a-long-running-workflow.md#BKMK_TerminateWorkflow)

- [So erstellen Sie die Anwendung und führen Sie aus](how-to-create-and-run-a-long-running-workflow.md#BKMK_BuildAndRun)

### <a name="BKMK_CreatePersistenceDatabase"></a>So erstellen Sie die Persistenzdatenbank

1. Öffnen Sie SQL Server Management Studio, und stellen Sie eine Verbindung zum lokalen Server her, z. b. **.\sqlexpress**. Klicken Sie mit der rechten Maustaste auf den Knoten **Datenbanken** auf dem lokalen Server, und wählen Sie **neue Datenbank**aus. Benennen Sie die neue Datenbank **WF45GettingStartedTutorial**, akzeptieren Sie alle anderen Werte, und wählen Sie **OK**aus.

    > [!NOTE]
    > Stellen Sie sicher, dass Sie die **Create Database** -Berechtigung auf dem lokalen Server haben, bevor Sie die Datenbank erstellen.

2. Wählen Sie im Menü **Datei** die Option **Öffnen**und dann **Datei** aus. Wechseln Sie zum folgenden Ordner: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`

    Wählen Sie die folgenden beiden Dateien aus, und klicken Sie auf **Öffnen**.

    - SqlWorkflowInstanceStoreLogic.sql

    - SqlWorkflowInstanceStoreSchema.sql

3. Wählen Sie im Menü **Fenster** die Option **SqlWorkflowInstanceStoreSchema. SQL** aus. Stellen Sie sicher, dass **WF45GettingStartedTutorial** in der Dropdown Liste **Verfügbare Datenbanken** ausgewählt ist, und klicken Sie im Menü **Abfrage** auf **Ausführen** .

4. Wählen Sie im Menü **Fenster** die Option **SqlWorkflowInstanceStoreLogic. SQL** aus. Stellen Sie sicher, dass **WF45GettingStartedTutorial** in der Dropdown Liste **Verfügbare Datenbanken** ausgewählt ist, und klicken Sie im Menü **Abfrage** auf **Ausführen** .

    > [!WARNING]
    > Es ist wichtig, die vorherigen beiden Schritte in der richtigen Reihenfolge auszuführen. Wenn die Abfragen nicht in der richtigen Reihenfolge ausgeführt werden, treten Fehler auf, und die Persistenzdatenbank wird nicht richtig konfiguriert.

### <a name="BKMK_AddReference"></a>Hinzufügen des Verweises zu den DurableInstancing-Assemblys

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflow** Message", und wählen Sie **Verweis hinzufügen**.

2. Wählen **Sie** Assemblys aus der Liste **Verweis hinzufügen** aus, und geben Sie im Feld Assemblys **Suchen** `DurableInstancing` ein Dadurch werden die Assemblys gefiltert, sodass die gewünschten Verweise einfacher auszuwählen sind.

3. Aktivieren Sie das Kontrollkästchen neben **System. Activities. DurableInstancing** und **System. Runtime. DurableInstancing** in der Liste **Suchergebnisse** , und klicken Sie auf **OK**.

### <a name="BKMK_CreateForm"></a>So erstellen Sie das Workflow Host Formular

> [!NOTE]
> Durch die Schritte in dieser Prozedur wird veranschaulicht, wie das Formular manuell hinzugefügt und konfiguriert wird. Auf Wunsch können Sie die Projektmappendateien für das Lernprogramm herunterladen und dem Projekt das abgeschlossene Formular hinzufügen. Informationen zum Herunterladen der Lernprogramm Dateien finden Sie unter [Windows Workflow Foundation (WF45): Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)zu den ersten Schritten. Nachdem die Dateien heruntergeladen wurden, klicken Sie mit der rechten Maustaste auf " **numguess Workflow** Message", und wählen Sie **Verweis hinzufügen**. Fügen Sie einen Verweis auf **System. Windows. Forms** und **System. Drawing**hinzu. Diese Verweise werden automatisch hinzugefügt, wenn Sie ein neues Formular aus dem Menü **Hinzufügen**, **Neues Element** hinzufügen. Sie müssen jedoch beim Importieren eines Formulars manuell hinzugefügt werden. Nachdem die Verweise hinzugefügt wurden, klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflowhost** " und wählen **Hinzufügen**, **Vorhandenes Element**. Navigieren Sie zum Ordner `Form` in den Projektdateien, wählen Sie **WorkflowHostForm.cs** (oder **workflowhostform. vb**) aus, und klicken Sie auf **Hinzufügen**. Wenn Sie sich dafür entscheiden, das Formular zu importieren, können Sie mit dem nächsten Abschnitt fortfahren, [um die Eigenschaften und Hilfsmethoden des Formulars hinzuzufügen](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods).

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflowhost** " und wählen Sie **Hinzufügen**, **Neues Element**.

2. Wählen Sie in der Liste **installierte** Vorlagen die Option **Windows Form**aus, geben Sie `WorkflowHostForm` in das Feld **Name** ein, und klicken Sie auf **Hinzufügen**.

3. Konfigurieren Sie die folgenden Eigenschaften für das Formular.

    |property|Wert|
    |--------------|-----------|
    |FormBorderStyle|FixedSingle|
    |MaximizeBox|False|
    |Größe|400, 420|

4. Fügen Sie dem Formular die folgenden Steuerelemente in der angegebenen Reihenfolge hinzu, und konfigurieren Sie die Eigenschaften wie angegeben.

    |Steuerelement|Eigenschaft: Wert|
    |-------------|---------------------|
    |**Button** (Schaltfläche)|Name: neues Spiel<br /><br /> Speicherort: 13, 13<br /><br /> Größe: 75, 23<br /><br /> Text: neues Spiel|
    |**Bezeichnung**|Standort: 94, 18<br /><br /> Text: erraten einer Zahl zwischen 1 und|
    |**ComboBox**|Name: anzahlbereich<br /><br /> DropDownStyle: Dropdown List<br /><br /> Elemente: 10, 100, 1000<br /><br /> Standort: 228, 12<br /><br /> Größe: 143, 21|
    |**Bezeichnung**|Speicherort: 13, 43<br /><br /> Text: Workflowtyp|
    |**ComboBox**|Name: WorkflowType<br /><br /> DropDownStyle: Dropdown List<br /><br /> Elemente: statemachinenumberguess Workflow, flowchartnumguess Workflow, sequentialnumguess Workflow<br /><br /> Speicherort: 94, 40<br /><br /> Größe: 277, 21|
    |**Bezeichnung**|Name: workflowversion<br /><br /> Speicherort: 13, 362<br /><br /> Text: Workflow Version|
    |**GroupBox**|Speicherort: 13, 67<br /><br /> Größe: 358, 287<br /><br /> Text: Spiel|

    > [!NOTE]
    > Wenn Sie die folgenden Steuerelemente hinzufügen, platzieren Sie Sie in der GroupBox.

    |Steuerelement|Eigenschaft: Wert|
    |-------------|---------------------|
    |**Bezeichnung**|Speicherort: 7, 20<br /><br /> Text: Workflow Instanz-ID|
    |**ComboBox**|Name: InstanceId<br /><br /> DropDownStyle: Dropdown List<br /><br /> Speicherort: 121, 17<br /><br /> Größe: 227, 21|
    |**Bezeichnung**|Speicherort: 7, 47<br /><br /> Text: erraten|
    |**TextBox**|Name: erraten<br /><br /> Speicherort: 50, 44<br /><br /> Größe: 65, 20|
    |**Button** (Schaltfläche)|Name: EnterGuess<br /><br /> Speicherort: 121, 42<br /><br /> Größe: 75, 23<br /><br /> Text: Geben Sie Guess ein.|
    |**Button** (Schaltfläche)|Name: quitgame<br /><br /> Speicherort: 274, 42<br /><br /> Größe: 75, 23<br /><br /> Text: beenden|
    |**TextBox**|Name: Workflow Status<br /><br /> Speicherort: 10, 73<br /><br /> Mehrzeilige Zeilen: true<br /><br /> Schreibgeschützt: true<br /><br /> Scrollleisten: vertikal<br /><br /> Größe: 338, 208|

5. Legen Sie die Eigenschaft " **akzeptbutton** " des Formulars auf " **EnterGuess**" fest.

 Im folgenden Beispiel wird das abgeschlossene Formular dargestellt.

 ![Screenshot eines Windows Workflow Foundation Workflow-Host Formulars.](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)

### <a name="BKMK_AddHelperMethods"></a>So fügen Sie die Eigenschaften und Hilfsmethoden des Formulars hinzu

Durch die Schritte in diesem Abschnitt werden der Formularklasse Eigenschaften und Hilfsmethoden hinzugefügt, die die Benutzeroberfläche des Formulars so konfigurieren, dass sie das Ausführen und Fortsetzen der Workflows zum Schätzen von Zahlen unterstützen.

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **workflowhostform** , und wählen Sie **Code anzeigen**aus.

2. Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.

    ```vb
    Imports System.Windows.Forms
    Imports System.Activities.DurableInstancing
    Imports System.Activities
    Imports System.Data.SqlClient
    Imports System.IO
    ```

    ```csharp
    using System.Windows.Forms;
    using System.Activities.DurableInstancing;
    using System.Activities;
    using System.Data.SqlClient;
    using System.IO;
    ```

3. Fügen Sie der **workflowhostform** -Klasse die folgenden Member-Deklarationen hinzu.

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    Dim store As SqlWorkflowInstanceStore
    Dim WorkflowStarting As Boolean
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    SqlWorkflowInstanceStore store;
    bool WorkflowStarting;
    ```

    > [!NOTE]
    > Wenn Ihre Verbindungszeichenfolge abweicht, aktualisieren Sie `connectionString`, damit sie auf Ihre Datenbank verweist.

4. Fügen Sie der `WorkflowInstanceId`-Klasse eine `WorkflowFormHost`-Eigenschaft hinzu.

    ```vb
    Public ReadOnly Property WorkflowInstanceId() As Guid
        Get
            If InstanceId.SelectedIndex = -1 Then
                Return Guid.Empty
            Else
                Return New Guid(InstanceId.SelectedItem.ToString())
            End If
        End Get
    End Property
    ```

    ```csharp
    public Guid WorkflowInstanceId
    {
        get
        {
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;
        }
    }
    ```

    Im Kombinations Feld `InstanceId` wird eine Liste der beibehaltenen Workflow Instanz-IDs angezeigt, und die `WorkflowInstanceId`-Eigenschaft gibt den aktuell ausgewählten Workflow zurück.

5. Fügen Sie einen Handler für das `Load`-Ereignis des Formulars hinzu. Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, klicken Sie oben im Fenster **Eigenschaften** auf das Symbol **Ereignisse** , und doppelklicken Sie dann auf **Laden**.

    ```vb
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load

    End Sub
    ```

    ```csharp
    private void WorkflowHostForm_Load(object sender, EventArgs e)
    {

    }
    ```

6. Fügen Sie `WorkflowHostForm_Load` den folgenden Code hinzu.

    ```vb
    'Initialize the store and configure it so that it can be used for
    'multiple WorkflowApplication instances.
    store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    'Set default ComboBox selections.
    NumberRange.SelectedIndex = 0
    WorkflowType.SelectedIndex = 0

    ListPersistedWorkflows()
    ```

    ```csharp
    // Initialize the store and configure it so that it can be used for
    // multiple WorkflowApplication instances.
    store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    // Set default ComboBox selections.
    NumberRange.SelectedIndex = 0;
    WorkflowType.SelectedIndex = 0;

    ListPersistedWorkflows();
    ```

    Beim Laden des Formulars geschieht Folgendes: `SqlWorkflowInstanceStore` wird konfiguriert, der Bereich und die Kombinationsfelder für den Workflowtyp werden auf die Standardwerte festgelegt, und die persistenten Workflowinstanzen werden dem Kombinationsfeld `InstanceId` hinzugefügt.

7. Fügen Sie einen `SelectedIndexChanged`-Handler für `InstanceId` hinzu. Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, wählen Sie das Kombinations Feld `InstanceId` aus, klicken Sie oben im Fenster **Eigenschaften** auf das Symbol **Ereignisse** , und doppelklicken Sie auf **SelectedIndexChanged**.

    ```vb
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged

    End Sub
    ```

    ```csharp
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)
    {

    }
    ```

8. Fügen Sie `InstanceId_SelectedIndexChanged` den folgenden Code hinzu. Sobald der Benutzer über das Kombinationsfeld einen Workflow auswählt, wird das Statusfenster von diesem Handler aktualisiert.

    ```vb
    If InstanceId.SelectedIndex = -1 Then
        Return
    End If

    'Clear the status window.
    WorkflowStatus.Clear()

    'Get the workflow version and display it.
    'If the workflow is just starting then this info will not
    'be available in the persistence store so do not try and retrieve it.
    If Not WorkflowStarting Then
        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        WorkflowVersion.Text = _
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)

        'Unload the instance.
        instance.Abandon()
    End If
    ```

    ```csharp
    if (InstanceId.SelectedIndex == -1)
    {
        return;
    }

    // Clear the status window.
    WorkflowStatus.Clear();

    // Get the workflow version and display it.
    // If the workflow is just starting then this info will not
    // be available in the persistence store so do not try and retrieve it.
    if (!WorkflowStarting)
    {
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);

        WorkflowVersion.Text =
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);

        // Unload the instance.
        instance.Abandon();
    }
    ```

9. Fügen Sie der Formularklasse die folgende `ListPersistedWorkflows`-Methode hinzu.

    ```vb
    Private Sub ListPersistedWorkflows()
        Using localCon As New SqlConnection(connectionString)
            Dim localCmd As String = _
                "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]"

            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)

                While (reader.Read())
                    'Get the InstanceId of the persisted Workflow.
                    Dim id As Guid = Guid.Parse(reader(0).ToString())
                    InstanceId.Items.Add(id)
                End While
            End Using
        End Using
    End Sub
    ```

    ```csharp
    using (SqlConnection localCon = new SqlConnection(connectionString))
    {
        string localCmd =
            "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]";

        SqlCommand cmd = localCon.CreateCommand();
        cmd.CommandText = localCmd;
        localCon.Open();
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
        {
            while (reader.Read())
            {
                // Get the InstanceId of the persisted Workflow
                Guid id = Guid.Parse(reader[0].ToString());
                InstanceId.Items.Add(id);
            }
        }
    }
    ```

    `ListPersistedWorkflows` fragt den Instanzspeicher für persistente Workflowinstanzen ab und fügt dem Kombinationsfeld `cboInstanceId` die Instanz-IDs hinzu.

10. Fügen Sie der Formularklasse die folgende `UpdateStatus`-Methode und den entsprechenden Delegaten hinzu. Durch diese Methode wird das Statusfenster auf dem Formular mit dem Status des derzeit ausgeführten Workflows aktualisiert.

    ```vb
    Private Delegate Sub UpdateStatusDelegate(msg As String)
    Public Sub UpdateStatus(msg As String)
        'We may be on a different thread so we need to
        'make this call using BeginInvoke.
        If InvokeRequired Then
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)
        Else
            If Not msg.EndsWith(vbCrLf) Then
                msg = msg & vbCrLf
            End If

            WorkflowStatus.AppendText(msg)

            'Ensure that the newly added status is visible.
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length
            WorkflowStatus.ScrollToCaret()
        End If
    End Sub
    ```

    ```csharp
    private delegate void UpdateStatusDelegate(string msg);
    public void UpdateStatus(string msg)
    {
        // We may be on a different thread so we need to
        // make this call using BeginInvoke.
        if (InvokeRequired)
        {
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);
        }
        else
        {
            if (!msg.EndsWith("\r\n"))
            {
                msg += "\r\n";
            }
            WorkflowStatus.AppendText(msg);

            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;
            WorkflowStatus.ScrollToCaret();
        }
    }
    ```

11. Fügen Sie der Formularklasse die folgende `GameOver`-Methode und den entsprechenden Delegaten hinzu. Wenn ein Workflow abgeschlossen ist, aktualisiert diese Methode die Benutzeroberfläche des Formulars, indem die Instanz-ID des abgeschlossenen Workflows aus dem Kombinations Feld **InstanceId** entfernt wird.

    ```vb
    Private Delegate Sub GameOverDelegate()
    Private Sub GameOver()
        If InvokeRequired Then
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))
        Else
            'Remove this instance from the InstanceId combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem)
            InstanceId.SelectedIndex = -1
        End If
    End Sub
    ```

    ```csharp
    private delegate void GameOverDelegate();
    private void GameOver()
    {
        if (InvokeRequired)
        {
            BeginInvoke(new GameOverDelegate(GameOver));
        }
        else
        {
            // Remove this instance from the combo box
            InstanceId.Items.Remove(InstanceId.SelectedItem);
            InstanceId.SelectedIndex = -1;
        }
    }
    ```

### <a name="BKMK_ConfigureWorkflowApplication"></a>So konfigurieren Sie den Instanzspeicher, die Workflow Lebenszyklus-Handler und Erweiterungen

1. Fügen Sie der Formularklasse eine `ConfigureWorkflowApplication`-Methode hinzu.

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)

    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
    }
    ```

    Durch diese Methode wird `WorkflowApplication` konfiguriert und die gewünschten Erweiterungen sowie Handler für die Lebenszyklusereignisse des Workflows werden hinzugefügt.

2. Geben Sie in `ConfigureWorkflowApplication` den `SqlWorkflowInstanceStore` für `WorkflowApplication` an.

    ```vb
    'Configure the persistence store.
    wfApp.InstanceStore = store
    ```

    ```csharp
    // Configure the persistence store.
    wfApp.InstanceStore = store;
    ```

3. Als Nächstes erstellen Sie eine `StringWriter`-Instanz und fügen sie der `Extensions`-Auflistung von `WorkflowApplication` hinzu. Wenn eine `StringWriter` zu den Erweiterungen hinzugefügt wird, erfasst Sie alle `WriteLine` Aktivitäts Ausgaben. Sobald der Workflow im Leerlauf ist, kann die `WriteLine` Ausgabe aus `StringWriter` extrahiert und im Formular angezeigt werden.

    ```vb
    'Add a StringWriter to the extensions. This captures the output
    'from the WriteLine activities so we can display it in the form.
    Dim sw As New StringWriter()
    wfApp.Extensions.Add(sw)
    ```

    ```csharp
    // Add a StringWriter to the extensions. This captures the output
    // from the WriteLine activities so we can display it in the form.
    StringWriter sw = new StringWriter();
    wfApp.Extensions.Add(sw);
    ```

4. Fügen Sie folgenden Handler für das `Completed`-Ereignis hinzu. Sobald ein Workflow erfolgreich abgeschlossen ist, wird die Anzahl der Durchläufe zum Schätzen der Zahl im Statusfenster angezeigt. Bei Beendigung des Workflows werden die Ausnahmeinformationen, die zur Beendigung geführt haben, angezeigt. Am Ende des Handlers wird die `GameOver`-Methode aufgerufen, durch die der abgeschlossene Workflow aus der Workflowliste entfernt wird.

    ```vb
    wfApp.Completed = _
        Sub(e As WorkflowApplicationCompletedEventArgs)
            If e.CompletionState = ActivityInstanceState.Faulted Then
                UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _
                    e.TerminationException.GetType().FullName, _
                    e.TerminationException.Message))
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                UpdateStatus("Workflow Canceled.")
            Else
                Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                UpdateStatus($"Congratulations, you guessed the number in {Turns} turns.")
            End If
            GameOver()
        End Sub
    ```

    ```csharp
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
    {
        if (e.CompletionState == ActivityInstanceState.Faulted)
        {
            UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
        }
        else if (e.CompletionState == ActivityInstanceState.Canceled)
        {
            UpdateStatus("Workflow Canceled.");
        }
        else
        {
            int Turns = Convert.ToInt32(e.Outputs["Turns"]);
            UpdateStatus($"Congratulations, you guessed the number in {Turns} turns.");
        }
        GameOver();
    };
    ```

5. Fügen Sie den folgenden `Aborted`-Handler und `OnUnhandledException`-Handler hinzu. Die `GameOver`-Methode wird nicht vom `Aborted`-Handler aufgerufen, da eine Workflowinstanz beim Abbruch nicht beendet wird. Es besteht keine Möglichkeit, die Instanz zu einem späteren Zeitpunkt fortzusetzen.

    ```vb
    wfApp.Aborted = _
        Sub(e As WorkflowApplicationAbortedEventArgs)
            UpdateStatus($"Workflow Aborted. Exception: {0e.Reason.GetType().FullName}" & vbCrLf & $"{e.Reason.Message}")
        End Sub

    wfApp.OnUnhandledException = _
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}" & vbCrLf & $"{e.UnhandledException.Message}")
            GameOver()
            Return UnhandledExceptionAction.Terminate
        End Function
    ```

    ```csharp
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
    {
        UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
    };

    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
    {
        UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
        GameOver();
        return UnhandledExceptionAction.Terminate;
    };
    ```

6. Fügen Sie den folgenden `PersistableIdle`-Handler hinzu. Dieser Handler ruft die hinzugefügte `StringWriter` Erweiterung ab, extrahiert die Ausgabe aus den `WriteLine`-Aktivitäten und zeigt sie im Statusfenster an.

    ```vb
    wfApp.PersistableIdle = _
        Function(e As WorkflowApplicationIdleEventArgs)
            'Send the current WriteLine outputs to the status window.
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()
            For Each writer In writers
                UpdateStatus(writer.ToString())
            Next
            Return PersistableIdleAction.Unload
        End Function
    ```

    ```csharp
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
    {
        // Send the current WriteLine outputs to the status window.
        var writers = e.GetInstanceExtensions<StringWriter>();
        foreach (var writer in writers)
        {
            UpdateStatus(writer.ToString());
        }
        return PersistableIdleAction.Unload;
    };
    ```

    Die <xref:System.Activities.PersistableIdleAction>-Enumeration besitzt drei Werte: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist> und <xref:System.Activities.PersistableIdleAction.Unload>. <xref:System.Activities.PersistableIdleAction.Persist> bewirkt, dass der Workflow persistent gespeichert wird, jedoch nicht, dass der Workflow entladen wird. <xref:System.Activities.PersistableIdleAction.Unload> bewirkt, dass der Workflow persistent gespeichert und entladen wird.

    Im folgenden Beispiel ist die abgeschlossene `ConfigureWorkflowApplication`-Methode dargestellt.

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)
        'Configure the persistence store.
        wfApp.InstanceStore = store

        'Add a StringWriter to the extensions. This captures the output
        'from the WriteLine activities so we can display it in the form.
        Dim sw As New StringWriter()
        wfApp.Extensions.Add(sw)

        wfApp.Completed = _
            Sub(e As WorkflowApplicationCompletedEventArgs)
                If e.CompletionState = ActivityInstanceState.Faulted Then
                    UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _
                        e.TerminationException.GetType().FullName, _
                        e.TerminationException.Message))
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                    UpdateStatus("Workflow Canceled.")
                Else
                    Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                    UpdateStatus($"Congratulations, you guessed the number in {Turns} turns.")
                End If
                GameOver()
            End Sub

        wfApp.Aborted = _
            Sub(e As WorkflowApplicationAbortedEventArgs)
                UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}" & vbCrLf & $"{e.Reason.Message}")
            End Sub

        wfApp.OnUnhandledException = _
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
                UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}" & vbCrLf & $"{e.UnhandledException.Message}")
                GameOver()
                Return UnhandledExceptionAction.Terminate
            End Function

        wfApp.PersistableIdle = _
            Function(e As WorkflowApplicationIdleEventArgs)
                'Send the current WriteLine outputs to the status window.
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()
                For Each writer In writers
                    UpdateStatus(writer.ToString())
                Next
                Return PersistableIdleAction.Unload
            End Function
    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
        // Configure the persistence store.
        wfApp.InstanceStore = store;

        // Add a StringWriter to the extensions. This captures the output
        // from the WriteLine activities so we can display it in the form.
        StringWriter sw = new StringWriter();
        wfApp.Extensions.Add(sw);

        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
        {
            if (e.CompletionState == ActivityInstanceState.Faulted)
            {
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
            }
            else if (e.CompletionState == ActivityInstanceState.Canceled)
            {
                UpdateStatus("Workflow Canceled.");
            }
            else
            {
                int Turns = Convert.ToInt32(e.Outputs["Turns"]);
                UpdateStatus($"Congratulations, you guessed the number in {Turns} turns.");
            }
            GameOver();
        };

        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
        {
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
        };

        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
        {
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
            GameOver();
            return UnhandledExceptionAction.Terminate;
        };

        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
        {
            // Send the current WriteLine outputs to the status window.
            var writers = e.GetInstanceExtensions<StringWriter>();
            foreach (var writer in writers)
            {
                UpdateStatus(writer.ToString());
            }
            return PersistableIdleAction.Unload;
        };
    }
    ```

### <a name="BKMK_WorkflowVersionMap"></a>So aktivieren Sie das Starten und fortsetzen mehrerer Workflow Typen

Um eine Workflowinstanz fortzusetzen, muss der Host die Workflowdefinition bereitstellen. In diesem Lernprogramm werden drei Workflowtypen verwendet, von denen in den folgenden Schritten mehrere Versionen vorgestellt werden. `WorkflowIdentity` ermöglicht einer Hostanwendung, einer persistenten Workflowinstanz Identifikationsinformationen zuzuordnen. Die Schritte in diesem Abschnitt veranschaulichen das Erstellen einer Hilfsprogrammklasse, die das Zuordnen der Workflowidentität von einer persistenten Workflowinstanz zur entsprechenden Workflowdefinition unterstützt. Weitere Informationen zu `WorkflowIdentity` und Versionsverwaltung finden Sie unter [Verwenden von workflowidentity und Versions](using-workflowidentity-and-versioning.md)Verwaltung.

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflowhost** **", und**wählen Sie **Hinzufügen**, Geben Sie im Feld **Name** `WorkflowVersionMap` ein, und klicken Sie auf **Hinzufügen**.

2. Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Activities
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Activities;
    ```

3. Ersetzen Sie die Deklaration der `WorkflowVersionMap`-Klasse durch die folgende Deklaration.

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            'Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
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

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
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

    `WorkflowVersionMap` enthält drei Workflowidentitäten, die den drei Workflowdefinitionen aus diesem Lernprogramm zugeordnet werden, und wird in den folgenden Abschnitten beim Starten und Fortsetzen von Workflows verwendet.

### <a name="BKMK_StartWorkflow"></a>So starten Sie einen neuen Workflow

1. Fügen Sie einen `Click`-Handler für `NewGame` hinzu. Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, und doppelklicken Sie auf `NewGame`. Ein `NewGame_Click`-Handler wird hinzugefügt, und die Ansicht wechselt zur Codeansicht für das Formular. Sobald der Benutzer auf diese Schaltfläche klickt, wird ein neuer Workflow gestartet.

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click

    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. Fügen Sie dem Click-Handler folgenden Code hinzu. Durch diesen Code wird ein Wörterbuch mit Eingabeargumenten für den Workflow erstellt, die nach Argumentnamen geordnet sind. Das Wörterbuch verfügt über einen Eintrag, der den Bereich der zufällig generierten Zahl enthält, die vom Bereichskombinationsfeld abgerufen wird.

    ```vb
    Dim inputs As New Dictionary(Of String, Object)()
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))
    ```

    ```csharp
    var inputs = new Dictionary<string, object>();
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));
    ```

3. Als Nächstes fügen Sie den folgenden Code hinzu, durch den der Workflow gestartet wird. `WorkflowIdentity` und die Workflowdefinition, die dem Typ des ausgewählten Workflows entspricht, werden mithilfe der `WorkflowVersionMap`-Hilfsklasse abgerufen. Anschließend wird eine neue `WorkflowApplication`-Instanz mithilfe von Workflowdefinition, `WorkflowIdentity` und des Wörterbuchs mit Eingabeargumenten erstellt.

    ```vb
    Dim identity As WorkflowIdentity = Nothing
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
    End Select

    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

    Dim wfApp = New WorkflowApplication(wf, inputs, identity)
    ```

    ```csharp
    WorkflowIdentity identity = null;
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
    };

    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);
    ```

4. Als Nächstes fügen Sie den folgenden Code hinzu, durch den der Workflowliste der Workflow hinzugefügt und die Versionsinformationen des Workflows für das Formular angezeigt werden.

    ```vb
    'Add the workflow to the list and display the version information.
    WorkflowStarting = True
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
    WorkflowVersion.Text = identity.ToString()
    WorkflowStarting = False
    ```

    ```csharp
    // Add the workflow to the list and display the version information.
    WorkflowStarting = true;
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
    WorkflowVersion.Text = identity.ToString();
    WorkflowStarting = false;
    ```

5. Rufen Sie `ConfigureWorkflowApplication` auf, um den Instanzspeicher, die Erweiterungen und die Workflowlebenszyklus-Handler für diese `WorkflowApplication`-Instanz zu konfigurieren.

    ```vb
    'Configure the instance store, extensions, and
    'workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)
    ```

    ```csharp
    // Configure the instance store, extensions, and
    // workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp);
    ```

6. Rufen Sie abschließend `Run` auf.

    ```vb
    'Start the workflow.
    wfApp.Run()
    ```

    ```csharp
    // Start the workflow.
    wfApp.Run();
    ```

     Im folgenden Beispiel ist der abgeschlossene `NewGame_Click`-Handler dargestellt.

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click
        'Start a new workflow.
        Dim inputs As New Dictionary(Of String, Object)()
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))

        Dim identity As WorkflowIdentity = Nothing
        Select Case WorkflowType.SelectedItem.ToString()
            Case "SequentialNumberGuessWorkflow"
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity

            Case "StateMachineNumberGuessWorkflow"
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

            Case "FlowchartNumberGuessWorkflow"
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
        End Select

        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

        Dim wfApp = New WorkflowApplication(wf, inputs, identity)

        'Add the workflow to the list and display the version information.
        WorkflowStarting = True
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
        WorkflowVersion.Text = identity.ToString()
        WorkflowStarting = False

        'Configure the instance store, extensions, and
        'workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp)

        'Start the workflow.
        wfApp.Run()
    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {
        var inputs = new Dictionary<string, object>();
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));

        WorkflowIdentity identity = null;
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
        };

        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

        WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);

        // Add the workflow to the list and display the version information.
        WorkflowStarting = true;
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
        WorkflowVersion.Text = identity.ToString();
        WorkflowStarting = false;

        // Configure the instance store, extensions, and
        // workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp);

        // Start the workflow.
        wfApp.Run();
    }
    ```

### <a name="BKMK_ResumeWorkflow"></a>So setzen Sie einen Workflow fort

1. Fügen Sie einen `Click`-Handler für `EnterGuess` hinzu. Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, und doppelklicken Sie auf `EnterGuess`. Sobald der Benutzer auf diese Schaltfläche klickt, wird ein Workflow fortgesetzt.

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click

    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {

    }
    ```

2. Fügen Sie den folgenden Code hinzu, um sicherzustellen, dass ein Workflow in der Workflowliste ausgewählt ist und dass der Schätzwert des Benutzers gültig ist.

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim userGuess As Integer
    If Not Int32.TryParse(Guess.Text, userGuess) Then
        MessageBox.Show("Please enter an integer.")
        Guess.SelectAll()
        Guess.Focus()
        Return
    End If
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    int guess;
    if (!Int32.TryParse(Guess.Text, out guess))
    {
        MessageBox.Show("Please enter an integer.");
        Guess.SelectAll();
        Guess.Focus();
        return;
    }
    ```

3. Rufen Sie anschließend die `WorkflowApplicationInstance` der resistenten Workflowinstanz ab. `WorkflowApplicationInstance` stellt eine persistente Workflowinstanz dar, die noch keiner Workflowdefinition zugeordnet wurde. Die `DefinitionIdentity` von `WorkflowApplicationInstance` enthält die `WorkflowIdentity` der persistenten Workflowinstanz. In diesem Lernprogramm wird die `WorkflowVersionMap` Hilfsklasse verwendet, um `WorkflowIdentity` der richtigen Workflowdefinition zuzuordnen. Beim Abrufen der Workflowdefinition wird anhand der richtigen Workflowdefinition eine `WorkflowApplication` erstellt.

    ```vb
    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    'Use the persisted WorkflowIdentity to retrieve the correct workflow
    'definition from the dictionary.
    Dim wf As Activity = _
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    'Associate the WorkflowApplication with the correct definition
    Dim wfApp As WorkflowApplication = _
        New WorkflowApplication(wf, instance.DefinitionIdentity)
    ```

    ```csharp
    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf =
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    WorkflowApplication wfApp =
        new WorkflowApplication(wf, instance.DefinitionIdentity);
    ```

4. Sobald `WorkflowApplication` erstellt wird, konfigurieren Sie den Instanzspeicher, die Handler des Workflowlebenszyklus und die Erweiterungen, indem Sie `ConfigureWorkflowApplication` aufrufen. Diese Schritte müssen bei jeder Erstellung einer neuen `WorkflowApplication` ausgeführt werden, und zwar bevor die Workflowinstanz in `WorkflowApplication` geladen wird. Nachdem der Workflow geladen wurde, wird er mit der Schätzung des Benutzers fortgesetzt.

    ```vb
    'Configure the extensions and lifecycle handlers.
    'Do this before the instance is loaded. Once the instance is
    'loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp)

    'Load the workflow.
    wfApp.Load(instance)

    'Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", userGuess)
    ```

    ```csharp
    // Configure the extensions and lifecycle handlers.
    // Do this before the instance is loaded. Once the instance is
    // loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", guess);
    ```

5. Löschen Sie abschließend den Eintrag im Textfeld, und bereiten Sie das Formular für die Eingabe eines anderen Schätzwerts vor.

    ```vb
    'Clear the Guess textbox.
    Guess.Clear()
    Guess.Focus()
    ```

    ```csharp
    // Clear the Guess textbox.
    Guess.Clear();
    Guess.Focus();
    ```

    Im folgenden Beispiel ist der abgeschlossene `EnterGuess_Click`-Handler dargestellt.

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click
        If WorkflowInstanceId = Guid.Empty Then
            MessageBox.Show("Please select a workflow.")
            Return
        End If

        Dim userGuess As Integer
        If Not Int32.TryParse(Guess.Text, userGuess) Then
            MessageBox.Show("Please enter an integer.")
            Guess.SelectAll()
            Guess.Focus()
            Return
        End If

        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        'Use the persisted WorkflowIdentity to retrieve the correct workflow
        'definition from the dictionary.
        Dim wf As Activity = _
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

        'Associate the WorkflowApplication with the correct definition
        Dim wfApp As WorkflowApplication = _
            New WorkflowApplication(wf, instance.DefinitionIdentity)

        'Configure the extensions and lifecycle handlers.
        'Do this before the instance is loaded. Once the instance is
        'loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp)

        'Load the workflow.
        wfApp.Load(instance)

        'Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", userGuess)

        'Clear the Guess textbox.
        Guess.Clear()
        Guess.Focus()
    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {
        if (WorkflowInstanceId == Guid.Empty)
        {
            MessageBox.Show("Please select a workflow.");
            return;
        }

        int guess;
        if (!Int32.TryParse(Guess.Text, out guess))
        {
            MessageBox.Show("Please enter an integer.");
            Guess.SelectAll();
            Guess.Focus();
            return;
        }

        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);

        // Use the persisted WorkflowIdentity to retrieve the correct workflow
        // definition from the dictionary.
        Activity wf =
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

        // Associate the WorkflowApplication with the correct definition
        WorkflowApplication wfApp =
            new WorkflowApplication(wf, instance.DefinitionIdentity);

        // Configure the extensions and lifecycle handlers.
        // Do this before the instance is loaded. Once the instance is
        // loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp);

        // Load the workflow.
        wfApp.Load(instance);

        // Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", guess);

        // Clear the Guess textbox.
        Guess.Clear();
        Guess.Focus();
    }
    ```

### <a name="BKMK_TerminateWorkflow"></a>So beenden Sie einen Workflow

1. Fügen Sie einen `Click`-Handler für `QuitGame` hinzu. Um den Handler hinzuzufügen, wechseln Sie zur **Entwurfs Ansicht** für das Formular, und doppelklicken Sie auf `QuitGame`. Sobald der Benutzer auf diese Schaltfläche klickt, wird der aktuell ausgewählte Workflow beendet.

    ```vb
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click

    End Sub
    ```

    ```csharp
    private void QuitGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. Fügen Sie dem `QuitGame_Click`-Handler folgenden Code hinzu. Durch diesen Code wird zuerst überprüft, ob in der Workflowliste ein Workflow ausgewählt ist. Anschließend lädt er die persistente Instanz in eine `WorkflowApplicationInstance`, ermittelt anhand von `DefinitionIdentity` die richtige Workflowdefinition und initialisiert die `WorkflowApplication`. Als Nächstes werden die Erweiterungen und die Workflowlebenszyklus-Handler mit einem Aufruf von `ConfigureWorkflowApplication` konfiguriert. Sobald `WorkflowApplication` konfiguriert ist, wird sie geladen, und `Terminate` wird aufgerufen.

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    'Use the persisted WorkflowIdentity to retrieve the correct workflow
    'definition from the dictionary.
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    'Associate the WorkflowApplication with the correct definition.
    Dim wfApp As WorkflowApplication = _
        New WorkflowApplication(wf, instance.DefinitionIdentity)

    'Configure the extensions and lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)

    'Load the workflow.
    wfApp.Load(instance)

    'Terminate the workflow.
    wfApp.Terminate("User resigns.")
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    WorkflowApplication wfApp =
        new WorkflowApplication(wf, instance.DefinitionIdentity);

    // Configure the extensions and lifecycle handlers
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Terminate the workflow.
    wfApp.Terminate("User resigns.");
    ```

### <a name="BKMK_BuildAndRun"></a> So erstellen und führen Sie die Anwendung aus

1. Doppelklicken Sie in **Projektmappen-Explorer** auf **Program.cs** (oder **Module1. vb**), um den Code anzuzeigen.

2. Fügen Sie die folgende `using`-Anweisung (oder `Imports`-Anweisung) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.

    ```vb
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Windows.Forms;
    ```

3. Entfernen Sie den vorhandenen Workflow-Hostingcode, oder kommentieren Sie ihn aus Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md)aus, und ersetzen Sie ihn durch den folgenden Code.

    ```vb
    Sub Main()
        Application.EnableVisualStyles()
        Application.Run(New WorkflowHostForm())
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        Application.EnableVisualStyles();
        Application.Run(new WorkflowHostForm());
    }
    ```

4. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflow** Message", und wählen Sie **Eigenschaften**aus. Geben Sie auf der Registerkarte **Anwendung** die **Windows-Anwendung** für den **Ausgabetyp**an. Dieser Schritt ist optional, wird er jedoch nicht ausgeführt, wird zusätzlich zum Formular das Konsolenfenster angezeigt.

5. Drücken Sie STRG+UMSCHALT+B, um die Anwendung zu erstellen.

6. Stellen Sie sicher, dass " **numguess Workflowhost** " als Start Anwendung festgelegt ist, und drücken Sie STRG + F5, um die Anwendung zu starten.

7. Wählen Sie einen Bereich für das Ratespiel und den Typ des zu startenden Workflows aus, und klicken Sie auf **Neues Spiel**. Geben Sie im Feld für die **Vermutung** einen Schätz Text ein, und klicken Sie auf " **Gehe** zu übermitteln Beachten Sie, dass die Ausgabe der `WriteLine`-Aktivitäten auf dem Formular angezeigt wird.

8. Starten Sie mehrere Workflows mit verschiedenen Workflow Typen und Zahlenbereichen, geben Sie einige Schätzwerte ein, und wechseln Sie zwischen den Workflows, indem Sie Sie aus der Liste der **workflowinstanzkennung**

    Wenn Sie zu einem neuen Workflow wechseln, werden die vorherigen Schätzwerte und der Workflowverlauf nicht im Statusfenster angezeigt. Der Status ist nicht verfügbar, weil er nicht erfasst wurde und nirgends gespeichert ist. Im nächsten Schritt des Tutorials, Gewusst [wie: Erstellen eines benutzerdefinierten Überwachungs Teilnehmers](how-to-create-a-custom-tracking-participant.md), erstellen Sie einen benutzerdefinierten nach Verfolgungs Teilnehmer, der diese Informationen speichert.
