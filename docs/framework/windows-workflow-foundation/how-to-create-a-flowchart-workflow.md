---
title: "Vorgehensweise: Erstellen eines Flussdiagrammworkflows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vorgehensweise: Erstellen eines Flussdiagrammworkflows
Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.In diesem Thema wird Schritt für Schritt die Erstellung eines Workflows erläutert, der integrierte Aktivitäten wie die <xref:System.Activities.Statements.Flowchart>\-Aktivität sowie benutzerdefinierte Aktivitäten aus dem vorherigen Thema [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) verwendet.Der Workflow erstellt ein Spiel, das Zahlen errät.  
  
> [!NOTE]
>  Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.Um dieses Thema verwenden zu können, müssen Sie zuerst [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) abschließen.  
  
> [!NOTE]
>  Um eine abgeschlossene Version des Lernprogramms herunterzuladen, informieren Sie sich unter [Windows Workflow Foundation \(WF45\) – Lernprogramm "Erste Schritte"](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### So erstellen Sie den Workflow  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **NumberGuessWorkflowActivities**, und wählen Sie **Hinzufügen** und dann **Neues Element** aus.  
  
2.  Wählen Sie im Knoten **Gemeinsame Elemente** unter **Installiert** die Option **Workflow** aus.Wählen Sie in der Liste **Workflow** die Option **Aktivität** aus.  
  
3.  Geben Sie im Feld **Name** den Namen `FlowchartNumberGuessWorkflow`ein, und klicken Sie auf **Hinzufügen**.  
  
4.  Ziehen Sie eine **Flowchart**\-Aktivität aus dem Abschnitt **Flowchart** der **Toolbox**, und legen Sie sie auf der Entwurfsoberfläche des Workflows auf der Bezeichnung **Aktivität hier ablegen** ab.  
  
### So erstellen Sie die Workflowvariablen und \-argumente  
  
1.  Doppelklicken Sie im **Projektmappen\-Explorer**auf **FlowchartNumberGuessWorkflow.xaml**, um den Workflow im Designer anzuzeigen, falls er nicht bereits angezeigt wird.  
  
2.  Klicken Sie links unten im Workflow\-Designer auf die Schaltfläche **Argumente**, um den Bereich **Argumente** anzuzeigen.  
  
3.  Klicken Sie auf **Argument erstellen**.  
  
4.  Geben Sie `MaxNumber` im Feld **Name** ein, wählen Sie aus der Dropdownliste **Richtung** die Richtung **In** und aus der Dropdownliste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
5.  Klicken Sie auf **Argument erstellen**.  
  
6.  Geben Sie in das Feld **Name**, das unter dem neu hinzugefügten Argument `MaxNumber` angezeigt wird, `Turns` ein. Wählen Sie aus der Dropdownliste **Richtung** die Richtung **Out** und aus der Dropdownliste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE.  
  
7.  Klicken Sie links unten im Aktivitäts\-Designer auf die Schaltfläche **Argumente**, um den Bereich **Argumente** zu schließen.  
  
8.  Klicken Sie links unten im Workflow\-Designer auf **Variablen**, um den Bereich **Variablen** anzuzeigen.  
  
9. Klicken Sie auf **Variable erstellen**.  
  
    > [!TIP]
    >  Wenn das Feld **Variable erstellen** nicht angezeigt wird, klicken Sie auf der Oberfläche des Workflow\-Designers auf die <xref:System.Activities.Statements.Flowchart>\-Aktivität, um sie auszuwählen.  
  
10. Geben Sie `Guess` im Feld **Name** ein, wählen Sie aus der Dropdownliste **Variablentyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
11. Klicken Sie auf **Variable erstellen**.  
  
12. Geben Sie `Target` im Feld **Name** ein, wählen Sie aus der Dropdownliste **Variablentyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
13. Klicken Sie links unten im Aktivitäts\-Designer auf **Variablen**, um den Bereich **Variablen** zu schließen.  
  
### So fügen Sie die Workflowaktivitäten hinzu  
  
1.  Ziehen Sie eine **Assign**\-Aktivität aus dem Abschnitt **Primitive** der **Toolbox**, und zeigen Sie auf den Knoten **Start**, der sich am oberen Rand des Flussdiagramms befindet.Wenn sich die **Assign**\-Aktivität über dem Knoten **Start** befindet, werden drei Dreiecke um den Knoten **Start** angezeigt.Legen Sie die **Assign**\-Aktivität auf dem Dreieck ab, das sich direkt unterhalb des Knotens **Start** befindet.Dadurch werden die beiden Elemente verknüpft und die **Assign**\-Aktivität als erste Aktivität im Flussdiagramm festgelegt.  
  
    > [!NOTE]
    >  Aktivitäten können auch als Startaktivität im Workflow angegeben werden, indem Sie die Aktivität manuell mit dem Startknoten verknüpfen.Hierzu zeigen Sie auf den Knoten **Start**, klicken auf eines der Rechtecke, die angezeigt werden, wenn sich der Mauszeiger über dem Knoten **Start** befindet, ziehen die Verbindungslinie auf die gewünschte Aktivität herunter und legen sie auf einem der angezeigten Rechtecke ab.Sie können eine Aktivität auch als Startaktivität festlegen, indem Sie mit der rechten Maustaste darauf klicken und **Als Startknoten festlegen** auswählen.  
  
2.  Geben Sie `Target` im Feld **To** und den folgenden Ausdruck im Feld **C\#\-Ausdruck eingeben** oder **VB\-Ausdruck eingeben** ein.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Wenn das Fenster **Toolbox** nicht sichtbar ist, wählen Sie im Menü **Ansicht** die Option **Toolbox** aus.  
  
3.  Ziehen Sie eine **Prompt**\-Aktivität aus dem Abschnitt **NumberGuessWorkflowActivities** der **Toolbox**, legen Sie sie unterhalb der **Assign**\-Aktivität aus dem vorherigen Schritt ab, und verbinden Sie die **Prompt**\-Aktivität mit der **Assign**\-Aktivität.Es gibt drei Möglichkeiten, die beiden Aktivitäten zu verbinden.Die erste Methode besteht darin, sie zu verbinden, während Sie die **Prompt**\-Aktivität im Workflow ablegen.Zeigen Sie, während Sie die **Prompt**\-Aktivität auf den Workflow ziehen, auf die **Assign**\-Aktivität, und legen Sie diese auf einem der vier Dreiecke ab, die angezeigt werden, wenn sich die **Prompt**\-Aktivität über der **Assign**\-Aktivität befindet.Die zweite Methode besteht darin, die **Prompt**\-Aktivität auf dem Workflow am gewünschten Ort abzulegen.Anschließend zeigen Sie auf die **Assign**\-Aktivität und ziehen eines der angezeigten Rechtecke nach unten auf die **Prompt**\-Aktivität.Ziehen Sie die Maus, sodass sich die Verbindungslinie von der **Assign**\-Aktivität mit einem der Rechtecke der **Prompt**\-Aktivität verbindet, und lassen Sie die Maustaste los.Der dritte Weg ist der ersten Methode sehr ähnlich, außer dass Sie die **Prompt**\-Aktivität nicht aus der **Toolbox** ziehen, sondern von ihrer Position auf der Entwurfsoberfläche des Workflows über die **Assign**\-Aktivität bewegen und auf einem der angezeigten Dreiecke ablegen.  
  
4.  Geben Sie im Eigenschaftenfenster für die **Prompt**\-Aktivität im Feld mit dem Eigenschaftswert **BookmarkName** den Begriff `"EnterGuess"` einschließlich der Anführungszeichen ein.Geben Sie im Feld mit dem Eigenschaftswert **Result** den Begriff `Guess` ein, und geben Sie den folgenden Ausdruck im Eigenschaftsfeld **Text** ein.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster**, falls das Fenster **Eigenschaften** nicht angezeigt wird.  
  
5.  Ziehen Sie eine **Assign**\-Aktivität aus dem Abschnitt **Primitive** der **Toolbox**, und verbinden Sie diese mit einer der im vorherigen Schritt beschriebenen Methoden, sodass sie sich unterhalb der **Prompt**\-Aktivität befindet.  
  
6.  Geben Sie `Turns` im Feld **To** und `Turns + 1` im Feld **C\#\-Ausdruck eingeben** oder **VB\-Ausdruck eingeben** ein.  
  
7.  Ziehen Sie in der Toolbox eine **FlowDecision** aus dem Abschnitt **Flowchart**, und verbinden Sie sie, sodass sie sich unterhalb der **Assign**\-Aktivität befindet.Geben Sie im Eigenschaftenfenster den folgenden Ausdruck im Feld mit dem Eigenschaftswert **Condition** ein.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  Ziehen Sie eine weitere **FlowDecision**\-Aktivität aus der Toolbox, und legen Sie diese unter der ersten Aktivität ab.Verbinden Sie die zwei Aktivitäten über Ziehen und Ablegen vom Rechteck mit der Bezeichnung **False** der obersten **FlowDecision**\-Aktivität zum Rechteck über der zweiten **FlowDecision**\-Aktivität.  
  
    > [!TIP]
    >  Wenn die Bezeichnungen **True** und **False** nicht für **FlowDecision** angezeigt werden, zeigen Sie mit der Maus auf **FlowDecision**.  
  
9. Klicken Sie auf die zweite **FlowDecision**\-Aktivität, um diese auszuwählen.Geben Sie im Eigenschaftenfenster den folgenden Ausdruck im Feld mit dem Eigenschaftswert **Condition** ein.  
  
    ```vb-c#  
    Guess < Target  
    ```  
  
10. Ziehen Sie in der Toolbox zwei **WriteLine**\-Aktivitäten aus dem Abschnitt **Primitive**, und legen Sie sie nebeneinander unter den zwei **FlowDecision**\-Aktivitäten ab.Verbinden Sie die **True**\-Aktion der untersten **FlowDecision**\-Aktivität mit der **WriteLine**\-Aktivität ganz links und die **False**\-Aktion mit der **WriteLine**\-Aktivität ganz rechts.  
  
11. Klicken Sie auf die **WriteLine**\-Aktivität ganz links, um sie auszuwählen, und geben Sie im Eigenschaftenfenster den folgenden Ausdruck im Feld mit dem Eigenschaftswert **Text** ein.  
  
    ```vb-c#  
    "Your guess is too low."  
    ```  
  
12. Verbinden Sie **WriteLine** mit der linken Seite der **Prompt**\-Aktivität, die sich darüber befindet.  
  
13. Klicken Sie auf die **WriteLine**\-Aktivität ganz rechts, um sie auszuwählen, und geben Sie im Eigenschaftenfenster den folgenden Ausdruck im Feld mit dem Eigenschaftswert **Text** ein.  
  
    ```vb-c#  
    "Your guess is too high."  
    ```  
  
14. Verbinden Sie **WriteLine**\-Aktivität mit der rechten Seite der **Prompt**\-Aktivität, die sich darüber befindet.  
  
     Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.  
  
     ![Abgeschlossene Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation//media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")  
  
### So erstellen Sie den Workflow  
  
1.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
     Informationen zum Ausführen des Workflows finden Sie im nächsten Thema, [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md).Wenn Sie den Schritt [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) bereits mit einer anderen Workflowart ausgeführt haben und ihn mit dem Flussdiagramm\-Workflow aus diesem Schritt ausführen möchten, gehen Sie direkt zum Abschnitt [So erstellen und führen Sie die Anwendung aus](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md#BKMK_ToRunTheApplication) unter [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) über.  
  
## Siehe auch  
 <xref:System.Activities.Statements.Flowchart>   
 <xref:System.Activities.Statements.FlowDecision>   
 [Windows Workflow Foundation\-Programmierung](../../../docs/framework/windows-workflow-foundation//programming.md)   
 [Entwerfen von Workflows](../../../docs/framework/windows-workflow-foundation//designing-workflows.md)   
 [Lernprogramm 'Erste Schritte'](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)   
 [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)