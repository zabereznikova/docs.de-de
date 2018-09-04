---
title: 'Vorgehensweise: Erstellen eines Flussdiagrammworkflows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 185d46d041ee342962c624ad6a3592e5a426cc6e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502150"
---
# <a name="how-to-create-a-flowchart-workflow"></a>Vorgehensweise: Erstellen eines Flussdiagrammworkflows
Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden. Dieses Thema führt durch Erstellen eines Workflows, der integrierten Aktivitäten wie z. B. verwendet die <xref:System.Activities.Statements.Flowchart> Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) Thema. Der Workflow erstellt ein Spiel, das Zahlen errät.  
  
> [!NOTE]
>  Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab. Um dieses Thema abzuschließen, müssen Sie zuerst abschließen [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).  
  
> [!NOTE]
>  Informationen zum Herunterladen einer abgeschlossenen Version des Lernprogramms finden Sie unter [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>So erstellen Sie den Workflow  
  
1.  Mit der rechten Maustaste **NumberGuessWorkflowActivities** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element**.  
  
2.  In der **installiert**, **gemeinsame Elemente** Knoten **Workflow**. Wählen Sie **Aktivität** aus der **Workflow** Liste.  
  
3.  Typ `FlowchartNumberGuessWorkflow` in die **Namen** ein, und klicken Sie auf **hinzufügen**.  
  
4.  Ziehen Sie eine **Flussdiagramm** Aktivität aus der **Flussdiagramm** im Abschnitt der **Toolbox** und legen ihn auf die **Aktivität hier ablegen** Bezeichnung auf der Workflow-Entwurfsoberfläche.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>So erstellen Sie die Workflowvariablen und -argumente  
  
1.  Doppelklicken Sie auf **FlowchartNumberGuessWorkflow.xaml** in **Projektmappen-Explorer** um den Workflow im Designer anzuzeigen, wenn er nicht bereits angezeigt wird.  
  
2.  Klicken Sie auf **Argumente** in der unteren linken Seite des Workflow-Designers zum Anzeigen der **Argumente** Bereich.  
  
3.  Klicken Sie auf **Argument erstellen**.  
  
4.  Typ `MaxNumber` in die **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
5.  Klicken Sie auf **Argument erstellen**.  
  
6.  Typ `Turns` in die **Namen** Feld unterhalb des neu erstellten `MaxNumber` Argument die Option **Out** aus der **Richtung** Dropdown-Liste  **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE.  
  
7.  Klicken Sie auf **Argumente** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Argumente** Bereich.  
  
8.  Klicken Sie auf **Variablen** in der unteren linken Seite des Workflow-Designers zum Anzeigen der **Variablen** Bereich.  
  
9. Klicken Sie auf **erstellen Variable**.  
  
    > [!TIP]
    >  Wenn kein **Variable erstellen** angezeigt wird, klicken Sie auf die <xref:System.Activities.Statements.Flowchart> Aktivität auf der workflowdesigneroberfläche, um es auszuwählen.  
  
10. Typ `Guess` in die **Namen** Kontrollkästchen **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
11. Klicken Sie auf **erstellen Variable**.  
  
12. Typ `Target` in die **Namen** Kontrollkästchen **Int32** aus der **Variablentyp** Dropdown-Liste, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern.  
  
13. Klicken Sie auf **Variablen** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Variablen** Bereich.  
  
### <a name="to-add-the-workflow-activities"></a>So fügen Sie die Workflowaktivitäten hinzu  
  
1.  Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** im Abschnitt der **Toolbox** und zeigen sie die **starten** Knoten, am oberen Rand der Flussdiagramm. Wenn die **zuweisen** Aktivität ist, über die **starten** Knoten drei Dreiecke um die **starten** Knoten. Löschen der **weisen** Aktivitäten auf dem Dreieck ab, direkt unterhalb der **starten** Knoten. Dadurch werden die beiden Elemente miteinander verknüpft, und bezieht sich auf die **weisen** Aktivität als erste Aktivität im Flussdiagramm.  
  
    > [!NOTE]
    >  Aktivitäten können auch als Startaktivität im Workflow angegeben werden, indem Sie die Aktivität manuell mit dem Startknoten verknüpfen. Zu diesem Zweck zeigen Sie auf den die **starten** Knoten, klicken Sie auf eines der Rechtecke, die angezeigt werden, wenn der Mauszeiger befindet der **starten** Knoten, und ziehen Sie das Herstellen einer Verbindung, auf die gewünschte Aktivität Zeile, und legen Sie es auf einem der die Rechtecke, die angezeigt werden. Sie können auch festlegen, und die Aktivitäten, die als Startaktivität indem mit der rechten Maustaste in It und **als Startknoten festlegen**.  
  
2.  Typ `Target` in die **zu** Feld und den folgenden Ausdruck in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Wenn die **Toolbox** Fenster nicht angezeigt wird, wählen Sie **Toolbox** aus der **Ansicht** Menü.  
  
3.  Ziehen Sie eine **Eingabeaufforderung** Aktivität aus der **NumberGuessWorkflowActivities** im Abschnitt der **Toolbox**, legen Sie sie unterhalb der **zuweisen** Aktivität aus dem vorherigen Schritt, und verbinden Sie die **Eingabeaufforderung** Aktivität, um die **weisen** Aktivität. Es gibt drei Möglichkeiten, die beiden Aktivitäten zu verbinden. Die erste Möglichkeit besteht, zu deren Verbindung, wie Sie löschen die **Eingabeaufforderung** Aktivität im Workflow. Wie Sie ziehen die **Eingabeaufforderung** Aktivität für den Workflow, zeigen sie die **zuweisen** Aktivität und legen ihn auf einem der vier Dreiecke, die angezeigt, wenn die **Eingabeaufforderung** Aktivität ist, über die **weisen** Aktivität. Die zweite Möglichkeit besteht darin, löschen die **Eingabeaufforderung** Aktivität auf dem Workflow am gewünschten Speicherort. Klicken Sie dann den Mauszeiger über die **weisen** -Aktivität, und ziehen Sie eines der Rechtecke, die nach unten zum angezeigt wird der **Eingabeaufforderung** Aktivität. Ziehen Sie die Maus, sodass die Verbindungslinie unter der **zuweisen** Aktivität eine Verbindung mit einem der Rechtecke der her die **Eingabeaufforderung** -Aktivität, und lassen Sie die Maustaste los. Die dritte Möglichkeit ist die erste Möglichkeit, außer dass ziehen sehr ähnlich der **Eingabeaufforderung** Aktivität aus der **Toolbox**, Sie an ihrem Speicherort auf der Workflowentwurfsoberfläche ziehen, bewegen Sie den Mauszeiger über die  **Weisen Sie** -Aktivität, und legen ihn auf eine der angezeigten Dreiecke.  
  
4.  In der **Fenster "Eigenschaften"** für die **Eingabeaufforderung** Aktivität, Typ `"EnterGuess"` einschließlich der Anführungszeichen der **BookmarkName** Wertefeld der Eigenschaft. Typ `Guess` in die **Ergebnis** Eigenschaft Wert im Feld, und geben Sie den folgenden Ausdruck in der **Text** Eigenschaftenfeld.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Wenn die **Fenster "Eigenschaften"** als nicht angezeigt, aktivieren **Fenster "Eigenschaften"** aus der **Ansicht** Menü.  
  
5.  Ziehen Sie ein **zuweisen** Aktivität aus der **primitive** Teil der **Toolbox** und verbinden Sie es mit einer der Methoden, die im vorherigen Schritt beschrieben wird, sodass sie sich unterhalb der befindet **Eingabeaufforderung** Aktivität.  
  
6.  Typ `Turns` in die **zu** Feld und `Turns + 1` in die **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld.  
  
7.  Ziehen Sie eine **FlowDecision** aus der **Flussdiagramm** Teil der **Toolbox** und verbinden Sie es unten die **zuweisen** Aktivität. In der **Fenster "Eigenschaften"**, geben Sie den folgenden Ausdruck in der **Bedingung** Wertefeld der Eigenschaft.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  Ziehen Sie ein weiteres **FlowDecision** Aktivität aus der **Toolbox** und legen Sie sie unterhalb der ersten. Verbinden Sie die beiden Aktivitäten, indem Sie ziehen, auf das Rechteck mit der Bezeichnung **"false"** am oberen Rand **FlowDecision** -Aktivität zum Rechteck am Anfang der zweiten **FlowDecision**Aktivität.  
  
    > [!TIP]
    >  Wenn Sie nicht sehen die **"true"** und **"false"** Bezeichnungen auf der **FlowDecision**, zeigen Sie auf den die **FlowDecision**.  
  
9. Klicken Sie auf die zweite **FlowDecision** Aktivität, um es auszuwählen. In der **Fenster "Eigenschaften"**, geben Sie den folgenden Ausdruck in der **Bedingung** Wertefeld der Eigenschaft.  
  
    ```
    Guess < Target  
    ```  
  
10. Ziehen Sie zwei **WriteLine** Aktivitäten aus der **primitive** Teil der **Toolbox** und legen Sie sie mit der Option, damit sie nebeneinander unter den zwei sind **FlowDecision**  Aktivitäten. Verbinden der **"true"** -Aktion der untersten **FlowDecision** Aktivität, um die am weitesten links stehende **WriteLine** -Aktivität, und die **"false"** Aktion aus, um die ganz rechts **WriteLine** Aktivität.  
  
11. Klicken Sie auf die am weitesten links stehende **WriteLine** Aktivität, um auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Eigenschaftswert im Feld der **Fenster "Eigenschaften"**.  
  
    ```
    "Your guess is too low."  
    ```  
  
12. Verbinden der **WriteLine** auf der linken Seite des der **Eingabeaufforderung** Aktivität, die darüber befindet.  
  
13. Klicken Sie auf der äußersten rechten **WriteLine** Aktivität, um auszuwählen, und geben Sie den folgenden Ausdruck in der **Text** Eigenschaftswert im Feld der **Fenster "Eigenschaften"**.  
  
    ```
    "Your guess is too high."  
    ```  
  
14. Verbinden der **WriteLine** Aktivität rechts neben der **Eingabeaufforderung** Aktivität darüber.  
  
     Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.  
  
     ![Windows Workflow Foundation abgeschlossen](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")  
  
### <a name="to-build-the-workflow"></a>So erstellen Sie den Workflow  
  
1.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
     Informationen zum Ausführen des Workflows finden Sie im nächste Thema, [wie: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md). Wenn Sie bereits abgeschlossen haben die [wie: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) Schritt mit einer anderen workflowart und ihn mit dem flussdiagrammworkflow aus diesem Schritt ausführen möchten, fahren Sie mit der [erstellen und Ausführen der Anwendung](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)Abschnitt [wie: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Windows Workflow Foundation-Programmierung](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [Entwerfen von Workflows](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [Tutorial mit ersten Schritten](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Vorgehensweise: Erstellen einer Aktivität](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [Vorgehensweise: Ausführen eines Workflows](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
