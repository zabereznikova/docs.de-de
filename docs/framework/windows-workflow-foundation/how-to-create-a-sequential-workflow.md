---
title: "Vorgehensweise: Erstellen eines sequenziellen Workflows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vorgehensweise: Erstellen eines sequenziellen Workflows
Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.In diesem Thema wird Schritt für Schritt die Erstellung eines Workflows erläutert, der integrierte Aktivitäten wie die <xref:System.Activities.Statements.Sequence>\-Aktivität sowie benutzerdefinierte Aktivitäten aus dem vorherigen Thema [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) verwendet.Der Workflow erstellt ein Spiel, das Zahlen errät.  
  
> [!NOTE]
>  Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.Um dieses Thema verwenden zu können, müssen Sie zuerst [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) abschließen.  
  
> [!NOTE]
>  Um eine abgeschlossene Version des Lernprogramms herunterzuladen, informieren Sie sich unter [Windows Workflow Foundation \(WF45\) – Lernprogramm "Erste Schritte"](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### So erstellen Sie den Workflow  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **NumberGuessWorkflowActivities**, und wählen Sie **Hinzufügen** und dann **Neues Element** aus.  
  
2.  Wählen Sie im Knoten **Gemeinsame Elemente** unter **Installiert** die Option **Workflow** aus.Wählen Sie in der Liste **Workflow** die Option **Aktivität** aus.  
  
3.  Geben Sie `SequentialNumberGuessWorkflow` im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.  
  
4.  Ziehen Sie eine **Sequence**\-Aktivität aus dem Abschnitt **Ablaufsteuerung** der **Toolbox**, und legen Sie sie auf der Bezeichnung **Aktivität hier ablegen** auf der Entwurfsoberfläche des Workflows ab.  
  
### So erstellen Sie die Workflowvariablen und \-argumente  
  
1.  Doppelklicken Sie im **Projektmappen\-Explorer** auf **SequentialNumberGuessWorkflow.xaml**, um den Workflow im Designer anzuzeigen, falls er nicht bereits angezeigt wird.  
  
2.  Klicken Sie links unten im Workflow\-Designer auf die Schaltfläche **Argumente**, um den Bereich **Argumente** anzuzeigen.  
  
3.  Klicken Sie auf **Argument erstellen**.  
  
4.  Geben Sie `MaxNumber` im Feld **Name** ein, wählen Sie aus der Dropdownliste **Richtung** die Richtung **In** und aus der Dropdownliste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
5.  Klicken Sie auf **Argument erstellen**.  
  
6.  Geben Sie in das Feld **Name**, das unter dem neu hinzugefügten Argument `MaxNumber` angezeigt wird, `Turns` ein. Wählen Sie aus der Dropdownliste **Richtung** die Richtung **Out** und aus der Dropdownliste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE.  
  
7.  Klicken Sie links unten im Aktivitäts\-Designer auf die Schaltfläche **Argumente**, um den Bereich **Argumente** zu schließen.  
  
8.  Klicken Sie links unten im Workflow\-Designer auf **Variablen**, um den Bereich **Variablen** anzuzeigen.  
  
9. Klicken Sie auf **Variable erstellen**.  
  
    > [!TIP]
    >  Wenn das Feld **Variable erstellen** nicht angezeigt wird, klicken Sie auf der Oberfläche des Workflow\-Designers auf die **Sequence**\-Aktivität, um sie auszuwählen.  
  
10. Geben Sie `Guess` im Feld **Name** ein, wählen Sie aus der Dropdownliste **Variablentyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
11. Klicken Sie auf **Variable erstellen**.  
  
12. Geben Sie `Target` im Feld **Name** ein, wählen Sie aus der Dropdownliste **Variablentyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
13. Klicken Sie links unten im Aktivitäts\-Designer auf **Variablen**, um den Bereich **Variablen** zu schließen.  
  
### So fügen Sie die Workflowaktivitäten hinzu  
  
1.  Ziehen Sie eine **Assign**\-Aktivität aus dem Abschnitt **Primitive** der Toolbox, und legen Sie sie auf der **Sequence**\-Aktivität ab.Geben Sie `Target` im Feld **To** und den folgenden Ausdruck im Feld **C\#\-Ausdruck eingeben** oder **VB\-Ausdruck eingeben** ein.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Wenn das Fenster **Toolbox** nicht sichtbar ist, wählen Sie im Menü **Ansicht** die Option **Toolbox** aus.  
  
2.  Ziehen Sie in der Toolbox eine **DoWhile**\-Aktivität aus dem Abschnitt **Ablaufsteuerung**, und legen Sie sie auf dem Workflow unterhalb der **Assign**\-Aktivität ab.  
  
3.  Geben Sie den folgenden Ausdruck in das Feld mit dem Eigenschaftswert **Condition** der **DoWhile**\-Aktivität ein.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     Eine <xref:System.Activities.Statements.DoWhile>\-Aktivität führt ihre untergeordneten Aktivitäten aus und wertet dann <xref:System.Activities.Statements.DoWhile.Condition%2A> aus.Wenn <xref:System.Activities.Statements.DoWhile.Condition%2A>`True` ergibt, dann werden die Aktivitäten in <xref:System.Activities.Statements.DoWhile> erneut ausgeführt.In diesem Beispiel wird der Schätzwert des Benutzers ausgewertet und <xref:System.Activities.Statements.DoWhile> fortgesetzt, bis die Schätzung richtig ist.  
  
4.  Ziehen Sie in der **Toolbox** eine **Prompt**\-Aktivität aus dem Abschnitt **NumberGuessWorkflowActivities**, und legen Sie sie in der **DoWhile**\-Aktivität aus dem vorherigen Schritt ab.  
  
5.  Geben Sie im Eigenschaftenfenster für die **Prompt**\-Aktivität im Feld mit dem Eigenschaftswert **BookmarkName** den Begriff `"EnterGuess"` einschließlich der Anführungszeichen ein.Geben Sie im Feld mit dem Eigenschaftswert **Result** den Begriff `Guess` ein, und geben Sie den folgenden Ausdruck im Eigenschaftsfeld **Text** ein.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster**, falls das Fenster **Eigenschaften** nicht angezeigt wird.  
  
6.  Ziehen Sie in der **Toolbox** eine **Assign**\-Aktivität aus dem Abschnitt **Primitive**, und legen Sie sie in der **DoWhile** \-Aktivität ab, sodass sie auf die **Prompt**\-Aktivität folgt.  
  
    > [!NOTE]
    >  Wenn Sie die **Assign**\-Aktivität ablegen, beachten Sie, wie der Workflow\-Designer automatisch eine **Sequence**\-Aktivität hinzufügt, um sowohl die **Prompt**\-Aktivität als auch die neu hinzugefügte **Assign**\-Aktivität einzuschließen.  
  
7.  Geben Sie `Turns` im Feld **To** und `Turns + 1` im Feld **C\#\-Ausdruck eingeben** oder **VB\-Ausdruck eingeben** ein.  
  
8.  Ziehen Sie eine **If**\-Aktivität aus dem Abschnitt **Ablaufsteuerung** der Toolbox, und legen Sie sie in der **Sequence**\-Aktivität ab, sodass sie auf die neu hinzugefügte **Assign**\-Aktivität folgt.  
  
9. Geben Sie den folgenden Ausdruck in das Feld mit dem Eigenschaftswert **Condition** der **If**\-Aktivität ein.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. Ziehen Sie eine weitere **If**\-Aktivität aus dem Abschnitt **Ablaufsteuerung** der **Toolbox**, und legen Sie sie im Abschnitt **Then**der ersten **If**\-Aktivität ab.  
  
11. Geben Sie den folgenden Ausdruck in das Feld mit dem Eigenschaftswert **Condition** der neu hinzugefügten **If**\-Aktivität ein.  
  
    ```vb-c#  
    Guess < Target  
    ```  
  
12. Ziehen Sie zwei **WriteLine**\-Aktivitäten aus dem Abschnitt **Primitive** der **Toolbox**, und legen Sie eine im Abschnitt **Then** und die andere im Abschnitt **Else** der neu hinzugefügten **If**\-Aktivität ab.  
  
13. Klicken Sie auf die **WriteLine**\-Aktivität im Abschnitt **Then**, um sie auszuwählen, und geben Sie den folgenden Ausdruck im Feld mit dem Eigenschaftswert **Text** ein.  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. Klicken Sie auf die **WriteLine**\-Aktivität im Abschnitt **Else**, um sie auszuwählen, und geben Sie den folgenden Ausdruck im Feld mit dem Eigenschaftswert **Text** ein.  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.  
  
     ![Abgeschlossener sequenzieller Workflow](../../../docs/framework/windows-workflow-foundation//media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")  
  
### So erstellen Sie den Workflow  
  
1.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
     Informationen zum Ausführen des Workflows finden Sie im nächsten Thema, [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md).Wenn Sie den Schritt [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) bereits mit einer anderen Workflowart ausgeführt haben und ihn mit dem sequenziellen Workflow aus diesem Schritt ausführen möchten, gehen Sie direkt zum Abschnitt [So erstellen und führen Sie die Anwendung aus](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md#BKMK_ToRunTheApplication) unter [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) über.  
  
## Siehe auch  
 <xref:System.Activities.Statements.Flowchart>   
 <xref:System.Activities.Statements.FlowDecision>   
 [Windows Workflow Foundation\-Programmierung](../../../docs/framework/windows-workflow-foundation//programming.md)   
 [Entwerfen von Workflows](../../../docs/framework/windows-workflow-foundation//designing-workflows.md)   
 [Lernprogramm 'Erste Schritte'](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)   
 [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)