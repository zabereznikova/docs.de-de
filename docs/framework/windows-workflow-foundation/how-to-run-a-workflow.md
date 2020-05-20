---
title: 'Vorgehensweise: Ausführen eines Workflows'
description: In diesem Artikel erfahren Sie, wie Sie einen Workflow Host erstellen und den Workflow ausführen, der in einem vorherigen Artikel dieser Windows Workflow Foundation tutorialreihe definiert wurde.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 86062dd5147e6e354833928fd98bd1f6b5de9114
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421500"
---
# <a name="how-to-run-a-workflow"></a>Vorgehensweise: Ausführen eines Workflows
Dieses Thema ist eine Fortsetzung des Tutorials „Windows Workflow Foundation: Erste Schritte“. Hierin wird beschrieben, wie Sie einen Workflowhost erstellen und den im vorherigen Thema [How to: Create a Workflow](how-to-create-a-workflow.md) definierten Workflow ausführen.

> [!NOTE]
> Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab. Um dieses Thema verwenden zu können, müssen Sie zuerst [How to: Create an Activity](how-to-create-an-activity.md) und [How to: Create a Workflow](how-to-create-a-workflow.md)durcharbeiten und abschließen.

> [!NOTE]
> Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.  
  
### <a name="to-create-the-workflow-host-project"></a>So erstellen Sie das Workflowhostprojekt  
  
1. Öffnen Sie die Projekt Mappe aus dem vorherigen Thema Gewusst [wie: Erstellen einer Aktivität](how-to-create-an-activity.md) mithilfe von Visual Studio 2012.  
  
2. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **WF45GettingStartedTutorial** , zeigen Sie auf **Hinzufügen**, und wählen Sie **Neues Projekt**aus.  
  
    > [!TIP]
    > Wird das Fenster **Projektmappen-Explorer** nicht angezeigt, wählen Sie **Projektmappen-Explorer** im Menü **Ansicht** aus.

3. Wählen Sie im Knoten **Installiert** die Option **Visual C#** und anschließend **Workflow** (oder **Visual Basic**, **Workflow**) aus.

    > [!NOTE]
    > Abhängig davon, welche Programmiersprache als primäre Sprache in Visual Studio konfiguriert ist, kann sich der Knoten **Visual C#** oder **Visual Basic** unter dem Knoten **Andere Sprachen** im Knoten **Installiert** befinden.

     Stellen Sie sicher, dass **.NET Framework 4.5** in der Dropdownliste für die .NET Framework-Version ausgewählt ist. Wählen Sie in der Liste **Workflow** die Option **Konsolenanwendung für Workflows** aus. Geben Sie im Feld `NumberGuessWorkflowHost` Name **die Bezeichnung** ein, und klicken Sie auf **OK**. Auf diese Weise wird eine Start-Workflowanwendung mit grundlegender Unterstützung von Workflowhosting erstellt. Dieser grundlegende Hostingcode wird geändert und zum Ausführen der Workflowanwendung verwendet.

4. Klicken Sie im Projektmappen-Explorer **** mit der rechten Maustaste auf das neu hinzugefügte Projekt **NumberGuessWorkflowHost** , und wählen Sie **Verweis hinzufügen**aus. Wählen Sie in der Liste **Verweis hinzufügen** den Eintrag **Projektmappe** aus, aktivieren Sie das Kontrollkästchen neben **NumberGuessWorkflowActivities**, und klicken Sie auf **OK**.

5. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Workflow1.xaml** , und wählen Sie **Löschen**aus. Klicken Sie zum Bestätigen auf **OK**.

### <a name="to-modify-the-workflow-hosting-code"></a>So ändern Sie den Code zum Hosten von Workflows

1. Doppelklicken Sie im **Projektmappen-Explorer** auf **Program.cs** oder **Module1.vb** , um den Code anzuzeigen.

    > [!TIP]
    > Wird das Fenster **Projektmappen-Explorer** nicht angezeigt, wählen Sie **Projektmappen-Explorer** im Menü **Ansicht** aus.

     Da dieses Projekt mit der Vorlage **Konsolenanwendung für Workflows** erstellt wurde, enthält **Program.cs** oder **Module1.vb** den folgenden grundlegenden Code zum Hosten von Workflows.

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

     Der generierte Hostingcode verwendet <xref:System.Activities.WorkflowInvoker>. <xref:System.Activities.WorkflowInvoker> stellt eine einfache Möglichkeit zum Aufrufen eines Workflows bereit, so als handelte es sich um einen Methodenaufruf, und kann nur für Workflows verwendet werden, die keine Persistenz verwenden. <xref:System.Activities.WorkflowApplication> bietet ein umfangreicheres Modell zum Ausführen von Workflows, die Benachrichtigungen über Lebenszyklusereignisse, Ausführungssteuerung, Wiederaufnahme von Lesezeichen und Persistenz enthalten. In diesem Beispiel werden Lesezeichen verwendet, und <xref:System.Activities.WorkflowApplication> wird zum Hosten des Workflows genutzt. Fügen Sie die folgende `using` - oder **Imports** -Anweisung am Anfang von **Program.cs** oder **Module1.vb** unter der vorhandenen **using** - oder **Imports** -Anweisung hinzu.

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     Ersetzen Sie die Codezeilen, in denen <xref:System.Activities.WorkflowInvoker> mit dem folgenden grundlegenden <xref:System.Activities.WorkflowApplication> -Hostingcode verwendet wird. In diesem Beispielhostingcode werden die grundlegenden Schritte zum Hosten und das Aufrufen eines Workflows veranschaulicht, das Beispiel enthält jedoch noch nicht die Funktionalität zum erfolgreichen Ausführen des Workflows aus diesem Thema. In den folgenden Schritten wird der grundlegende Code geändert, und es werden zusätzliche Funktionen hinzugefügt, bis die Anwendung abgeschlossen wurde.

    > [!NOTE]
    > Ersetzen Sie `Workflow1` in diesen Beispielen durch `FlowchartNumberGuessWorkflow`, und wählen Sie `SequentialNumberGuessWorkflow`, und wählen Sie or `StateMachineNumberGuessWorkflow`, und wählen Sie depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) abgeschlossen haben. Wenn Sie `Workflow1` nicht ersetzen, erhalten Sie Buildfehler, wenn Sie versuchen, den Workflow zu erstellen oder auszuführen.

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     In diesem Code wird ein <xref:System.Activities.WorkflowApplication>-Element erstellt, es werden drei Lebenszyklusereignisse des Workflows abonniert, der Workflow wird per Aufruf von <xref:System.Activities.WorkflowApplication.Run%2A>gestartet, und dann wird auf den Abschluss des Workflows gewartet. Nach Abschluss des Workflows wird <xref:System.Threading.AutoResetEvent> festgelegt, und die Hostanwendung wird abgeschlossen.

### <a name="to-set-input-arguments-of-a-workflow"></a>So legen Sie die Eingabeargumente eines Workflows fest

1. Fügen Sie oben in der Datei **Program.cs** oder **Module1.vb** unter den vorhandenen `using` - oder `Imports` -Anweisung die folgende Anweisung hinzu.

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. Ersetzen Sie die Codezeile, die das neue <xref:System.Activities.WorkflowApplication> -Element erstellt, durch den folgenden Code, der ein Wörterbuch mit Parametern erstellt und dieses nach seiner Erstellung an den Workflow übergibt.

    > [!NOTE]
    > Ersetzen Sie `Workflow1` in diesen Beispielen durch `FlowchartNumberGuessWorkflow`, und wählen Sie `SequentialNumberGuessWorkflow`, und wählen Sie or `StateMachineNumberGuessWorkflow`, und wählen Sie depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) abgeschlossen haben. Wenn Sie `Workflow1` nicht ersetzen, erhalten Sie Buildfehler, wenn Sie versuchen, den Workflow zu erstellen oder auszuführen.

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     Dieses Wörterbuch enthält ein Element mit dem Schlüssel `MaxNumber`. Schlüssel im Eingabewörterbuch entsprechen Eingabeargumenten in der Stammaktivität des Workflows. `MaxNumber` wird vom Workflow verwendet, um die Obergrenze für die zufällig generierte Zahl zu bestimmen.

### <a name="to-retrieve-output-arguments-of-a-workflow"></a>So rufen Sie die Ausgabeargumente eines Workflows ab

1. Ändern Sie den <xref:System.Activities.WorkflowApplication.Completed%2A> -Handler, um die Anzahl der vom Workflow verwendeten Durchgänge (turns) abzurufen und anzuzeigen.

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a>So nehmen Sie ein Lesezeichen wieder auf

1. Fügen Sie oben in der `Main` -Methode direkt nach der bestehenden <xref:System.Threading.AutoResetEvent> -Deklaration den folgenden Code hinzu.

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. Fügen Sie direkt unterhalb der drei bestehenden Lebenszyklushandler des Workflows im Abschnitt <xref:System.Activities.WorkflowApplication.Idle%2A> den folgenden `Main`-Handler hinzu.

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     Jedes Mal, wenn der Workflow in den Leerlauf wechselt und auf die nächste Vermutung wartet, wird dieser Handler aufgerufen, und der `idleAction` <xref:System.Threading.AutoResetEvent> wird festgelegt. Der Code im folgenden Schritt verwendet `idleEvent` und `syncEvent` , um zu ermitteln, ob der Workflow auf den nächsten Lösungsversuch wartet oder abgeschlossen ist.

    > [!NOTE]
    > In diesem Beispiel verwendet die Hostanwendung AutoReset-Ereignisse in den Handlern <xref:System.Activities.WorkflowApplication.Completed%2A> und <xref:System.Activities.WorkflowApplication.Idle%2A> , um die Hostanwendung mit dem Status des Workflows zu synchronisieren. Das Blockieren und das Warten auf den Eintritt des Workflows in den Leerlaufzustand ist nicht erforderlich, bevor ein Lesezeichen wiederaufgenommen wird. In diesem Beispiel sind die Synchronisierungsereignisse jedoch erforderlich, damit der Host weiß, ob der Workflow abgeschlossen ist oder ob dieser mithilfe von <xref:System.Activities.Bookmark>auf weitere Benutzereingaben wartet. Weitere Informationen finden Sie unter [Lesezeichen](bookmarks.md).

3. Entfernen Sie den Aufruf von `WaitOne`, und ersetzen Sie diesen durch Code zum Erfassen der Eingabe des Benutzers und zum Wiederaufnehmen von <xref:System.Activities.Bookmark>.

     Entfernen Sie die folgende Codezeile.

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     Ersetzen Sie diese durch den folgenden Beispielcode.

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="to-build-and-run-the-application"></a><a name="BKMK_ToRunTheApplication"></a>So erstellen Sie die Anwendung und führen Sie aus

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **NumberGuessWorkflowHost** , und wählen Sie **Als Startprojekt festlegen**aus.

2. Drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen. Versuchen Sie, die Zahl in möglichst wenigen Durchgängen zu erraten.

     Um die Anwendung mit einem der anderen Workflowtypen auszuprobieren, ersetzen Sie `Workflow1` im Code, durch den <xref:System.Activities.WorkflowApplication> erstellt wird, durch `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`oder `StateMachineNumberGuessWorkflow`, je nachdem, welcher Workflowtyp gewünscht ist.

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     Eine Anleitung dazu, wie Sie einer Workflowanwendung Persistenz hinzufügen, finden Sie im nächsten Thema: [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).

## <a name="example"></a>Beispiel
 Das folgende Beispiel ist die vollständige Codeauflistung für die `Main` -Methode.

> [!NOTE]
> Ersetzen Sie `Workflow1` in diesen Beispielen durch `FlowchartNumberGuessWorkflow`, und wählen Sie `SequentialNumberGuessWorkflow`, und wählen Sie or `StateMachineNumberGuessWorkflow`, und wählen Sie depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) abgeschlossen haben. Wenn Sie `Workflow1` nicht ersetzen, erhalten Sie Buildfehler, wenn Sie versuchen, den Workflow zu erstellen oder auszuführen.

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [Windows Workflow Foundation-Programmierung](programming.md)
- [Tutorial zu den ersten Schritten](getting-started-tutorial.md)
- [Vorgehensweise: Erstellen eines Workflows](how-to-create-a-workflow.md)
- [Vorgehensweise: Erstellen und Ausführen eines Workflows mit langer Laufzeit](how-to-create-and-run-a-long-running-workflow.md)
- [Warten auf Eingabe in einem Workflow](waiting-for-input-in-a-workflow.md)
- [Hosten von Workflows](hosting-workflows.md)
