---
title: 'Vorgehensweise: Erstellen eines sequenziellen Workflows'
description: In diesem Artikel wird ein Workflow erstellt, der integrierte Aktivitäten verwendet, wie z. b. die Sequence-Aktivität und benutzerdefinierte Aktivitäten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: f80ac471fdcc425504b11b5fb17effa888aa9590
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419693"
---
# <a name="how-to-create-a-sequential-workflow"></a>Vorgehensweise: Erstellen eines sequenziellen Workflows

Workflows können aus integrierten Aktivitäten und aus benutzerdefinierten Aktivitäten erstellt werden. In diesem Thema wird Schritt für Schritt beschrieben, wie Sie einen Workflow erstellen, der integrierte Aktivitäten wie die <xref:System.Activities.Statements.Sequence> -Aktivität und die benutzerdefinierten Aktivitäten aus dem vorherigen Thema Gewusst [wie: Erstellen einer Aktivität](how-to-create-an-activity.md) verwendet. Der Workflow erstellt ein Spiel, das Zahlen errät.

> [!NOTE]
> Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab. Um dieses Thema abzuschließen, müssen Sie zunächst Gewusst [wie: Erstellen einer Aktivität durchführen](how-to-create-an-activity.md).

> [!NOTE]
> Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.

## <a name="to-create-the-workflow"></a>So erstellen Sie den Workflow

1. Klicken Sie mit der rechten Maustaste **Projektmappen-Explorer** auf " **numguess Workflow Activities** ", und wählen Sie **Hinzufügen**, **Neues Element**aus.

2. Wählen Sie im Knoten **installierte**, **Allgemeine Elemente** die Option **Workflow**aus. Wählen Sie **Aktivität** aus der Liste **Workflow** aus.

3. Geben `SequentialNumberGuessWorkflow` Sie im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.

4. Ziehen Sie eine **Sequence** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie diese auf der Bezeichnung **Aktivität hier ablegen** auf der Workflow Entwurfs Oberfläche ab.

## <a name="to-create-the-workflow-variables-and-arguments"></a>So erstellen Sie die Workflowvariablen und -argumente

1. Doppelklicken Sie in **Projektmappen-Explorer** auf **sequentialnumguess Workflow. XAML** , um den Workflow im Designer anzuzeigen, falls er nicht bereits angezeigt wird.

2. Klicken Sie Links unten im Workflow-Designer auf **Argumente** , um den Bereich **Argumente** anzuzeigen.

3. Klicken Sie auf **Argument erstellen**.

4. Geben `MaxNumber` Sie in das Feld **Name** ein, wählen Sie in der Dropdown Liste **Richtung** die Option **in** aus, wählen Sie **Int32** aus der Dropdown Liste **Argumenttyp** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.

5. Klicken Sie auf **Argument erstellen**.

6. Geben `Turns` Sie in das Feld **Name** unter dem neu hinzugefügten `MaxNumber` Argument ein, wählen Sie aus der Dropdown Liste **Richtung** die Option **aus** , wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE.

7. Klicken Sie unten links im Aktivitäts-Designer auf **Argumente**, um den Bereich **Argumente** zu schließen.

8. Klicken Sie Links unten im Workflow-Designer auf **Variablen** , um den Bereich **Variablen** anzuzeigen.

9. Klicken Sie auf **Variable erstellen**.

    > [!TIP]
    > Wenn das Feld **Variable erstellen** nicht angezeigt wird, klicken Sie auf der Oberfläche des Workflow-Designers auf die **Sequenz** Aktivität, um Sie auszuwählen.

10. Geben `Guess` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern

11. Klicken Sie auf **Variable erstellen**.

12. Geben `Target` Sie in das Feld **Name** ein, wählen Sie **Int32** aus der Dropdown Liste **Variablentyp** aus, und drücken Sie dann die EINGABETASTE, um die Variable zu speichern

13. Klicken Sie unten links im Aktivitäts-Designer auf **Variablen**, um den Bereich **Variablen** zu schließen.

## <a name="to-add-the-workflow-activities"></a>So fügen Sie die Workflowaktivitäten hinzu

1. Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf der **Sequence** -Aktivität ab. Geben Sie in das Feld `Target` **an** und den folgenden Ausdruck im Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > Wird das Fenster **Toolbox** nicht angezeigt, wählen Sie **Toolbox** im Menü **Ansicht** aus.

2. Ziehen Sie eine **DoWhile** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie Sie auf dem Workflow ab, sodass Sie sich unterhalb der **assign** -Aktivität befindet.

3. Geben Sie den folgenden Ausdruck **in das Feld Bedingungs Eigenschafts Wert** der **DoWhile** -Aktivität ein.

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     Eine <xref:System.Activities.Statements.DoWhile>-Aktivität führt ihre untergeordneten Aktivitäten aus und wertet dann <xref:System.Activities.Statements.DoWhile.Condition%2A> aus. Wenn <xref:System.Activities.Statements.DoWhile.Condition%2A>`True` ergibt, dann werden die Aktivitäten in <xref:System.Activities.Statements.DoWhile> erneut ausgeführt. In diesem Beispiel wird der Schätzwert des Benutzers ausgewertet und <xref:System.Activities.Statements.DoWhile> fortgesetzt, bis die Schätzung richtig ist.

4. Ziehen Sie eine **prompt** -Aktivität aus dem Abschnitt " **nummeriguess Workflow Activities** " der **Toolbox** , und legen Sie Sie aus dem vorherigen Schritt in der **DoWhile** -Aktivität ab.

5. Geben Sie im **Eigenschaften Fenster** `"EnterGuess"` die Anführungszeichen in das Feld **BookmarkName** -Eigenschafts Wert für die **prompt** -Aktivität ein. Geben Sie `Guess` in das Feld **Ergebnis** Eigenschafts Wert ein, und geben Sie den folgenden Ausdruck in das Eigenschaften Feld **Text** ein.

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > Wenn das **Fenster Eigenschaften** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Eigenschaften Fenster** aus.

6. Ziehen Sie eine **assign** -Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie in der **DoWhile** -Aktivität ab, sodass Sie der **prompt** -Aktivität folgt.

    > [!NOTE]
    > Beachten Sie beim Löschen der **assign** -Aktivität, wie der Workflow-Designer automatisch eine **Sequence** -Aktivität hinzufügt, die sowohl die **prompt** -Aktivität als auch die neu hinzugefügte **assign** -Aktivität enthält.

7. Geben `Turns` Sie im Feld **an** und `Turns + 1` im Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben ein** .

8. Ziehen Sie eine **if** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie Sie in der **Sequence** -Aktivität ab, sodass Sie auf die neu hinzugefügte **assign** -Aktivität folgt.

9. Geben Sie den folgenden Ausdruck in das Feld Bedingungs **Eigenschafts Wert** der **if** -Aktivität ein.

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. Ziehen Sie eine weitere **if** -Aktivität aus dem Abschnitt Ablauf **Steuerung** der **Toolbox** , und legen Sie Sie im Abschnitt **Then** der ersten **if** -Aktivität ab.

11. Geben Sie den folgenden Ausdruck in das **Feldeigenschaften Wert der neu** hinzugefügten **if** -Aktivität ein.

    ```text
    Guess < Target
    ```

12. Ziehen Sie **zwei schreiben** -Aktivitäten aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie diese so ab, dass Sie sich im **Then** -Abschnitt der neu hinzugefügten **if** -Aktivität befinden und eine im Abschnitt **else** .

13. Klicken Sie im Abschnitt **Then** auf die Aktivität **Write** -Aktivität, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert ein.

    ```text
    "Your guess is too low."
    ```

14. Klicken Sie im Abschnitt **else** auf die Aktivität **Write** -Aktivität, um Sie auszuwählen, und geben Sie den folgenden Ausdruck in das Feld **Text** -Eigenschafts Wert ein.

    ```text
    "Your guess is too high."
    ```

     Im folgenden Beispiel wird der abgeschlossene Workflow veranschaulicht:

     ![Screenshot, der den abgeschlossenen sequenziellen Workflow anzeigt.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a>So erstellen Sie den Workflow

1. Drücken Sie STRG+UMSCH+B, um die Lösung zu erstellen.

     Anweisungen zum Ausführen des Workflows finden Sie im nächsten Thema Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md). Wenn Sie den Schritt Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md) mit einem anderen Workflow Workflow abgeschlossen haben und ihn mit dem sequenziellen Workflow aus diesem Schritt ausführen möchten, fahren Sie mit dem Abschnitt so [Erstellen und führen Sie den Anwendungs](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) Abschnitt "Gewusst [wie: Ausführen eines Workflows](how-to-run-a-workflow.md)" fort.

## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Windows Workflow Foundation-Programmierung](programming.md)
- [Entwerfen von Workflows](designing-workflows.md)
- [Tutorial zu den ersten Schritten](getting-started-tutorial.md)
- [Vorgehensweise: Erstellen einer Aktivität](how-to-create-an-activity.md)
- [Vorgehensweise: Ausführen eines Workflows](how-to-run-a-workflow.md)
