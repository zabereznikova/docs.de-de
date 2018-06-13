---
title: 'Gewusst wie: Erstellen eines Zustandsautomatenworkflows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 00f764421d3caf44d853d26d76c6b6d872ab1e3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520028"
---
# <a name="how-to-create-a-state-machine-workflow"></a>Gewusst wie: Erstellen eines Zustandsautomatenworkflows
Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden. Dieses Thema führt Sie durch Erstellen eines Workflows, die sowohl integrierten Aktivitäten, wie z. B. verwendet die <xref:System.Activities.Statements.StateMachine> Aktivität und den benutzerdefinierten Aktivitäten aus dem vorherigen [Vorgehensweise: Erstellen Sie eine Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) Thema. Der Workflow erstellt ein Spiel, das Zahlen errät.  
  
> [!NOTE]
>  Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab. Um dieses Thema abzuschließen, müssen Sie zuerst ausführen [Vorgehensweise: Erstellen Sie eine Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).  
  
> [!NOTE]
>  Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.  
  
### <a name="to-create-the-workflow"></a>So erstellen Sie den Workflow  
  
1.  Mit der rechten Maustaste **NumberGuessWorkflowActivities** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element**.  
  
2.  In der **installiert**, **gemeinsame Elemente** Knoten **Workflow**. Wählen Sie **Aktivität** aus der **Workflow** Liste.  
  
3.  Typ `StateMachineNumberGuessWorkflow` in der **Namen** Feld, und klicken Sie auf **hinzufügen**.  
  
4.  Ziehen Sie eine **StateMachine** Aktivität aus der **Zustandsautomat** Teil der **Toolbox** und legen ihn auf die **Aktivität hier ablegen** Beschriftung im die Entwurfsoberfläche des Workflows.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>So erstellen Sie die Workflowvariablen und -argumente  
  
1.  Doppelklicken Sie auf **StateMachineNumberGuessWorkflow.xaml** in **Projektmappen-Explorer** um den Workflow im Designer anzuzeigen, wenn er nicht bereits angezeigt wird.  
  
2.  Klicken Sie auf **Argumente** in der unteren linken Seite im Workflow-Designer zum Anzeigen der **Argumente** Bereich.  
  
3.  Klicken Sie auf **Argument erstellen**.  
  
4.  Typ `MaxNumber` in der **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
5.  Klicken Sie auf **Argument erstellen**.  
  
6.  Typ `Turns` in der **Namen** Feld, das unterhalb der neu hinzugefügten `MaxNumber` Argument die Option **Out** aus der **Richtung** Dropdown-Liste  **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE.  
  
7.  Klicken Sie auf **Argumente** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Argumente** Bereich.  
  
8.  Klicken Sie auf **Variablen** in der unteren linken Seite im Workflow-Designer zum Anzeigen der **Variablen** Bereich.  
  
9. Klicken Sie auf **erstellen Variable**.  
  
    > [!TIP]
    >  Wenn kein **Variable erstellen** angezeigt wird, klicken Sie auf die <xref:System.Activities.Statements.StateMachine> Aktivität auf der workflowdesigneroberfläche, um es auszuwählen.  
  
10. Typ `Guess` in der **Namen** wählen Sie im **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
11. Klicken Sie auf **erstellen Variable**.  
  
12. Typ `Target` in der **Namen** wählen Sie im **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
13. Klicken Sie auf **Variablen** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Variablen** Bereich.  
  
### <a name="to-add-the-workflow-activities"></a>So fügen Sie die Workflowaktivitäten hinzu  
  
1.  Klicken Sie auf **State1** um es auszuwählen. In der **Fenster "Eigenschaften"**, ändern Sie die **DisplayName** auf `Initialize Target`.  
  
    > [!TIP]
    >  Wenn die **Fenster "Eigenschaften"** wird nicht angezeigt werden, wählen Sie **Fenster "Eigenschaften"** aus der **Ansicht** Menü.  
  
2.  Doppelklicken Sie auf den umbenannten **Ziel initialisieren** Zustand im Workflow-Designer, um ihn zu erweitern.  
  
3.  Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und legen ihn auf die **Eintrag** -Abschnitt des Zustands. Typ `Target` in der **auf** Feld und den folgenden Ausdruck in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Wenn die **Toolbox** Fenster nicht angezeigt wird, wählen Sie **Toolbox** aus der **Ansicht** Menü.  
  
4.  Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers.  
  
5.  Ziehen Sie eine **Zustand** Aktivität aus der **Zustandsautomat** Teil der **Toolbox** auf die Workflow-Designer und zeigen sie auf die **Ziel initialisieren** Zustand. Beachten Sie, dass vier Dreiecke, um angezeigt werden die **Ziel initialisieren** Zustand, wenn der neue Zustand darüber befindet. Legen Sie den neuen Zustand auf dem Dreieck ab, das unmittelbar unterhalb der **Ziel initialisieren** Zustand. Dadurch wird der neue Zustand auf dem Workflow, und erstellt einen Übergang von der **Ziel initialisieren** Zustands, in dem Zustand "Neu".  
  
6.  Klicken Sie auf **State1** ändern, um ihn auszuwählen, die **DisplayName** auf `Enter Guess`, und doppelklicken Sie dann auf den Zustand im Workflow-Designer, um ihn zu erweitern.  
  
7.  Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** Teil der **Toolbox** und legen ihn auf die **Eintrag** -Abschnitt des Zustands.  
  
8.  Geben Sie den folgenden Ausdruck in der **Text** Eigenschaftenfeld der **WriteLine**.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und legen Sie auf der **beenden** -Abschnitt des Zustands.  
  
10. Typ `Turns` in der **auf** Feld und `Turns + 1` in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.  
  
11. Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers.  
  
12. Ziehen Sie eine **FinalState** Aktivität aus der **Zustandsautomat** im Abschnitt der **Toolbox**, zeigen sie auf die **Enter Guess** Status, und legen Sie sie auf dem Dreieck ab, die rechts neben der **Enter Guess** versetzt, sodass ein Übergang zwischen erstellt ist **Enter Guess** und **FinalState**.  
  
13. Der Standardname des Übergangs lautet **T2**. Klicken Sie auf den Übergang im Workflowdesigner, um auszuwählen, und legen Sie dessen **DisplayName** auf **Guess Correct**. Klicken Sie dann auf, und wählen Sie die **FinalState**, und ziehen Sie es auf der rechten Seite, damit genügend Platz für den vollständigen Namen des Übergangs angezeigt werden, ohne einen der beiden Zustände zu überlagern vorhanden ist. Das vereinfacht die Ausführung der verbleibenden Schritte im Lernprogramm.  
  
14. Doppelklicken Sie auf den umbenannten **Guess Correct** Übergang im Workflow-Designer, um ihn zu erweitern.  
  
15. Ziehen Sie eine **ReadInt** Aktivität aus der **NumberGuessWorkflowActivities** Teil der **Toolbox** und legen Sie sie in der **Trigger** Abschnitt des Übergangs.  
  
16. In der **Fenster "Eigenschaften"** für die **ReadInt** -Aktivität `"EnterGuess"` einschließlich der Anführungszeichen in der **BookmarkName** Feld mit dem Eigenschaftswert ein, und geben `Guess`in der **Ergebnis** Feld mit dem Eigenschaftswert  
  
17. Geben Sie den folgenden Ausdruck in der **Guess Correct** des Übergangs **Bedingung** Feld mit dem Eigenschaftswert.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers.  
  
    > [!NOTE]
    >  Ein Übergang erfolgt, wenn das Triggerereignis empfangen wird und <xref:System.Activities.Statements.Transition.Condition%2A>, falls vorhanden, `True` ergibt. Bei diesem Übergang Wenn des Benutzers `Guess` entspricht, die nach dem Zufallsprinzip generierte `Target`, übergibt die Steuerung an die **FinalState** und der Workflow abgeschlossen ist.  
  
19. Je nachdem, ob die Schätzung richtig ist, sollte der Workflow Übergang entweder auf die **FinalState** oder wieder auf die **Enter Guess** Zustand versuchen Sie es erneut. Beide Übergänge verwenden den gleichen Trigger warten Schätzwert des Benutzers über empfangen werden die **ReadInt** Aktivität. Dies wird als gemeinsamer Übergang bezeichnet. Um einen gemeinsamen Übergang zu erstellen, klicken Sie auf den Kreis, der den Anfang des Zustands der **Guess Correct** Übergang erfolgt, und ziehen Sie es auf den gewünschten Zustand. In diesem Fall wird des Übergangs ein Übergang, ziehen Sie daher den Ausgangspunkt der **Guess Correct** darstellt, und legen diesen wieder auf den unteren Rand der **Enter Guess** Zustand. Nachdem der Übergang erstellt haben, wählen sie im Workflow-Designer, und legen seine **DisplayName** Eigenschaft **Guess Incorrect**.  
  
    > [!NOTE]
    >  Gemeinsame Übergänge können auch aus erstellt werden innerhalb des Übergangs-Designers durch Klicken auf **gemeinsamen triggerübergang hinzufügen** am unteren Rand des Übergangs-Designers, und wählen Sie dann den gewünschten Zielzustand aus der  **Verfügbare Zustände für Verbindung** Dropdownliste aus.  
  
    > [!NOTE]
    >  Wenn die <xref:System.Activities.Statements.Transition.Condition%2A>-Aktivität eines Übergangs mit `false` ausgewertet wird (oder alle Bedingungen eines Übergangs mit freigegebenem Trigger mit `false` ausgewertet werden), erfolgt der Übergang nicht, und die Trigger aller Übergänge aus dem Zustand werden neu geplant. In diesem Lernprogramm kann diese Situation aufgrund der Konfigurationsmethode für die Bedingungen (es gibt spezielle Aktionen für richtige oder falsche Schätzungen) nicht auftreten.  
  
20. Doppelklicken Sie auf die **Guess Incorrect** Übergang im Workflow-Designer, um ihn zu erweitern. Beachten Sie, dass die **Trigger** bereits festgelegt ist, auf das gleiche **ReadInt** Aktivität, die verwendet wurde, indem die **Guess Correct** Übergang.  
  
21. Geben Sie den folgenden Ausdruck in der **Bedingung** Feld mit dem Eigenschaftswert.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. Ziehen Sie ein **Wenn** Aktivität aus der **Control Flow** Teil der **Toolbox** und legen Sie sie in der **Aktion** Abschnitt des Übergangs.  
  
23. Geben Sie den folgenden Ausdruck in der **Wenn** Aktivität **Bedingung** Feld mit dem Eigenschaftswert.  
  
    ```
    Guess < Target  
    ```  
  
24. Ziehen Sie zwei **WriteLine** Aktivitäten aus der **primitive** im Abschnitt der **Toolbox** und ablegen, sodass ist die **dann** im Abschnitt die **Wenn** Aktivität, und eine befindet sich in der **Else** Abschnitt.  
  
25. Klicken Sie auf die **WriteLine** Aktivität in der **dann** Abschnitt, um ihn auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Feld mit dem Eigenschaftswert.  
  
    ```
    "Your guess is too low."  
    ```  
  
26. Klicken Sie auf die **WriteLine** Aktivität in der **Else** Abschnitt, um ihn auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Feld mit dem Eigenschaftswert.  
  
    ```
    "Your guess is too high."  
    ```  
  
27. Zurück zur allgemeinen zustandsautomatenansicht im Workflow-Designer durch Klicken auf **StateMachine** in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers.  
  
     Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.  
  
     ![Abgeschlossener Zustandsautomatworkflow](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>So erstellen Sie den Workflow  
  
1.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
     Anweisungen zum Ausführen des Workflows finden Sie unter dem nächsten Thema [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md). Wenn Sie bereits abgeschlossen haben die [wie: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) Schritt mit einem anderen Format des Workflows und sie mit den Zustandsautomat-Workflow aus diesen Schritt ausführen möchten, fahren Sie mit der [zum Erstellen und Ausführen der Anwendung](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) Abschnitt [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Windows Workflow Foundation-Programmierung](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [Entwerfen von Workflows](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [Tutorial mit ersten Schritten](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
