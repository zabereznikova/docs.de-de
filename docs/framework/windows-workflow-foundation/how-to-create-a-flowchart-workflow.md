---
title: 'Vorgehensweise: Erstellen eines Flussdiagrammworkflows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 0faf4d77b1ea2881ba8e029d544f2e42cf552349
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989688"
---
# <a name="how-to-create-a-flowchart-workflow"></a>Vorgehensweise: Erstellen eines Flussdiagrammworkflows
Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden. In diesem Thema wird Schritt für Schritt beschrieben, wie Sie einen Workflow erstellen, der integrierte Aktivitäten verwendet, z. b. die <xref:System.Activities.Statements.Flowchart> Aktivität, und die benutzerdefinierten Aktivitäten aus dem vorherigen [Gewusst wie: Erstellen Sie eine Aktivität Thema](how-to-create-an-activity.md). Der Workflow erstellt ein Spiel, das Zahlen errät.  
  
> [!NOTE]
> Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab. Um dieses Thema abzuschließen, müssen Sie zuerst [Gewusst wie: Erstellen Sie eine Aktivitäts](how-to-create-an-activity.md).  
  
> [!NOTE]
> Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.  
  
### <a name="to-create-the-workflow"></a>So erstellen Sie den Workflow  
  
1. Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf " **numguess Workflow Activities** ", und wählen Sie **Hinzufügen**, **Neues Element**aus.  
  
2. Wählen Sie im Knoten **installierte**, **Allgemeine Elemente** die Option **Workflow**aus. Wählen Sie in der Liste **Workflow** die Option **Aktivität** aus.  
  
3. Geben Sie im Feld **Name** `FlowchartNumberGuessWorkflow` ein, und klicken Sie auf **Hinzufügen**.  
  
4. Ziehen Sie eine **Flowchart** -Aktivität aus dem Abschnitt **Flowchart** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** auf der Workflow Entwurfs Oberfläche ab.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>So erstellen Sie die Workflowvariablen und -argumente  
  
1. Doppelklicken Sie in **Projektmappen-Explorer** auf **flowchartnumguess Workflow. XAML** , um den Workflow im Designer anzuzeigen, falls er nicht bereits angezeigt wird.  
  
2. Klicken Sie Links unten im Workflow-Designer auf **Argumente** , um den Bereich **Argumente** anzuzeigen.  
  
3. Klicken Sie auf **Argument erstellen**.  
  
4. Geben Sie `MaxNumber` in das Feld **Name** ein, wählen Sie **in** der Dropdown Liste **Richtung** die Option ein aus, wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern  
  
5. Klicken Sie auf **Argument erstellen**.  
  
6. Geben Sie `Turns` in das Feld **Name** ein, das sich unterhalb des neu hinzugefügten `MaxNumber` Arguments befindet, wählen Sie aus der Dropdown Liste **Richtung** die Option **out** aus, wählen Sie **Int32** aus der Dropdown Liste **Argumenttyp** aus, und drücken Sie dann die EINGABETASTE.  
  
7. Klicken Sie Links unten im Aktivitäts-Designer auf **Argumente** , um den Bereich **Argumente** zu schließen.  
  
8. Klicken Sie Links unten im Workflow-Designer auf **Variablen** , um den Bereich **Variablen** anzuzeigen.  
  
9. Klicken Sie auf **Variable erstellen**.  
  
    > [!TIP]
    > Wenn das Feld **Variable erstellen** nicht angezeigt wird, klicken Sie auf der Oberfläche des Workflow-Designers auf die <xref:System.Activities.Statements.Flowchart> Aktivität, um Sie auszuwählen.  
  
10. Geben Sie `Guess` in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern  
  
11. Klicken Sie auf **Variable erstellen**.  
  
12. Geben Sie `Target` in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern  
  
13. Klicken Sie Links unten im Aktivitäts-Designer auf **Variablen** , um den Bereich **Variablen** zu schließen.  
  
### <a name="to-add-the-workflow-activities"></a>So fügen Sie die Workflowaktivitäten hinzu  
  
1. Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und zeigen Sie auf den Knoten **Start** , der sich am oberen Rand des Fluss Diagramms befindet. Wenn sich die **assign** -Aktivität über dem **Start** Knoten befindet, werden drei Dreiecke um den **Start** Knoten angezeigt. Legen Sie die **assign** -Aktivität auf dem Dreieck ab, das sich direkt unter dem **Start** Knoten befindet. Dadurch werden die beiden Elemente miteinander verknüpft, und die **assign** -Aktivität wird als erste Aktivität im Flussdiagramm bezeichnet.  
  
    > [!NOTE]
    > Aktivitäten können auch als Startaktivität im Workflow angegeben werden, indem Sie die Aktivität manuell mit dem Startknoten verknüpfen. Zeigen Sie dazu mit dem Mauszeiger auf den Knoten **Start** , klicken Sie auf einen der Rechtecke, die angezeigt werden, wenn sich der Mauszeiger über dem Knoten **Start** befindet, und ziehen Sie die Verbindungslinie auf die gewünschte Aktivität, und legen Sie Sie auf einem der angezeigten Rechtecke ab. Sie können eine Aktivität auch als Start Aktivität festlegen, indem Sie mit der rechten Maustaste darauf klicken und **als Start Knoten festlegen**auswählen.  
  
2. Geben Sie `Target` in das Feld **an** und den folgenden Ausdruck in das Feld  **C# Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > Wenn das Fenster **Toolbox** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Toolbox** aus.  
  
3. Ziehen Sie eine **prompt** -Aktivität aus dem Abschnitt " **nummeriguess Workflow Activities** " der **Toolbox**, legen Sie Sie unterhalb der **assign** -Aktivität aus dem vorherigen Schritt ab, und verbinden Sie die **prompt** -Aktivität mit der **assign** -Aktivität. Es gibt drei Möglichkeiten, die beiden Aktivitäten zu verbinden. Die erste Möglichkeit besteht darin, Sie zu verbinden, während Sie die **prompt** -Aktivität für den Workflow ablegen. Wenn Sie die **prompt** -Aktivität in den Workflow ziehen, zeigen Sie auf die **assign** -Aktivität, und legen Sie Sie auf einem der vier Dreiecke ab, die angezeigt werden, wenn die **prompt** -Aktivität über der **assign** -Aktivität ist. Die zweite Möglichkeit besteht darin, die **prompt** -Aktivität am gewünschten Speicherort auf dem Workflow abzulegen. Zeigen Sie dann mit der Maus auf die **assign** -Aktivität, und ziehen Sie einen der unten angezeigten Rechtecke auf die Aktivität **prompt** . Ziehen Sie die Maus, sodass sich die Verbindungslinie der **assign** -Aktivität mit einer der Rechtecke der **prompt** -Aktivität verbindet, und lassen Sie dann die Maustaste los. Die dritte Möglichkeit ähnelt der ersten Methode, mit dem Unterschied, dass Sie nicht die **prompt** -Aktivität aus der **Toolbox**ziehen, sondern von der Position auf der Workflow Entwurfs Oberfläche ziehen, mit der Maus auf die **assign** -Aktivität zeigen und Sie auf einem der angezeigten Dreiecke ablegen.  
  
4. Geben Sie im **Eigenschaften Fenster** für die **prompt** -Aktivität `"EnterGuess"`, einschließlich der Anführungszeichen, in das Feld **BookmarkName** -Eigenschafts Wert ein. Geben Sie `Guess` in das Feld **Ergebnis** Eigenschafts Wert ein, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschaft ein.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > Wenn das **Fenster Eigenschaften** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Eigenschaften Fenster** aus.  
  
5. Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und verbinden Sie Sie mit einer der im vorherigen Schritt beschriebenen Methoden, sodass Sie sich unterhalb der **prompt** -Aktivität befindet.  
  
6. Geben Sie `Turns` in das Feld **an** ein **C#** , und `Turns + 1` Sie in das Feld Ausdruck eingeben oder **VB-Ausdruck eingeben** .  
  
7. Ziehen Sie eine **FlowDecision** aus dem Abschnitt **Flowchart** der **Toolbox** , und verbinden Sie Sie unter der **assign** -Aktivität. Geben Sie im **Fenster Eigenschaften**den folgenden Ausdruck **in das Feld Bedingungs Eigenschaften Wert** ein.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. Ziehen Sie eine weitere **FlowDecision** -Aktivität aus der **Toolbox** , und legen Sie Sie unterhalb der ersten ab. Verbinden Sie die beiden Aktivitäten, indem Sie aus dem Rechteck mit der Bezeichnung **false** auf der Top- **FlowDecision** -Aktivität in das Rechteck am Anfang der zweiten **FlowDecision** -Aktivität ziehen.  
  
    > [!TIP]
    > Wenn die Bezeichnungen **true** und **false** bei **FlowDecision**nicht angezeigt werden, zeigen Sie mit der Maus auf die **FlowDecision**.  
  
9. Klicken Sie auf die zweite **FlowDecision** -Aktivität, um Sie auszuwählen. Geben Sie im **Fenster Eigenschaften**den folgenden Ausdruck **in das Feld Bedingungs Eigenschaften Wert** ein.  
  
    ```text
    Guess < Target
    ```  
  
10. Ziehen Sie **zwei schreiben** -Aktivitäten aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie diese so ab, dass Sie sich unter den zwei **FlowDecision** -Aktivitäten nebeneinander befinden. Verbinden Sie die " **true** "-Aktion der untersten **FlowDecision** -Aktivität mit **der Schreib** Schutz-Aktivität ganz links und der " **false** "-Aktion an die "äußersten rechten"-Aktivität " **WriteLine** ".  
  
11. Klicken Sie zum auswählen auf die **Schreib** geschützte Aktivität ganz links, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert im **Eigenschaften Fenster**ein.  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. Verbinden Sie die **Schreib** geschützte Seite mit der linken Seite der **prompt** -Aktivität, die sich darüber befindet.  
  
13. Klicken Sie auf die **WriteLine** -Aktivität ganz rechts, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert im **Fenster Eigenschaften**ein.  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. Verbinden Sie die Aktivität " **Write teline** " mit der rechten Seite der **prompt** -Aktivität oberhalb der Aktivität.  
  
     Im folgenden Beispiel wird der abgeschlossene Workflow dargestellt.  
  
     ![Diagramm, das ein abgeschlossenes Windows Workflow Foundation Flussdiagramm anzeigt.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a>So erstellen Sie den Workflow  
  
1. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
     Anweisungen zum Ausführen des Workflows finden Sie im nächsten Thema [Vorgehensweise: Führt einen Workflow](how-to-run-a-workflow.md)aus. Wenn Sie die [bereits abgeschlossen haben, Vorgehensweise: Führen Sie einen Workflow](how-to-run-a-workflow.md) Schritt mit einem anderen Workflow Workflow aus, und möchten Sie ihn mit dem Flussdiagramm Workflow aus diesem Schritt ausführen, fahren Sie mit dem Abschnitt so [Erstellen und führen Sie die Anwendung](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) aus [Gewusst wie: Führt einen Workflow aus.](how-to-run-a-workflow.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Windows Workflow Foundation-Programmierung](programming.md)
- [Entwerfen von Workflows](designing-workflows.md)
- [Tutorial mit ersten Schritten](getting-started-tutorial.md)
- [Vorgehensweise: Erstellen einer Aktivitäts](how-to-create-an-activity.md)
- [Vorgehensweise: Workflow ausführen](how-to-run-a-workflow.md)
