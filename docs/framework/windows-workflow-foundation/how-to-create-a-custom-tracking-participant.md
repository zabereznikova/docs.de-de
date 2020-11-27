---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten Nachverfolgungskomponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b612c7e-2381-4a7c-b07a-77030415f2a3
ms.openlocfilehash: 5f00997b059d7ea6f6ac6fb6d7bd83e4515ac02a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275800"
---
# <a name="how-to-create-a-custom-tracking-participant"></a>Vorgehensweise: Erstellen einer benutzerdefinierten Nachverfolgungskomponente

Die Workflownachverfolgung gewährt Einblick in den Status der Workflowausführung. Die Workflowlaufzeit gibt Überwachungsdatensätze aus, die Ereignisse im Workflow- und Aktivitätslebenszyklus, Lesezeichenwiederaufnahmen und Fehler beschreiben. Diese Überwachungsdatensätze werden von den Überwachungsteilnehmern genutzt. Windows Workflow Foundation (WF) umfasst einen Standard-nach Verfolgungs Teilnehmer, der nach Verfolgungs Datensätze als ETW-Ereignisse (Ereignis Ablauf Verfolgung für Windows) schreibt. Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben. In diesem Schritt des Lernprogramms wird beschrieben, wie ein benutzerdefinierter Überwachungsteilnehmer und ein Nachverfolgungsprofil erstellt werden, die die Ausgabe von `WriteLine`-Aktivitäten aufzeichnen, damit sie dem Benutzer angezeigt werden können.  
  
> [!NOTE]
> Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab. Um dieses Thema abzuschließen, müssen Sie die vorherigen Themen abgeschlossen haben. Informationen zum Herunterladen einer abgeschlossenen Version oder zum Anzeigen einer exemplarischen Vorgehensweise für das Tutorial finden Sie unter [Windows Workflow Foundation (WF45)-Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)für die ersten Schritte.  
  
## <a name="to-create-the-custom-tracking-participant"></a>So erstellen Sie den benutzerdefinierten Überwachungsteilnehmer  
  
1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf " **numguess Workflowhost** **", und** wählen Sie **Hinzufügen**, Geben `StatusTrackingParticipant` Sie in das Feld **Name** ein, und klicken Sie auf **Hinzufügen**.  
  
2. Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3. Ändern Sie `StatusTrackingParticipant`-Klasse so, dass sie von `TrackingParticipant` erbt.  
  
    ```vb  
    Public Class StatusTrackingParticipant  
        Inherits TrackingParticipant  
  
    End Class  
    ```  
  
    ```csharp  
    class StatusTrackingParticipant : TrackingParticipant  
    {  
    }  
    ```  
  
4. Fügen Sie die folgende `Track`-Methodenüberschreibung hinzu. Es gibt mehrere Typen von Überwachungsdatensätzen. Nur die Ausgabe der `WriteLine`-Aktivitäten, die in den Überwachungsdatensätzen für Aktivitäten enthalten sind, ist für uns interessant. Wenn `TrackingRecord` ein `ActivityTrackingRecord` für eine `WriteLine`-Aktivität ist, wird der `Text` von `WriteLine` an eine Datei angefügt, die nach der `InstanceId` des Workflows benannt ist. In diesem Lernprogramm wird die Datei im aktuellen Ordner der Hostanwendung gespeichert.  
  
    ```vb  
    Protected Overrides Sub Track(record As TrackingRecord, timeout As TimeSpan)  
        Dim asr As ActivityStateRecord = TryCast(record, ActivityStateRecord)  
  
        If Not asr Is Nothing Then  
            If asr.State = ActivityStates.Executing And _  
            asr.Activity.TypeName = "System.Activities.Statements.WriteLine" Then  
  
                'Append the WriteLine output to the tracking  
                'file for this instance.  
                Using writer As StreamWriter = File.AppendText(record.InstanceId.ToString())  
                    writer.WriteLine(asr.Arguments("Text"))  
                    writer.Close()  
                End Using  
            End If  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        ActivityStateRecord asr = record as ActivityStateRecord;  
  
        if (asr != null)  
        {  
            if (asr.State == ActivityStates.Executing &&  
                asr.Activity.TypeName == "System.Activities.Statements.WriteLine")  
            {  
                // Append the WriteLine output to the tracking  
                // file for this instance  
                using (StreamWriter writer = File.AppendText(record.InstanceId.ToString()))  
                {  
                    writer.WriteLine(asr.Arguments["Text"]);  
                    writer.Close();  
                }  
            }  
        }  
    }  
    ```  
  
     Wenn kein Nachverfolgungsprofil angegeben ist, wird das standardmäßige Nachverfolgungsprofil verwendet. Wenn das standardmäßige Nachverfolgungsprofil verwendet wird, werden Überwachungsdatensätze für alle `ActivityStates` ausgegeben. Da Text während des Lebenszyklus der `WriteLine`-Aktivität nur einmal aufgezeichnet werden muss, extrahieren wir nur den Text des `ActivityStates.Executing`-Zustands. Wenn [Sie in das Überwachungs Profil erstellen und den Überwachungs Teilnehmer registrieren möchten](#to-create-the-tracking-profile-and-register-the-tracking-participant), wird ein Verfolgungs Profil erstellt, das angibt, dass nur nach `WriteLine` `ActivityStates.Executing` Verfolgungs Datensätze ausgegeben werden.  
  
## <a name="to-create-the-tracking-profile-and-register-the-tracking-participant"></a>So erstellen Sie das Nachverfolgungsprofil und registrieren den Überwachungsteilnehmer  
  
1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **workflowhostform** , und wählen Sie **Code anzeigen** aus.  
  
2. Fügen Sie die folgende `using`-Anweisung (oder `Imports`-Anweisung) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3. Fügen Sie `ConfigureWorkflowApplication` den folgenden Code unmittelbar nach dem Code, durch den `StringWriter` den Workflowerweiterungen hinzugefügt wird, und vor den Handlern des Workflowlebenszyklus hinzu.  
  
    ```vb  
    'Add the custom tracking participant with a tracking profile  
    'that only emits tracking records for WriteLine activities.  
    Dim query As New ActivityStateQuery()  
    query.ActivityName = "WriteLine"  
    query.States.Add(ActivityStates.Executing)  
    query.Arguments.Add("Text")  
  
    Dim profile As New TrackingProfile()  
    profile.Queries.Add(query)  
  
    Dim stp As New StatusTrackingParticipant()  
    stp.TrackingProfile = profile  
  
    wfApp.Extensions.Add(stp)  
    ```  
  
    ```csharp  
    // Add the custom tracking participant with a tracking profile  
    // that only emits tracking records for WriteLine activities.  
    StatusTrackingParticipant stp = new StatusTrackingParticipant  
    {  
        TrackingProfile = new TrackingProfile  
        {  
            Queries =
            {  
                new ActivityStateQuery  
                {  
                    ActivityName = "WriteLine",  
                    States = { ActivityStates.Executing },  
                    Arguments = { "Text" }  
                }  
            }  
        }  
    };  
  
    wfApp.Extensions.Add(stp);  
    ```  
  
     Dieses Nachverfolgungsprofil gibt an, dass nur Zustandsdatensätze für `WriteLine`-Aktivitäten im `Executing`-Zustand an den benutzerdefinierten Überwachungsteilnehmer ausgegeben werden.  
  
     Nachdem der Code hinzugefügt wurde, sieht der Anfang von `ConfigureWorkflowApplication` wie im folgenden Beispiel aus.  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        'Add the custom tracking participant with a tracking profile  
        'that only emits tracking records for WriteLine activities.  
        Dim query As New ActivityStateQuery()  
        query.ActivityName = "WriteLine"  
        query.States.Add(ActivityStates.Executing)  
        query.Arguments.Add("Text")  
  
        Dim profile As New TrackingProfile()  
        profile.Queries.Add(query)  
  
        Dim stp As New StatusTrackingParticipant()  
        stp.TrackingProfile = profile  
  
        wfApp.Extensions.Add(stp)  
  
        'Workflow lifecycle handlers...  
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
  
        // Add the custom tracking participant with a tracking profile  
        // that only emits tracking records for WriteLine activities.  
        StatusTrackingParticipant stp = new StatusTrackingParticipant  
        {  
            TrackingProfile = new TrackingProfile  
            {  
                Queries =
                {  
                    new ActivityStateQuery  
                    {  
                        ActivityName = "WriteLine",  
                        States = { ActivityStates.Executing },  
                        Arguments = { "Text" }  
                    }  
                }  
            }  
        };  
  
        wfApp.Extensions.Add(stp);  
  
        // Workflow lifecycle handlers...  
    ```  
  
## <a name="to-display-the-tracking-information"></a>So zeigen Sie die Nachverfolgungsinformationen an  
  
1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **workflowhostform** , und wählen Sie **Code anzeigen** aus.  
  
2. Fügen Sie im `InstanceId_SelectedIndexChanged`-Handler den folgenden Code unmittelbar nach dem Code hinzu, durch den das Statusfenster gelöscht wird.  
  
    ```vb  
    'If there is tracking data for this workflow, display it  
    'in the status window.  
    If File.Exists(WorkflowInstanceId.ToString()) Then  
        Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
        UpdateStatus(status)  
    End If  
    ```  
  
    ```csharp  
    // If there is tracking data for this workflow, display it  
    // in the status window.  
    if (File.Exists(WorkflowInstanceId.ToString()))  
    {  
        string status = File.ReadAllText(WorkflowInstanceId.ToString());  
        UpdateStatus(status);  
    }  
    ```  
  
     Wenn ein neuer Workflow in der Workflowliste ausgewählt wird, werden die Überwachungsdatensätze für diesen Workflow geladen und im Statusfenster angezeigt. Im folgenden Beispiel ist der abgeschlossene `InstanceId_SelectedIndexChanged`-Handler dargestellt.  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
        If InstanceId.SelectedIndex = -1 Then  
            Return  
        End If  
  
        'Clear the status window.  
        WorkflowStatus.Clear()  
  
        'If there is tracking data for this workflow, display it  
        'in the status window.  
        If File.Exists(WorkflowInstanceId.ToString()) Then  
            Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
            UpdateStatus(status)  
        End If  
  
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
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
        if (InstanceId.SelectedIndex == -1)  
        {  
            return;  
        }  
  
        // Clear the status window.  
        WorkflowStatus.Clear();  
  
        // If there is tracking data for this workflow, display it  
        // in the status window.  
        if (File.Exists(WorkflowInstanceId.ToString()))  
        {  
            string status = File.ReadAllText(WorkflowInstanceId.ToString());  
            UpdateStatus(status);  
        }  
  
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
    }  
    ```  
  
## <a name="to-build-and-run-the-application"></a>So erstellen Sie die Anwendung und führen sie aus  
  
1. Drücken Sie STRG+UMSCHALT+B, um die Anwendung zu erstellen.  
  
2. Drücken Sie STRG+F5, um die Anwendung zu starten.  
  
3. Wählen Sie einen Bereich für das Ratespiel und den Typ des zu startenden Workflows aus, und klicken Sie auf **Neues Spiel**. Geben Sie im Feld für die **Vermutung** einen Schätz Text ein, und klicken Sie auf " **Gehe** zu übermitteln Beachten Sie, dass der Status des Workflows im Statusfenster angezeigt wird. Diese Ausgabe wird von den `WriteLine`-Aktivitäten aufgezeichnet. Wechseln Sie zu einem anderen Workflow, indem Sie einen aus dem Kombinations Feld **Workflow Instanz-ID** auswählen. Beachten Sie, dass der Status des aktuellen Workflows entfernt wurde. Wechseln Sie zurück zum vorherigen Workflow. Wie im folgenden Beispiel dargestellt, wird der Status wiederhergestellt.  
  
    > [!NOTE]
    > Wenn Sie zu einem Workflow wechseln, der vor dem Aktivieren der Nachverfolgung gestartet wurde, wird kein Status angezeigt. Wenn Sie zusätzliche Schätzwerte eingeben, wird deren Status jedoch gespeichert, da die Nachverfolgung jetzt aktiviert ist.  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```

    > [!NOTE]
    > Diese Informationen sind hilfreich, um den Bereich der Zufallszahl bestimmen. Sie sagen jedoch nichts darüber aus, welche Schätzwerte zuvor angegeben wurden. Diese Informationen finden Sie im nächsten Schritt, Vorgehens [Weise: paralleles Hosten mehrerer Workflow Versionen](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).

    Notieren Sie sich die Workflowinstanz-ID, und durchlaufen Sie das Spiel bis zum Ende.
  
4. Öffnen Sie Windows-Explorer, und navigieren Sie zum Ordner " **numguess workflowhost\bin\debug** " (bzw. " **bin\Release** ", abhängig von den Projekteinstellungen). Zusätzlich zu den ausführbaren Projektdateien sehen Sie jetzt auch Dateien mit GUID-Dateinamen. Identifizieren Sie die Datei, die der Workflowinstanz-ID des im vorherigen Schritt abgeschlossenen Workflows entspricht, und öffnen Sie sie im Editor. Die Nachverfolgungsinformationen enthalten in etwa die folgenden Angaben.  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```

    Abgesehen davon, dass Schätzwerte des Benutzers fehlen, enthalten diese Nachverfolgungsinformationen auch keine Angaben über den endgültigen Schätzwert des Workflows. Das liegt daran, dass die Nachverfolgungsinformationen nur die `WriteLine`-Ausgabe des Workflows enthalten und die abschließend angezeigte Meldung nach Abschluss des Workflows vom `Completed`-Handler ausgegeben wird. Im nächsten Schritt des Tutorials, Gewusst [wie: Hosten mehrerer Versionen eines Workflows nebeneinander](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), werden die vorhandenen Aktivitäten so geändert, `WriteLine` dass die Schätzwerte des Benutzers angezeigt werden, und es wird eine zusätzliche `WriteLine` Aktivität hinzugefügt, die die Endergebnisse anzeigt. Nachdem diese Änderungen integriert wurden, wird [durch Gewusst wie: das parallele Hosten mehrerer Versionen eines Workflows](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) veranschaulicht, wie mehrere Versionen eines Workflows gleichzeitig gehostet werden.
