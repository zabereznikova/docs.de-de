---
title: "Gewusst wie: Erstellen eines Zustandsautomatenworkflows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Gewusst wie: Erstellen eines Zustandsautomatenworkflows
Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden.In diesem Thema wird Schritt für Schritt die Erstellung eines Workflows erläutert, der integrierte Aktivitäten wie die <xref:System.Activities.Statements.StateMachine>\-Aktivität sowie benutzerdefinierte Aktivitäten aus dem vorherigen Thema [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) verwendet.Der Workflow erstellt ein Spiel, das Zahlen errät.  
  
> [!NOTE]
>  Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.Um dieses Thema verwenden zu können, müssen Sie zuerst [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) abschließen.  
  
> [!NOTE]
>  Um eine abgeschlossene Version des Lernprogramms herunterzuladen, informieren Sie sich unter [Windows Workflow Foundation \(WF45\) – Lernprogramm "Erste Schritte"](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### So erstellen Sie den Workflow  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **NumberGuessWorkflowActivities**, und wählen Sie **Hinzufügen** und dann **Neues Element** aus.  
  
2.  Wählen Sie im Knoten **Gemeinsame Elemente** unter **Installiert** die Option **Workflow** aus.Wählen Sie in der Liste **Workflow** die Option **Aktivität** aus.  
  
3.  Geben Sie `StateMachineNumberGuessWorkflow` im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.  
  
4.  Ziehen Sie eine **StateMachine**\-Aktivität aus dem Abschnitt **Zustandsautomat** der **Toolbox**, und legen Sie sie auf der Bezeichnung **Aktivität hier ablegen** auf der Entwurfsoberfläche des Workflows ab.  
  
### So erstellen Sie die Workflowvariablen und \-argumente  
  
1.  Doppelklicken Sie im **Projektmappen\-Explorer** auf **StateMachineNumberGuessWorkflow.xaml**, um den Workflow im Designer anzuzeigen, falls er nicht bereits angezeigt wird.  
  
2.  Klicken Sie links unten im Workflow\-Designer auf die Schaltfläche **Argumente**, um den Bereich **Argumente** anzuzeigen.  
  
3.  Klicken Sie auf **Argument erstellen**.  
  
4.  Geben Sie `MaxNumber` im Feld **Name** ein, wählen Sie aus der Dropdownliste **Richtung** die Richtung **In** und aus der Dropdownliste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
5.  Klicken Sie auf **Argument erstellen**.  
  
6.  Geben Sie in das Feld **Name**, das unter dem neu hinzugefügten Argument `MaxNumber` angezeigt wird, `Turns` ein. Wählen Sie aus der Dropdownliste **Richtung** die Richtung **Out** und aus der Dropdownliste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE.  
  
7.  Klicken Sie links unten im Aktivitäts\-Designer auf die Schaltfläche **Argumente**, um den Bereich **Argumente** zu schließen.  
  
8.  Klicken Sie links unten im Workflow\-Designer auf **Variablen**, um den Bereich **Variablen** anzuzeigen.  
  
9. Klicken Sie auf **Variable erstellen**.  
  
    > [!TIP]
    >  Wenn das Feld **Variable erstellen** nicht angezeigt wird, klicken Sie auf der Oberfläche des Workflow\-Designers auf die <xref:System.Activities.Statements.StateMachine>\-Aktivität, um sie auszuwählen.  
  
10. Geben Sie `Guess` im Feld **Name** ein, wählen Sie aus der Dropdownliste **Variablentyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
11. Klicken Sie auf **Variable erstellen**.  
  
12. Geben Sie `Target` im Feld **Name** ein, wählen Sie aus der Dropdownliste **Variablentyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
13. Klicken Sie links unten im Aktivitäts\-Designer auf **Variablen**, um den Bereich **Variablen** zu schließen.  
  
### So fügen Sie die Workflowaktivitäten hinzu  
  
1.  Klicken Sie auf **State1**, um ihn auszuwählen.Ändern Sie im **Eigenschaftenfenster** die Option **DisplayName** in `Ziel initialisieren`.  
  
    > [!TIP]
    >  Klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster**, falls das Fenster **Eigenschaften** nicht angezeigt wird.  
  
2.  Doppelklicken Sie auf den umbenannten Zustand **Ziel initialisieren** im Workflow\-Designer, um ihn zu erweitern.  
  
3.  Ziehen Sie eine **Assign**\-Aktivität aus dem Abschnitt **Primitive** der **Toolbox**, und legen Sie sie auf dem Abschnitt **Entry** des Zustands ab.Geben Sie `Target` im Feld **To** und den folgenden Ausdruck im Feld **C\#\-Ausdruck eingeben** oder **VB\-Ausdruck eingeben** ein.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Wenn das Fenster **Toolbox** nicht sichtbar ist, wählen Sie im Menü **Ansicht** die Option **Toolbox** aus.  
  
4.  Kehren Sie zur allgemeinen Zustandsautomatenansicht im Workflow\-Designer zurück, indem Sie in der Breadcrumb\-Anzeige am oberen Rand des Workflow\-Designers auf **StateMachine** klicken.  
  
5.  Ziehen Sie eine **State**\-Aktivität aus dem Abschnitt **Zustandsautomat** der **Toolbox** auf den Zustand **Ziel initialisieren** im Workflow\-Designer.Beachten Sie, dass um den Zustand **Ziel initialisieren** vier Dreiecke angezeigt werden, wenn sich der neue Zustand darüber befindet.Legen Sie den neuen Zustand auf dem Dreieck ab, das sich unmittelbar unterhalb des Zustands **Ziel initialisieren** befindet.Dadurch wird der neue Zustand im Workflow positioniert und ein Übergang vom Zustand **Ziel initialisieren** zum neuen Zustand erstellt.  
  
6.  Klicken Sie auf **State1**, um ihn auszuwählen, ändern Sie **DisplayName** in `Enter Guess`, und doppelklicken Sie dann auf den Zustand im Workflow\-Designer, um ihn zu erweitern.  
  
7.  Ziehen Sie eine **WriteLine**\-Aktivität aus dem Abschnitt **Primitive** der **Toolbox**, und legen Sie sie auf dem Abschnitt **Entry** des Zustands ab.  
  
8.  Geben Sie den folgenden Ausdruck in das Eigenschaftenfeld **Text** von **WriteLine** ein.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. Ziehen Sie eine **Assign**\-Aktivität aus dem Abschnitt **Primitive** der **Toolbox**, und legen Sie sie auf dem Abschnitt **Exit** des Zustands ab.  
  
10. Geben Sie `Turns` im Feld **To** und `Turns + 1` im Feld **C\#\-Ausdruck eingeben** oder **VB\-Ausdruck eingeben** ein.  
  
11. Kehren Sie zur allgemeinen Zustandsautomatenansicht im Workflow\-Designer zurück, indem Sie in der Breadcrumb\-Anzeige am oberen Rand des Workflow\-Designers auf **StateMachine** klicken.  
  
12. Ziehen Sie eine **FinalState**\-Aktivität aus dem Abschnitt **Zustandsautomat** der **Toolbox** auf den Zustand **Enter Guess**, und legen Sie sie auf dem rechts neben dem Zustand **Enter Guess** angezeigten Dreieck ab, sodass ein Übergang zwischen **Enter Guess** und **FinalState** erstellt wird.  
  
13. Der Standardname des Übergangs lautet **T2**.Klicken Sie auf den Übergang im Workflow\-Designer, um ihn auszuwählen, und legen Sie dessen **DisplayName** auf **Guess Correct** fest.Klicken Sie dann auf **FinalState**, wählen Sie ihn aus, und ziehen Sie ihn nach rechts, damit genügend Platz vorhanden ist, um den vollständigen Namen des Übergangs anzuzeigen, ohne einen der beiden Zustände zu überlagern.Das vereinfacht die Ausführung der verbleibenden Schritte im Lernprogramm.  
  
14. Doppelklicken Sie auf den umbenannten Übergang **Guess Correct** im Workflow\-Designer, um ihn zu erweitern.  
  
15. Ziehen Sie eine **ReadInt**\-Aktivität aus dem Abschnitt **NumberGuessWorkflowActivities** der **Toolbox**, und legen Sie sie im Abschnitt **Trigger** des Übergangs ab.  
  
16. Geben Sie im **Eigenschaftenfenster** der **ReadInt**\-Aktivität `"EnterGuess"` einschließlich der Anführungszeichen im Feld mit dem Eigenschaftswert **BookmarkName** und `Guess` im Feld mit dem Eigenschaftswert **Result** ein.  
  
17. Geben Sie den folgenden Ausdruck in das Feld mit dem Eigenschaftswert **Condition** des Übergangs **Guess Correct** ein.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Kehren Sie zur allgemeinen Zustandsautomatenansicht im Workflow\-Designer zurück, indem Sie in der Breadcrumb\-Anzeige am oberen Rand des Workflow\-Designers auf **StateMachine** klicken.  
  
    > [!NOTE]
    >  Ein Übergang erfolgt, wenn das Triggerereignis empfangen wird und <xref:System.Activities.Statements.Transition.Condition%2A>, falls vorhanden, `True` ergibt.Wenn der `Guess`\-Wert des Benutzers bei diesem Übergang mit dem zufällig generierten `Target` übereinstimmt, geht die Steuerung an **FinalState** über, und der Workflow wird abgeschlossen.  
  
19. Abhängig davon, ob die Schätzung richtig ist, sollte der Workflow entweder in den Zustand **FinalState** oder zurück in den Zustand **Enter Guess** übergehen, damit ein neuer Versuch ausgeführt werden kann.Beide Übergänge verwenden den gleichen Trigger, d. h., es wird gewartet, bis die Schätzung des Benutzers über die **ReadInt**\-Aktivität empfangen wird.Dies wird als gemeinsamer Übergang bezeichnet.Um einen gemeinsamen Übergang zu erstellen, klicken Sie auf den Kreis, der den Anfang des Zustands **Guess Correct** darstellt, und ziehen Sie ihn auf den gewünschten Zustand.Da der Übergang in diesem Fall ein Selbstübergang ist, ziehen Sie den Startpunkt des Übergangs **Guess Correct** und legen diesen wieder auf dem unteren Bereich des Zustands **Enter Guess** ab.Nachdem Sie den Übergang erstellt haben, wählen Sie ihn im Workflow\-Designer aus, und legen dessen **DisplayName**\-Eigenschaft auf **Guess Incorrect** fest.  
  
    > [!NOTE]
    >  Gemeinsame Übergänge können auch innerhalb des Übergangs\-Designers erstellt werden, indem Sie im unteren Bereich des Übergangs\-Designers auf **Gemeinsamen Triggerübergang hinzufügen** klicken und dann den gewünschten Zielzustand aus der Dropdownliste **Verfügbare Zustände für Verbindung** auswählen.  
  
    > [!NOTE]
    >  Wenn die <xref:System.Activities.Statements.Transition.Condition%2A>\-Aktivität eines Übergangs mit `false` ausgewertet wird \(oder alle Bedingungen eines Übergangs mit freigegebenem Trigger mit `false` ausgewertet werden\), erfolgt der Übergang nicht, und die Trigger aller Übergänge aus dem Zustand werden neu geplant.In diesem Lernprogramm kann diese Situation aufgrund der Konfigurationsmethode für die Bedingungen \(es gibt spezielle Aktionen für richtige oder falsche Schätzungen\) nicht auftreten.  
  
20. Doppelklicken Sie auf den Übergang **Guess Incorrect** im Workflow\-Designer, um ihn zu erweitern.Beachten Sie, dass **Trigger** bereits auf dieselbe **ReadInt**\-Aktivität festgelegt ist, die auch vom Übergang **Guess Correct** verwendet wurde.  
  
21. Geben Sie den folgenden Ausdruck im Feld mit dem Eigenschaftswert **Condition** ein.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. Ziehen Sie eine **If**\-Aktivität aus dem Abschnitt **Ablaufsteuerung** der **Toolbox**, und legen Sie sie im Abschnitt **Action** des Übergangs ab.  
  
23. Geben Sie den folgenden Ausdruck in das Feld mit dem Eigenschaftswert **Condition** der **If**\-Aktivität ein.  
  
    ```vb-c#  
    Guess < Target  
    ```  
  
24. Ziehen Sie zwei **WriteLine**\-Aktivitäten aus dem Abschnitt **Primitive** der **Toolbox**, und legen Sie eine im Abschnitt **Then** und die andere im Abschnitt **Else** der **If**\-Aktivität ab.  
  
25. Klicken Sie auf die **WriteLine**\-Aktivität im Abschnitt **Then**, um sie auszuwählen, und geben Sie den folgenden Ausdruck im Feld mit dem Eigenschaftswert **Text** ein.  
  
    ```vb-c#  
    "Your guess is too low."  
    ```  
  
26. Klicken Sie auf die **WriteLine**\-Aktivität im Abschnitt **Else**, um sie auszuwählen, und geben Sie den folgenden Ausdruck im Feld mit dem Eigenschaftswert **Text** ein.  
  
    ```vb-c#  
    "Your guess is too high."  
    ```  
  
27. Kehren Sie zur allgemeinen Zustandsautomatenansicht im Workflow\-Designer zurück, indem Sie in der Breadcrumb\-Anzeige am oberen Rand des Workflow\-Designers auf **StateMachine** klicken.  
  
     Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.  
  
     ![Abgeschlossener Zustandsautomatworkflow](../../../docs/framework/windows-workflow-foundation//media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### So erstellen Sie den Workflow  
  
1.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
     Informationen zum Ausführen des Workflows finden Sie im nächsten Thema, [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md).Wenn Sie den Schritt [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) bereits mit einer anderen Workflowart ausgeführt haben und ihn mit dem Zustandsautomatworkflow aus diesem Schritt ausführen möchten, gehen Sie direkt zum Abschnitt [So erstellen und führen Sie die Anwendung aus](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md#BKMK_ToRunTheApplication) unter [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) über.  
  
## Siehe auch  
 <xref:System.Activities.Statements.Flowchart>   
 <xref:System.Activities.Statements.FlowDecision>   
 [Windows Workflow Foundation\-Programmierung](../../../docs/framework/windows-workflow-foundation//programming.md)   
 [Entwerfen von Workflows](../../../docs/framework/windows-workflow-foundation//designing-workflows.md)   
 [Lernprogramm 'Erste Schritte'](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)   
 [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)