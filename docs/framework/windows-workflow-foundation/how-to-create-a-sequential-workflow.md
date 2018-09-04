---
title: 'Vorgehensweise: Erstellen eines sequenziellen Workflows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: e2cfb3068a416da40b99072a0c7dfd751d3578c3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524183"
---
# <a name="how-to-create-a-sequential-workflow"></a>Vorgehensweise: Erstellen eines sequenziellen Workflows
Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden. Dieses Thema führt durch Erstellen eines Workflows, der integrierten Aktivitäten wie z. B. verwendet die <xref:System.Activities.Statements.Sequence> Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) Thema. Der Workflow erstellt ein Spiel, das Zahlen errät.  
  
> [!NOTE]
>  Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab. Um dieses Thema abzuschließen, müssen Sie zuerst abschließen [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).  
  
> [!NOTE]
>  Informationen zum Herunterladen einer abgeschlossenen Version des Lernprogramms finden Sie unter [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>So erstellen Sie den Workflow  
  
1.  Mit der rechten Maustaste **NumberGuessWorkflowActivities** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element**.  
  
2.  In der **installiert**, **gemeinsame Elemente** Knoten **Workflow**. Wählen Sie **Aktivität** aus der **Workflow** Liste.  
  
3.  Typ `SequentialNumberGuessWorkflow` in die **Namen** ein, und klicken Sie auf **hinzufügen**.  
  
4.  Ziehen Sie eine **Sequenz** Aktivität aus der **Control Flow** im Abschnitt der **Toolbox** und legen ihn auf der **Aktivität hier ablegen** Bezeichnung auf der Workflow-Entwurfsoberfläche.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>So erstellen Sie die Workflowvariablen und -argumente  
  
1.  Doppelklicken Sie auf **SequentialNumberGuessWorkflow.xaml** in **Projektmappen-Explorer** um den Workflow im Designer anzuzeigen, wenn er nicht bereits angezeigt wird.  
  
2.  Klicken Sie auf **Argumente** in der unteren linken Seite des Workflow-Designers zum Anzeigen der **Argumente** Bereich.  
  
3.  Klicken Sie auf **Argument erstellen**.  
  
4.  Typ `MaxNumber` in die **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
5.  Klicken Sie auf **Argument erstellen**.  
  
6.  Typ `Turns` in die **Namen** Feld unterhalb des neu erstellten `MaxNumber` Argument die Option **Out** aus der **Richtung** Dropdown-Liste  **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE.  
  
7.  Klicken Sie auf **Argumente** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Argumente** Bereich.  
  
8.  Klicken Sie auf **Variablen** in der unteren linken Seite des Workflow-Designers zum Anzeigen der **Variablen** Bereich.  
  
9. Klicken Sie auf **erstellen Variable**.  
  
    > [!TIP]
    >  Wenn kein **Variable erstellen** angezeigt wird, klicken Sie auf die **Sequenz** Aktivität auf der workflowdesigneroberfläche, um es auszuwählen.  
  
10. Typ `Guess` in die **Namen** Kontrollkästchen **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
11. Klicken Sie auf **erstellen Variable**.  
  
12. Typ `Target` in die **Namen** Kontrollkästchen **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
13. Klicken Sie auf **Variablen** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Variablen** Bereich.  
  
### <a name="to-add-the-workflow-activities"></a>So fügen Sie die Workflowaktivitäten hinzu  
  
1.  Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und legen ihn auf die **Sequenz** Aktivität. Typ `Target` in die **zu** Feld und den folgenden Ausdruck in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Wenn die **Toolbox** Fenster nicht angezeigt wird, wählen Sie **Toolbox** aus der **Ansicht** Menü.  
  
2.  Ziehen Sie eine **DoWhile** Aktivität aus der **Control Flow** Teil der **Toolbox** und legen Sie es auf dem Workflow, damit es unter ist der **zuweisen** Aktivität.  
  
3.  Geben Sie den folgenden Ausdruck in der **DoWhile** Aktivität **Bedingung** Wertefeld der Eigenschaft.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     Eine <xref:System.Activities.Statements.DoWhile>-Aktivität führt ihre untergeordneten Aktivitäten aus und wertet dann <xref:System.Activities.Statements.DoWhile.Condition%2A> aus. Wenn <xref:System.Activities.Statements.DoWhile.Condition%2A> `True` ergibt, dann werden die Aktivitäten in <xref:System.Activities.Statements.DoWhile> erneut ausgeführt. In diesem Beispiel wird der Schätzwert des Benutzers ausgewertet und <xref:System.Activities.Statements.DoWhile> fortgesetzt, bis die Schätzung richtig ist.  
  
4.  Ziehen Sie eine **Eingabeaufforderung** Aktivität aus der **NumberGuessWorkflowActivities** im Abschnitt der **Toolbox** und legen Sie sie in der **DoWhile** Aktivität aus dem vorherigen Schritt.  
  
5.  In der **Fenster "Eigenschaften"**, Typ `"EnterGuess"` einschließlich der Anführungszeichen der **BookmarkName** Eigenschaft im Feld für die **Eingabeaufforderung** Aktivität. Typ `Guess` in die **Ergebnis** Eigenschaft Wert im Feld, und geben Sie den folgenden Ausdruck in der **Text** Eigenschaftenfeld.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Wenn die **Fenster "Eigenschaften"** als nicht angezeigt, aktivieren **Fenster "Eigenschaften"** aus der **Ansicht** Menü.  
  
6.  Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** im Abschnitt der **Toolbox** und legen Sie sie in der **DoWhile** -Aktivität, folgt die **Eingabeaufforderung** Aktivität.  
  
    > [!NOTE]
    >  Beim Ablegen der **zuweisen** Aktivität, die sich wie der Workflow-Designer fügt automatisch hinzu eine **Sequenz** Aktivität, um beide enthalten den **Eingabeaufforderung** Aktivität und der neu hinzugefügten **Weisen** Aktivität.  
  
7.  Typ `Turns` in die **zu** Feld und `Turns + 1` in die **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.  
  
8.  Ziehen Sie ein **Wenn** Aktivität aus der **Control Flow** im Abschnitt der **Toolbox** und legen Sie sie in der **Sequenz** -Aktivität, folgt die neu hinzugefügte **weisen** Aktivität.  
  
9. Geben Sie den folgenden Ausdruck in der **Wenn** Aktivität **Bedingung** Wertefeld der Eigenschaft.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. Ziehen Sie ein weiteres **Wenn** Aktivität aus der **Ablaufsteuerung** Teil der **Toolbox** und legen Sie sie in der **klicken Sie dann** Abschnitt des ersten **Wenn** Aktivität.  
  
11. Geben Sie den folgenden Ausdruck in der neu hinzugefügten **Wenn** Aktivität **Bedingung** Wertefeld der Eigenschaft.  
  
    ```
    Guess < Target  
    ```  
  
12. Ziehen Sie zwei **WriteLine** Aktivitäten aus der **primitive** Teil der **Toolbox** und legen Sie sie, dass sich eine in der **klicken Sie dann** Teil die neu hinzugefügte **Wenn** -Aktivität, und eine hat die **Else** Abschnitt.  
  
13. Klicken Sie auf die **WriteLine** -Aktivität in der **dann** Abschnitt, um es auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Wertefeld der Eigenschaft.  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. Klicken Sie auf die **WriteLine** -Aktivität in der **Else** Abschnitt, um es auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Wertefeld der Eigenschaft.  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.  
  
     ![Abgeschlossener sequenzieller Workflow](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>So erstellen Sie den Workflow  
  
1.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
     Informationen zum Ausführen des Workflows finden Sie im nächste Thema, [wie: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md). Wenn Sie bereits abgeschlossen haben die [wie: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) Schritt mit einer anderen workflowart und ihn mit dem sequenziellen Workflow aus diesem Schritt ausführen möchten, fahren Sie mit der [erstellen und Ausführen der Anwendung](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)Abschnitt [wie: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Windows Workflow Foundation-Programmierung](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [Entwerfen von Workflows](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [Tutorial mit ersten Schritten](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
