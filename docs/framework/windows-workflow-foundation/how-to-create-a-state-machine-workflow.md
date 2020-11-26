---
title: 'Vorgehensweise: Erstellen eines Zustandsautomatworkflows'
description: In diesem Artikel wird ein Workflow erstellt, der integrierte Aktivitäten verwendet, z. b. die StateMachine-Aktivität und benutzerdefinierte Aktivitäten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 9df911779422ca2710686963a040a95258db8891
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248918"
---
# <a name="how-to-create-a-state-machine-workflow"></a>Vorgehensweise: Erstellen eines Zustandsautomatworkflows

Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden. In diesem Thema wird Schritt für Schritt beschrieben, wie Sie einen Workflow erstellen, der integrierte Aktivitäten wie die <xref:System.Activities.Statements.StateMachine> -Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen Thema Gewusst [wie: Erstellen einer Aktivität](how-to-create-an-activity.md) verwendet. Der Workflow erstellt ein Spiel, das Zahlen errät.  
  
> [!NOTE]
> Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab. Um dieses Thema abzuschließen, müssen Sie zunächst Gewusst [wie: Erstellen einer Aktivität durchführen](how-to-create-an-activity.md).  
  
> [!NOTE]
> Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.  
  
### <a name="to-create-the-workflow"></a>So erstellen Sie den Workflow  
  
1. Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf " **numguess Workflow Activities** ", und wählen Sie **Hinzufügen**, **Neues Element** aus.  
  
2. Wählen Sie im Knoten **installierte**, **Allgemeine Elemente** die Option **Workflow** aus. Wählen Sie **Aktivität** aus der Liste **Workflow** aus.  
  
3. Geben `StateMachineNumberGuessWorkflow` Sie im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.  
  
4. Ziehen Sie eine **StateMachine** -Aktivität aus dem Abschnitt **Zustands Automat** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** auf der Workflow Entwurfs Oberfläche ab.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>So erstellen Sie die Workflowvariablen und -argumente  
  
1. Doppelklicken Sie in **Projektmappen-Explorer** auf **statemachinenumberguess Workflow. XAML** , um den Workflow im Designer anzuzeigen, falls er nicht bereits angezeigt wird.  
  
2. Klicken Sie Links unten im Workflow-Designer auf **Argumente** , um den Bereich **Argumente** anzuzeigen.  
  
3. Klicken Sie auf **Argument erstellen**.  
  
4. Geben `MaxNumber` Sie in das Feld **Name** ein, wählen Sie in der Dropdown Liste **Richtung** die Option **in** aus, wählen Sie **Int32** aus der Dropdown Liste **Argumenttyp** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
5. Klicken Sie auf **Argument erstellen**.  
  
6. Geben `Turns` Sie in das Feld **Name** unter dem neu hinzugefügten `MaxNumber` Argument ein, wählen Sie aus der Dropdown Liste **Richtung** die Option **aus** , wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE.  
  
7. Klicken Sie unten links im Aktivitäts-Designer auf **Argumente**, um den Bereich **Argumente** zu schließen.  
  
8. Klicken Sie Links unten im Workflow-Designer auf **Variablen** , um den Bereich **Variablen** anzuzeigen.  
  
9. Klicken Sie auf **Variable erstellen**.  
  
    > [!TIP]
    > Wenn das Feld **Variable erstellen** nicht angezeigt wird, klicken Sie auf der Oberfläche des Workflow-Designers auf die- <xref:System.Activities.Statements.StateMachine> Aktivität, um Sie auszuwählen.  
  
10. Geben `Guess` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern  
  
11. Klicken Sie auf **Variable erstellen**.  
  
12. Geben `Target` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern  
  
13. Klicken Sie unten links im Aktivitäts-Designer auf **Variablen**, um den Bereich **Variablen** zu schließen.  
  
### <a name="to-add-the-workflow-activities"></a>So fügen Sie die Workflowaktivitäten hinzu  
  
1. Klicken Sie auf **state1** , um es auszuwählen. Ändern Sie im **Fenster Eigenschaften** den **Display Name** in `Initialize Target` .  
  
    > [!TIP]
    > Wenn das **Fenster Eigenschaften** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Eigenschaften Fenster** aus.  
  
2. Doppelklicken Sie auf den neu umbenannten Zustand **Ziel initialisieren** im Workflow-Designer, um ihn zu erweitern.  
  
3. Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf dem Abschnitt **Entry** des Zustands ab. Geben Sie in das Feld `Target` **an** und den folgenden Ausdruck im Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > Wird das Fenster **Toolbox** nicht angezeigt, wählen Sie **Toolbox** im Menü **Ansicht** aus.  
  
4. Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.  
  
5. Ziehen Sie eine **State** -Aktivität aus dem Abschnitt **Zustands Automat** der **Toolbox** auf den Workflow-Designer, und bewegen Sie den Mauszeiger über den Zustand **Ziel initialisieren** . Beachten Sie, dass vier Dreiecke um den **Initialisierungs Ziel** Status angezeigt werden, wenn sich der neue Status darüber befindet. Legen Sie den neuen Zustand auf dem Dreieck ab, das sich direkt unterhalb des **Ziel Zustands initialisieren** befindet. Dadurch wird der neue Zustand auf dem Workflow platziert, und es wird ein Übergang vom Zustand " **Initialize Target** " in den neuen Zustand erstellt.  
  
6. Klicken Sie auf **state1** , um es auszuwählen, ändern Sie **Display Name** in `Enter Guess` , und doppelklicken Sie dann auf den Zustand im Workflow-Designer, um ihn zu erweitern.  
  
7. Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf dem Abschnitt **Entry** des Zustands ab.  
  
8. Geben Sie den folgenden Ausdruck in das **Text** -Eigenschaften Feld von " **Write teline**" ein.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf dem **Exit** -Abschnitt des Zustands ab.  
  
10. Geben `Turns` Sie im Feld **an** und `Turns + 1` im Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .  
  
11. Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.  
  
12. Ziehen Sie eine **FinalState** -Aktivität aus dem Abschnitt **Zustands Automat** der **Toolbox**, zeigen Sie mit dem Mauszeiger auf den Status **Enter Guess** , und legen Sie ihn auf dem Dreieck ab, das rechts neben dem Status **Eingabe Raten** angezeigt wird, sodass ein Übergang zwischen **Enter Guess** und **FinalState** erstellt wird.  
  
13. Der Standardname des Übergangs ist **T2**. Klicken Sie auf den Übergang im Workflow-Designer, um ihn auszuwählen, und legen Sie dessen **Display Name** auf **Guess correct** fest. Klicken Sie anschließend auf **FinalState**, und ziehen Sie ihn nach rechts, damit genügend Platz vorhanden ist, damit der vollständige Übergangs Name angezeigt wird, ohne einen der beiden Zustände zu überlagern. Das vereinfacht die Ausführung der verbleibenden Schritte im Lernprogramm.  
  
14. Doppelklicken Sie im Workflow-Designer auf den neu umbenannten Abschnitt " **Guess correct** ", um ihn zu erweitern.  
  
15. Ziehen Sie eine Aktivität "read **int** " aus dem Abschnitt " **nummeriguess Workflow Activities** " der **Toolbox** , und legen Sie Sie im **triggerabschnitt** des Übergangs ab.  
  
16. Geben Sie im **Eigenschaften Fenster** für die Aktivität "read **int** " `"EnterGuess"` die Anführungszeichen in das Feld **BookmarkName** -Eigenschafts Wert ein, und geben Sie `Guess` in das Feld **Ergebnis** Eigenschafts Wert ein.  
  
17. Geben Sie den folgenden Ausdruck in das Feld **Eigenschafts Wert des Bedingungs** Werts des Übergangs **erraten** ein.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.  
  
    > [!NOTE]
    > Ein Übergang erfolgt, wenn das Triggerereignis empfangen wird und <xref:System.Activities.Statements.Transition.Condition%2A>, falls vorhanden, `True` ergibt. Wenn der Benutzer für diesen Übergang `Guess` mit dem zufällig generierten übereinstimmt `Target` , übergibt die Steuerung an den **FinalState** , und der Workflow wird beendet.  
  
19. Abhängig davon, ob der Schätzwert richtig ist, sollte der Workflow für einen anderen Versuch entweder in den **FinalState** oder zurück in den Zustand " **Enter Guess** " übergehen. Beide Übergänge verwenden denselben-Triggern, der darauf wartet, dass die Schätzung des Benutzers über die Read **int** -Aktivität empfangen wird. Dies wird als gemeinsamer Übergang bezeichnet. Um einen freigegebenen Übergang zu erstellen, klicken Sie auf den Kreis, der den Anfang des **korrekten Guess** -Übergangs angibt, und ziehen Sie ihn in den gewünschten Zustand. In diesem Fall handelt es sich bei dem Übergang um einen selbst Übergang. ziehen Sie daher den Startpunkt des über-/Unterbrechungs **-Übergangs,** und legen Sie ihn wieder am unteren Ende des Zustands für die **Eingabe Vermutung** ab Nachdem Sie den Übergang erstellt haben, wählen Sie ihn im Workflow-Designer aus, und legen Sie dessen Eigenschaft **Display Name** auf nicht **richtig** fest.  
  
    > [!NOTE]
    > Freigegebene Übergänge können auch aus dem Übergangs-Designer erstellt werden, indem Sie im unteren Bereich des Übergangs-Designers auf frei **gegebenen triggerübergang hinzufügen** klicken und dann den gewünschten Ziel Status aus der Dropdown Liste **Verfügbare Zustände zum Verbinden** auswählen.  
  
    > [!NOTE]
    > Wenn die <xref:System.Activities.Statements.Transition.Condition%2A>-Aktivität eines Übergangs mit `false` ausgewertet wird (oder alle Bedingungen eines Übergangs mit freigegebenem Trigger mit `false` ausgewertet werden), erfolgt der Übergang nicht, und die Trigger aller Übergänge aus dem Zustand werden neu geplant. In diesem Lernprogramm kann diese Situation aufgrund der Konfigurationsmethode für die Bedingungen (es gibt spezielle Aktionen für richtige oder falsche Schätzungen) nicht auftreten.  
  
20. Doppelklicken Sie im Workflow-Designer auf den Übergang **erraten** , um ihn zu erweitern. Beachten Sie, dass der- **Triggerwert** bereits auf die gleiche Read **int** -Aktivität festgelegt ist **, die von der falschen** Übertragung verwendet wurde.  
  
21. Geben **Sie im Feld Bedingungs Eigenschaften Wert** den folgenden Ausdruck ein.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. Ziehen Sie eine **if** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie Sie im Abschnitt **Aktion** des Übergangs ab.  
  
23. Geben Sie den folgenden Ausdruck in das Feld Bedingungs **Eigenschafts Wert** der **if** -Aktivität ein.  
  
    ```text
    Guess < Target
    ```  
  
24. Ziehen Sie zwei **Write** -Aktivitäten aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie diese so ab, dass Sie sich im **Then** -Abschnitt der **if** -Aktivität befinden und eine im Abschnitt **else** .  
  
25. Klicken Sie im Abschnitt **Then** auf die Aktivität **Write** -Aktivität, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert ein.  
  
    ```text
    "Your guess is too low."  
    ```  
  
26. Klicken Sie im Abschnitt **else** auf die Aktivität **Write** -Aktivität, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert ein.  
  
    ```text
    "Your guess is too high."  
    ```  
  
27. Kehren Sie im Workflow-Designer zur Ansicht Gesamt Zustands Automat zurück, indem Sie in der Breadcrumb-Anzeige am oberen Rand des Workflow-Designers auf **StateMachine** klicken.  
  
     Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.  
  
     ![Die Abbildung zeigt den abgeschlossenen Zustandsautomatworkflow.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a>So erstellen Sie den Workflow  
  
1. Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.  
  
     Anweisungen zum Ausführen des Workflows finden Sie im nächsten Thema Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md). Wenn Sie den Schritt Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md) mit einem anderen Workflow Workflow abgeschlossen haben und ihn mit dem Zustandsautomatworkflow aus diesem Schritt ausführen möchten, fahren Sie mit dem Abschnitt so [Erstellen und führen Sie den Anwendungs](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) Abschnitt "Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md)" fort.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Windows Workflow Foundation-Programmierung](programming.md)
- [Entwerfen von Workflows](designing-workflows.md)
- [Lernprogramm 'Erste Schritte'](getting-started-tutorial.md)
- [Vorgehensweise: Erstellen einer Aktivität](how-to-create-an-activity.md)
- [Vorgehensweise: Ausführen eines Workflows](how-to-run-a-workflow.md)
